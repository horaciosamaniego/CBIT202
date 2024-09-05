---
title: "Programación y Análisis de Datos Geoespaciales"
author: "Horacio Samaniego"
date: "2024-09-05"
site: bookdown::bookdown_site
documentclass: book
# bibliography: [book.bib, packages.bib]
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

11. 7 Noviembre — Proyectos

12. 14 Noviembre — Proyectos

13. 21 Noviembre — Proyectos

14. 28 Noviembre — Proyectos



## Recursos adicionales

Si bien intentamos buscar ejemplos originales y sets de datos locales, gran parte del material con que trabajaremos ha sido ya 
trabajado  elaborado por otros. Es por eso que se sugiere revisar algunos sitios claves como los siguientes:

- [R for Data Sciences](https://r4ds.hadley.nz)
- [Stackoverflow](https://stackoverflow.com/)
- [GIS Stack Exchange](https://gis.stackexchange.com/)
- [Spatial Data Science](https://rspatial.org/index.html)
- [R Graph Gallery](https://r-graph-gallery.com/)
- [ggplot2 tips](https://www.cedricscherer.com/2019/08/05/a-ggplot2-tutorial-for-beautiful-plotting-in-r/)



