
# Principios de Tidydata

Gran parte del manejo de datos consiste en limpiar, ordenar,
redistribuir, reemplazar datos. La gran mayoría de esas tareas son
complejas y repetitivas.

La documentación dice
[aqui](https://cran.r-project.org/web/packages/tidyr/vignettes/tidy-data.html)
que:

> Los principios de tidydata (datos ordenados, en castellano)
> proporcionan una forma estándar de organizar los valores de los datos
> dentro de un conjunto de datos. Un estándar facilita la limpieza
> inicial de los datos, ya que no es necesario empezar de cero y
> reinventar la rueda cada vez. El estándar tidydata se ha diseñado para
> facilitar la exploración y el análisis de los datos, y para
> simplificar el desarrollo de herramientas de análisis de datos que
> funcionen bien juntas. Las herramientas actuales suelen requerir
> traducción. Hay que dedicar tiempo a procesar los resultados de una
> herramienta para poder introducirlos en otra. Los conjuntos de datos
> ordenados y las herramientas ordenadas trabajan codo a codo para
> facilitar el análisis, lo que permite centrarse en la parte
> interesante del problema, no en lo "aburrido" de la logística de los
> datos.

## Definiciones

En el manejo estadístico de los datos estructuramos, usualmente, con
tablas (dataframes) con filas y columnas. Las columnas siempre tienen
títulos, aunque las filas solo a veces.

![Elementos de una
tabla](https://d33wubrfki0l68.cloudfront.net/6f1ddb544fc5c69a2478e444ab8112fb0eea23f8/91adc/images/tidy-1.png)

Usemos el set de datos de ejemplo llamado `iris`, pero le vamos a
agregar un año de colecta ficticio. Para eso, vamos a crear un vector
con 3 fechas asignadas de forma aleatoria a cada fila. Veamos las
primeras 7 filas con la función `head()`.


``` r

data(iris)
año <- sample(rep(c("2003","2013","2023"), nrow(iris) / 3))

iris$Año <- año

kableExtra::kable(head(iris,7))
```



| Sepal.Length| Sepal.Width| Petal.Length| Petal.Width|Species |Año  |
|------------:|-----------:|------------:|-----------:|:-------|:----|
|          5.1|         3.5|          1.4|         0.2|setosa  |2013 |
|          4.9|         3.0|          1.4|         0.2|setosa  |2013 |
|          4.7|         3.2|          1.3|         0.2|setosa  |2023 |
|          4.6|         3.1|          1.5|         0.2|setosa  |2013 |
|          5.0|         3.6|          1.4|         0.2|setosa  |2023 |
|          5.4|         3.9|          1.7|         0.4|setosa  |2013 |
|          4.6|         3.4|          1.4|         0.3|setosa  |2023 |



## Lógica y funciones

La lógica básica para el manejo de datos usando `dplyr` es que el
resultado de una operación puede ser "conectada" a otra, lo que facilita
la letura del código cuando lo revisitamos. Para eso existe una operador
que hace esta conexión.

### Funciones esenciales

-   *pipe*: *\|\>*
-   *group_by* (agrupa datos)
-   *summarize* (resume datos agrupados)
-   *filter* (Encuentra filas con ciertas condiciones)
-   *select* junto a *starts_with*, *ends_with* o *contains*
-   *mutate* (Genera variables nuevas)
-   *arrange* ordenar

### pipe

Esta "conexión", se hace con este operador `%>%` o bien `|>`. La
diferencia entre los dos es que el uso del segundo no debieras requerir
pre cargar la librería y es de uso mas reciente.

por ejemplo, podemos calcular el largo promedio de los petalos de las
especie en el set de datos `iris`.


``` r
library(dplyr)
iris |>
  group_by(Species) |>
  summarize(Promedio=mean(Petal.Length)) 
#> # A tibble: 3 × 2
#>   Species    Promedio
#>   <fct>         <dbl>
#> 1 setosa         1.46
#> 2 versicolor     4.26
#> 3 virginica      5.55
```

### Agrupar

`dplyr` provee un set acotado de funciones, pero muy poderosas para
manejar y ordenarnos con los datos. El ejemplo anterior muestra como se
conecta una función con otra. Lo primero que hace es definir la tabla
sobre la que vamos a trabajar, `iris`. Esta tabla es luego agrupada por
la columna Species que es finalmente usada en la función `summarize`
para calcular la media sobre los groupos de filas para cada especie.

De forma similar, podriamos también buscar la varianza de todas las
columnas que son de tipo numérico, adjuntar una columna con el número de
filas sobre el que calculamos dicha varianza y luego imprimirla a la
pantalla de forma mas estilizada.


``` r
iris |>
  group_by(Species) |>
  summarise(across(where(is.numeric), var, na.rm = TRUE), N = n())|>
  kableExtra::kable() |>
  kableExtra::kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"), full_width = F)
```

<table class="table table-striped table-hover table-condensed table-responsive" style="width: auto !important; margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> Species </th>
   <th style="text-align:right;"> Sepal.Length </th>
   <th style="text-align:right;"> Sepal.Width </th>
   <th style="text-align:right;"> Petal.Length </th>
   <th style="text-align:right;"> Petal.Width </th>
   <th style="text-align:right;"> N </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> setosa </td>
   <td style="text-align:right;"> 0.1242490 </td>
   <td style="text-align:right;"> 0.1436898 </td>
   <td style="text-align:right;"> 0.0301592 </td>
   <td style="text-align:right;"> 0.0111061 </td>
   <td style="text-align:right;"> 50 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:right;"> 0.2664327 </td>
   <td style="text-align:right;"> 0.0984694 </td>
   <td style="text-align:right;"> 0.2208163 </td>
   <td style="text-align:right;"> 0.0391061 </td>
   <td style="text-align:right;"> 50 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:right;"> 0.4043429 </td>
   <td style="text-align:right;"> 0.1040041 </td>
   <td style="text-align:right;"> 0.3045878 </td>
   <td style="text-align:right;"> 0.0754327 </td>
   <td style="text-align:right;"> 50 </td>
  </tr>
</tbody>
</table>



### Filtrar

Filter nos permite encontrar, y operar, solo sobre filas que cumplen una
condición determinada. Por ejemplo solo un tipo de especie


``` r
iris |>
  filter(Species == 'virginica') |>
  kableExtra::kable() |> 
  kableExtra::kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"), full_width = F) |>
  kableExtra::scroll_box(height = "250px")
```

<div style="border: 1px solid #ddd; padding: 0px; overflow-y: scroll; height:250px; "><table class="table table-striped table-hover table-condensed table-responsive" style="width: auto !important; margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Sepal.Length </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Sepal.Width </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Petal.Length </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Petal.Width </th>
   <th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;"> Species </th>
   <th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;"> Año </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.1 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.9 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.9 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.6 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 6.6 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 4.5 </td>
   <td style="text-align:right;"> 1.7 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.3 </td>
   <td style="text-align:right;"> 2.9 </td>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.2 </td>
   <td style="text-align:right;"> 3.6 </td>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 5.3 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.8 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.5 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 2.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 5.3 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.5 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 3.8 </td>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 2.6 </td>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.2 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.2 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 4.8 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.2 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 1.6 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.4 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.9 </td>
   <td style="text-align:right;"> 3.8 </td>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.6 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 3.4 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.5 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 4.8 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.4 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.8 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 5.9 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.2 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.2 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.2 </td>
   <td style="text-align:right;"> 3.4 </td>
   <td style="text-align:right;"> 5.4 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.9 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
</tbody>
</table></div>



Debemos tener en cuenta que si usamos filter tendremos que siempre tener
un operador en el argumento de la función. En este caso era el operado
`==` que es un *igual*, pero de forma literal, no como una asignación.
Otro ejemplo podría ser seleccionar aquellas filas que tengan un largo
de petalos mayor a 4.5, por ejemplo


``` r
iris |>
  filter(Petal.Length > 4.5) |>
  kableExtra::kable() |>
  kableExtra::kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"), full_width = F) |>
  kableExtra::scroll_box(height = "250px")
```

<div style="border: 1px solid #ddd; padding: 0px; overflow-y: scroll; height:250px; "><table class="table table-striped table-hover table-condensed table-responsive" style="width: auto !important; margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Sepal.Length </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Sepal.Width </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Petal.Length </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Petal.Width </th>
   <th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;"> Species </th>
   <th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;"> Año </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:right;"> 7.0 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 4.7 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 4.6 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 4.7 </td>
   <td style="text-align:right;"> 1.6 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.6 </td>
   <td style="text-align:right;"> 2.9 </td>
   <td style="text-align:right;"> 4.6 </td>
   <td style="text-align:right;"> 1.3 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.9 </td>
   <td style="text-align:right;"> 4.7 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.9 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 4.8 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 4.7 </td>
   <td style="text-align:right;"> 1.2 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.8 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 4.8 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 1.7 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.6 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 4.7 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 4.6 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.1 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.9 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.9 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.6 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 6.6 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.3 </td>
   <td style="text-align:right;"> 2.9 </td>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.2 </td>
   <td style="text-align:right;"> 3.6 </td>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 5.3 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.8 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.5 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 2.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 5.3 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.5 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 3.8 </td>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 2.6 </td>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.2 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.2 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 4.8 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.2 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 1.6 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.4 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.9 </td>
   <td style="text-align:right;"> 3.8 </td>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.6 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 3.4 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.5 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 4.8 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.4 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.8 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 5.9 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.2 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.2 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.2 </td>
   <td style="text-align:right;"> 3.4 </td>
   <td style="text-align:right;"> 5.4 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.9 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
</tbody>
</table></div>



### Crear nuevas variables

Con `mutate()` podemos crear una nueva columna de forma explícita. Por
ejemplo, si quisieramos saber cuales son las especies y años en que se
colectaron especies con una razon largo/ancho determinado.


``` r
iris |>
  mutate(Petal.Ratio = Petal.Length/Petal.Width)|>
  select(Petal.Ratio,Species,Año) |>
  group_by(Species,Año) |>
  summarize(Petal.Ratio.Mean = mean(Petal.Ratio)) |>
  filter(Petal.Ratio.Mean > median(Petal.Ratio.Mean))
#> `summarise()` has grouped output by 'Species'. You can
#> override using the `.groups` argument.
#> # A tibble: 3 × 3
#> # Groups:   Species [3]
#>   Species    Año   Petal.Ratio.Mean
#>   <fct>      <chr>            <dbl>
#> 1 setosa     2023              7.38
#> 2 versicolor 2013              3.33
#> 3 virginica  2023              2.92
```

### Responder:

-   ¿Escriba la pregunta que responde el análisis?
-   En función del último análisis, ¿existe diferencia interespecífica
    en la relación entre largo y ancho largo para estes grupo de
    especies? -¿Cómo formularías la pregunta anterior de forma mas
    precisa en función del análisis anterior?

## Cambiar formato de tabla

Muchas veces es necesario reorientar la tabla de datos.

Primero, podríamos interesarnos en definir clases para las muestras.
Definimos tamaños como clases usando terciles.


``` r
etiquetas <- c("alto","medio","bajo")
miIris <- iris |>
  mutate(Tamaño = factor(ntile(Petal.Length/Petal.Width,3),ordered = TRUE, labels = etiquetas))
```

Luego vamos a re-orientar la tabla de manera a poder indagar si existe
diferencia entre especies respecto de la característica `Tamaño`


``` r
miIris |>
  select(Species, Año,Tamaño,Sepal.Width) |>
  tidyr::pivot_wider(names_from = Tamaño, values_from = Sepal.Width,values_fn=mean) |>
  kableExtra::kable()
```



|Species    |Año  |     bajo|    medio|     alto|
|:----------|:----|--------:|--------:|--------:|
|setosa     |2013 | 3.287500| 4.150000|       NA|
|setosa     |2023 | 3.488235|       NA|       NA|
|setosa     |2003 | 3.415385| 3.300000| 3.500000|
|versicolor |2003 |       NA| 2.694737| 2.775000|
|versicolor |2023 |       NA| 2.790909| 3.025000|
|versicolor |2013 | 2.566667| 2.650000| 3.020000|
|virginica  |2013 |       NA| 2.857143| 3.107692|
|virginica  |2023 | 2.600000| 3.175000| 2.992308|
|virginica  |2003 |       NA| 2.650000| 2.880000|



### ¿Podemos explicar que sucedió aquí?

-   ¿En qué caso aparecen los `NA`?
-   ¿Qué tipo de gráfico evidenciaría la relación entre el ratio
    largo:ancho del pétalo y el ancho del sépalo?
-   grafica

## Ejercicio

Usando la base de datos del repositorio del ministerio de ciencias, genera un dataframe que responda lo siguiente:


``` r
url <- "https://raw.githubusercontent.com/MinCiencia/Datos-COVID19/master/output/producto19/CasosActivosPorComuna_std.csv"
Casos_Activos <- read_csv(url)
```


* ¿Qué proporción de las comunas ha tenido en algún momento más de 50 casos por cada 100.000 habitantes?
* Genera un dataframe, donde aparezca para cada comuna que haya tenido sobre 50 casos por cada 100.000 habitantes, cuantos días ha tenido sobre ese valor.
* Genera una tabla con las comunas que han tenido sobre 50 casos por cada 100.000 habitantes y de esas comunas crea una variable que sea la prevalencia máxima de dicha comuna.

## **Bonus** (Esto requiere investigar no basta con lo que aprendimos)

* Ve cuales son las 10 comunas que han tenido la mayor mediana de prevalencia, para cada una de estas 10 comunas, genera una tabla con la mediana, prevalencia máxima y fecha en que se alcanzó la prevalencia máxima

* La _prevalencia_ es la proporción de la población afectada en un período de tiempo determinado.



## Recursos

-   [data wrangling cheatsheet](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)
-   [tablas "bonitinhas" con Kable](https://haozhu233.github.io/kableExtra/awesome_table_in_html.html)
