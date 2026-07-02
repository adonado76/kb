---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Diseño centrado en la nube"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
source_path: "boit/billing/admin-ops/ao-cloud-centric.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Diseño centrado en la nube

Nota: Se aplica únicamente a la norma de facturación.

**Cuándo utilizarlo**

- El gasto en la nube es significativo y está siendo objeto de escrutinio.
- Las partes interesadas desean ver los cargos por servicios en la nube por proveedor, cuenta, servicio, agrupación de etiquetas y consumidor.

**Forma**

- Los datos en la nube se modelan como su propio dominio.
- Las etiquetas y las cuentas se asignan a:
  - Servicios o categorías de costes.
  - Consumidores (unidades de negocio, productos, aplicaciones).
- La facturación utiliza tablas de dominios en la nube, además de la configuración de unidades y precios, para generar cargos y tarifas unitarias.

**Elementos clave**

- Incorporó archivos de facturación en la nube a tablas de uso estandarizadas.
- Tablas de asignación de etiquetas que vinculan etiquetas y cuentas con servicios y consumidores.
- Definiciones de unidades específicas de la nube:
  - GB al mes.
  - vCPU hora.
  - Recuento de solicitudes, etc.
- Opcional:
  - Lógica de precios en la nube separada para reembolsos frente a costes.

**Informes típicos**

- Gasto en la nube por proveedor, región y servicio.
- Tarifas unitarias de la nube y análisis de tendencias.
- Gasto en la nube por agrupación de etiquetas (por ejemplo, aplicación, entorno).

**Notas de implementación**

- La disciplina en el etiquetado no es negociable aquí. La facturación reflejará con precisión cualquier error de etiquetado que exista.
- Utilice informes de excepciones para resaltar los gastos en la nube sin etiquetar o mal etiquetados.
