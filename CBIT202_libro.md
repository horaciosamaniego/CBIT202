---
title: "Programación y Análisis de Datos Geoespaciales"
author: "Horacio Samaniego"
date: "2024-08-22"
site: bookdown::bookdown_site
documentclass: book
bibliography: [book.bib, packages.bib]
# url: your book url like https://bookdown.org/yihui/bookdown
# cover-image: path to the social sharing image like images/cover.jpg
description: |
  Gitbook para el curso Introducción al Análisis de Geoespaciales (CBIT202),
  Universidad Austral de Chile
biblio-style: apalike
csl: chicago-fullnote-bibliography.csl
---




# Datos del curso

-   **Universidad Austral de Chile:** [Laboratorio de Ecoinformatica](http://www.ecoinformatica.cl)
-   **Nombre asignatura:** Introducción al Análisis de Datos Geoespaciales
-   **Código asignatuta:** CBIT202-18   
-   **Docente responsable:** Horacio Samaniego
-   **Correo electrónico:** [horaciosamaniego\@uach.cl](mailto:horaciosamaniego@uach.cl){.email}
-   **Creadores:** [Derek Corcoran B.](https://derek-corcoran-barrios.github.io/) & Giorgia Graells C.
-   **Modalidad de clases:**
    -   Prácticas
    -   Presenciales
    -   Consultas por [Discord](https://discord.gg/CQPepwS4) (chat o video) -- link válido 7 días! - hasta 29/8/2024
-   **Horario de clases:** Jueves 9:50 - 13:00 hrs
-   **Lugar:** Sala de computación, Facultad de Ciencias Forestales y Recursos Naturales, Campus Isla Teja, Valdivia
-   **Inicio clases:** 8 agosto 2024
-   **Término clases:** 28 noviembre 2024 (puede modificarse según calendario académico)
-   **Web del curso** [aqui](https://cbit202-18-analisis-de-datos-geo.github.io/CBIT202_libro/)

## DESCRIPCIÓN DEL CURSO

Este curso tiene como objetivo central adquirir herramientas para el manejo de datos con un énfasis en datos espaciales para el menejo de los recursos naturales y la aproximación y resolución de problemas ambientaleslos. Se busca la creación de competencias en los principios de investigación reproducible, representación y análisis de información espacial y la creación de mapas estáticos e interactivos. Esto permitirá la adquisiciónde herramientas para profundizar el conocimientos acerca del diseño y desarrollo de análisis de datos ambientales complejos y espacialmente explícitos.

### OBJETIVOS

1.  Conocer y entender el concepto de Investigación Reproducible como una forma y filosofía de trabajo que permite que las investigaciones sean más ordenadas y replicables, desde la toma de datos hasta la escritura de resultados utilizando R

2.  Realizar análisis críticos de la naturaleza de los datos al realizar análisis exploratorios y reforzar conociminetos en estadística

3.  Realizar análisis de datos espaciales, poder hacer mapas y aplicar a preguntas de conservación y manejo de recursos naturales.

4.  Aprender a utilizar de forma proficiente el lenguaje de programación R y la plataforma GitHub en un ambiente de trabajo colaborativo.

## Evaluación

### tareas
-   Se entregarán ejercicios que deben resolverse semanales. La entrega se hará usando la plataforma GitHub. Cada estudiante será responsable de entregar su tarea y de corregir a tres compañeros al azar. Las correcciones ocurrirán en modalidad "doble ciego", es decir, tanto el corrector como el autor de la tarea serán mantenido como anónimo. Esta modalidad de corrección por pares será moderada por el profesor y seguirá una pauta entregada para cada tarea. Los estudiantes recibirán un punto por cada tarea revisada, lo que se sumará para completar el puntaje de su propia tarea. 

### proyectos
-   Se desarrollán proyectos de análisis y de programación que consistirán en la resolución de un problema o set de preguntas.

### calificaciones
```{=html}
<style type="text/css">
  .calificaciones {width: 35%; left: 50%}
</style>
```
::: calificaciones
| *Evaluación*               | *Ponderación* |
|----------------------------|---------------|
| Ejercicios \& Tareas  $$\frac{1}{n}\sum_i^n nota\, tarea_i$$       | 50%           |
| Proyecto código 1           | 15%           |
| Proyecto código 2           | 10%           |
| Proyecto código 3           | 15%           |
| Participación / Asistencia | 10%            |
:::

## Calendario

### Módulo 1: Introducción a R y RStudio

1. 8 Agosto — Presentación del curso
    - R como lenguaje de programación para análisis de datos
    - Entorno de RStudio: navegación básica y gestión del espacio de trabajo
    - Tipos y estructuras de datos: vectores, matrices, data frames y tibbles
    - Operaciones aritméticas y lógicas básicas
    - Introducción a paquetes y gestión de paquetes
  
(.) 15 Agosto - FERIADO (Asunción de la Virgen) 

### Módulo 2: R Markdown \& Github

2.  22 Agosto — Introducción a Markdown y R Markdown
    - Creación de informes reproducibles
    - Sintaxis Markdown
    - Incorporación de fragmentos de código R
    - Formatos de salida (HTML, PDF, Word)
    - Investigación reproducible

### Módulo 3: Manipulación de Datos con Tidyverse

3. 29 Agosto — datos desde varios formatos (CSV, Excel, bases de datos, etc.)
    - Introducción al tidyverse
    - Importación y Exportación de Datos
    - Manejo de valores faltantes
    - Limpieza y preprocesamiento de datos

4. 5 Septiembre  — ****
    - Manipulación de datos con dplyr: select, filter, arrange, mutate, group_by, summarize
    - Tabulaciones
    - Ordenación de datos con tidyr: gather, spread, separate, unite
    - Transformación de datos con purrr: programación funcional para análisis de datos

### Modulo 5: Visualización de Datos

5. 12 Septiembre — Introducción a ggplot2
    - Creación de diversos tipos de gráficos (diagramas de dispersión, histogramas, diagramas de caja, gráficos de barras, gráficos de líneas)
    - Personalización de gráficos con estética, escalas y temas
    - Facetas y capas de gráficos
    

(.) 19 Septiembre - FERIADO (Fiestas patrias)

6. 26 Septiembre — Visualización 
    - Visualización interactiva
    - Mapview
    - 

### Módulo 6: Introducción al Análisis Geoespacial

7. 3 Octubre — Introducción a los datos espaciales

   - Lectura y escritura de datos espaciales (shapefiles, GeoJSON, etc.)
   - Definir y transformar proyecciones
   - Operaciones espaciales básicas (unión, intersección, búfer)
   - Análisis de datos espaciales

8. 10 Octubre — datos en grilla
    - Fuentes y formatos
    - filtros y procesamiento
    - algebra de mapa
    - mapas categóricos, clasificación y reclasificación

9.  17 Octubre — Mapas
    - Cartografía
    - Mapas de distintas fuentes
    - Mapas interactivos, mapview y leaflet
  
10. 24 Octubre — Operaciones de grillas
    - Operaciones espaciales conjuntas: puntos, vectores y grillas
    - Tabular informacion raster
    - interpolaciones

(.) 31 Octubre — FERIADO (Día de las Iglesias Evangélicas)

11. 7 Noviembre —

12. 14 Noviembre —

13. 21 Noviembre —

14. 28 Noviembre —



## Recursos adicionales

Si bien intentamos buscar ejemplos originales y sets de datos locales, gran parte del material con que trabajaremos ha sido ya 
trabajado  elaborado por otros. Es por eso que se sugiere revisar algunos sitios claves como los siguientes:

- [R for Data Sciences](https://r4ds.hadley.nz)
- [Stackoverflow](https://stackoverflow.com/)
- [GIS Stack Exchange](https://gis.stackexchange.com/)
- [Spatial Data Science](https://rspatial.org/index.html)
- [R Graph Gallery](https://r-graph-gallery.com/)
- [ggplot2 tips](https://www.cedricscherer.com/2019/08/05/a-ggplot2-tutorial-for-beautiful-plotting-in-r/)




<!--chapter:end:index.Rmd-->



```{=html}
<!-- # El tidyverso {#tidy}

En esta clase empezaremos a trabajar en r, puedes seguir la presentación en el siguiente [link](https://derek-corcoran-barrios.github.io/CursoProgrPres/Clase1/Clase1TidyData.html), y a continuación tienes el link de la clase online en youtube:

<iframe width="560" height="315" src="https://www.youtube.com/embed/pr6dMwtto0w" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
-->
```
# Introducción

R es un entorno y lenguaje de programación con un enfoque al análisis
estadístico. Permite hacer todos los análisis numéricos que requieras en
tu vida profesional. Es una implementación de libre distribución de otro
programa estadístico de uso comercial, S. Al ser software libre, es la
comunidad de usuarios la que guía su desarrollo, transformándolo en uno
de los programas más versátiles para trabajos cuantitativos existentes
hoy en día. La página principal desde la que se puede acceder a los
archivos y documentación necesarias para su utilización es:

[www.r-project.org](http://www.r-project.org)

Si bien R es un software que puede usarse desde la línea de comando,
para trabajar utilizaremos [http://www.rstudio.org](%60R%20Studio%60).

Este es un Entorno de Desarrollo Integrado (IDE, por su sigla en inglés)
que, al igual que R, es software libre y permite integrar herramientas
necesarias para el desarrollo y así facilitarlo. La página oficial para
descargarlo es:

[www.rstudio.com](http://www.rstudio.com)

## Objetos

En términos genéricos, todos los elementos que R maneja son objetos. Un
objeto tiene ciertas propiedades y en ocasiones es capaz de llevar a
cabo ciertas tareas si se le dan los argumentos necesarios. Por ejemplo,
un teléfono es capaz de realizar llamadas siempre que le demos el número
a marcar.

## Variables

Al momento de trabajar, es probable que necesitemos guardar valores o
cálculos, de manera que no necesitemos escribirlos cada vez que los
usemos, para esto utilizamos variables.

Para realizar una asignación de variable:


``` r
a = 200
```

Luego, podemos utilizar el valor contenido en la variable, utilizando su
nombre:


``` r
print(a)
#> [1] 200
```

### Tipos de variables

Existen diversos tipos o clases de variables, dependiendo de las
características del objeto que les es asignado. Para conocer a qué tipo
corresponde un objeto usamos class:


``` r
x=7
x
#> [1] 7
class (x)
#> [1] "numeric"
```


``` r
x=5/3
x
#> [1] 1.666667
class (x)
#> [1] "numeric"
```


``` r
x="Trece"
x
#> [1] "Trece"
class (x)
#> [1] "character"
```

## Funciones

Muchas cosas en R pueden hacerse a través del uso de funciones, estas
permiten realizar operaciones típicas sin necesidad de escribir grandes
cantidades de código. Por ejemplo:


``` r
sqrt(10)
#> [1] 3.162278
round(1.9)
#> [1] 2
seq(0,10)
#>  [1]  0  1  2  3  4  5  6  7  8  9 10
seq(0,10,2)
#> [1]  0  2  4  6  8 10
rep(5,10)
#>  [1] 5 5 5 5 5 5 5 5 5 5
paste(seq(5,10), "elefantes")
#> [1] "5 elefantes"  "6 elefantes"  "7 elefantes" 
#> [4] "8 elefantes"  "9 elefantes"  "10 elefantes"
```

Los datos o variables que van dentro de las funciones, se denominan
*argumentos* y cada función requiere que se le entreguen los argumentos
apropiados para ejecutar la acción prevista.

Por ejemplo, la función mean() no puede calcular el promedio si como
argumentos se le pasan letras.


``` r
mean(c("a","b","c"))
#> Warning in mean.default(c("a", "b", "c")): argument is not
#> numeric or logical: returning NA
#> [1] NA
```

Esto es importante, porque al introducir datos podemos estar utilizando
números como palabras:

1, 2, 3 ≠ "1", "2", "3"

Si nos encontramos con este problema, debemos transformar los datos al
tipo o clase adecuada, con las funciones:

`as.numeric()` y `as. character()`x\`

## Vectores

Conjunto ordenado de valores del mismo tipo, agrupados en un único
objeto. Para crear una variable vector utilizamos:


``` r
v = c(1,1,2,3)
vector = c("mi", "primer", "vector")
vector
#> [1] "mi"     "primer" "vector"
```

Cada objeto dentro de un vector posee un índice, el cual indica la
posición que ocupa dentro del vector, para acceder a una posición
específica usamos:


``` r
vector[1]
#> [1] "mi"
vector[2]
#> [1] "primer"
vector[3] 
#> [1] "vector"
```

y si queremos reemplazar alguno de esos objetos:


``` r
vector[2]="segundo"
vector
#> [1] "mi"      "segundo" "vector"
```

Un vector permite almacenar varios valores en una única variable y
permite ejecutar operaciones o funciones a un conjunto de datos:


``` r
vector = c(1,2,3,4,5)
vector*2
#> [1]  2  4  6  8 10
vector^2
#> [1]  1  4  9 16 25
```

o incluso realizar operaciones entre vectores:


``` r
v1=c(1:3)
v2=c(6,8,10)
```


``` r
v1
#> [1] 1 2 3
v2
#> [1]  6  8 10
```


``` r
v1 + v2
#> [1]  7 10 13
```


``` r
v1*v2
#> [1]  6 16 30
```


``` r
v3=c("a","b","c")
v1 * v3
#> Error in v1 * v3: non-numeric argument to binary operator
```


## Instalar librerías

Muchas veces las funciones incorporadas en R son insuficientes para
nuestros fines, por lo que es necesario instalar paquetes o "packages"
de herramientas hechas por la comunidad. En este caso, usaremos el
paquete "openxlsx", que nos permite leer archivos Excel. Para
instalarlo:


``` r
install.packages("openxlsx")
```

Debe hacerse una única vez, los paquetes quedan instalados en nuestra
versión de R. Y para usarlo dentro de nuestro proyecto:


``` r
library(openxlsx)
```

Debe incluirse en cada proyecto donde queramos usarlo y ejecutarse cada
vez que abrimos R.

## R Notebook

Un Notebook en R es un documento con bloques o "chunks" que pueden ser
ejecutados directa e interactivamente, para así visualizar los
resultados directamente bajo el código.

Para instalar esta librería:


``` r
install.packages("rmarkdown")
```

Una vez instalada, puedes crear un nuevo notebook en RStudio llendo a
*File -\> new file -\> R notebook*.

Agrega un nuevo chunk haciendo click en el botón *Insert Chunk* en la
barra de herramientas o presionando *Ctrl+Alt+I*

Un chunk puede ser ejecutado usando:

1.  Haciendo click en el triángulo verde o "Run Current Chunk" en la
    esquina superior derecha de cada chunk.

2.  Clickeando al interior de un chunk y presionando *Ctrl + Enter*.

De ambas formas se ejecutará todo el código contenido dentro de el
chunk.

Cuando guardas ul notebook, un archivo HTML que contiene el código y los
resultados se guardará junto a él (Click en el botón de *Preview* o
presiona *Ctrl+Shift+K* para previsualizar el archivo HMTL)

## Leer datos

Delimitados por coma: read_csv("file.csv")

Con cualquier delimitador: read_delim("file.txt", delim = "\|")


## Ejercicios


1. Cree una nueva variable que contenga un vector con 10 números aleatorios
2. multiplíquela por seis.
3. cree una segunda variable que contenga una secuencia de 5 caracteres
4. combine las dos variable en una sola variable
5. ¿cuál es el largo de esta última variable creada?
6. ¿de qué tipo es esta variable?
7. ¿qué sucede si divie esta última variable por 3?
8. cree un vector con los elementos 1 2 3 4 5 6 y llámelo `x`
9. cree un nuevo vector con los elementos 10 20 30 40 50 y llámelo `y`
10. ¿qué ocurre si intenta sumar `x` e `y`? explique
11. agregue el valor 60 al vector `y` (ayuda: puedes usar la función `c()`)
12. sume `x` e `y`
13. multiplique `x` e `y`
14. cree un `data.frame`  con el mímimo código posible usando los datos de la siguiente imagen y llámelo `z`:

![](df.jpg)<!-- -->

15. cree un dataframe de datos ficticios que represente una muestra de 100 individuos de aves y su tamaño corporal. Use 4 tipos de aves: un paseriforme, un columbiforme, un rapaz y trochiliformes en aproximadamente las mismas proporciones. (Averigue el real tamaño promedio de cada grupo)
16. grafique los pesos corporales de cada grupo (ayuda: puede usar graficos de distribuciones, caja y bigote o bien de violín)

<!-- ![¿Cuál es el código mas corto para crear este df?](df.JPG) -->

<!--chapter:end:01-intro.Rmd-->


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
|          5.1|         3.5|          1.4|         0.2|setosa  |2023 |
|          4.9|         3.0|          1.4|         0.2|setosa  |2003 |
|          4.7|         3.2|          1.3|         0.2|setosa  |2013 |
|          4.6|         3.1|          1.5|         0.2|setosa  |2003 |
|          5.0|         3.6|          1.4|         0.2|setosa  |2003 |
|          5.4|         3.9|          1.7|         0.4|setosa  |2013 |
|          4.6|         3.4|          1.4|         0.3|setosa  |2013 |



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
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.9 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.6 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 6.6 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 4.5 </td>
   <td style="text-align:right;"> 1.7 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
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
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.8 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.5 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
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
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.5 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 3.8 </td>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
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
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.2 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 1.6 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.4 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.9 </td>
   <td style="text-align:right;"> 3.8 </td>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.6 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
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
   <td style="text-align:left;"> 2003 </td>
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
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.2 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
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
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.2 </td>
   <td style="text-align:right;"> 3.4 </td>
   <td style="text-align:right;"> 5.4 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.9 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
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
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 4.6 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2013 </td>
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
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.9 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 4.8 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 4.7 </td>
   <td style="text-align:right;"> 1.2 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.8 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 4.8 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 1.7 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.6 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 4.7 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 4.6 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:left;"> versicolor </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.9 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.6 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 6.6 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.8 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.5 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
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
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.5 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.5 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 3.8 </td>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
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
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.7 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.2 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.8 </td>
   <td style="text-align:right;"> 1.6 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.4 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.9 </td>
   <td style="text-align:right;"> 3.8 </td>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.4 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.2 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.3 </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.6 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7.7 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 6.1 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
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
   <td style="text-align:left;"> 2003 </td>
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
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.6 </td>
   <td style="text-align:right;"> 2.4 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.9 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
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
   <td style="text-align:left;"> 2003 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.3 </td>
   <td style="text-align:right;"> 5.7 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.2 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2013 </td>
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
   <td style="text-align:left;"> 2013 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6.2 </td>
   <td style="text-align:right;"> 3.4 </td>
   <td style="text-align:right;"> 5.4 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2023 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.9 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:left;"> virginica </td>
   <td style="text-align:left;"> 2003 </td>
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
#> 1 setosa     2023              7.47
#> 2 versicolor 2023              3.26
#> 3 virginica  2003              2.92
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
|setosa     |2023 | 3.392857| 3.900000|       NA|
|setosa     |2003 | 3.365000| 3.300000| 3.500000|
|setosa     |2013 | 3.458333| 4.400000|       NA|
|versicolor |2023 | 2.800000| 2.778571| 3.033333|
|versicolor |2013 | 2.450000| 2.672727| 2.950000|
|versicolor |2003 |       NA| 2.688889| 2.875000|
|virginica  |2023 |       NA| 2.725000| 3.061539|
|virginica  |2013 | 2.600000| 3.050000| 3.006667|
|virginica  |2003 |       NA| 3.000000| 2.900000|



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

<!--chapter:end:02-dplyr.Rmd-->

