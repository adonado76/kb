---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Finanzas de TI: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financiero"
  - "Finanzas de TI"
source_path: "cost-transparency/it-financials/itf-getting-started.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Finanzas de TI: Introducción

## Cómo empezar

Utilice los componentes de Finanzas de TI para cargar y gestionar los datos financieros necesarios para la elaboración de informes sobre OpEx y CapEx gastos. El componente CTF-Cost Source proporciona los datos financieros fundamentales para todos OpEx los informes. El componente opcional CapEx CTF permite CapEx-specific generar informes y garantiza que CapEx los campos solo se muestren cuando su organización utilice CapEx los datos.

Instale y configure estos componentes antes de cargar sus datos financieros. Una vez instalados los componentes, cargue sus conjuntos de datos de costes y presupuestos y asígnelos a las tablas de datos maestros correspondientes.

## Instalación de componentes

**CTF: fuente de costes (instalada automáticamente)**

El componente CTF-Cost Source se instala automáticamente al crear el proyecto Costing Standard. Proporciona la estructura de datos maestros necesaria para todos OpEx los informes. Utilizará este componente al cargar datos reales de costes, presupuestos de costes y campos de asignación en la tabla de datos maestros de fuentes de costes.

**CTF- CapEx (Componente adicional)**

El componente CapEx CTF separa CapEx la presentación de informes de OpEx la presentación de informes. Instale este componente si su organización carga CapEx datos o requiere CapEx informes específicos.

Utilice este componente cuando:

- Desea analizar los gastos de capital por cuenta, grupo de costes y centro de costes.
- Debe revisar CapEx las diferencias en los informes presupuestarios y de previsión.

**CTF: Informes de origen de costes NX (componente adicional)**

Este componente ofrece informes NX predefinidos basados en datos de Cost Source para el análisis de costes por centros de coste, grupos de cuentas y períodos de tiempo.

Utilice este componente cuando:

- Necesitas informes de costes estándar
- ¿Quieres comparar los datos reales con los presupuestos?
- Necesitas informes periódicos sobre las fuentes de coste

**Para instalar el componente:**

1. Abre el proyecto Costing Standard.
2. Seleccione **Proyecto** > **Componentes**.
3. Seleccionar **CTF – CapEx**.
4. Haga clic en **Instalar**.

Después de la instalación, proceda a cargar los datos en las tablas de datos maestros.

## Fuentes comunes de datos

Las cifras de costes y presupuestos suelen extraerse de fuentes como el libro mayor y el plan de cuentas. Estos datos suelen ser proporcionados por aplicaciones como Oracle, SAP, Lawson, Netsuite y Cognos Financial Statement Reporting. Los datos que utilice determinarán el nivel de detalle disponible y las columnas que asignará a la tabla de datos maestros de fuentes de costes.

**Conjuntos de datos**

Es posible que tenga que cargar varias tablas y asignarlas a las tablas maestras proporcionadas con los componentes. Las tablas son:

- Libro mayor (GL): Fuente de información veraz para todas las transacciones financieras, clasificadas por cuenta y a menudo asociadas con centros de coste o propietarios regionales.
- Plan de cuentas: Lista completa de las cuentas utilizadas en el sistema financiero. Determina el nivel de detalle disponible a nivel de cuenta para la generación de informes. Una cuenta es un registro único para cada tipo de activo, pasivo, patrimonio neto, ingreso y gasto.
- Jerarquía organizativa: Define la estructura de la organización, incluyendo la propiedad de los centros de coste y las relaciones jerárquicas.
- Presupuesto: Gasto previsto por centro de coste y cuenta. Necesario para el análisis de variaciones presupuestarias y previsiones.
