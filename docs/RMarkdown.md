# RMarkdown

## ¿Qué es R Markdown?

## Librerías


``` r
install.packages("rmarkdown")
library(rmarkdown)
```

## Crear un R Markdown

## Encabezado YAML

El archivo `.Rmd` comienza con una sección que definie los parámetros con que se va a compilar este `.Rmd`. En general, usa un lenguaje de serialización que sirve para definir configuraciones.

``` yaml
---
title: "Informe de Biodiversity"
author: Juan Pérez
date: 21/Oct/2024
output: html_document
---
```

La línea importante es la del `output`, pues indica el tipo de archivo que se producirá al compilar este `.Rmd`. Intentaremos usar HTML como output en cuánto se pueda. Es lo mas sencillo y liviano, puede verse en el navegador. Otra posibildad es usar PDF, pero eso requiere tener instaladas librerías que compilen un archivo LaTeX.

## Sintáxis de Markdown

Markdown es un lenguaje parecido a html que permite dar un ormato simplificado a documentos de texto. Puedes encontrar distintos recursos con ayudas para recordar como usarlo.

-   [Markdown Cheatsheet](https://www.markdownguide.org/cheat-sheet/)

### Lo esencial

Lo mas simple es los siguiente:

-   **Títulos y subtítulos**: se escriben con `#`, pueden haber hasta 4 niveles de subtítulos
-   **Enlaces**: `[texto a linkear](http://wwww.ENLACE.cl)`
-   **Negritas**: flankear texto con `**`, asi `**negrita**`
-   **Itálica**: flankear texto con solo un asterisco: `*`

### Listas

Existen 2 tipos de listas, las numeradas y las que no.

-   **Listas numeradas**: Iniciar frase con un número seguido por un punto.

    > 1.  Primer elemento
    > 2.  Segundo...

-   **Listas simples**: iniciar frase con un guión seguido por un espacio.

    > -   elemento de list
    > -   otro elemento

### Mostrar ejemplos de de código (sin ejecutarlos)

Los pedazos de código en la sección de text (no del chunk!) irán flankeadas por *cremilla inversa* `` ` ``. Habrán veces en que necesitaremos no solo mostrar código en la linea (inline), sino que vamos a querer ejecutar código. En esos casos, podemos incluir el leguaje que RStudio debe usar para interpretar dicho código. Por ejemplo `` 2024-10-03 `` imprime la fecha actual en R: 2024-10-03

Usaremos un TAB, o 4 espacios para insertar un bloque de código

Además de las imágenes quepodemos generar durante el uso mismo de R, podemos incrustar imágenes.

-   **Imágenes**: `![texto que describe imagen](archivo.png)`, podemos usar los mismos formatos de imagenes que usa HTML. Estos son al menos GIF, JPG y PNG. Nota: ajustar el tamaño de imágenes es considerado mas avanzado y puede hacerse embebiendo código HTML en markdown.

Usaríamos:

``` html
<figure>       
  <img src="archivo.jpg"  alt="texto que describe la imágen (visible al pasar el mouse sobre ella)">                      
  <figcaption>CAPTION.</figcaption>
</figure>
```

### Figuras

Podemos incluir figuras en un `.Rmd`. Esto es posible de muchas maneras, demostraremos 2:

1. Usando la sintaxis de markdown ("nativa"). 
  - `![caption](direcion/desde/el/espacio/de/trabajo)`
    Debemos tener super claro el espacio de trabajo desde donde se ejecuta este `.Rmd`. Lo puedes verificar desde la consola usando `getwd()`.
  - Usando la librería *knitr*. Existe una fnucion `knitr::include_graphics()` que permite un control mas fino de como se muestra la imagen.
  
``` txt
  Incluir imágen externa usando kintr:
  
  ```{r chunk de imagen, echo=FALSE, out.width="50%", fig.cap="A nice image."}
    knitr::include_graphics("foo/bar.png")
  ```
  Ojo, con la ruta de acceso a la imágen!

```


## MD -\> HTML

Cuando escribimos en markdown, la gran mayoría de las veces, el interpretador hará una transformación del documento a HTML. Esto ocurre de forma interna, no tienes nada que hacer. Un ejemplo de ello es pinchar en la opcion `Visual`, para verlo en HTML, o seguir usando la opción `Source` en la esquina superior izquierda de RStudio. 
![Botón Visual/Source en RStudio](Source-Visual%20button.png)

## Código R

En un `.Rmd`, vamos a confinar el código que queremos que R procese un un *chunk*.

Usaremos tres (3) *cremillas inversas*. Se pone entre corchetes `{}` el lenguaje que queremos que RStudio interprete. En general, este será `R`, pero podría ser otros que tu instalacion permita, como python, o bash.

Dentro de los corchetes podemos incluir distintos parámetros con los que se ejecutara (o no) el código. Pero es mas sencillo usar el botón del engranaje: 
![parámetros del chunk](./Chunk_gear_button.png)

Pinchando en él, puedes ver que se permite ajustar los parámetros básicos, como título del chunk, si es que quieres que se ejecute o si quieres que no muestre los Warnings, etc...

![parámtros de chunk 2](./Chunk_gear_button2.png){width=95%}

**OJO QUE FINALMENTE:** 

> Es dentro del estos chunks donde ocurre la magia, RStudio los interpreta enviándolos a `R` para que los ejecute. Todo el resto es intepretado como un archivo Markdown que, al ser compilado es enviado a un HTML, PDF o DOCX para poder ser distribuido. 


## Recursos

-   [Torpedo / CheatSheet](https://rstudio.github.io/cheatsheets/html/rmarkdown.html)
-   [R Markdown for scientists](https://rmd4sci.njtierney.com/)
-   [data wrangling cheatsheet](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)
-   [tablas "bonitinhas" con Kable](https://haozhu233.github.io/kableExtra/awesome_table_in_html.html)
