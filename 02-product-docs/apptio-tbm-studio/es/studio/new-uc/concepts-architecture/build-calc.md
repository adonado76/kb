---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Proceso de construcción y cálculo"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Ciclo de vida de la compilación y la implementación"
source_path: "studio/new-uc/concepts-architecture/build-calc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Proceso de construcción y cálculo

En TBM Studio, una «compilación» se refiere al proceso de calcular todas las transformaciones, métricas, análisis detallados e informes para un entorno determinado. Entender qué factores desencadenan las compilaciones y cómo se gestionan en la cola te ayuda a planificar tu trabajo de forma eficaz.

**¿Qué desencadena una compilación?**

Las compilaciones se activan mediante diferentes acciones, dependiendo del entorno:

|  |  |  |
| --- | --- | --- |
| **Entorno** | **Desencadenante** | **¿Qué se tiene en cuenta?** |
| Desarrollo | Guardar (con la función de cálculo automático activada) | Transformaciones y métricas |
| Transfiriendo | Registro de cualquier documento | Transformaciones, métricas, análisis detallados, informes |
| Producción | Ascenso desde el equipo de preproducción | Recibe la compilación calculada (sin recalcular) |

**Flujo de datos de cálculo**

Comprender el flujo de datos de cálculo ayuda a diagnosticar problemas cuando las compilaciones fallan o producen resultados inesperados. El proceso general es el siguiente:

1. **Tablas de datos:** Se cargan o importan los datos sin procesar.
2. **Pasos de la transformación:** los datos se limpian, se asignan, se unen y se enriquecen.
3. **Conjuntos de datos maestros:** las tablas unificadas (por ejemplo, el maestro de fuentes de costes) combinan datos del libro mayor, del presupuesto y de las previsiones.
4. **Objetos de modelo:** El modelo hace referencia a estas tablas de transformación unificadas.
5. **Asignaciones:** Las métricas se transmiten hacia abajo a lo largo de la cadena de asignación.
6. **Informes:** Los valores calculados se muestran en los informes.

Nota:

**Comportamiento clave:** El modelo no puede realizar cálculos a menos que las tablas de transformación superen la validación. Los errores en las transformaciones previas bloquearán la lógica de la capa del modelo. Resuelve siempre los errores de transformación antes de esperar a que finalicen los cálculos del modelo.

**Supervisión de la cola de cálculo**

La cola de cálculos muestra lo que ya se ha calculado (con la duración), lo que se está calculando en este momento y lo que está en espera. Para verlo:

1. En TBM Studio, selecciona la pestaña «Compilar».
2. Haga clic en «Cola de cálculos».

Cuando se producen varios registros en un breve periodo de tiempo, es posible que se agrupen en un único cálculo. Si ya hay un cálculo en ejecución, los registros posteriores se ponen en cola para el siguiente cálculo. En el caso de cálculos de Stage que duran mucho tiempo, te recomendamos que utilices la función «Cancelar compilación» ( v.12.3.1+ ) para cancelar la compilación en curso, de modo que los cambios pendientes se puedan incluir en la siguiente compilación.

Sugerencia:

Coordina las reuniones con tu equipo. Si todo el mundo realiza el registro al mismo tiempo (por ejemplo, al final del día), el sistema agrupa los datos en un solo cálculo en lugar de poner en cola varios cálculos secuenciales.
