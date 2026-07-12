---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Delegar costes de activos"
breadcrumb:
  - "Planning"
  - "Planificación de proyectos"
source_path: "it-planning/planning/iip/asset-depreciation-cost-center.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Delegar costes de activos

Importante: Disponible con la *suscripción* ***Apptio Planning Standard.***

Recuerde: *la función de planificación integrada de inversiones (IIP) debe estar habilitada.*

La función «**Delegar costes de activos** » le permite asignar la parte de amortización del coste de un activo a un centro de costes distinto al que posee la compra del activo. Esto resulta útil en escenarios de planificación de proyectos en los que un centro de costes del proyecto financia la **compra** inicial de capital (por ejemplo, la fase de construcción), mientras que los **gastos de amortización** continuos corren a cargo de un centro de costes operativo o de mantenimiento (por ejemplo, la fase de funcionamiento).

Esta delegación garantiza que los costes de los activos fijos se atribuyan con precisión a los departamentos responsables de mantener, consumir o amortizar el activo a lo largo del tiempo.

## Cómo funciona la delegación de costes de activos

La delegación de los gastos de activos tiene dos componentes principales:

- **Importe de compra del activo** : asignado al **centro** de costes seleccionado en la línea del activo.
- **Importe de amortización** : asignado al **centro de costes de amortización** seleccionado en la línea del activo.

Al elegir un centro de costes de amortización diferente, puede delegar los costes de amortización continuos a otro equipo, manteniendo la compra de capital en el proyecto o centro de costes original.

## Pasos para delegar los costes de amortización de activos

1. Ve a **Plan** → **Gastos** → **Activos**.
2. Crea un nuevo activo o edita uno ya existente.
3. En la línea de activos, seleccione el **centro de costes de amortización**. Este centro de coste recibirá todos los gastos de amortización generados por el sistema para el activo.

**Notas importantes**

- La delegación de amortización solo está disponible cuando la función **Planificación integrada de inversiones (IIP)** está habilitada.
- La depreciación siempre se asigna **íntegramente** al centro de costes de depreciación seleccionado.
- A diferencia de la delegación por contrato (que divide los gastos por fecha), la delegación de activos se aplica **a toda la depreciación**, a partir del calendario de depreciación del activo.
- No se puede delegar parcialmente la depreciación: cada activo solo admite un centro de costes de depreciación.
