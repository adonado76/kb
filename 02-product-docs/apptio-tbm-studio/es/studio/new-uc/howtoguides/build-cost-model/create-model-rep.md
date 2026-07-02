---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear informes de modelos (diagramas de Sankey)"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Modelización avanzada"
source_path: "studio/new-uc/howtoguides/build-cost-model/create-model-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear informes de modelos (diagramas de Sankey)

## Objetivo

Crea un informe de modelo que visualice los flujos de costes a lo largo de tu modelo en formato de diagrama de Sankey, lo que facilita la comunicación con las partes interesadas y la auditabilidad.

## Cuándo utilizar este procedimiento

Crea informes de modelo cuando:

- Debes comunicar los flujos de costes a las partes interesadas sin conocimientos técnicos
- Quieres ofrecer una visualización intuitiva de cómo se distribuyen los costes a lo largo del modelo
- Debes apoyar las auditorías financieras o las iniciativas de transparencia
- Quieres que los usuarios finales puedan explorar los flujos de costes de forma interactiva sin tener que acceder a Model Studio
- Vas a presentar datos financieros de TI a los responsables de las unidades de negocio

**Requisitos previos**

- El modelo se ha construido con asignaciones que fluyen entre objetos
- Las tablas que desea incluir en el informe tienen pasos de modelo
- Ya has seleccionado los niveles (capas) que deseas mostrar

## Tiempo estimado

Entre 20 y 30 minutos para la configuración inicial; entre 5 y 10 minutos para las modificaciones

## Comprender los diagramas de Sankey

En un diagrama de Sankey, el valor fluye de izquierda a derecha. La anchura de cada línea de asignación es proporcional al valor que representa. Esta metáfora visual lo deja claro:

- ¿Qué fuentes suponen el mayor coste (líneas más anchas)?
- Cómo se distribuyen los costes a medida que avanzan por el modelo
- La proporción relativa de los costes que corresponden a cada destino

## Pasos para crear un informe modelo

1. En el Explorador de proyectos, haz clic con el botón derecho del ratón en la carpeta «Modelos», dentro de «Informes», y selecciona «Nuevo informe de modelo».
2. Introduzca un nombre para su informe de modelo (por ejemplo, «Flujo de costes de TI» o «Modelo de costes laborales»).
3. El informe se abre en el editor de informes de plantilla. Echa un vistazo al informe para revisarlo.
4. Haz clic en el menú «Ver» de la pestaña «Inicio» y selecciona «Mostrar editor de niveles».
5. En el Editor de niveles, haz clic en el icono «Añadir nivel» para crear tu primer nivel.
6. Haga clic en el campo «Nombre» situado en la parte superior del nivel e introduzca un nombre descriptivo (por ejemplo, «Finanzas», «Grupos de costes», «Infraestructura», «Servicios»).
7. En el Explorador de proyectos, arrastra una tabla modelada al nivel. Repite este proceso para añadir varias tablas al mismo nivel si es necesario.
8. También puedes desplegar una tabla en el Explorador de proyectos y arrastrar una columna concreta para crear un nivel centrado en esa dimensión (por ejemplo, arrastra la columna «Cost Pool» en lugar de toda la tabla).
9. Repite los pasos 5 a 8 para crear niveles adicionales que representen cada capa de tu modelo.
10. Utiliza el icono «Reorganizar» para arrastrar los niveles y colocarlos en el orden correcto de izquierda a derecha.
11. Haz clic en «Ver» > «Mostrar documento» para obtener una vista previa del informe del modelo.
12. Guarda y revisa el informe.

## Configuración de niveles

Los niveles determinan la estructura y el nivel de detalle del informe de tu modelo. Considera estas opciones:

- Nivel de tabla: muestra la tabla completa. Los usuarios pueden hacer clic en el menú y seleccionar «Desglosar» para ver las columnas por separado.
- Nivel de columna: muestra una dimensión específica (por ejemplo, grupo de costes, nombre del proveedor). Ofrece un análisis detallado.
- Nivel de varias tablas: contiene varias tablas en el mismo nivel. Útil para mostrar flujos de costes paralelos.

Nota: Un nivel puede contener una sola columna O una o varias tablas, pero no ambas cosas.

## Interacción con los informes de modelos

Una vez creados, los usuarios pueden interactuar con los informes de modelos de las siguientes maneras:

- Haz clic en un elemento de la tabla para ver sus factores determinantes y sus asignaciones
- Sigue haciendo clic en los elementos de la tabla para seguir el recorrido del valor a través del modelo
- Abre el menú de una tabla y haz clic en «Desglosar» para ver los valores de una columna concreta
- Haga clic en las líneas de asignación para ver los detalles de las transacciones subyacentes

## Añadir informes de modelo a colecciones de informes

En TBM Studio 12.2.2 y versiones posteriores, puedes añadir informes de modelos a colecciones de informes para facilitar el acceso:

1. Abre el informe de modelo y échale un vistazo.
2. Haz clic en la pestaña «Modelado» de la cinta de opciones.
3. Haz clic en «Asignar a la colección».
4. Selecciona la colección de informes de destino en el menú desplegable.
5. Guarda y revisa el informe.

## Mejores prácticas

- Utiliza nombres de niveles claros y fáciles de entender para el personal de la empresa («Infraestructura de TI» en lugar de «Nivel 3»)
- Limita los niveles a entre 4 y 6 para facilitar la lectura; demasiados niveles abruman al lector
- Elabora varios informes específicos en lugar de un único informe general
- Utiliza los niveles de columna cuando quieras destacar una dimensión concreta (por ejemplo, el flujo de un grupo de costes)
- Añade los informes de modelo a las colecciones de informes para que los usuarios finales puedan encontrarlos fácilmente

## Tareas relacionadas

- [Seguimiento de los flujos de costes a lo largo del modelo](trace-cost-flow.html)
- [Crear colecciones de informes de compilación](../create-reports/build-rc.html)
- [Ver el diagrama del modelo](view-model-diagram.html)

**Tema principal:** [Modelización avanzada](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
