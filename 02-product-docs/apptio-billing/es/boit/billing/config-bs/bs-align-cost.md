---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Alineación de costes, consumo y definiciones de unidades"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/bs-align-cost.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Alineación de costes, consumo y definiciones de unidades

La norma de facturación requiere una historia coherente en cuanto a costes, unidades y precios.

Pasos:

1. **Revisar los resultados de la asignación de costes.**
   - Confirme que los costes fluyen:
     - Desde torres de recursos y dominios hasta servicios/aplicaciones.
     - Desde servicios/aplicaciones hasta consumidores.
2. **Definir unidades estándar**
   - Para cada dominio, asigna las medidas brutas a unidades estandarizadas, por ejemplo:
     - Horas VM → VM al mes.
     - GB brutos/horas → GB al mes.
     - Entradas → Entradas por mes.
     - Rellene la tabla de unidades según corresponda.
3. **Vincular los volúmenes de dominio a los servicios y consumidores.**
   - Asegúrese de que las tablas de dominio (servidores, almacenamiento, nube, dispositivos, proyectos) se incorporen a:
     - Volúmenes a nivel de servicio.
     - Volúmenes a nivel de consumidor.
4. **Vincular los costes de producción a las unidades de facturación cuando sea necesario.**
   - Para el análisis de la tasa unitaria:
     - Combine el coste de Costing con los volúmenes de Billing para obtener el coste por unidad.
   - Utilícelo para:
     - Validar precios.
     - Explique los cambios en las tarifas unitarias.
