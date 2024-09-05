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

- **Listas simples**: iniciar frase con un guión seguido por un espacio.

  > - elemento de list
  > - otro elemento


### Código

Los pedazos de código en la sección de text (no del chunk!) irán flankeadas por *cremilla inversa* `` ` ``. Habrán veces en que necesitaremos no solo mostrar código en la linea (inline), sino que vamos a querer ejecutar código. En esos casos, podemos incluir el leguaje que RStudio debe usar para interpretar dicho código. Por ejemplo `` 2024-09-05 `` imprime la fecha actual en R: 2024-09-05`

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

## MD -> HTML

Cuando escribimos en markdown, la gran mayoría de las veces, el interpretador hará una transformación del documento a HTML. Esto ocurre de forma interna, no tienes nada que hacer. Un ejemplo de ello es pinchar en la opcion `Visual`, para verlo en HTML, o seguir usando la opción `Source` en la esquina superior izquierda de RStudio. ![Botón Visual/Source en RStudio](Source-Visual%20button.png)

## Recursos

-   [data wrangling cheatsheet](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)
-   [tablas "bonitinhas" con Kable](https://haozhu233.github.io/kableExtra/awesome_table_in_html.html)
