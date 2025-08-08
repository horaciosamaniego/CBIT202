---
title: "Programación y Análisis de Datos Geoespaciales"
author: "Horacio Samaniego"
date: "2025-08-08"
site: bookdown::bookdown_site
documentclass: book
# output:
#   bookdown::bs4_book: 
    # css: "style.css"
# bibliography: [book.bib, packages.bib]
url: https://github.com/horaciosamaniego/CBIT202
# cover-image: path to the social sharing image like images/cover.jpg
description: |
  Gitbook para el curso Introducción al Análisis de Geoespaciales (CBIT202),
  Universidad Austral de Chile
biblio-style: apalike
csl: chicago-fullnote-bibliography.csl

---

# Datos del curso (CBIT202-23)

-   **Universidad Austral de Chile:** [Laboratorio de Ecoinformatica](http://www.ecoinformatica.cl)
-   **Nombre asignatura:** Introducción al Análisis de Datos Geoespaciales
-   **Código asignatuta:** CBIT202-23   
-   **Docente responsable:** Horacio Samaniego
-   **Correo electrónico:** [horaciosamaniego\@uach.cl](mailto:horaciosamaniego@uach.cl){.email}
-   **Modalidad de clases:**
    -   Prácticas
    -   Presenciales
    -   Consultas por [Discord](https://discord.gg/adqSpqVH7Z) (chat o video) -
-   **Horario de clases:** Lunes 9:50 - 13:00 hrs
-   **Lugar:** Sala de computación, Facultad de Ciencias Forestales y Recursos Naturales, Campus Isla Teja, Valdivia
-   **Inicio clases:** 11 agosto 2025
-   **Pausa lectiva** _13 - 17 Octubre 2025_
-   **Término clases:** 28 noviembre 2025 (puede modificarse según calendario académico)

## DESCRIPCIÓN DEL CURSO

Este curso tiene como objetivo central adquirir herramientas para el manejo de datos con un énfasis en datos espaciales para el menejo de los recursos naturales y la aproximación y resolución de problemas ambientaleslos. Se busca la creación de competencias en los principios de investigación reproducible, representación y análisis de información espacial y la creación de mapas estáticos e interactivos. Esto permitirá la adquisiciónde herramientas para profundizar el conocimientos acerca del diseño y desarrollo de análisis de datos ambientales complejos y espacialmente explícitos.

### OBJETIVOS

1.  Conocer y entender el concepto de Investigación Reproducible como una forma y filosofía de trabajo que permite que las investigaciones sean más ordenadas y replicables, desde la toma de datos hasta la escritura de resultados utilizando R.

2.  Realizar análisis críticos de la naturaleza de los datos al realizar análisis exploratorios y reforzar conociminetos en estadística.

3.  Realizar análisis de datos espaciales, poder hacer mapas y aplicar a preguntas de conservación y manejo de recursos naturales.

4.  Aprender a utilizar de forma proficiente el lenguaje de programación R y la plataforma GitHub en un ambiente de trabajo colaborativo.

## Evaluación

### Tareas
-   Se entregarán ejercicios semanales que deben ser resueltos. 
<!-- La entrega se hará usando la plataforma GitHub. Cada estudiante será responsable de entregar su tarea y de corregir a tres compañeros al azar. Las correcciones ocurrirán en modalidad "doble ciego", es decir, tanto el corrector como el autor de la tarea serán mantenido como anónimo. Esta modalidad de corrección por pares será moderada por el profesor y seguirá una pauta entregada para cada tarea. Los estudiantes recibirán un punto por cada tarea revisada, lo que se sumará para completar el puntaje de su propia tarea.  -->


### proyectos
-   Se desarrollán proyectos de análisis y de programación que consistirán en la resolución de un problema, o set de preguntas.

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
| Proyecto código 2           | 25%           |
| Participación / Asistencia | 10%            |
:::

## Calendario

### Módulo 1: Introducción a R y RStudio

1. **18 Agosto** — Presentación del curso
    - R como lenguaje de programación para análisis de datos
    - Entorno de RStudio: navegación básica y gestión del espacio de trabajo
    - Tipos y estructuras de datos: vectores, matrices, data frames y tibbles
    - Operaciones aritméticas y lógicas básicas
    - Introducción a paquetes y gestión de paquetes
  
### Módulo 2: HTML, Markdown \& R

2.  18 Agosto — Introducción a Markdown y R Markdown
    - Creación de informes reproducibles
    - Sintaxis Markdown
    - Incorporación de fragmentos de código R
    - Formatos de salida (HTML, PDF, Word)
    - Investigación reproducible

### Módulo 3: Manipulación de Datos con Tidyverse

3. 25 Agosto — datos desde varios formatos (CSV, Excel, bases de datos, etc.)
    - Introducción a `tidyverse`
    - Importación y Exportación de Datos
    - Manejo de valores faltantes
    - Limpieza y preprocesamiento de datos

4. 1 Septiembre  — Manejo y Análisis de datos
    - Manipulación de datos con `dplyr`: `select`, `filter`, `arrange`, `mutate`, `group_by`, `summarize`
    - Tabulaciones
    - Ordenación de datos con tidyr: gather, spread, separate, unite
    - Transformación de datos con purrr: programación funcional para análisis de datos


5. 8 Septiembre — Análisis y comunicación de resultados


### Modulo 5: Visualización de Datos

5. **15 Septiembre** — Introducción a ggplot2
    - Creación de diversos tipos de gráficos (diagramas de dispersión, histogramas, diagramas de caja, gráficos de barras, gráficos de líneas)
    - Personalización de gráficos con estética, escalas y temas
    - Facetas y capas de gráficos

6. **22 Septiembre** — Visualización 
    - Visualización interactiva
    - Mapview
    

7. **29 Septiembre** — *Presentación de resolución de problema* en 3'+2'
  - Presentación en ppt (markdown)
  - Resultados y Discusión

### Módulo 6: Introducción al Análisis Geoespacial

8. **6 Octubre** — Introducción a los datos espaciales

   - Lectura y escritura de datos espaciales (shapefiles, GeoJSON, etc.)
   - Definir y transformar proyecciones
   - Operaciones espaciales básicas (unión, intersección, búfer)
   - Análisis de datos espaciales
 

9. **13 Octubre** — (Semana de receso)


10 **20 Octubre** — datos en grilla
    - Fuentes y formatos
    - filtros y procesamiento
    - algebra de mapa
    - mapas categóricos, clasificación y reclasificación

11.  **27 Octubre** — Mapas
    - Cartografía
    - Mapas de distintas fuentes
    - Mapas interactivos, mapview y leaflet
  
12. **3 Noviembre** — Operaciones de grillas
    - Operaciones espaciales conjuntas: puntos, vectores y grillas
    - Tabular informacion raster
    - interpolaciones


13. **10 Noviembre** — Proyectos

14. **17 Noviembre** — Proyectos

15. **24 Noviembre** — Proyectos



## Recursos adicionales

Si bien intentamos buscar ejemplos originales y sets de datos locales, gran parte del material con que trabajaremos ha sido ya 
trabajado  elaborado por otros. Es por eso que se sugiere revisar algunos sitios claves como los siguientes:

- [R for Data Sciences](https://r4ds.hadley.nz)
- [Stackoverflow](https://stackoverflow.com/)
- [GIS Stack Exchange](https://gis.stackexchange.com/)
- [Spatial Data Science](https://rspatial.org/index.html)
- [R Graph Gallery](https://r-graph-gallery.com/)
- [ggplot2 tips](https://www.cedricscherer.com/2019/08/05/a-ggplot2-tutorial-for-beautiful-plotting-in-r/)



