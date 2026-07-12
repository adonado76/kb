---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Instalar los componentes de integración de ITPF"
breadcrumb: []
source_path: "cost-transparency/configuration/installitpfintegration.html"
images:
  - "resources/images/ct_images/gear_icon.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Instalar los componentes de integración de ITPF

Hay tres componentes disponibles como parte del módulo Costing Standard Foundation para conectar Costing Standard (CT) con IT Planning Foundation (ITPF).

## Introducción

Utilice los componentes de Integración ITPF para hacer lo siguiente:

- Garantizar que los datos de referencia de CT e ITP tengan una fuente de verdad en TBM Studio y poner los datos a disposición de ITP.
- Ponga los datos reales de la aplicación Costing Standard a disposición de la aplicación ITP.
- Poner a disposición de la aplicación CT los datos presupuestarios y de previsión de la aplicación ITP.

Nota:

El intercambio de datos se inicia desde la aplicación ITP.

Para que la integración funcione, debe configurar tanto CT como ITPF.

Componentes

- Apptio Integración ITPF - Este componente transfiere datos presupuestarios, de previsiones y reales entre CT e ITPF. El componente Fuente de costes debe instalarse antes de instalar el componente Integración de proveedores de Apptio ITPF. Se instalan tres conjuntos de datos:
  - ITPF Actuals es una transformación de los Datos Maestros de la Fuente de Coste que permite transferir los datos reales de CT a ITPF.
  - ITPF Budget e ITPF Forecast son los destinos para el presupuesto del año fiscal y los últimos datos de previsión transferidos desde ITPF a CT. Estos conjuntos de datos se asignan a los datos maestros de fuentes de costes en CT.
- Apptio Integración de activos ITPF - Este componente pasa los datos del plan de activos de ITPF a CT. El componente instala los conjuntos de datos ITPF Asset Budget e ITPF Asset Forecast. Los siguientes componentes deben estar instalados antes de instalar el componente Apptio ITPF Integration:
  - Fuente de costes
  - Activos fijos
- Apptio Integración de proveedores ITPF - Este componente pasa los datos relacionados con los planes de contratos de proveedores de ITPF a CT. El componente instala los conjuntos de datos Presupuesto de Contrato ITPF y Previsión de Contrato ITPF. El componente Fuente de costes debe instalarse antes de instalar el componente Integración de proveedores de Apptio ITPF.

## Instalar los componentes

Para instalar los componentes:

1. Abra la página TBM Studio.
2. En la pestaña Proyecto, haga clic en **Componentes**.
3. Haga clic en el componente **Apptio Integración ITPF**.
4. Haga clic en **Instalar**.
5. Haga clic en el componente **Apptio ITPF Asset Integration**.
6. Haga clic en **Instalar**.
7. Haga clic en el componente **Apptio Integración de proveedores ITPF**.
8. Haga clic en **Instalar**.

Si desea utilizar los componentes Proveedores y Activos en ITP, debe instalar los componentes Integración de proveedores ITPF e Integración de activos ITPF para asegurarse de que se instalan los siguientes conjuntos de datos:

- Datos maestros de proveedores de ITP
- ITPF Tipo de contrato Maestro
- Presupuesto del contrato ITPF
- Previsión de contratos ITPF
- Maestro de clases de activos ITP

## Datos maestros

Para obtener una descripción de los campos de la tabla de datos maestros y de los informes instalados con cada componente, consulte la descripción que figura en cada componente. Para visualizar las descripciones, haga lo siguiente:

1. En la pestaña Proyecto, haga clic en **Componentes**.
2. Haga clic en un componente para abrirlo en la página de descripción.

## Configurar la aplicación ITPF

Para configurar el ITPF, abra la aplicación ITPF, haga clic en el icono Configuración (![icono de configuración](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/gear_icon.png)) y, a continuación, haga clic en **Cost Transparency Integration**. Para obtener información sobre cómo rellenar los campos obligatorios, consulte [Integración con Costing
Standard](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-integrate-cost-transparency "(se abre en una pestaña o una ventana nueva)").
