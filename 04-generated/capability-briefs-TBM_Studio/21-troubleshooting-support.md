---
tbm_concept: "Troubleshooting and Support — diagnóstico de problemas comunes por estudio, recomendaciones de configuración/agrupación numérica/recursos no usados, y canales de soporte"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/support-introduction.md
  - kb/02-product-docs/apptio-tbm-studio/en/solutions-data-studio-issues.md
  - kb/02-product-docs/apptio-tbm-studio/en/solutions-model-studio-issues.md
  - kb/02-product-docs/apptio-tbm-studio/en/solutions-report-studio-issues.md
  - kb/02-product-docs/apptio-tbm-studio/en/solutions-build-deployment-issues.md
  - kb/02-product-docs/apptio-tbm-studio/en/explained-configuration-recommendations.md
  - kb/02-product-docs/apptio-tbm-studio/en/explained-numeric-grouping-recommendations.md
  - kb/02-product-docs/apptio-tbm-studio/en/explained-unused-resource-recommendations.md
  - kb/02-product-docs/apptio-tbm-studio/en/support-diagnostic-tools.md
  - kb/02-product-docs/apptio-tbm-studio/en/support-getting-help.md
last_updated: "2026-07-07"
---
# Troubleshooting and Support — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

El capítulo de cierre del producto: diagnóstico organizado por estudio (Data/Model/Report/Build), un motor de recomendaciones proactivas para higiene de configuración, y los canales formales de soporte — cerrando el círculo completo del ciclo de vida de TBM Studio documentado en este proyecto.

## Cómo lo resuelve Apptio TBM Studio

**Common Issues & Solutions, organizado por estudio — el mismo patrón de segmentación por área ya visto en Costing Standard y Billing:**

- **Data Studio Issues** — "Data Won't Load or Upload Fails" (validación falla, tabla muestra cero filas, o la carga cuelga/expira) y "Transform Table Not Calculating" (datos obsoletos, objetos del modelo posteriores con valores incorrectos, badge de error).
- **Model Studio Issues** — "Allocation Not Working as Expected" (costo no fluye a los destinos esperados, costo sin asignar remanente, valores cero en objetos destino) y "Model Calculation Taking Too Long" (builds de horas, Staging frecuentemente desactualizado, performance de reporte lenta para el usuario final).
- **Report Studio Issues** — "Report Not Loading or Loading Slowly" (reporte en blanco o que nunca termina de cargar, timeout del navegador, o carga que toma varios minutos).
- **Build and Deployment Issues** — "Build Stuck in Pending or Calculating State" (primero revisar la Calculation Queue — múltiples check-ins pueden encolar builds, y cambios de configuración grandes pueden requerir cálculo extenso) y "Cannot Promote to Production" (verificar que el cálculo de Stage esté completo, revisar estado de bloqueo de ambiente, revisar errores bloqueantes en el panel de Errores).

**Error Messages Explained — un motor de recomendaciones proactivo, no solo reactivo.** Tres categorías documentadas con mecanismo de resolución guiado:
- **Configuration Recommendations** — sugerencias generales de configuración.
- **Numeric Grouping Recommendations** — con una ruta de resolución explícita: cuando la agrupación involucra campos calculados (montos, porcentajes, valores decimales), la opción recomendada es remover esos campos de la agrupación. Un mecanismo de validación posterior confirma si el fix funcionó: si la recomendación reaparece después de guardar y hacer check-in, la configuración no satisfizo el requisito — hay que verificar que se guardaron todos los cambios y que se removieron **todas** las dimensiones numéricas de la operación de agrupación.
- **Unused Resource Recommendations** — identifica proactivamente **métricas calculadas no usadas** en otras métricas ni reportes, y **asignaciones no usadas (con flujo de costo cero)**, que pueden indicar errores de configuración o lógica obsoleta — ambas navegables desde TBM Studio → Recommendations, con un flujo guiado ("Troubleshoot All Identified Problems") para revisar y eliminar. Existe también una categoría de **Unused Reports (BETA)**, en desarrollo activo.

**Diagnostic Tools y Getting Help** — herramientas de diagnóstico técnico (probablemente incluyendo la Calculation Queue ya mencionada, y otras utilidades de introspección) y los canales formales de escalamiento cuando el troubleshooting autónomo no resuelve el problema.

## Por qué importa en una conversación con el cliente

El motor de Unused Resource Recommendations es un argumento de valor de mantenimiento proactivo poco común en herramientas de modelado: en lugar de que un modelo acumule métricas y asignaciones obsoletas indefinidamente (aumentando complejidad y tiempo de build sin que nadie lo note), el propio producto las identifica y ofrece un flujo guiado para limpiarlas — vale la pena mencionarlo en cualquier conversación sobre costo total de propiedad a largo plazo de un modelo TBM.

El mecanismo de validación de Numeric Grouping Recommendations (que confirma explícitamente si el fix aplicado realmente resolvió el problema, en vez de asumirlo) es un buen ejemplo de diseño de producto centrado en confiabilidad — vale la pena destacarlo para clientes preocupados por la curva de aprendizaje de troubleshooting de un producto de modelado complejo.

La organización de problemas por estudio (Data/Model/Report/Build) es directamente reutilizable como estructura de un runbook de soporte de primer nivel para el equipo operativo del cliente — permite dirigir rápidamente un ticket de soporte al área correcta según el síntoma reportado, antes de escalar a soporte formal de IBM.

## Documentos fuente

- Introduction — `kb/02-product-docs/apptio-tbm-studio/en/support-introduction.md`
- Data Studio Issues — `kb/02-product-docs/apptio-tbm-studio/en/solutions-data-studio-issues.md`
- Model Studio Issues — `kb/02-product-docs/apptio-tbm-studio/en/solutions-model-studio-issues.md`
- Report Studio Issues — `kb/02-product-docs/apptio-tbm-studio/en/solutions-report-studio-issues.md`
- Build and Deployment Issues — `kb/02-product-docs/apptio-tbm-studio/en/solutions-build-deployment-issues.md`
- Configuration Recommendations — `kb/02-product-docs/apptio-tbm-studio/en/explained-configuration-recommendations.md`
- Numeric Grouping Recommendations — `kb/02-product-docs/apptio-tbm-studio/en/explained-numeric-grouping-recommendations.md`
- Unused Resource Recommendations — `kb/02-product-docs/apptio-tbm-studio/en/explained-unused-resource-recommendations.md`
- Diagnostic Tools — `kb/02-product-docs/apptio-tbm-studio/en/support-diagnostic-tools.md`
- Getting Help — `kb/02-product-docs/apptio-tbm-studio/en/support-getting-help.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
