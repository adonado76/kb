---
concept: "Setting up Time Zone Preferences (zona horaria de la organización, resúmenes de gasto por correo, y métrica de costo por defecto por módulo)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/setup-setting-up-time-zone-preferences.md
last_updated: "2026-07-13"
---
# Setup — Time Zone Preferences — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Aunque el nombre sugiere solo configurar una zona horaria, esta página de Manage Profile agrupa tres configuraciones distintas que determinan cómo cada usuario (o toda la organización) ve e interpreta el gasto: la zona horaria de referencia para todos los cálculos de Cloudability, la cadencia y contenido de los correos de resumen de gasto, y la métrica de costo por defecto que usa cada módulo de la plataforma.

## Cómo lo resuelve IBM Cloudability Standard

**Configuración de zona horaria**: desde el ícono de Usuario → Manage Profile → pestaña PREFERENCES → sección View and Timezone, donde se define tanto la View por defecto como la zona horaria — esta última se convierte en la zona horaria de referencia de Cloudability para ese usuario.

**Suscripción a correos de resumen de gasto (Cloud Spend Summary Emails), con control granular:**
- **Frecuencia**: Daily, Weekly, Monthly, Quarterly, u Off (para no recibir el correo).
- **Cost Metric for Mail**: métrica de costo usada en el correo — relevante para clientes con cuentas vinculadas en un Consolidated Billing family de AWS, donde el reporte con Unblended cost suele ser más apropiado si el cliente usa Reserved Instances (la facturación detallada expone tanto tasa blended como unblended).
- **Nota técnica documentada**: para usar costos amortizados en el correo, la View por defecto del usuario no puede incluir un filtro basado en tags — si se selecciona Cost (Amortized) bajo esa condición, las estimaciones reflejarán Cost (Total) en su lugar.
- **Budget for Mail**: presupuesto de referencia mostrado en el correo.

**Métricas explicadas en el correo diario**: Month-to-Date Spend (comparado con el mismo día del mes anterior), Est. Monthly Spend (proyección basada en un promedio móvil de N días definidos por el usuario), Yesterday's Spend, desglose de Cost por cuenta/servicio de mayor gasto del mes, Month-to-Date Usage Hours, Yesterday's Usage Hours, Yesterday's Running Instance Count, y las 5 instancias más recientes iniciadas en la cuenta.

**Comportamiento documentado ante datos retrasados del proveedor**: si la data completa del día anterior (UTC) no está disponible, el correo diario se entrega alrededor de las 10am hora Pacífico para permitir que la data se reciba y procese completamente — esto evita que "Yesterday's Estimated Spend" se reporte por debajo de lo real por datos incompletos del proveedor en ese momento.

**Choice of delivery para organizaciones con retraso consistente de datos** (configuración custom para cuentas Enterprise, habilitada por el equipo de Cloudability Success): permite elegir entre recibir el correo con la data más actualizada disponible (comportamiento por defecto) o esperar hasta tener "el último día completo" de datos — pensado para evitar que usuarios reciban repetidamente el correo de "Data Delayed" cuando su pipeline de datos tiene latencia estructural.

**Configuración de métrica de costo por defecto a nivel de organización** (Manage Profile → Organization Settings, solo administradores): cada módulo de Cloudability (TrueCost Explorer, Rightsizing, etc.) soporta un set específico de métricas de costo (Cost Total, Cost List, Cost Amortized, etc.), con Cost (Total) como default. Un administrador puede cambiar el default por módulo desde esta pantalla, y el cambio aplica a todos los usuarios de la organización al guardar.

## Por qué importa en una conversación con el cliente

**RETOS QUE RESUELVE:** en organizaciones con equipos distribuidos globalmente, fijar la zona horaria correctamente evita ambigüedad sobre "qué día" corresponde un pico de gasto en los reportes — un detalle menor en apariencia pero que genera confusión recurrente en discusiones de anomaly detection o troubleshooting de facturación. La opción de elegir entrega retrasada resuelve la fatiga de alertas de "Data Delayed" en clientes con pipelines de datos estructuralmente lentos.

**VALOR DIFERENCIAL:** la advertencia sobre Cost (Amortized) y filtros basados en tags en la View por defecto es un detalle técnico fácil de pasar por alto que puede hacer que un cliente reciba métricas de amortización silenciosamente sustituidas por Cost (Total) sin darse cuenta — vale la pena validar esta configuración explícitamente en cualquier cliente que use Reserved Instances o Savings Plans y dependa de reporting amortizado. La configuración de métrica de costo por defecto por módulo, aplicada a nivel de organización completa, es una decisión de gobernanza que conviene decidir deliberadamente en el discovery en vez de dejar el default de Cost (Total) sin revisar.

## Documentos fuente

- Setting up Time Zone Preferences — `kb/02-product-docs/apptio-cloudability-standard/en/setup-setting-up-time-zone-preferences.md`
- Fuente oficial: https://www.ibm.com/docs/en/cloudability-commercial/cloudability-standard/saas?topic=setup-setting-up-time-zone-preferences

*Nota: versión en español/portugués se genera en una siguiente pasada.*
