---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Ejecutar el cálculo de Billing Essentials"
breadcrumb:
  - "Billing"
  - "Configuración de los elementos esenciales de facturación (implementación)"
source_path: "boit/billing/config-be/running.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Ejecutar el cálculo de Billing Essentials

Una vez establecidas las ofertas, los consumidores, el consumo y las tarifas, el cálculo de Billing Essentials se puede ejecutar en Desarrollo y Preproducción.

Pasos:

1. **Ejecutar modelos de facturación en desarrollo**
   - Ejecute el modelo o modelos de cálculo de facturación principales creados por el componente Facturación - Cargos.
   - Confirme que la ejecución se completa correctamente.
2. **Inspeccionar salidas**
   - Revise la tabla de salida de facturación:
     - Asegúrese de que haya filas para todos los consumidores y ofertas previstos.
     - Compruebe aleatoriamente las unidades, las tarifas y los cargos.
3. **Publicar y probar informes en Desarrollo/Puesta en escena**
   - Abrir facturas e informes detallados de la colección de informes de facturación.
   - Validar:
     - Totales por consumidor y oferta.
     - Casos de uso clave (por ejemplo, una unidad de negocio importante, un servicio de gran envergadura).
4. **Realizar un control de calidad formal en la fase de preparación.**
   - Una vez confirmado el comportamiento inicial, pasa a la fase de preparación y:
     - Vuelva a ejecutar los modelos de facturación con datos más completos.
     - Ejecute informes de control de calidad que destaquen las asignaciones que faltan o las anomalías.

Solo después de que este ciclo sea estable en Staging se debe promover una compilación a Producción.
