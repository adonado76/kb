---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Perspectiva de la entidad jurídica y los precios de transferencia"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
source_path: "boit/billing/admin-ops/ao-legal-entity.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Perspectiva de la entidad jurídica y los precios de transferencia

Nota: Se aplica únicamente a la norma de facturación.

**Cuándo utilizarlo**

- Múltiples entidades jurídicas consumen y prestan servicios tecnológicos.
- Los requisitos normativos, fiscales y de facturación entre empresas son importantes.

**Forma**

- La entidad jurídica se convierte en una dimensión clave junto con el consumidor y el servicio.
- Facturación separada:
  - Líneas de ingresos internos.
  - Líneas de gastos internos.
  - Posibles recargos relacionados con impuestos.

**Elementos clave**

- Datos maestros de la entidad jurídica con atributos de país e impuestos.
- Asignaciones:
  - De consumidores a personas jurídicas.
  - Servicios o infraestructura para entidades proveedoras.
- Reglas en los modelos de facturación para:
  - Identificar flujos entre entidades.
  - Crear líneas entre empresas.
  - Etiquétalos con los códigos adecuados.

**Informes típicos**

- Matriz interempresarial:
  - Filas como entidades proveedoras.
  - Las columnas como entidades consumidoras.
  - Células que muestran cargas.
- Vistas de pérdidas y ganancias de entidades jurídicas para servicios tecnológicos.
- Extractos fáciles de auditar que concilian con los diarios.

**Notas de implementación**

- No intente aplicar precios de transferencia hasta que el modelo de facturación básico sea estable y esté conciliado.
- Trabajar en estrecha colaboración con los equipos fiscales y financieros en lo relativo a las estructuras contables y la documentación.
