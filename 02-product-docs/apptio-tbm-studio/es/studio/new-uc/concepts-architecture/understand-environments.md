---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Comprender los tres entornos"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Ciclo de vida de la compilación y la implementación"
source_path: "studio/new-uc/concepts-architecture/understand-environments.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Comprender los tres entornos

TBM Studio organiza el trabajo en tres entornos distintos, cada uno de los cuales cumple una función específica en el flujo de trabajo desde el desarrollo hasta la producción. Se puede acceder a los tres entornos desde un único URL a través del menú «Entorno» de la barra de herramientas.

**Entorno de Desarrollo**

El entorno de desarrollo es tu espacio de trabajo personal para realizar cambios. Cuando extraes un documento y empiezas a editarlo, entras automáticamente en el entorno de desarrollo. Entre sus características principales se incluyen:

- **Aislamiento:** tus modificaciones se limitan a tu espacio de trabajo. Los demás usuarios no podrán ver tus cambios hasta que los guardes.
- **Cálculo en tiempo real:** al guardar los cambios, TBM Studio calcula las transformaciones y las métricas para que puedas comprobar tu trabajo de inmediato.
- **Varios espacios de trabajo:** si otros usuarios tienen documentos extraídos, sus entornos de desarrollo aparecen en el menú Entorno. Si dispones de los permisos adecuados, puedes ver o incluso editar documentos en el espacio de trabajo de otro usuario.
- **Cambio automático:** cuando no tienes ningún documento extraído, TBM Studio te cambia automáticamente al entorno de prueba.

**Entorno de pruebas**

El entorno de prueba recopila todos los cambios registrados por todos los usuarios. Sirve como capa de integración y validación previa a la puesta en producción. Entre sus características principales se incluyen:

- **Estado compartido:** todas las modificaciones de todos los usuarios se combinan aquí tras el check-in.
- **Cálculo completo:** tras cada registro, Stage realiza un cálculo completo que incluye simulacros e informes.
- **Pasarela de validación:** los administradores validan los cambios en el entorno de prueba antes de implementarlos en el entorno de producción.
- **Función de bloqueo:** Se puede bloquear la fase de preparación para impedir que se realicen nuevas incorporaciones durante el proceso de promoción.

Nota:

Los nodos de cálculo por etapas se aprovisionan bajo demanda, lo que puede tardar hasta 15 minutos. El cálculo se ejecuta una vez finalizado el aprovisionamiento.

**Entorno de producción**

El entorno de producción contiene la versión validada y aprobada de tu proyecto que utilizan los usuarios finales. Entre sus características principales se incluyen:

- **Solo lectura para la mayoría de los usuarios:** los usuarios con acceso de solo lectura siempre ven el entorno de producción. No pueden ver los entornos de prueba ni de desarrollo.
- **Actualizaciones controladas:** solo los administradores pueden pasar contenido del entorno de prueba al de producción.
- **Promoción casi instantánea:** En TBM Studio 12.x, la promoción a la fase de producción es casi instantánea.
- **La visibilidad depende de la promoción:** la producción solo aparece en el menú «Entorno» después de que «Stage» haya sido promocionado al menos una vez.

**Comparación de entornos**

|  |  |  |  |
| --- | --- | --- | --- |
| **Aspecto** | **Desarrollo** | **Transfiriendo** | **Producción** |
| Finalidad | Edición individual | Integración y validación | Consumo de los usuarios finales |
| Visibilidad | Específico para cada usuario | Todos los editores | Todos los usuarios |
| Calcula | Transformaciones, métricas | Transformaciones, métricas, análisis detallados, informes | Recibe versiones promocionadas |
| ¿Quién puede editar? | Usuarios avanzados, administradores | N/A (acepta registros de entrada) | N/A (recibe promociones) |
