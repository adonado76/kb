---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Rellenar el catálogo de ofertas"
breadcrumb:
  - "Billing"
  - "Configuración de los elementos esenciales de facturación (implementación)"
source_path: "boit/billing/config-be/populate.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Rellenar el catálogo de ofertas

El catálogo de ofertas determina lo que aparece en las facturas. Debe completarse y validarse antes de la primera facturación.

Pasos:

1. **Definir el catálogo inicial**
   - Enumere los servicios/productos que se facturarán.
   - Asignar:
     - Nombres cortos y reconocibles.
     - Unidades de medida (por ejemplo, usuarios por mes, GB por mes).
     - Ofrecer identificadores estables y únicos.
2. **Cargar las ofertas en la tabla**
   - Usar:
     - TBM Studio ETL si la configuración se gestiona completamente en Studio, o
     - Carga de tabla si el catálogo se mantiene en un CSV o una hoja de cálculo.
3. **Establecer indicadores**
   - Mark:
     - Facturable = Sí para las ofertas que deben aparecer en las facturas.
     - Activo para ofertas actualmente en uso.
     - Indicadores internos o similares si algunas ofertas se utilizan únicamente para asignaciones internas.
4. **Validar catálogo**
   - Ejecute un informe o consulta simple para:
     - Comprueba si hay duplicados.
     - Confirme que las unidades están pobladas.
     - Confirme que los indicadores de estado son correctos.

Mantenga el catálogo inicial conciso. Es más fácil añadir ofertas más adelante que revertir un catálogo desordenado.
