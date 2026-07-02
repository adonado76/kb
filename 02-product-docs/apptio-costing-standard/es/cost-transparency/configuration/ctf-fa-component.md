---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "CTF - Componente de activos fijos: instalar y configurar"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-fa-component.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - Componente de activos fijos: instalar y configurar

Utilice el componente CTF - Activo fijo para conocer mejor sus costes de depreciación y tomar decisiones sobre la gestión de activos. La tabla Datos maestros de inmovilizado define los datos necesarios para rellenar los informes relacionados con costes y presupuestos. Para rellenar el conjunto de datos, debe cargar las cifras de costes de activos fijos y asignarlas a la tabla Datos maestros de activos fijos.

Se aplica a: Costing Standard en TBM Studio 12.4 y posteriores

## Usos

Utilice los informes del componente CTF - Inmovilizado para hacer lo siguiente:

- Gestionar los costes de amortización
- Determinar la asignación de recursos
- Alinear la gestión de activos con los objetivos empresariales
- Adaptar la gestión de activos a la estrategia
- Confirmar las anulaciones resultantes de las modificaciones presupuestarias

## Instalar el componente

El componente CTF - Inmovilizado no se instala con el proyecto estándar Costing Standard .

Para instalar el componente CTF - Inmovilizado:

1. Abra el proyecto Costing Standard .
2. En la pestaña Proyecto, haga clic en **Componentes**.
3. Haga clic en **Instalar**.

## Fuentes de datos habituales

Las cifras de activos fijos suelen extraerse de una aplicación de gestión de activos o CMDB (Configuration Management Data Base) como BMC Asset Mgmt, BMC Atrium CMDB,HP Univ Config Mgmt, Sage, AssetWorks, SAP Enterprise Asset Mgmt, CA Unicenter, SAP, Lawson, Oracle, o PeopleSoft.

Las aplicaciones suelen incluir un registro de activos fijos. El registro de activos fijos hace un seguimiento de activos como máquinas, equipos de oficina, edificios, etc. destinados a la producción de bienes o servicios. En el registro de Activos Fijos se suele hacer un seguimiento de la vida útil en meses del activo, la fecha de compra, el importe de compra y la depreciación mensual.

## Una carga

Normalmente se carga un único conjunto de datos de activos fijos que se anexa y se asigna a la tabla de datos maestros de activos fijos. El conjunto de datos debe contener campos que puedan asignarse a los campos apropiados de la tabla Datos maestros de activos fijos.

## Datos maestros

Para una descripción de los campos de la tabla de datos maestros, véase la información en la página del componente CTF - Inmovilizado del producto. Para visualizar la página:

1. Haga clic en la pestaña **Proyecto**.
2. Haga clic en **Componentes**.
3. Haga clic en el componente **CTF - Inmovilizado**.

## Campos obligatorios y recomendados

A continuación se enumeran los campos obligatorios y recomendados necesarios para iluminar los informes estándar de activos fijos de Costing Standard .

- Fecha de adquisición (obligatorio)
- Edad (obligatorio)
- Recuento de activos (obligatorio)
- Número de activo (obligatorio)
- Tipo de activo (recomendado)
- Categoría (recomendada)
- Clase (obligatoria)
- Centro de costes (recomendado)
- Importe de la amortización (obligatorio)
- Descripción (obligatoria)
- Amortización del inmovilizado LIM (obligatorio)
- Coste inicial del inmovilizado (obligatorio)
- ID del ledger de activos fijos (obligatorio)
- En servicio (obligatorio)
- Fecha de entrada en servicio (obligatoria)
- Subpotencia de recursos informáticos (obligatorio)
- Torre de recursos informáticos (obligatorio)
- Lugar (obligatorio)
- Identificador de objeto (obligatorio)
- Proveedor (obligatorio)

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
