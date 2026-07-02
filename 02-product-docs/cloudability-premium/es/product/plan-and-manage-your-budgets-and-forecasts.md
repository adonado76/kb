---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Presupuestos y previsiones"
breadcrumb:
  - "Cloudability Premium"
  - "Plan"
source_path: "product/plan-and-manage-your-budgets-and-forecasts.html"
images:
  - "images/using_the_cost_mceclip0.jpg"
  - "images/using_the_cost_mceclip1.jpg"
  - "images/using_the_cost_mceclip2.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Presupuestos y previsiones

Presupuestos y previsiones le ayuda a comprender y predecir sus gastos en nube mediante:

- Elaboración [de previsiones](bf-forecast.html) basadas en patrones históricos de gasto.
- Utilizar las previsiones para elaborar [presupuestos](bf-budgets.html).
- Supervisar y notificar los gastos relacionados con los presupuestos.

Todas estas herramientas se basan en vistas, lo que le permite separar las Unidades de Negocio individuales y gestionarlas de forma independiente. Si actualmente tiene un plan Pro, sólo podrá utilizar estas funciones a nivel de organización. Consulta [la API de vistas](https://developers.cloudability.com/v1.0/ "(se abre en una pestaña o una ventana nueva)") para obtener más información sobre cómo crear vistas mediante programación.

Algunas de las características de estas herramientas son:

- Soporta múltiples opciones de contabilidad, incluyendo Efectivo (recomendado), Amortizado (útil si su organización compra RIs Parciales/Todo por Adelantado), Ajustado (reflejando cualquier acuerdo de Precios Personalizados que haya calibrado) y Ajustado Amortizado.
- Configure alertas periódicas para recibir notificaciones y los gastos del mes en curso.
- Vistas sencillas para analizar su presupuesto,
- En combinación con el servicio [de detección de anomalías](identify-unusual-spending-patterns-with-anomaly-detection.html).

Utilización de la métrica Coste (Lista) para la elaboración de presupuestos y previsiones

Coste (Lista) le permite presupuestar y prever su gasto en nube utilizando métricas de coste coherentes.

Si el uso de una instancia ha sido cubierto por una reserva todo por adelantado, el Coste (Total) mostrará $0 mientras que el Coste (Lista) mostrará el coste bajo demanda para ese uso en particular. Por otro lado, para las cuotas mensuales recurrentes y las cuotas únicas ocasionales, el Coste (Lista) mostrará 0$, ya que es probable que estos cargos se excluyan de los ejercicios presupuestarios y de previsión. Para los casos puntuales, el Coste (Total) muestra el coste real con gran descuento, mientras que el Coste (Lista) muestra el coste bajo demanda para ese uso concreto.

[Las FAQ](#plan-and-manage-your-budgets-and-forecasts__FAQ) explican cómo Cloudability genera los valores de Coste (Lista). La diferencia entre Coste (Lista) y Coste (Total) o Coste (Ajustado) muestra las ventajas generales de las reservas y los precios personalizados.

![presupuestos y previsiones captura de pantalla](../../../../03-media/cloudability-premium/images/using_the_cost_mceclip0.jpg)

Si no se exponen métricas de costes específicas, utilice Coste (Lista) para proporcionar el reembolso a los consumidores (o unidades de negocio, grupos de cuentas, etc.).

![pantalla de costes](../../../../03-media/cloudability-premium/images/using_the_cost_mceclip1.jpg)

Puedes configurar notificaciones diarias por correo electrónico.

![resumen de gastos en la nube correos electrónicos captura de pantalla](../../../../03-media/cloudability-premium/images/using_the_cost_mceclip2.jpg)

FAQ

**¿Qué dirección  Public Cloud Vendors admite Cost (List)?**

Cost (List) es compatible con AWS y GCP.

¿Por qué el Coste (Lista) muestra a veces un valor inferior al de las demás métricas de costes?

El principal caso de uso de la métrica Coste (Lista) gira en torno a los Presupuestos y las Previsiones. Cloudability reduce a cero los valores de determinadas partidas dependiendo de los tipos de transacción y de los tipos de arrendamiento para ayudar a reducir el ruido en el trabajo de Presupuestos y Previsiones. Las partidas que Cloudability pone a cero incluyen:

- Cuotas iniciales recurrentes de RI
- Cuotas iniciales únicas de RI
- Créditos de precios personalizados

**¿Cuáles son los elementos que Cloudability indica como coste (lista)**?

Cloudability informa de los créditos extraordinarios (ex. Corrección de errores de facturación) tal cual para Coste (Lista). En el caso de GCP, Cloudability pone a cero los créditos correspondientes a los descuentos por uso comprometido. Sin embargo, los créditos por Descuentos por Uso Sostenido se declaran tal cual. Una vez más, se trata del caso de uso principal del Coste (Lista) - Presupuesto y Previsión. Los elementos que se comunican tal cual para Coste (Lista) son los que los consumidores (o unidades de negocio, grupos de cuentas) necesitan contabilizar para los trabajos de Presupuestación y Previsión.

- **[Mes en curso](../product/bf-current-month.html)**
- **[Previsión](../product/bf-forecast.html)**
- **[Presupuestos](../product/bf-budgets.html)**
