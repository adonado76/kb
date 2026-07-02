---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Vista de costes y tarifas unitarias en la nube"
breadcrumb:
  - "Billing"
  - "Patrones de diseño y casos de uso"
source_path: "boit/billing/design-uc/uc-cloud.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Vista de costes y tarifas unitarias en la nube

Nota: **Se aplica únicamente a la norma de facturación.**

**Problema**

Necesita una visión repetible de los costes y cargos de la nube por proveedor, cuenta, servicio y consumidor, con visibilidad de la tarifa unitaria.

**Entradas**

- Datos de facturación/uso del proveedor de servicios en la nube
- Tablas de asignación de etiquetas y cuentas (a servicios y consumidores)
- Definiciones de unidades específicas de la nube
- Tarifas o reglas de precios para servicios en la nube

**Pasos**

1. Confirme **que los datos de uso de la nube** para el período se han cargado y están completos.
2. Validar **asignaciones de etiquetas** :
   - Prueba algunas cuentas y asegúrate de que las etiquetas se asignan al servicio y al consumidor esperados.
3. Ejecute los **modelos de dominio en la nube** en Billing Standard:
   - Agregar volúmenes en unidades estándar.
   - Añada el coste y el precio cuando corresponda.
4. Abre el **informe de facturación en la nube** :
   - Filtrar por proveedor y periodo.
   - Revisar los cargos por servicio y consumidor.
5. Abre el **informe de tarifas unitarias de Cloud** :
   - Para cada combinación de proveedor y servicio:
   - Unidades, coste por unidad, precio por unidad.
   - Identificar valores atípicos (tarifas unitarias altas o bajas).
6. Utilice filtros para profundizar en:
   - Una cuenta o suscripción.
   - Una agrupación de etiquetas (por ejemplo, aplicación, entorno).

**Informes clave**

- Facturación en la nube por proveedor/cuenta/servicio
- Tarifas unitarias de la nube por proveedor/servicio/entorno
- Informe de excepciones en la nube para usos sin etiquetar o mal etiquetados
