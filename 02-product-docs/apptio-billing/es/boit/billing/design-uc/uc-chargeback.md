---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Contracargo con exportación de diario"
breadcrumb:
  - "Billing"
  - "Patrones de diseño y casos de uso"
source_path: "boit/billing/design-uc/uc-chargeback.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Contracargo con exportación de diario

**Problema**

Desea que las salidas de facturación impulsen los asientos internos de ingresos y gastos en el libro mayor.

**Entradas**

- Todas las aportaciones proceden de 15.1 ( PxQ showback)
- Asignación de consumidores a segmentos financieros (centro de costes, código de empresa, etc.)
- Asignación de servicios a cuentas financieras
- Formato de diario y normas de contabilización acordados con Finanzas

**Pasos**

1. Valide **las facturas del período actual** utilizando la receta « PxQ » ( 15.1 ).
2. Asegúrese de que **las tablas de mapeo** estén completas:
   - Consumidores → centros de coste / segmentos
   - Servicios → Cuentas GL o patrones de cuentas
3. Ejecute los modelos de facturación y compruebe que **la tabla de salida/diario de facturación** contiene:
   - Periodo, Consumidor, Servicio
   - Unidades, cargos
   - Todos los campos obligatorios del segmento Finanzas
4. Abre el **informe de exportación del diario** :
   - Filtrar por el período actual.
   - Confirme que los totales coinciden con el informe resumido de facturación.
5. Exporta el archivo del diario en el formato acordado (por ejemplo, CSV).
6. Proporcione el archivo al departamento financiero o cárguelo mediante la integración.
7. Confirmar publicación:
   - Los totales en Finanzas coinciden con los totales exportados.
   - No falló ninguna línea debido a segmentos faltantes o no válidos.

**Informes clave**

- Factura / informe resumido (para comparación)
- Informe de exportación del diario
- Informe de conciliación: total de facturación frente al total del diario
