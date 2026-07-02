---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Preguntas frecuentes sobre el inventario de recursos"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Inventario de recursos"
source_path: "product/resource-inventory-faqs.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Preguntas frecuentes sobre el inventario de recursos

## ¿Por qué no puedo seleccionar los últimos tres días en el selector de intervalo de fechas del inventario de recursos?

En el Inventario de recursos, no permitimos seleccionar los últimos tres días en el intervalo de fechas, ya que algunas métricas pueden tardar hasta 72 horas en reflejarse en el informe de inventario y no se garantiza la integridad de los datos.

Verás un mensaje en el selector de fechas que muestra el intervalo de fechas disponible, junto con un aviso de que se excluyen los últimos tres días.

## ¿Por qué cambian con el tiempo las cifras de mi informe guardado?

Puede haber varias razones por las que las cifras sean diferentes:

- Si ejecutas un informe guardado cuya fecha se remonta a más de 90 días atrás, la fecha se restablecerá automáticamente a 7 días. Esto es para garantizar que el informe se cargue correctamente. En este caso, también aparecerá un mensaje de advertencia parpadeante.
- Si en tu informe tenías activada la opción «Fecha móvil» y el criterio era «últimos 90 días», las cifras pueden variar cada día.

## ¿Por qué algunos recursos aparecen como «No disponible»?

El Inventario de recursos puede mostrar el estado **«No disponible»** en los siguientes casos:

- Permisos faltantes: si no se ha configurado la autenticación avanzada, Resource Inventory obtendrá los detalles del recurso a partir de los datos de costes, que no incluirán todos los metadatos, incluido el estado del recurso.
- Recursos de corta duración: el inventario de recursos recopila datos a intervalos definidos. Si un recurso se crea y se elimina entre dos ciclos de recopilación, es posible que no se registren los detalles sobre su estado y su utilización, por lo que el estado no aparecerá.
- Instantáneas: no hay información sobre el estado disponible para los recursos de instantáneas.
- Recursos de transferencia de datos: algunos recursos (por ejemplo, la transferencia de datos a través de una puerta de enlace NAT) no tienen un estado asociado y aparecerán como «No disponible».
- Azure Recursos cancelados: en Azure, una vez que se cancela un recurso, aunque no sea un recurso de corta duración, la información sobre su estado deja de estar disponible y se muestra como «No disponible».

**Tema principal:** [Inventario de recursos](../product/resource-inventory.html)
