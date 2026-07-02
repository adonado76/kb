---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Configuración de alertas de compromiso"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Guía para la gestión de compromisos"
source_path: "product/setting_commitment_alerts.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configuración de alertas de compromiso

## Finalidad

Las alertas de compromiso reducen la supervisión manual al notificarle cuándo se acerca el vencimiento de los compromisos o cuándo la utilización cae por debajo de un umbral que usted define. Este documento explica cómo configurar las alertas, interpretarlas y actuar en consecuencia, además de los matices específicos de cada proveedor.

## Alerta Básica

Admitimos dos tipos de alertas de compromiso:

**Vencimiento** - Notifica a los usuarios los próximos compromisos que vencen. Según la frecuencia de vencimiento elegida, Cloudability determinará si un compromiso vence en el plazo especificado.

**Umbral de utilización** : notifica a los usuarios los compromisos que presentan una utilización inferior a un umbral especificado. En el "período de retrospectiva" y el "umbral" elegidos, Cloudability ejecuta el algoritmo de utilización de la cartera de compromisos para determinar si alguno de los compromisos existentes cumple los criterios especificados.

Para configurar las alertas, vaya a la cartera de compromisos y seleccione el botón de alertas en la esquina superior derecha. Las alertas se facilitan mediante una notificación por correo electrónico. Tenga en cuenta que existe un informe por correo electrónico personalizado para cada uno de los dos tipos de alerta. Las alertas evalúan toda su cartera de tipos admitidos con credenciales válidas; no están segmentadas por la ficha del proveedor o el tipo seleccionado al abrir el panel. (Por ejemplo, si se configura una alerta en la pestaña « AWS », dicha alerta se aplicará tanto a Azure como a GCP ).

La notificación por correo electrónico se producirá según la frecuencia de envío especificada y la hora seleccionada. Tenga en cuenta que la hora está en UTC. Tenga en cuenta que para ambos tipos de alerta, puede decidir enviar la alerta con la frecuencia especificada, incluso si ningún compromiso cumple los criterios especificados.

## Vendedor Nuance

- Azure Los Planes de Ahorro no admiten una retrospectiva de 90 días. En su lugar, la alerta se establece por defecto en el periodo más largo disponible, 30 días.
- GCP no ofrece el nivel de detalle necesario para determinar la utilización de un compromiso concreto. En su lugar, proporcionamos alertas de umbral de utilización en el grupo de compromiso. Para obtener más información sobre los grupos de compromiso de « GCP », consulta la documentación de la cartera de compromisos.

## Configuración de alertas paso a paso

1. Navegue hasta Optimizar → Cartera de compromisos.
2. Haz clic en Alertas (arriba a la derecha).
3. En Alertas de Compromiso:

   **Caducidad**
   1. Conmutar ON/OFF
   2. Establecer plazo de caducidad (por ejemplo, 7, 14, 30, 60, 90 días)
   3. (Opcional) Marque Enviar aunque no expire ninguna

   **Umbral de utilización**
   1. Conmutar ON/OFF
   2. Establecer periodo de retrospección (N días)
   3. (Opcional) Marque Enviar aunque no haya ninguno por debajo del umbral

   **Frecuencia**
   1. Elija con qué frecuencia evaluar y a qué hora enviar el correo electrónico
4. Haga clic en Enviar para suscribirse.
5. Para desactivarla, abra el panel y haga clic en Anular suscripción para la alerta correspondiente.

## Interpretar las alertas por correo electrónico

*Correo electrónico de caducidad*

**Lo que verá:**

Compromiso(s) que vencen dentro de la ventana seleccionada, junto con identificadores y detalles de calendario.

**Acciones recomendadas:**

- Validar la cobertura y la utilización en la cartera de compromisos.
- Comprender la consideración de la carga de trabajo actual y futura para evaluar la renovación.
- Inmediatamente después de la expiración, evalúe sus recomendaciones para determinar si procede adquirir nuevos compromisos.

*Umbral de utilización Correo electrónico*

**Lo que verá:**

Compromisos por debajo del umbral de utilización, junto con los detalles de su utilización evaluada.

**Acciones recomendadas:**

- Investigar el alcance (zonal frente a regional), las configuraciones de reparto y los cambios en la carga de trabajo
- Considerar intercambios/convertibles o reducir tamaños/plazos de compra futuros
- Reevaluar la estrategia de compromiso para comprender por qué se ha producido una infrautilización frecuente y cómo evitarla en el futuro.

## Mejores prácticas

- **Selección del umbral** : Empezar en el 90-95% y afinar según el umbral de rentabilidad del tipo y la volatilidad histórica.
- **Ventana de retrospectiva** : 7-14 días equilibra el ruido frente a la capacidad de respuesta. Utilizar entre 30 y 90 días para un uso más estable.
- **Operar a la señal, no al ruido** : Investigar la baja utilización durante un periodo de tiempo prolongado. Las caídas de un solo día pueden reflejar cambios de uso benignos o estacionales que aún así puede merecer la pena cubrir con un compromiso.
- **Empareje con cuadros de mando** : Realice un seguimiento de la cobertura, la utilización, la tasa de ahorro y el coste restante para contextualizar los picos de alerta.

## Puntos de partida clave

- Configure las alertas de vencimiento y umbral de utilización en Cartera de compromisos → Alertas.
- Establezca una retrospectiva y un umbral alineados con el umbral de rentabilidad y la volatilidad; elija la frecuencia y la hora de envío.
- Utilice los correos electrónicos como señal para investigar.
- Ten en cuenta los límites de retroactividad de Azure y las evaluaciones a nivel de grupo de GCP.

**Tema principal:** [Guía para la gestión de compromisos](../product/guide_to_commitment_management.html)
