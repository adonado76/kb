---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Ver el diagrama del modelo"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Conceptos básicos sobre modelos"
source_path: "studio/new-uc/howtoguides/build-cost-model/view-model-diagram.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ver el diagrama del modelo

|  |  |
| --- | --- |
| **Tipo de contenido** | Guía práctica |
| **Destinatarios** | Analistas de negocios, equipos de TI y finanzas, administradores |
| **Tiempo estimado** | 5-10 minutos |
| **Requisitos previos** | Se ha añadido al menos una tabla al modelo |

## Objetivo

Consulte el diagrama del modelo para comprender la estructura general de su modelo de costes, ver cómo se relacionan las tablas mediante asignaciones y seguir el flujo de los costes a lo largo de su organización.

## Cuándo utilizar este procedimiento

Consulte el diagrama del modelo cuando lo necesite:

- Comprende el flujo de costes de principio a fin en tu modelo
- Incorpora a los nuevos miembros del equipo mostrándoles la estructura del modelo
- Depura los problemas de asignación mediante el seguimiento de las rutas de costes
- Documenta el diseño de tu modelo para las partes interesadas
- Comprueba que las tablas recién añadidas estén conectadas correctamente

## Vistas de modelos disponibles

TBM Studio ofrece tres formas de visualizar tu modelo:

**1. Modelador de objetos únicos (diagrama de Sankey)**

Esta es la vista predeterminada que aparece al hacer clic en el paso «Modelo» del proceso de transformación de una tabla. Muestra la tabla seleccionada en el centro, con sus controladores a la izquierda y los destinos de asignación a la derecha. Utilice esta vista al configurar controladores y asignaciones para una tabla concreta.

**2. Vista métrica modelada (diagrama completo del modelo)**

Esta vista muestra todos los objetos del modelo y sus conexiones en un diagrama similar al de Visio. Muestra todo el flujo de costes desde las tablas de origen, pasando por las capas intermedias, hasta los destinos finales. Utiliza esta vista para tener una visión general de tu modelo.

**3. Informes de modelos (vista de Sankey por niveles)**

Los informes de modelos presentan el modelo en un formato fácil de usar, con niveles definidos (como «Finanzas», «Grupos de costes», «Infraestructura» y «Servicios»). Están pensados para el uso por parte del usuario final y ofrecen funciones de análisis detallado.

## Pasos: Ver el diagrama de métricas modeladas

Para ver el diagrama completo del modelo, en el que se muestran todas las tablas y sus conexiones:

1. **Abre cualquier objeto de modelo.** En el Explorador de proyectos, selecciona una tabla que contenga un paso «Modelo» y, a continuación, haz clic en **dicho** paso dentro del proceso de transformación.
2. **Cambia a la vista «Métrica modelada».** En el menú **Ver**, haz clic en **Métrica modelada**. El diagrama se amplía para mostrar todos los objetos del modelo y sus relaciones.
3. **Explora el diagrama.** Utiliza los controles de zoom y desplazamiento para explorar el modelo. Haz clic en cualquier objeto del modelo para resaltar sus conexiones y ver sus detalles.
4. **Selecciona una métrica para verla.** Utiliza el selector de métricas situado en la parte superior del diagrama para cambiar entre «Coste», «Presupuesto», «Previsión» u otras métricas. El gráfico se actualiza para mostrar los valores de la métrica seleccionada.

## Interpretación del diagrama del modelo

El diagrama del modelo utiliza una visualización de tipo Sankey en la que:

- Los rectángulos representan objetos del modelo (tus tablas)
- Las líneas entre los rectángulos representan asignaciones
- El grosor de la línea es proporcional al valor: las líneas más gruesas indican que por esa ruta circula una mayor cantidad de dinero
- El valor se desplaza de izquierda a derecha (o de abajo hacia arriba en algunas vistas)

**Cómo interpretar el flujo:** Empieza por los objetos situados más a la izquierda (o en la parte inferior); estos suelen ser las fuentes de coste, es decir, por donde entra el dinero en el modelo. Sigue las líneas hacia la derecha (o hacia arriba) para ver cómo se distribuyen los costes entre los objetos intermedios y llegan finalmente a destinos finales como las unidades de negocio o los servicios.

## Patrones comunes de diagramas

**Una sola fuente, varios destinos:** una tabla de fuentes de costes que se imputa a varias categorías de grupos de costes (mano de obra, instalaciones, hardware). Las líneas de distribución se extienden desde el punto de origen.

**Múltiples fuentes, un único destino:** varios componentes de infraestructura (servidores, almacenamiento, red) que se asignan a las aplicaciones. Las líneas convergen en el punto de mira.

**Asignaciones en cascada:** Fuente de costes → Proveedores → Servicios tecnológicos → Soluciones → Unidades de negocio. Cada nivel pasa a la siguiente etapa, creando un flujo secuencial.

## Uso del diagrama para la resolución de problemas

**Conexiones faltantes:** si una tabla aparece aislada, sin líneas que la conecten, significa que la asignación no se ha configurado. Comprueba la sección «Modelo» de la tabla para añadir asignaciones.

**Líneas inesperadamente finas:** si una línea de asignación es mucho más fina de lo esperado, comprueba los pesos de asignación o los datos del controlador. Es posible que haya registros sin emparejar, lo que hace que algunos costes sigan sin asignarse.

**Seguimiento de costes específicos:** haz clic en un objeto del modelo en el diagrama para resaltar sus conexiones. Puedes seguir el rastro hacia adelante para ver adónde van los costes, o hacia atrás para ver de dónde proceden.

**Consejo:** El diagrama del modelo refleja la configuración del modelo actualmente implementada. Los cambios realizados en las asignaciones no aparecerán hasta que guardes, valides y el proyecto vuelva a calcular.

## Navegación a partir del diagrama

El diagrama es interactivo. Al hacer clic en un objeto modelo, se abre la vista «Modelador de objeto único», donde se pueden configurar los controladores y las asignaciones. Esto permite pasar fácilmente de una visión general a los detalles de una tabla concreta.

## ¿Qué viene ahora?

- Configure las asignaciones para las tablas que aún no están conectadas; consulte la sección 3.2.2
- Crea informes del modelo para ponerlo a disposición de los usuarios finales; consulta la sección 3.3
- Utilice las funciones de desglose para rastrear partidas de costes específicas; consulte la Referencia de Model Studio (sección 5.2 )

## Conceptos relacionados

- [Arquitectura del modelo](../../concepts-architecture/model-architecture/model-concepts-overview.html) : comprender cómo se ejecutan las asignaciones y cómo fluyen las métricas
- Informes de modelos (Sección 5.2 ) — Creación de visualizaciones de modelos destinadas al usuario final

**Tema principal:** [Conceptos básicos del modelo](../../../../studio/new-uc/howtoguides/build-cost-model/model-basics.html)
