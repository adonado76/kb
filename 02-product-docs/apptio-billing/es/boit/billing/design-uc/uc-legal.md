---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Persona jurídica y visión interempresarial"
breadcrumb:
  - "Billing"
  - "Patrones de diseño y casos de uso"
source_path: "boit/billing/design-uc/uc-legal.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Persona jurídica y visión interempresarial

Nota: **Se aplica únicamente a la norma de facturación.**

**Problema**

Los equipos financieros y fiscales necesitan visibilidad sobre los gastos tecnológicos que traspasan los límites de las entidades jurídicas.

**Entradas**

- Tabla maestra de entidades jurídicas (entidad, país, atributos fiscales)
- Asignaciones:
  - Consumidores → persona jurídica
  - Servicios / infraestructura → entidad proveedora
- Configuración de precios de transferencia estándar de facturación

**Pasos**

1. Confirmar **asignaciones de entidades jurídicas** :
   - Los consumidores tienen asignaciones de entidades válidas.
   - Las entidades proveedoras se definen para los servicios o dominios incluidos en el ámbito de aplicación.
2. Ejecute modelos estándar de facturación con la lógica de precios de transferencia habilitada.
3. Abra el **informe Intercompany / Transfer Pricing** (Precios de transferencia entre empresas):
   - Ver cargos por Entidad de origen, Entidad de destino, Servicio y Período.
   - Compruebe los totales con los datos de facturación de alto nivel.
4. Filtrar por pares de entidades específicos de interés.
5. Revise los atributos fiscales según sea necesario (por ejemplo, país, tipo de servicio).
6. Utilice los resultados para:
   - Apoyo en la preparación de diarios interempresariales.
   - Proporcionar extractos para análisis fiscales o normativos.

**Informes clave**

- Matriz de precios de transferencia (De entidad × A entidad)
- Entidad jurídica Tecnología Vistas de estilo P&L
- Extracto del diario ajustado a los requisitos contables entre empresas
