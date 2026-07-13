---
concept: "Data Reprocess (refresh retrospectivo self-service de data histórica tras cambios de taxonomía, con límite de Month-units)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/setup-data-reprocess.md
last_updated: "2026-07-13"
---
# Setup — Data Reprocess — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Cuando un cliente modifica su estrategia de negocio — nuevas cuentas, cambio de estrategia de tagging, reestructuración de Business Mappings o Account Groups — esos cambios por defecto solo aplican hacia adelante. Data Reprocess es el mecanismo self-service para aplicar esos cambios retrospectivamente sobre la data histórica, sin depender de que Soporte o Customer Success lo ejecuten manualmente.

## Cómo lo resuelve IBM Cloudability Standard

**Self-service, restringido a usuarios Admin, y con opt-in explícito.** La funcionalidad no viene habilitada por defecto — hay que solicitar su activación a Soporte o al Customer Success Manager. Una vez habilitada, se accede desde Organize → Data Reprocess.

**Modelo de "Month-units" como unidad de consumo del feature**: cada mes de data reprocesada consume un Month-unit. Un solo request de 12 meses consume 12 Month-units; dos requests de 3 meses cada uno consumen 6 Month-units en total. Los totales y remanentes de Month-units se muestran siempre en pantalla.

**Límites documentados:**
- **12 Month-units disponibles por mes** de asignación.
- **Lookback máximo de 12 meses** por solicitud de reprocess.
- Si la selección excede los Month-units remanentes, se muestra un error antes de poder enviar el request.
- **Dos requests no pueden correr simultáneamente para el mismo período o mes** (se permite correr dos requests en paralelo si no hay traslape en los meses seleccionados).
- Si un job falla para un mes específico, ese mes **no consume Month-units** y se puede volver a enviar solo para ese mes.
- **Una vez enviado, un request de reprocess no se puede cancelar.**
- La data del mes en curso **ya se reprocesa automáticamente todos los días** (disponible en 24 horas) — no requiere un request manual.

**Flujo de solicitud (self-service para usuarios de solo Cloudability):** en la pestaña New Request se define Job Name, Start Date, End Date y Reason, y se envía con el botón Start Reprocess. La pestaña Job Status muestra el historial de requests, permite expandir por Job ID para ver el estado de cada mes individualmente, y refrescar el estado.

**Flujo extendido para clientes que además usan Costing & Planning**: el proceso agrega pasos previos de selección — qué Tags & Labels, qué Account Groups, y qué Business Mappings específicamente exportar/llevar a Costing & Planning o TBM Studio (nota importante: esta selección solo afecta lo que se exporta a Costing & Planning — dentro de Cloudability mismo, **todas** las dimensiones de negocio se reprocesan sin importar esta selección). Business Mappings que contengan columnas de Resource ID y/o Date en su definición **no son soportadas** para exportar a Costing & Planning o TBM Studio. Todas las Business Metrics configuradas fluyen automáticamente a Costing & Planning sin necesidad de selección. Esta ruta extendida está actualmente **en pausa (on hold)** para clientes con la oferta de Costing & Planning junto a Cloudability o CDI, mientras IBM mejora la experiencia — los clientes que ya tenían acceso lo conservan.

**Cuándo escalar a TAM/CSM/Soporte en vez de usar el self-service**: si el job falla más de una vez, si ya se agotó el límite mensual de Month-units y existe una necesidad urgente de negocio, o para cualquier feedback/issue adicional.

## Por qué importa en una conversación con el cliente

**RETOS QUE RESUELVE:** es el argumento de integridad histórica a mencionar proactivamente en cualquier conversación donde el cliente anticipe una reorganización de negocio (fusión, reestructuración de unidades, cambio de estrategia de tagging) — sin este mecanismo, el histórico de reportes quedaría permanentemente desalineado con la nueva taxonomía, generando discrepancias que socavan la confianza en los números.

**VALOR DIFERENCIAL:** el modelo de Month-units (12 por mes, lookback máximo de 12 meses) es una restricción de capacidad concreta que conviene dimensionar durante cualquier discovery de reestructuración de taxonomía — un cliente planeando una migración grande de Business Mappings puede agotar su cupo mensual si no planifica los requests en batches. El hecho de que el reprocess no se pueda cancelar una vez enviado es un detalle operativo que vale la pena remarcar antes de que el cliente presione "Start" sobre un rango de fechas incorrecto. Para clientes con Costing & Planning, la pausa actual del flujo extendido es un dato de vigencia de producto importante de confirmar antes de prometer esa integración específica.

## Documentos fuente

- Data Reprocess — `kb/02-product-docs/apptio-cloudability-standard/en/setup-data-reprocess.md`
- Fuente oficial: https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=setup-data-reprocess

*Nota: versión en español/portugués se genera en una siguiente pasada.*
