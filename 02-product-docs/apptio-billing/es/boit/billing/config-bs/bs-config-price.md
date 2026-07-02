---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Configuración de la lógica de precios y variaciones"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/bs-config-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Configuración de la lógica de precios y variaciones

Billing Standard puede analizar costes, planes y precios. La configuración decide cómo funciona eso.

Pasos:

1. **Definir listas de precios**
   - Decida si el precio es:
     - Tarifa única por servicio.
     - Clasificado por consumidor, región o volumen.
   - Rellene las tablas de precios con:
     - Identificación del servicio/oferta.
     - Periodo o fechas de vigencia.
     - Precio por unidad.
     - Moneda y tipo de tipo de cambio.
2. **Conectar datos del plan y del presupuesto**
   - Si la varianza está dentro del alcance:
     - Integre los costes previstos y/o los volúmenes previstos de los sistemas de planificación o las hojas de cálculo.
   - Alinee las claves de datos del plan con los mismos servicios y consumidores utilizados en la facturación.
3. **Configurar reglas de variación**
   - Decida qué tipos de varianza se controlan:
     - Variación de volumen.
     - Variación de la tasa (coste frente a precio).
     - Mezcla o variación estructural, según corresponda.
   - Configure qué variaciones aparecen en:
     - Informes de dominio (por ejemplo, nube, aplicaciones).
     - Informes resumidos de variaciones.
4. **Resultados de la varianza de la prueba**
   - Ejecutar casos de prueba pequeños:
     - Escenarios conocidos de costes, planes y precios.
     - Confirme que la descomposición de la varianza coincide con las expectativas.
