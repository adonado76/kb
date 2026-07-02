---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Configuración de servicios y ofertas"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/bs-setup.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Configuración de servicios y ofertas

El catálogo de lo que se factura es fundamental independientemente de la edición, pero Billing Standard a menudo necesita una vinculación más rica con los dominios.

Pasos:

1. **Revisar el catálogo actual de servicios/productos.**
   - Reutiliza lo que ya está definido en Costing siempre que sea posible.
   - Confirmar:
     - Los nombres son importantes para los interesados en el negocio.
     - Cada servicio/producto se puede asignar a objetos de dominio subyacentes (aplicaciones, nube, servidores, etc.) donde sea necesario.
2. **Rellenar o actualizar la tabla de servicios.**
   - Para cada servicio o producto:
     - Asigne un ID de servicio/oferta estable.
     - Establezca un nombre y una descripción claros.
     - Defina la unidad de medida.
     - Establecer el estado (activo/retirado) y los indicadores facturables.
3. **Vincular servicios a dominios**
   - Dependiendo del diseño:
     - Servicios de mapas para aplicaciones (para vistas centradas en aplicaciones).
     - Asignar servicios a servidores o grupos de almacenamiento.
     - Asignar servicios a cuentas en la nube/agrupaciones de etiquetas.
     - Asigne los servicios a proyectos o carteras, si procede.

Sugerencias de diseño:

- Evite un servicio por cada pequeño componente técnico. Agrupe los componentes técnicos en servicios que tengan sentido desde el punto de vista empresarial.
- Utiliza enlaces de dominio para enriquecer el análisis, no para complicar demasiado el catálogo.
