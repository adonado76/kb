---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Activos fijos: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financiero"
  - "Activos fijos"
source_path: "cost-transparency/it-financials/fa-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Activos fijos: Introducción

**Cómo empezar**

Utilice la función de activos fijos para realizar un seguimiento de los activos de TI capitalizados, supervisar la depreciación y respaldar decisiones informadas sobre la gestión de activos. El **componente CTF (activos fijos)** permite generar informes sobre los costes de amortización y el valor residual de los activos, lo que ayuda a los responsables financieros y de servicios de TI a comprender el ciclo de vida de los activos y su impacto financiero.

Antes de utilizar los informes de activos fijos, instale el componente necesario y cargue los datos de activos fijos en la tabla de datos maestros.

## Instalación de componentes

**CTF - Activos fijos**

El componente CTF-Activos fijos proporciona la estructura necesaria para analizar el coste, la depreciación y el valor residual de los activos fijos a lo largo del tiempo.

**Requisitos previos**

- CTF: Fuente de costes

Después de instalar el componente, debe cargar los datos de costes de activos fijos y asignarlos a la tabla **de datos maestros de activos fijos** para rellenar los informes relacionados con la depreciación y los activos.

## Fuentes comunes de datos

Los datos sobre activos fijos suelen proceder de sistemas de gestión de activos empresariales o bases de datos de gestión de configuraciones (CMDB) que mantienen un registro de activos fijos. Estos sistemas realizan un seguimiento de los activos utilizados para suministrar bienes o servicios y suelen incluir detalles como la fecha de compra, el coste de compra, la vida útil del activo en meses y los valores de depreciación.

Las fuentes más utilizadas incluyen **SAP Enterprise Asset Management**, **Oracle** **PeopleSoft**, **BMC Asset Management / BMC Atrium CMDB**, **ServiceNow Asset Management** y **Workday Financial Management**

**Conjuntos de datos maestros**

La tabla Datos maestros de activos fijos define los datos necesarios para la elaboración de informes sobre el coste y la amortización de los activos fijos. Para rellenar esta tabla, cargue un conjunto de datos de activos fijos que contenga información sobre el coste y la depreciación y asígnelo a los campos correspondientes de la tabla de datos maestros.

Normalmente, se carga un **único conjunto de datos de activos fijos**, que se añade y se asigna a la tabla de datos maestros de activos fijos. El conjunto de datos debe incluir campos que se ajusten a la estructura de datos maestros requerida para permitir la elaboración de informes precisos sobre la depreciación y el ciclo de vida.
