---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Resumen de conceptos de modelos"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura del modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/model-concepts-overview.html"
images:
  - "resources/images/studio_images/cost-model.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Resumen de conceptos de modelos

El modelo de costes es el núcleo de TBM Studio. Se trata de una representación estructurada del flujo de costes a lo largo de su organización: desde los asientos del libro mayor, donde el dinero entra en el sistema, pasando por las capas de asignación intermedias, hasta las unidades de negocio, aplicaciones o servicios finales que consumen esos recursos.

Piensa en un modelo de costes como si fuera un mapa. Los datos financieros brutos te indican cuánto has gastado. Un modelo de costes te indica en qué se gastó el dinero, quién lo utilizó y por qué. Sin un modelo, solo tienes cifras. Con un modelo, se obtiene una visión clara.

## ¿Qué es un modelo de costes?

En pocas palabras, un modelo de costes responde a la siguiente pregunta: ¿cómo distribuimos de forma equitativa los costes compartidos entre las personas y los servicios que realmente los utilizan?

Imaginemos un centro de datos cuyo funcionamiento cuesta 2 millones de dólares al año. Los costes aparecen como una sola partida en el libro mayor, pero hay seis unidades de negocio diferentes que utilizan servidores en ese centro de datos. Un modelo de costes te permite distribuir (asignar) esos 2 millones de dólares entre esas seis unidades de negocio en función del número de servidores que utiliza cada una, la cantidad de almacenamiento que consumen o cualquier otro factor que refleje el consumo real.

Nota:

**Concepto clave: el modelo de costes como mapa**

Un modelo de costes no es un conjunto de datos sin procesar, sino un conjunto de reglas que describen cómo deben distribuirse los costes. El modelo define las rutas; los datos aportan las cantidades. Cuando se ejecuta un cálculo (denominado «compilación»), TBM Studio aplica esas reglas a los datos actuales y genera los resultados de la asignación.

**Objetivo de un modelo de costes:**

- Convierte los datos financieros brutos en información útil y detallada
- Distribuir los costes compartidos de forma equitativa en función de factores de consumo cuantificables
- Habilitar el showback y el chargeback para las unidades de negocio
- Facilitar la planificación presupuestaria mediante la simulación de escenarios hipotéticos de asignación
- Proporcionar un registro auditable desde el coste de origen hasta el consumidor final

## Modelo, datos e informes: los tres estudios

TBM Studio cuenta con tres espacios de trabajo principales, y es fundamental comprender cómo se relacionan entre sí antes de adentrarse en la arquitectura de modelos.

|  |  |  |
| --- | --- | --- |
| **Estudio** | **Rol** | **Analogía** |
| Data Studio | Importa, limpia y transforma los datos sin procesar en tablas | La despensa de la cocina: ingredientes frescos, bien ordenados y listos para usar |
| Estudio de modelos | Define cómo se transfieren los costes de las tablas de origen a las tablas de destino mediante asignaciones | La receta: las reglas para combinar los ingredientes y obtener un producto final |
| Report Studio | Presenta los resultados correspondientes a las partes interesadas mediante gráficos, tablas y paneles de control | La mesa del comedor: la comida ya preparada, emplatada y servida |

Los datos circulan por estos estudios siguiendo una secuencia concreta. En primer lugar, Data Studio prepara tablas de conversión a partir de los archivos subidos. A continuación, Model Studio utiliza esas tablas de transformación como entradas para los objetos del modelo y aplica las reglas de asignación. Por último, Report Studio consulta el modelo para mostrar los resultados. Si tus datos cambian, vuelve a ejecutar la compilación y el modelo se recalculará. Si cambia la lógica de asignación, modifica el modelo y vuelve a ejecutarlo.

## Cómo leer un diagrama de modelo

TBM Studio ofrece una vista esquemática que muestra todos los objetos del modelo y sus conexiones. Esta es una de las herramientas más útiles para comprender un modelo de costes de un solo vistazo.

Nota:

**Lo que muestra el diagrama**

Cada rectángulo (nodo) representa un objeto del modelo: un contenedor de costes en un nivel concreto. Las líneas entre los nodos representan asignaciones: reglas que transfieren los costes de un objeto a otro. El ancho de cada línea es proporcional al valor que se le asigna (visualización al estilo Sankey). Los costes se desplazan de izquierda a derecha (o de abajo hacia arriba), desde las fuentes hasta los consumidores finales.

A continuación se muestra una representación conceptual de un diagrama típico de modelo de costes:

![Modelo de costes](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cost-model.png)

En la vista de diagrama de TBM Studio, puedes hacer clic en cualquier nodo para abrir el Modelador de objetos individuales, que muestra en detalle los controladores, las asignaciones y las conexiones de ese objeto. El diagrama se actualiza automáticamente cuando cambian los objetos del modelo, y no es posible modificar las asignaciones directamente desde el diagrama, ya que se trata de una visualización de solo lectura del modelo implementado.

Sugerencia:

**Cómo utilizar el diagrama de forma eficaz**

Utiliza la vista de diagrama para incorporar a nuevos miembros del equipo, depurar resultados de asignación inesperados y comunicar la estructura del modelo a las partes interesadas. Ofrece una visión inmediata e intuitiva de cómo se distribuyen los costes en tu organización.
