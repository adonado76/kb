---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Configuración y tasas de carga"
breadcrumb:
  - "Billing"
  - "Configuración de los elementos esenciales de facturación (implementación)"
source_path: "boit/billing/config-be/configure.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Configuración y tasas de carga

Las tarifas convierten las unidades en cargos monetarios.

Pasos:

1. **Definir estrategia de tarifas**
   - Para cada oferta, determine si la tasa será:
     - Basado en los costes, coste más margen, basado en el precio, basado en el presupuesto o híbrido.
   - Decida con qué frecuencia pueden cambiar las tarifas:
     - Anualmente, trimestralmente o de forma puntual con la dirección.
2. **Diseñar el diseño de la tabla de tarifas**
   - Como mínimo:
     - Ofrecer identificación.
     - Periodo o fecha de entrada en vigor.
     - Importe de la tasa.
     - Moneda.
   - Opcional:
     - Tipo de tarifa (estándar, con descuento, interna).
     - Notas o comentarios.
3. **Cargar tasas iniciales**
   - Rates de población para:
     - El primer periodo de facturación.
     - Un horizonte futuro definido (por ejemplo, el año fiscal completo).
4. **Validar resolución**
   - Ejecute un informe de prueba o una ejecución de modelo para confirmar:
     - Cada oferta facturada en el periodo se resuelve en una tarifa única e inequívoca.
     - No faltan ofertas.

Consejo de gobernanza:

- Trate los cambios en las tarifas como eventos controlados, con documentación y aprobación claras, especialmente a mitad de año.
