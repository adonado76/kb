---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Torre de recursos: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financiero"
  - "Torres de recursos"
source_path: "cost-transparency/it-financials/rt-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Torre de recursos: Introducción

Utilice las torres de recursos de TI para analizar el gasto en TI por torres y subtorres funcionales, lo que permite una revisión coherente de la distribución de los costes, las tendencias y la alineación con el presupuesto. El componente **CTF – IT Towers** forma parte del Estándar de Costes y proporciona la estructura de datos maestros necesaria para respaldar la elaboración de informes y análisis a nivel de torre.

Antes de utilizar los informes de IT Towers, instale los componentes necesarios y asegúrese de que los datos de costes estén asignados a la taxonomía de IT Resource Towers.

## Instalación de componentes

- **CTF- IT Tower** : el componente **CTF – IT Towers** proporciona información sobre los costes de las torres y subtorres de recursos de TI y permite comparar el gasto con el presupuesto para realizar revisiones operativas y estratégicas. La instalación de este componente crea los **datos maestros de torres de recursos de TI**, que son necesarios para todos los informes de torres de TI.

Este componente le permite:

- Identificar los cambios mensuales y trimestrales en el gasto de la torre de TI
- Identificar las torres de TI con variaciones significativas respecto al presupuesto
- Gestionar el gasto en torres de TI a nivel funcional
- Analizar las fuentes de costes primarios que contribuyen a cada torre

**Requisitos previos:**

- **CTF – Fuente de costes** *(obligatorio)*
- Proporciona los datos de costes fundamentales utilizados para asignar el gasto a las torres de recursos de TI.
- **CTF – Trabajo** *(Opcional)*
- Permite asignar los costes laborales a las torres y subtorres de recursos de TI.
- **CTF – Proveedor** *(opcional)*
- Permite asignar el gasto de los proveedores a torres y subtorres de recursos de TI.
- **CTF – Activos fijos** *(opcional)*
- Permite asignar los costes de los activos fijos a torres y subtorres de recursos de TI.

## Fuentes comunes de datos

La taxonomía de torres y subtorres de recursos de TI está definida por el **Modelo Unificado TBM Apptio ( ATUM )** y se carga automáticamente con el proyecto Estándar de Costos en la **Lista de Recursos de Torres de Recursos de TI**.

No todos los costes se asignan automáticamente a las torres a través de otros componentes. Para garantizar la precisión de los informes de las torres, las organizaciones suelen:

- Asignar centros de coste a torres y subtorres de recursos de TI
- Defina los porcentajes de asignación cuando un centro de costes se asigna a varias torres
- Definir una lógica de asignación separada para los datos reales y los datos presupuestarios

Apptio Las automatizaciones pueden ayudar a optimizar y acelerar el proceso de mapeo. Póngase en contacto con su gestor de éxito del cliente para obtener más información sobre las opciones disponibles.

**Ejemplos de escenarios de mapeo**

Los siguientes ejemplos ilustran enfoques comunes para asignar datos de costes a las torres y subtorres de recursos tecnológicos de TBM:

- Un centro de costes responsable de las operaciones del centro de datos puede asignarse a Centro de datos → Centro de datos empresarial.
- Los roles como ingenieros de red o administradores de LAN se pueden asignar a Red → LAN, mientras que los administradores de almacenamiento se pueden asignar a Almacenamiento → Almacenamiento en línea.
- Los costes de los proveedores de servicios de seguridad gestionados pueden asignarse a Seguridad → Seguridad digital, mientras que los proveedores de ITSM o de servicios de asistencia técnica pueden asignarse a Entrega → Gestión de servicios.

## Conjuntos de datos maestros

**Torres de recursos informáticos Datos maestros**

Los datos maestros de las torres de recursos de TI definen la estructura utilizada para clasificar los costes por torre y subtorre. Estos datos maestros se instalan con el componente **CTF – IT Towers**.

Para facilitar la asignación y la presentación de informes completos, otros conjuntos de datos deben incluir los siguientes campos, cuando proceda:

- Datos maestros de fuentes de costes
  - Centro de costes
  - Torre de recursos informáticos
  - Subtorre de recursos informáticos
- Datos maestros de mano de obra *(si están instalados)*
  - Torre de recursos informáticos
  - Subtorre de recursos informáticos
- Datos maestros de activos fijos *(si están instalados)*
  - Torre de recursos informáticos
  - Subtorre de recursos informáticos
- Datos maestros del proveedor *(si están instalados)*
  - Torre de recursos informáticos
  - Subtorre de recursos informáticos

Si no se dispone de datos suficientes para asignar los costes con precisión, deje esos costes en el objeto Fuente de costes en lugar de aplicar asignaciones incompletas o incorrectas.
