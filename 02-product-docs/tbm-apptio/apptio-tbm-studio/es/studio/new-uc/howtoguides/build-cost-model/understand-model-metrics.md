---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Comprender las métricas del modelo (coste, presupuesto, previsión)"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Conceptos básicos sobre modelos"
source_path: "studio/new-uc/howtoguides/build-cost-model/understand-model-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Comprender las métricas del modelo (coste, presupuesto, previsión)

|  |  |
| --- | --- |
| **Tipo de contenido** | Guía práctica / Conceptual |
| **Destinatarios** | Analistas de negocios, equipos de TI y finanzas |
| **Tiempo estimado** | 10-15 minutos |
| **Requisitos previos** | Conocimientos básicos de TBM Studio; familiaridad con conceptos financieros |

## Objetivo

Comprenda qué son las métricas del modelo, cómo funcionan las métricas principales (coste, presupuesto y previsión) y cómo se distribuyen a través de las asignaciones en su modelo de costes.

## Cuándo utilizar esta información

Esta guía conceptual te servirá de ayuda cuando:

- Configurar un nuevo modelo y decidir qué métricas se van a monitorizar
- Configuración de asignaciones que se aplican a métricas específicas
- Interpretación de informes de modelos que muestran múltiples métricas
- Creación de informes de desviaciones que comparan los costes con el presupuesto
- Solución de problemas: por qué ciertos valores no fluyen como se esperaba

## ¿Qué son las métricas de modelos?

Una **métrica de modelo** es un valor numérico que circula por el modelo de costes a través de las asignaciones. Aunque TBM Studio admite muchos tipos de métricas, hay tres que son fundamentales para la mayoría de las gestiones financieras en el ámbito de las tecnologías de la información:

|  |  |
| --- | --- |
| **Métrica** | **Descripción** |
| **Coste** | Gastos realmente incurridos. Esta suele ser la métrica principal en un modelo TBM, y se obtiene del libro mayor, las facturas u otros sistemas financieros. El coste es lo que realmente has gastado. |
| **Presupuesto** | Importes de gasto previstos o asignados. El presupuesto representa lo que tenías previsto gastar y, por lo general, se establece durante la planificación anual. Al comparar el presupuesto con los costes se detectan las desviaciones. |
| **Previsión** | Gasto previsto para el futuro según las tendencias actuales. Por lo general, las previsiones se actualizan a lo largo del año a medida que se van conociendo los patrones de gasto reales, lo que ofrece una visión más precisa de la evolución de los costes. |

Es posible que su organización utilice también otros indicadores, como los gastos de capital ( CapEx ), la utilización o indicadores personalizados específicos para las necesidades de su negocio.

## Métricas del modelo frente a métricas calculadas

TBM Studio admite dos tipos de métricas:

**Las métricas modeladas** (también denominadas métricas simuladas) se originan en los datos de origen y se transmiten a través de las asignaciones. El coste, el presupuesto y la previsión suelen ser métricas del modelo. Son los valores brutos que se introducen en el modelo en el nivel más bajo (como «Fuente de costes») y se propagan hacia arriba a través de cada paso de asignación.

**Las métricas calculadas** se obtienen a partir de las métricas del modelo mediante fórmulas. Por ejemplo, podrías crear una métrica calculada denominada «Desviación presupuestaria», definida como «Presupuesto» menos «Coste». Las métricas calculadas no se tienen en cuenta en las asignaciones; se calculan en el nivel de generación de informes.

**Nota:** Las métricas del modelo se suman al agrupar los datos. Las métricas calculadas se vuelven a calcular utilizando sus fórmulas. Esta distinción es importante a la hora de agregar datos entre distintos periodos o jerarquías.

## Cómo se aplican las métricas a las asignaciones

Al crear una asignación, se especifica a qué métricas se aplica. Así es como funciona el proceso:

1. **Los conductores de las unidades aportan valor.** En la tabla de costes (el nivel inferior de tu modelo), los controladores de unidades extraen los valores de las columnas de tus datos. Por ejemplo, un controlador de unidad podría utilizar la columna «Importe» para incorporar el coste al modelo.
2. **Las asignaciones distribuyen el valor.** Cada asignación toma un valor de una tabla y lo distribuye a otra según unas reglas de ponderación. Por ejemplo, se puede asignar el coste de la fuente de costes a los proveedores en función de los importes de las facturas de estos.
3. **Las métricas se propagan de forma independiente.** Si configuras una asignación para que se aplique tanto al coste como al presupuesto, cada métrica se contabiliza por separado. Los valores de costes se transfieren del origen al destino utilizando los coeficientes de asignación, y lo mismo ocurre con los valores presupuestarios, manteniendo sus totales independientes en todo el modelo.
4. **Los valores se transmiten a través de los distintos niveles.** A medida que se crea un modelo de varios niveles (Fuente de costes → Proveedores → Servicios tecnológicos → Unidades de negocio), las métricas fluyen a través de cada nivel, acumulándose y distribuyéndose según las reglas de asignación establecidas.

## Visualización de métricas en el modelo

Puedes cambiar de sistema de medidas mientras visualizas el modelo:

1. Abre un objeto de modelo haciendo clic en su paso «Modelo» en el flujo de transformación.
2. Busca el selector de unidades de medida en la parte superior del panel del modelo. Este menú desplegable muestra todas las métricas disponibles (coste, presupuesto, previsión, etc.).
3. Selecciona otra métrica para ver cómo se refleja ese valor en el modelo. El ancho de los diagramas de Sankey se actualiza para reflejar los valores de la métrica seleccionada.

Consejo: Al crear informes de modelo, puedes seleccionar qué métricas incluir mediante el botón «Editar métricas» del Editor de niveles. Incluir menos métricas mejora el rendimiento de los cálculos.

## Creación y gestión de métricas

Las métricas se definen a nivel de proyecto y aparecen en la sección «Métricas» del Explorador de proyectos. Para crear una nueva métrica:

1. En la pestaña Inicio, haz clic en **Nuevo** y, a continuación, en **Métrico**.
2. Escribe un nombre y haz clic en **Aceptar**.
3. Configure las propiedades de la métrica, incluyendo el tipo de modelo (Modelo o Calculado), el formato y el tipo de métrica (Coste, Precio o Numérico).
4. Guarda y comprueba la métrica.

## Propiedades de las métricas clave

**Tipo de modelo:** Selecciona «Modelo» para las métricas que se calculan a partir de asignaciones, o «Calculado» para las métricas basadas en fórmulas.

**Tipo de métrica:** Seleccione «Coste» para valores monetarios procedentes de fuentes con costes completos (como un libro mayor), «Precio» para modelos de precio × cantidad, o «Numérico» para valores no monetarios.

**Formato de tabla:** Determina cómo se muestra la métrica en los informes. Utiliza =Currency($\_) para que los valores monetarios se muestren en dólares.

**Comportamiento temporal:** determina cómo se agrega la métrica a lo largo de los periodos de tiempo: suma, media o recálculo.

## ¿Qué viene ahora?

- [Configurar asignaciones](setup-sa.html) para que los datos se transfieran entre tablas
- Crea métricas calculadas para el análisis de variaciones; consulta [la Referencia de Model Studio](../../reference/model-studio-ref.html)
- Más información sobre las propiedades y fórmulas de las métricas: consulta «[Arquitectura del modelo](../../concepts-architecture/model-architecture/model-concepts-overview.html) ».

## Conceptos relacionados

- [Arquitectura del modelo](../../concepts-architecture/model-architecture/model-concepts-overview.html) : explicación detallada de cómo el motor de asignación procesa las métricas
- [Fórmulas y funciones](../../reference/formula-function.html) : creación de métricas calculadas con fórmulas

**Tema principal:** [Conceptos básicos del modelo](../../../../studio/new-uc/howtoguides/build-cost-model/model-basics.html)
