---
concept: "Configuration Guide (arquitectura de datos, responsabilidades, alineación de taxonomía, perfil organizacional, datos de costo/infraestructura, peer groups, y gobierno de configuración)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-benchmarking
status: draft
generated_from:
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-purpose-scope.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-architecture-data-flow.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-configuration-responsibilities.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-taxonomy-version-alignment.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-organizational-profile-configuration.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-cost-data-configuration.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-infrastructure-data-volumes.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-peer-group-configuration.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-data-refresh-maintenance.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-configuration-governance.md
last_updated: "2026-07-12"
---
# Configuration Guide — Cómo IBM Apptio Benchmarking Aborda Esta Capacidad

## El concepto

Pasado el Quickstart, la configuración de Benchmarking tiene decisiones estructurales que, si se toman mal o sin coordinación, invalidan silenciosamente las comparaciones durante meses — desalineación de versión de taxonomía, datos de infraestructura sin volumen asociado, o peer groups mal escogidos que hacen que el cliente "no se parezca a sus pares" por razones de configuración, no operativas. Esta capacidad documenta el cableado completo: de dónde vienen los datos, quién es dueño de qué decisión, y cómo mantener la configuración sana a medida que el modelo TBM evoluciona.

## Cómo lo resuelve IBM Apptio Benchmarking

**Alcance explícito de esta sección — y lo que deliberadamente deja fuera.** El Configuration Guide cubre cómo fluyen los datos entre Costing, Benchmarking y los datasets externos, qué decisiones de configuración importan y quién las posee, cómo configurar perfil organizacional/costo/volúmenes de infraestructura/peer groups, y cómo mantener la configuración saludable conforme evoluciona el modelo TBM. Explícitamente **no** cubre cómo interpretar reportes o abordar brechas — eso vive en Using Benchmarking Reports y Operations & Governance, una separación de responsabilidades útil para no mezclar "cómo se configura" con "qué significa lo que veo".

**Flujo de datos en cuatro capas** — datasets de benchmark externos (economía de industria, distribuciones de OpEx, costo/eficiencia unitaria de infraestructura), perfil organizacional propio (revenue, headcount, industria, región, banda de tamaño), datos de costo del área de TI (costo anual por Cost Pool, Resource Tower y Sub-Tower), y datos de volumen/capacidad (servidores, TB de storage, puertos de red, FTEs). Este es el mapa mental a usar en cualquier sesión de arquitectura de datos con el equipo técnico del cliente.

**Reparto explícito de responsabilidades — el "quién hace qué" que evita la parálisis de "no sé quién decide esto":**

- **TBM/ITFM Program Lead** — dueño de cómo se usa Benchmarking dentro del programa; aprueba cambios mayores como selección de peer group y versión de taxonomía.
- **TBMA / analista** — impulsa el trabajo de configuración y mapeo; mantiene perfil organizacional, costo, volúmenes y FTEs; corre validaciones y responde "por qué se ve así".
- **Admin de plataforma** — gestiona acceso al producto y configuración a nivel de ambiente; coordina con soporte de IBM Apptio si algo falla.
- **Dueños de Resource Tower** — proveen datos fuente y contexto; hacen sanity-check de los resultados de infraestructura y OpEx de su área.

El documento incluye una versión "de administrador" del Implementation Checklist: un solo proyecto de Costing designado como fuente si hay integración, versión TBM seleccionada y alineada, perfil organizacional completo, costo anual disponible por Cost Pool/Tower, datos de infraestructura si aplica, peer group por defecto definido, y dominios de Industria/OpEx habilitados y devolviendo valores sensatos.

**Alineación de taxonomía y versión — la decisión estructural de mayor riesgo si se ignora.** Si el modelo del proyecto de Costing no está alineado con la versión ATUM seleccionada en Interactive Benchmarking, las métricas resultan inexactas e incompletas. La versión determina qué Cost Pools/Resource Towers/Sub-Towers existen, cómo se agrupan las métricas de infraestructura, y qué definiciones de benchmark están disponibles. La guía recomienda explícitamente: si el cliente está a mitad de una migración, elegir la versión objetivo y terminar primero el lado de Costing; identificar estructuras custom o fusionadas (ej. una categoría local de "Data Center" que mezcla varias Resource Towers estándar, o Cost Pools custom que mezclan Labor y Outside Services) y crear tablas de mapeo que traduzcan códigos locales a la taxonomía estándar — mapeando a la torre más cercana con anotación, o excluyendo del alcance de benchmarking cuando no hay mapeo 1-a-1. La advertencia es directa: saltarse este paso significa "meses discutiendo por qué tu estructura no se parece a la de tus pares".

**Perfil organizacional — tres campos simples que afectan métricas de escalamiento y elegibilidad de datasets.** Revenue anual, OpEx anual, y conteo promedio de FTE para el año. Se debe actualizar cuando hay una adquisición o desinversión material, cuando cambia la clasificación de industria primaria, o cuando el alcance de TI pasa de regional a global (o viceversa).

**Datos de costo — dos rutas, con los mismos ocho Cost Pools estándar como destino:** External Labor, Facilities & Power, Hardware, Internal Labor, Other, Outside Services, Software, y Telecom. La conexión con Costing sigue el mismo flujo visto en Quickstart (seleccionar "Cost Transparency", validar conexión, elegir proyecto y período fiscal, traer los datos), con validaciones de conciliación contra Finanzas y de que todas las Resource Towers mayores tengan valores no-cero. Un detalle técnico importante: si Costing usa múltiples monedas, la conversión debe ocurrir **antes** de que los datos lleguen a Benchmarking — la moneda de costo de TI y de revenue debe ser la misma, y el período usado debe ser un año fiscal completo, no un semestre o período mixto.

**Datos de infraestructura — costo solo no es suficiente; se necesita volumen y FTEs correlacionados.** Para cada Resource Sub-Tower se requieren tres elementos alineados: costo anual, una métrica de volumen/capacidad que coincida con la definición del benchmark, y volumen de FTE del personal que da soporte a esa Sub-Tower. Ejemplos concretos documentados: Servers (costo = hardware + licencias OS + labor; volumen = número de servidores o vCPUs), Storage (volumen = TB de capacidad usable), Network (volumen = dispositivos o puertos). Reglas de integridad explícitas: el volumen debe alinearse con el alcance del costo, no se debe contar el mismo dispositivo en múltiples Sub-Towers a menos que sea el diseño intencional, y se debe usar la unidad exacta que espera la definición del benchmark.

El documento incluye además una tabla de referencia extensa (soportada hasta TBM versión 4) que mapea cada Resource Tower/Sub-Tower estándar a su unidad de medida específica y si tiene benchmarking disponible — por ejemplo, Compute/Servers usa "Logical Servers", Storage/Online Storage usa "Installed TB", End User/Mobile Devices usa "Devices". No todas las Sub-Towers tienen benchmarking disponible (ej. Compute/Converged Infrastructure y varias de Security & Compliance están marcadas como "No") — un detalle útil para gestionar expectativas del cliente sobre qué torres específicas sí van a tener comparación de peers disponible.

**Configuración de peer groups — hasta tres criterios combinables, con 39 categorías de industria estandarizadas** (desde Automotive hasta Utilities, pasando por Banking & Finance, Healthcare Payer, Information Technology, etc.). El peer group por defecto se recomienda alinear con industria similar, banda de revenue similar, y la región/vista global que coincida con el alcance real de TI del cliente — seleccionable de forma interactiva haciendo clic directamente sobre las barras/cajas de las distribuciones mostradas en la interfaz.

**Refresh y mantenimiento — la configuración no es "configurar una vez y olvidar".** Cadencia anual (después del refresh de datos de benchmark, fin del segundo trimestre calendario): validar la configuración core para el año fiscal completo más reciente y alinear con planificación o cierre financiero. Cadencia trimestral: spot-check de métricas clave buscando saltos anómalos, y si hay integración, validar que el modelo de Costing no tenga mapeos rotos. Disparadores de revisión ad hoc: agregar/renombrar Resource Towers, introducir nuevos Cost Pools, o cambios significativos en lógica de asignación — cualquiera de estos exige revisar mapeos, re-correr un set estándar de vistas para confirmar plausibilidad, y **documentar que ocurrió un cambio estructural** para que cualquiera que revise tendencias después sepa dónde está el quiebre.

**Gobierno de configuración — tratar las decisiones de configuración como cambios reales, no preferencias casuales.** Se recomienda mantener un resumen de configuración corto por ambiente (proyecto de Costing, versión TBM, peer groups seleccionados), un log de cambios simple (fecha, cambio, razón, aprobador), y reglas de aprobación claras: el TBM Lead debe aprobar cambios de versión, proyecto de Costing principal, o peer group; el TBMA puede ajustar mapeos y configuraciones menores con documentación y validación básica. La regla práctica que cierra la sección: **si una decisión de configuración puede cambiar una diapositiva ejecutiva, merece una línea en el log.**

## Por qué importa en una conversación de cliente

Esta es la sección más técnica y también la de mayor riesgo reputacional si se hace mal: una mala alineación de taxonomía o un peer group mal escogido no produce un error visible — produce números que "se ven raros" y erosionan silenciosamente la confianza del cliente en la herramienta completa. El reparto de responsabilidades (Program Lead / TBMA / Admin / Dueños de Tower) es directamente reutilizable como una diapositiva de RACI en cualquier propuesta de implementación. Y la regla de gobierno ("si puede cambiar una diapositiva ejecutiva, merece una línea en el log") es un argumento de venta de disciplina de proceso fácil de defender frente a un CFO escéptico de la trazabilidad de los números que va a presentar a la junta.

## Documentos fuente

- Purpose and scope — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-purpose-scope.md`
- Architecture and data flow — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-architecture-data-flow.md`
- Configuration responsibilities — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-configuration-responsibilities.md`
- Taxonomy and version alignment — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-taxonomy-version-alignment.md`
- Organizational profile configuration — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-organizational-profile-configuration.md`
- Cost data configuration — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-cost-data-configuration.md`
- Infrastructure data and volumes — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-infrastructure-data-volumes.md`
- Peer group configuration — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-peer-group-configuration.md`
- Data refresh and maintenance — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-data-refresh-maintenance.md`
- Configuration governance — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-configuration-governance.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
