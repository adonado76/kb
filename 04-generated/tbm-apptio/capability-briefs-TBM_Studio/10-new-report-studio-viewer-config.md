---
tbm_concept: "IBM Apptio Report Studio (New) — Report Viewer, Saved Views, configuración/migración desde reportes clásicos, y evolución reciente de release notes"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/rn-recent-releases.md
  - kb/02-product-docs/apptio-tbm-studio/en/notes-previous-releases.md
  - kb/02-product-docs/apptio-tbm-studio/en/viewer-report-overview.md
  - kb/02-product-docs/apptio-tbm-studio/en/viewer-export-report-pdf.md
  - kb/02-product-docs/apptio-tbm-studio/en/viewer-email-report.md
  - kb/02-product-docs/apptio-tbm-studio/en/viewer-saved-views.md
  - kb/02-product-docs/apptio-tbm-studio/en/viewer-admin-control-new-report-access.md
  - kb/02-product-docs/apptio-tbm-studio/en/new-configuration-customization.md
  - kb/02-product-docs/apptio-tbm-studio/en/cc-steps-enable-modernized-ootb-nx-reports-in-client-instance.md
  - kb/02-product-docs/apptio-tbm-studio/en/customization-apptio-report-migration-assistant-guide.md
  - kb/02-product-docs/apptio-tbm-studio/en/new-troubleshooting-faqs.md
last_updated: "2026-07-07"
---
# IBM Apptio Report Studio (New) — Report Viewer & Configuration — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

Cierra el recorrido del New Report Studio: cómo el usuario final consume reportes (Report Viewer y Saved Views), cómo un administrador migra reportes OOTB clásicos hacia la experiencia moderna, y qué tan rápido está evolucionando esta interfaz — el historial de release notes revela un ritmo de lanzamiento de funcionalidad mensual, no trimestral.

## Cómo lo resuelve Apptio TBM Studio

**Accessing the Report Viewer** — dos caminos: desde la página de inicio del New Report Studio vía el menú "Take me to" → "Modern IBM Costing", o desde el Classic Report Viewer vía el botón azul "Open New Report Viewer" — confirmando que ambas experiencias coexisten y son intercambiables durante el período de transición.

**Landing Page con dos pestañas separadas** — "Reports" (colecciones disponibles en la experiencia moderna) y "Classic Reports" (reportes creados con la experiencia clásica) — visibles en el mismo lugar, sin forzar al usuario a saber de antemano en qué sistema vive cada reporte.

**Admin Control for New Report Viewer Access** — un interruptor a nivel de proyecto (habilitado por defecto) que un administrador puede desactivar para restringir el acceso de usuarios finales al Report Viewer — útil durante configuración o pruebas de reportes antes de hacerlos visibles.

**Saved Views — el mecanismo de personalización más sofisticado documentado en esta categoría, con cuatro conceptos clave:**
- **Default Report** — la versión original tal como la creó el autor/admin, sin filtros guardados; siempre disponible para volver al punto de partida (icono de casa).
- **Saved View** — una versión personalizada creada por un usuario que captura filtros aplicados, interacciones con visualizaciones, y el estado completo del reporte en el momento de guardar; el título del reporte muestra el nombre de la vista entre paréntesis (ej. "Cost Analysis Report (Finance Department View)").
- **Landing View** — la vista guardada que se abre automáticamente al acceder al reporte (icono de estrella); solo una vista por reporte puede marcarse como landing view por usuario.
- **Diverged View** — ocurre cuando el reporte base se modificó después de crear la vista guardada; un ícono de advertencia señala que la vista puede ya no coincidir completamente con la estructura actual del reporte — un mecanismo de integridad que evita que un usuario confíe silenciosamente en una vista desactualizada.

**Configuration and Customization — el puente entre lo clásico y lo nuevo:**
- **Steps to Enable Modernized OOTB (NX) Reports in Client Instance** — el procedimiento formal para activar, en la instancia de un cliente específico, las versiones NX (modernizadas) de los reportes estándar que antes solo existían en la experiencia clásica.
- **IBM Apptio Report Migration Assistant Guide** — una herramienta dedicada de asistencia a la migración, confirmando que IBM invierte en tooling específico para facilitar la transición Classic → New, no solo documentación.

**El historial de release notes revela evolución mensual activa**, con hitos recientes documentados explícitamente: Heatmaps y Bubble Charts (julio 2026), Theme Engine con temas reutilizables a nivel de proyecto (mayo 2026), descripciones en Custom Formulas (mayo 2026), Admin Control de acceso al Viewer + Button Component + Tab Visibility Rules + eje compartido en Overlay Charts (abril 2026), Show Values y Tree View en tablas + exportación a PDF/Excel (febrero 2026), configuración de "Viewable by" a nivel de reporte y colección + reubicación del panel de configuración (enero 2026), y soporte de localización + componente Group + mejoras de tabla (noviembre 2025).

## Por qué importa en una conversación con el cliente

El ritmo de release mensual documentado explícitamente es un argumento de inversión activa del producto que vale la pena mencionar a cualquier cliente evaluando si migrar del Report Studio clásico al nuevo — no es una funcionalidad estática, sino una plataforma en desarrollo acelerado.

Saved Views (en particular el concepto de Diverged View) es un mecanismo de gobernanza de contenido personalizado que vale la pena explicar proactivamente a cualquier cliente con muchos usuarios de autoservicio — sin este mecanismo, un cambio al reporte base podría invalidar silenciosamente cientos de vistas personalizadas sin que nadie lo note.

El Report Migration Assistant Guide y los pasos formales para habilitar reportes NX son el recurso correcto para cualquier propuesta de proyecto de migración Classic → New — vale la pena confirmar con el cliente en qué versión de plantilla está antes de prometer un cronograma de migración, dado que la habilitación de reportes modernizados es un procedimiento explícito, no automático.

## Documentos fuente

- Recent Releases — `kb/02-product-docs/apptio-tbm-studio/en/rn-recent-releases.md`
- Previous Releases — `kb/02-product-docs/apptio-tbm-studio/en/notes-previous-releases.md`
- Report Viewer Overview — `kb/02-product-docs/apptio-tbm-studio/en/viewer-report-overview.md`
- Export Report to PDF — `kb/02-product-docs/apptio-tbm-studio/en/viewer-export-report-pdf.md`
- Email Report — `kb/02-product-docs/apptio-tbm-studio/en/viewer-email-report.md`
- Saved Views — `kb/02-product-docs/apptio-tbm-studio/en/viewer-saved-views.md`
- Admin Control for New Report Viewer Access — `kb/02-product-docs/apptio-tbm-studio/en/viewer-admin-control-new-report-access.md`
- Configuration and Customization (índice) — `kb/02-product-docs/apptio-tbm-studio/en/new-configuration-customization.md`
- Steps to Enable Modernized OOTB (NX) Reports in Client Instance — `kb/02-product-docs/apptio-tbm-studio/en/cc-steps-enable-modernized-ootb-nx-reports-in-client-instance.md`
- IBM Apptio Report Migration Assistant Guide — `kb/02-product-docs/apptio-tbm-studio/en/customization-apptio-report-migration-assistant-guide.md`
- Troubleshooting & FAQs — `kb/02-product-docs/apptio-tbm-studio/en/new-troubleshooting-faqs.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
