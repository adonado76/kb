---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Investigar un aumento repentino de la tasa unitaria"
breadcrumb:
  - "Billing"
  - "Patrones de diseño y casos de uso"
source_path: "boit/billing/design-uc/uc-investgate.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Investigar un aumento repentino de la tasa unitaria

**Problema**

Una parte interesada informa de que la tarifa de un servicio concreto «se ha disparado» este mes. Tienes que explicar por qué.

**Entradas**

- Datos históricos sobre las tarifas unitarias del servicio
- Cálculo de los costes de ese servicio (si está disponible)
- Volúmenes de consumo a lo largo del tiempo
- Historial de la tabla de tarifas

**Pasos**

1. Abra el **informe de análisis de tarifas unitarias** para el servicio:
   - Filtrar por servicio, período actual y al menos tres períodos anteriores.
2. Compare:
   - Unidades por período
   - Cargos por período
   - Tarifa unitaria por período
3. Determinar qué controlador ha cambiado:
   - Las unidades se movieron significativamente con un costo estable: probablemente impulsadas por el volumen.
   - Cambio en el coste por unidad: probable asignación o cambio en el factor determinante del coste en el cálculo de costes.
   - Cambio explícito de tarifa: consulte la tabla de tarifas.
4. Comprueba la **tabla de tarifas** :
   - Confirme si se ha configurado un cambio de tarifa para el período.
   - Si es así, comprueba que el cambio fue aprobado y documentado.
5. Si el coste está disponible en Costing:
   - Compare **el coste por unidad** con **el precio por unidad** entre distintos periodos.
6. Resuma los resultados en términos sencillos:
   - «La tarifa unitaria aumentó porque el volumen se redujo en un X % sobre una base de costes mayoritariamente fijos»
   - «La tarifa unitaria aumentó porque la tarifa se modificó de A a B por unidad»
   - «La tarifa unitaria ha cambiado porque la asignación de costes subyacente ha cambiado en Costing»

**Informes clave**

- Informe sobre la evolución de la tarifa unitaria del servicio
- Historial de tarifas (vista de tabla de tarifas)
- Vista de comparación de coste frente a precio (si está configurada)
