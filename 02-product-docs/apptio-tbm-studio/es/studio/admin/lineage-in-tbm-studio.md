---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Linaje"
breadcrumb: []
source_path: "studio/admin/lineage-in-tbm-studio.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Linaje

El linaje de datos es el proceso de rastrear el flujo de datos a lo largo del tiempo, proporcionando una comprensión clara de dónde se originaron los datos, cómo han cambiado y su destino final dentro de la cadena de datos.

## ¿Por qué exigimos Linaje en TBM Studio

En Apptio, el linaje muestra una descripción del flujo a través de una red de muchas relaciones complejas. Ejemplo: Una tabla que fluye a otras tablas, una tabla que pasa a objetos modelo con muchas métricas y luego a diferentes informes. Diferentes áreas en TBM Studio donde el linaje es capaz de rastrear y entender la dependencia son :

- Interconexión de datos
- Modelización
- Informes

En **la canalización de datos**, lo primero que se hace es ingerir los datos de diferentes fuentes, puede que una tabla se obtenga de otra tabla, o puede que se añadan tablas. También puede tener uniones de tablas que pueden identificar relaciones clave entre diferentes tablas. Y por último, dentro de cualquier tabla también puede haber fórmulas con definiciones que dependen de otra tabla, como por ejemplo lookup.

En la **modelización** se pueden establecer relaciones de uno a uno, de uno a muchos o de muchos a muchos entre diferentes objetos de asignación y se derivan complejos algoritmos de ponderación para esos objetos.

Con los **informes analíticos y las visualizaciones**, cada informe puede tener varias pestañas con varios componentes. Cada componente se compone de varias métricas. Ahora puede comprender que su proyecto Apptio puede convertirse en un entorno complejo.

Nuestro objetivo es visualizar esta red masiva de conexiones entre tablas, modelos e informes y mostrar interdependencias potencialmente oscuras y desconocidas. Esto permitirá a los administradores comprender el impacto de los cambios realizados en la configuración. Así, Lineage nos proporciona análisis y perspectivas muy potentes que nos ayudan a responder preguntas básicas como: "¿Qué pasaría si suprimiera esta columna de esta tabla?

## Casos prácticos de linaje

Algunos de los casos de uso de Lineage son:

- Muestra inmediatamente qué es "utilizado por" una entidad concreta (dependencias descendentes) o de qué depende esa entidad (dependencias ascendentes).
- Identifique el impacto del proyecto, si modifica o cambia una entidad como una columna o qué pasa si elimina una tabla.
- Limpie la complejidad del proyecto que crece con el tiempo, identificando y eliminando tablas huérfanas o métricas calculadas no utilizadas.
- Remediar la información sobre privacidad de datos identificando exactamente dónde existen los datos y dónde están expuestos.

## Cómo acceder a Lineage

Una forma de acceder al linaje es en el panel izquierdo del Explorador de proyectos, abriendo el menú mediante <clic derecho> y seleccionando **Trazar linaje para este documento**. La otra es hacer <clic derecho> en una pestaña de entidades en la parte inferior de navegación por pestañas. Se abre una ventana Linaje con una representación visual del flujo de datos en función de la entidad inicial seleccionada. La vista inicial está limitada a una profundidad de 1 y mostrará o bien las dependencias descendentes si se parte de una tabla, columna o métrica calculada; o bien las dependencias ascendentes si se parte de un informe. Empecemos por definir la información que se muestra en la vista de linaje. Cada color representa una entidad concreta:

- El gris representa los datos brutos.
- El verde representa las tablas y columnas estándar.
- El color marrón representa tablas y columnas editables.
- El azul representa los objetos del modelo y las métricas.
- Tan representa informes y componentes de informes.

Puedes desplazar el rodillo del ratón o arrastrar el panel táctil de tu portátil para acercar o alejar el diagrama.

Puede explorar el gráfico Lineage modificando los siguientes datos:

|  |  |
| --- | --- |
| Profundidad | Empezamos siempre con la profundidad 1, que amplía el alcance de las relaciones a partir de la entidad seleccionada. A medida que el proyecto se vuelva más complejo, podrás profundizar más en las relaciones. Mueva el control deslizante para aumentar la profundidad y profundizar en el nivel de dependencias. |
| Mostrar documentos que | También tienes la posibilidad de cambiar entre dependencias descendentes, que es por defecto si eliges algo como una tabla, o dependencias ascendentes, que sería por defecto si eliges un informe. Seleccione para ver los documentos que Dependen de la entidad enfocada (dependencia descendente)o para La entidad enfocada depende de (dependencia ascendente). |
| Sólo ciclos | Seleccione esta casilla para ver sólo el ciclo |
| Cuadro de texto de búsqueda | Introduzca la(s) palabra(s) clave que desea excluir (-) o incluir (+)en los resultados de la búsqueda. Para más información sobre la búsqueda de linaje. Pulse aquí. |
| Teclas añadidas | Muestra todas las entidades que tienen las palabras clave añadidas en el cuadro de texto de búsqueda |
| Llaves excluidas | Muestra todas las entidades que la palabra clave eliminada en el cuadro de texto de búsqueda |
| Alternar subtipos | Seleccione esta opción para activar/desactivar todos los subtipos a la vez. |
| Alternar la eliminación masiva | Elimina todas las entidades incluidas en las Claves Añadidas o Claves Ocultas |
| Aplicar | Seleccione este botón para aplicar los cambios realizados en este panel. |

Temas relacionados:

- [Demostración de linaje](lineage-demo.html "La función Lineage no está activa por defecto. Un Administrador puede habilitarlo navegando a la pestaña Proyecto > Habilitar Características, y luego seleccionando Mostrar Linaje. A continuación, se puede acceder a ella desde diferentes entidades, como Tablas, Columnas en Tablas, Tablas editables e Informes de métricas.")
- [Filtro relacionado](lineage-related-filter.html "Otra forma de utilizar la función de linaje en una experiencia de usuario simplificada en el explorador de proyectos es que ahora tiene la posibilidad de que cuando haga clic en cualquier tabla se le mostrarán las tablas relacionadas mediante la vinculación de su relación.")
- [Buscar documentos no utilizados](lineage-unused-docs.html)
- [Búsqueda de linaje](lineage-search.html)
