---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Validación de facturas del período actual"
breadcrumb:
  - "Billing"
  - "Ejecutar el ciclo de facturación"
source_path: "boit/billing/run-bill-cycle/validating.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Validación de facturas del período actual

La validación es donde se detectan la mayoría de los problemas de facturación antes de que lleguen a los consumidores.

Validaciones típicas:

1. **Comprobaciones estructurales**
   - Confirme que:
     - Cada consumidor al que se le va a facturar tiene al menos un cargo.
     - Los consumidores nuevos o jubilados son tratados correctamente.
     - Las ofertas marcadas como facturables aparecen realmente.
2. **Comprobaciones de volumen**
   - Compare las unidades del período actual con:
     - Periodos anteriores.
     - Eventos empresariales conocidos, como migraciones, nuevos lanzamientos o jubilaciones.
   - Investigar:
     - Grandes subidas o bajadas.
     - Cambios importantes entre las ofertas.
3. **Comprobación de tarifas**
   - Confirme que:
     - Se aplica la tasa correcta para el período actual.
     - Se aplican tarifas especiales o descuentos cuando así se acuerde.
     - No se utilizan tasas predeterminadas ni provisionales cuando no deben utilizarse.
4. **Razonabilidad de los cargos**
   - Comprueba el total de los cargos:
     - Por consumidor.
     - Al ofrecer o prestar un servicio.
   - Comparar con:
     - Presupuesto o plan.
     - Cálculo de costes para implementaciones basadas en costes.

1. **Conciliación con el cálculo de costes**
   - En caso de devolución de cargo, confirme que:
     - Los cargos totales de facturación se aproximan a la vista de costes de los costes recuperables.
     - Cualquier diferencia entre el coste y los cargos se entiende y documenta como una desviación prevista.

En cuanto a la norma de facturación, algunas validaciones pueden realizarse a nivel de dominio (por ejemplo, nube, servidores, proyectos) en lugar de solo a nivel de oferta. Se aplican los mismos principios.
