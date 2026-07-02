---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Salida, entrada y creación de edificios"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Entornos y gestión de lanzamientos"
source_path: "boit/billing/environ-relnmgmt/checkin-checkout.html"
images:
  - "resources/images/boit_images/chckin.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Salida, entrada y creación de edificios

Los cambios de configuración para la facturación siguen el mismo patrón que los de costes:

1. **Extracción**
   - Los administradores o analistas comprueban los elementos relevantes en «En desarrollo»:
     - Modelos relacionados con la facturación.
     - Conjuntos de datos, tablas o métricas de los que depende la facturación.
     - Definiciones o plantillas de informes para facturación.
2. **Editar**
   - Los cambios se realizan en Desarrollo:
     - Ajustar la lógica en los modelos.
     - Añadir o modificar tablas y campos.
     - Actualización de diseños de informes o nuevos informes.
3. **Incorporar**
   - Cuando se completan los cambios, los elementos se registran.
   - El sistema automáticamente:
     - Crea una nueva **compilación en desarrollo**.
     - Crea una **compilación de ensayo** correspondiente basada en los mismos cambios.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/chckin.png)

Fig. n.º: Comprobación en el informe «Factura de TI»

Consejos prácticos:

- Agrupa los cambios en un pequeño número de conjuntos de registro para que sean más fáciles de rastrear y probar.
- Utiliza notas de compilación significativas en el registro para que quede claro qué compilaciones contienen qué cambios de facturación.
