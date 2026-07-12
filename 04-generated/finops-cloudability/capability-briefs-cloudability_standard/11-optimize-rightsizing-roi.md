---
tbm_concept: "Optimize — Rightsizing ROI (cierre del ciclo de oportunidad a ejecución vía tickets manuales o políticas automatizadas, con integración Jira/ServiceNow bidireccional)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/optimize-rightsizing-roi.md
last_updated: "2026-07-09"
---
# Optimize — Rightsizing ROI — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Una recomendación de Rightsizing que nadie ejecuta no genera ahorro real — el problema clásico de cualquier motor de recomendaciones es el vacío entre "identificar la oportunidad" y "confirmar que se actuó sobre ella y cuánto se ahorró en realidad". Rightsizing ROI es el mecanismo que cierra ese ciclo, de oportunidad a finalización, con reporte del impacto real logrado.

## Cómo lo resuelve IBM Cloudability Standard

**Tres opciones de sistema de ticket, cada una con su propio mecanismo de sincronización:**
- **Jira Cloud** — vía la extensión Jira Service Management, creando issues y requests con **sincronización bidireccional** de estado.
- **ServiceNow** — vía un script generado por Cloudability para incidents y requests, también con sincronización bidireccional.
- **Tracking standalone** — funcionalidad de seguimiento de tickets contenida dentro del propio Cloudability, sin depender de un sistema externo.

**Dos vías de creación de tickets.** **Manual**: desde cualquier página de recomendaciones de Rightsizing, seleccionar el menú de más opciones de una recomendación específica y elegir el sistema de ticket deseado — crea y vincula el ticket con los detalles relevantes ya incluidos. **Automatizada vía políticas**: una forma escalable de generar tickets contra las oportunidades que surge el motor de Rightsizing, ejecutándose en intervalos programados y creando tickets hasta un número máximo de resultados, para que los equipos se enfoquen solo en las oportunidades más grandes en lugar de procesar manualmente cada recomendación individual.

**Configuración de política, con siete criterios documentados**: nombre, **umbral de ahorro a 30 días** (el mínimo de costo ahorrado requerido para generar un ticket), servicio de nube a incluir, base de costo para el cálculo del umbral, qué acciones de rightsizing incluir, número máximo de resultados por ejecución programada, la View que filtra qué recursos considera, y el tipo de integración de ticket a usar (con selección de proyecto específico para Jira).

## Por qué importa en una conversación con el cliente

Rightsizing ROI es el argumento correcto para cerrar la brecha entre "Cloudability identifica oportunidades" y "la organización realmente captura ese ahorro" — sin este mecanismo, las recomendaciones de Rightsizing corren el riesgo de quedar como una lista que nadie revisa sistemáticamente.

La creación automatizada de tickets vía políticas, con umbral de ahorro configurable, es un argumento de escala operativa importante para cualquier cliente con un volumen alto de recomendaciones — permite dirigir el esfuerzo humano de revisión solo hacia las oportunidades de mayor impacto, en lugar de procesar cada recomendación manualmente.

La sincronización bidireccional con Jira y ServiceNow (el estado del ticket se mantiene alineado en ambos sistemas) es un detalle técnico que vale la pena confirmar en discovery con cualquier cliente que ya use uno de estos sistemas como su flujo de trabajo de ITSM/desarrollo estándar — evita que el equipo tenga que revisar dos sistemas por separado para saber el estado real de una acción de optimización.

## Documentos fuente

- Rightsizing ROI — `kb/02-product-docs/apptio-cloudability-standard/en/optimize-rightsizing-roi.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
