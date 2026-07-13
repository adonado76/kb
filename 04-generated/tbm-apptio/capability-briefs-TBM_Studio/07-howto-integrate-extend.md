---
concept: "How-To: Integrate and Extend (autenticación y operaciones vía API, y extensión de lógica de negocio vía ApptioScript)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/extend-api-integration.md
  - kb/02-product-docs/apptio-tbm-studio/en/integration-how-authenticate-api.md
  - kb/02-product-docs/apptio-tbm-studio/en/integration-how-upload-data-via-api.md
  - kb/02-product-docs/apptio-tbm-studio/en/integration-uploader-service-api.md
  - kb/02-product-docs/apptio-tbm-studio/en/integration-how-download-data-via-api.md
  - kb/02-product-docs/apptio-tbm-studio/en/integration-how-handle-api-errors.md
  - kb/02-product-docs/apptio-tbm-studio/en/integration-quick-reference.md
  - kb/02-product-docs/apptio-tbm-studio/en/extend-scripting.md
  - kb/02-product-docs/apptio-tbm-studio/en/scripting-how-guide-write-apptioscript-formulas.md
  - kb/02-product-docs/apptio-tbm-studio/en/scripting-how-guide-use-common-script-patterns.md
last_updated: "2026-07-07"
---
# How-To: Integrate and Extend — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

Para el rol de Developer ya perfilado en Learning Paths, este capítulo es su manual operativo: cómo automatizar el flujo de datos hacia/desde TBM Studio vía API, y cómo extender la lógica de negocio del producto vía su lenguaje de scripting propio, ApptioScript.

## Cómo lo resuelve Apptio TBM Studio

### API Integration — seis guías cubriendo el ciclo completo

**Authenticate with the API** — obtener un token de autenticación, requerido antes de cualquier operación de carga o descarga.

**Upload Data via API** — cargar archivos programáticamente, para automatizar cargas mensuales, integrar con pipelines ETL, o cargar desde sistemas donde no se puede instalar un agente DataLink.

**Uploader Service API** — un servicio dedicado específicamente al patrón de carga (complementario al API general).

**Download Data via API** — extraer datos programáticamente para análisis externo, alimentar data warehouses, o integrar con herramientas de BI.

**Handle API Errors** — manejo robusto de errores y lógica de reintento para integraciones de producción, documentado con el formato exacto de respuesta de error (JSON con campo `message` describiendo el problema — ej. `"Poorly formatted date string..."`) y los códigos de retorno del API.

**Quick Reference** — referencia rápida consolidada de los endpoints y parámetros más usados.

### Scripting — ApptioScript, el lenguaje de extensión propio del producto

**Write ApptioScript Formulas** — fundamentos del lenguaje: corre en **dos contextos principales** — adjunto a tablas editables (respondiendo a cambios de celda, adición de filas, o carga de datos) y adjunto a botones (ejecutando al hacer clic el usuario). Entender esta distinción de contexto es prerrequisito antes de escribir cualquier script.

**Use Common Script Patterns** — un catálogo de **ocho patrones probados** para escenarios de negocio comunes, cada uno con el caso de uso, el código completo, y notas de implementación — un acelerador directo que evita reinventar lógica ya resuelta.

## Por qué importa en una conversación con el cliente

La distinción entre los tres mecanismos de integración de datos (API, DataLink, Published Tables — ya vistos en la categoría Work with Data) más el criterio de "cuándo usar cada uno" ya anticipado en Learning Paths para Developers es la pregunta de discovery técnico correcta antes de diseñar cualquier arquitectura de integración: DataLink para conexiones recurrentes automatizadas con agente instalable, API para integración programática flexible o sistemas donde no se puede instalar un agente, Published Tables para consumo por sistemas externos de BI.

Los ocho patrones de ApptioScript son un acelerador de estimación de esfuerzo real: antes de cotizar tiempo de desarrollo de una lógica personalizada, vale la pena confirmar si el escenario del cliente ya coincide con uno de los ocho patrones documentados, en lugar de asumir que se necesita desarrollo desde cero.

El formato exacto de manejo de errores del API (JSON con mensaje descriptivo, códigos de retorno documentados) es información directamente reutilizable para cualquier especificación técnica de integración que el equipo de desarrollo del cliente necesite antes de construir su lado de la integración.

## Documentos fuente

- API Integration (índice) — `kb/02-product-docs/apptio-tbm-studio/en/extend-api-integration.md`
- How-To: Authenticate with the API — `kb/02-product-docs/apptio-tbm-studio/en/integration-how-authenticate-api.md`
- How-To: Upload Data via API — `kb/02-product-docs/apptio-tbm-studio/en/integration-how-upload-data-via-api.md`
- Uploader Service API — `kb/02-product-docs/apptio-tbm-studio/en/integration-uploader-service-api.md`
- How-To: Download Data via API — `kb/02-product-docs/apptio-tbm-studio/en/integration-how-download-data-via-api.md`
- How-To: Handle API Errors — `kb/02-product-docs/apptio-tbm-studio/en/integration-how-handle-api-errors.md`
- Quick Reference — `kb/02-product-docs/apptio-tbm-studio/en/integration-quick-reference.md`
- Scripting (índice) — `kb/02-product-docs/apptio-tbm-studio/en/extend-scripting.md`
- How-To Guide: Write ApptioScript Formulas — `kb/02-product-docs/apptio-tbm-studio/en/scripting-how-guide-write-apptioscript-formulas.md`
- How-To Guide: Use Common Script Patterns — `kb/02-product-docs/apptio-tbm-studio/en/scripting-how-guide-use-common-script-patterns.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
