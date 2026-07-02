---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Flujo de trabajo de promoción"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Ciclo de vida de la compilación y la implementación"
source_path: "studio/new-uc/concepts-architecture/promotion-workflow.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Flujo de trabajo de promoción

La promoción es el proceso de trasladar el contenido validado del entorno de prueba al de producción. TBM Studio admite dos modos de promoción: bajo demanda y periódico.

**Promociones bajo demanda**

La promoción bajo demanda es el modo predeterminado en el que los administradores promocionan las compilaciones según sea necesario. El proceso es el siguiente:

1. **Validar:** El administrador revisa y valida la versión actual en el entorno de prueba.
2. **Bloqueo:** el administrador bloquea el proyecto para impedir que se realicen nuevas incorporaciones durante la promoción.
3. **Promocionar:** El administrador puede promocionar utilizando las opciones «Promocionar ahora» o «Promocionar más tarde».
4. **Desbloquear:** el administrador desbloquea el proyecto para reanudar las operaciones normales.

**Bloquear un proyecto:** Cuando la fase está bloqueada:

- Los usuarios pueden sacar documentos, pero no pueden devolverlos
- El menú desplegable «Entorno» muestra el estado «Bloqueado»
- Solo los administradores pueden pasar a Producción

Para bloquear o desbloquear un proyecto: Selecciona el entorno de prueba y, a continuación, en la pestaña «Build», selecciona «Bloquear» (o «Desbloquear» si ya está bloqueado).

**Opciones de promoción:**

|  |  |
| --- | --- |
| **Opción** | **Comportamiento** |
| **Promociona ahora** | Promociona el proyecto de inmediato. Desactivado cuando está desbloqueado o cuando todavía se está ejecutando otra compilación. |
| **Promocionar más tarde** | Programa una promoción para una fecha concreta. Las opciones son: publicar tan pronto como finalice la compilación (sin esperar al tiempo especificado) o publicar a la hora especificada si la compilación ha finalizado. |
| **Promoción forzosa** | ( v.12.11.0+ ) Publica la última compilación calculada sin bloquear Stage. Úsalo para actualizaciones urgentes cuando no sea posible bloquear el sistema. |

**Ofertas periódicas**

La promoción recurrente es un modo avanzado para equipos con ritmos consolidados. Se publica automáticamente a las horas programadas. Requisitos previos para utilizar promociones periódicas:

- El equipo tiene un ritmo bien establecido de reuniones y validaciones según un calendario
- El equipo quiere que se informe a Producción con una periodicidad establecida para su uso
- Los miembros del equipo se coordinan entre sí para acordar la hora de llegada

Importante:

El bloqueo no se puede utilizar con promociones periódicas. Si el proyecto está bloqueado durante el periodo de promoción programado, la promoción no se llevará a cabo. No mezcles el bloqueo bajo demanda con las programaciones periódicas.
