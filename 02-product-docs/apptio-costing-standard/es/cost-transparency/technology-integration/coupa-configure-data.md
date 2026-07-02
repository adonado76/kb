---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Configurar los datos de Coupa para Apptio"
breadcrumb:
  - "Costing Standard"
  - "Integraciones tecnológicas"
  - "Información sobre proveedores Coupa"
  - "Información sobre proveedores Coupa Introducción"
source_path: "cost-transparency/technology-integration/coupa-configure-data.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configurar los datos de Coupa para Apptio

**Descripción general**

Una vez que los datos de Coupa se exportan y están disponibles en BIIT, es necesario transformarlos para que puedan ser utilizados por Vendor Insights . Este documento proporciona instrucciones para preparar los datos de Coupa que se integrarán en Vendor Insights .

Cuando se importan datos desde Coupa a través del conector de Datalink (Classic) :

- Los datos se exportan a tablas individuales, una por cada objeto Coupa, mediante los modos de recuperación inicial y delta.
- Tanto los datos iniciales como los datos delta se añaden a la tabla de transformación de cada objeto Coupa.
- El paso Eliminar duplicados se utiliza para determinar los datos más recientes de Coupa.
- El centro de costes y el departamento asociados al gasto se buscan en los datos de RR. HH. utilizando el correo electrónico del solicitante de Coupa.
- Los importes de las partidas individuales se suman para determinar el importe total de la factura o la orden de compra.
- A continuación, estas tablas de transformación se asignan Vendor Insights a conjuntos de datos maestros (MDS) para permitir la Vendor Insights generación de informes.

**Requisitos previos**

Deben existir los siguientes datos:

- Proveedor – inicial
- Proveedor – delta
- Contratos: iniciales
- Contratos – delta
- Órdenes de compra – iniciales
- Órdenes de compra – delta
- Líneas de orden de compra: inicial
- Líneas de orden de compra – delta
- Cuentas de líneas de órdenes de compra: inicial
- Cuentas de líneas de órdenes de compra: delta
- Facturas – iniciales
- Facturas – delta
- Líneas de factura: iniciales
- Líneas de factura: delta
- Cuentas de líneas de factura: inicial
- Cuentas de líneas de factura - delta

**NOTA** : Si cada mes se recuperan todos los datos iniciales, no se necesitan los datos delta.

**Instrucciones**

**Tarea 1: Recuperar datos de RR. HH.**

Recupere los siguientes campos de su sistema de RR. HH.:

- Nombre completo
- Correo electrónico
- Centro de costes
- Nombre del centro de costes
- Responsable del centro de costes
- Departamento
- Descripción del departamento

**Tarea 2: Crear la tabla de referencia de RR. HH.**

Los datos de RR. HH. se utilizan para determinar el centro de costes y el departamento asociados a cada gasto. El correo electrónico del solicitante de Coupa se utiliza para determinar el centro de costes y el departamento. Los datos de RR. HH. proporcionan datos complementarios para garantizar que cualquier dato que pueda no existir en una implementación estándar de Coupa esté disponible en Apptio.

1. Cree una tabla y cargue la tabla sin procesar **de RRHH** :
   - **Nombre** de la tabla: Datos brutos de RR. HH
   - **Categoría** - Vendor Insightsz\_\_Raw
   - **Fuente de datos** - Carga de archivos
   - **Fuente de datos inicial** - <Datos de RR. HH.>
   - **Uso** : lista de usuarios, direcciones de correo electrónico y jerarquía organizativa de la fuente de datos original
2. Cree las siguientes tablas maestras de referencia:
   - **Nombre** de la tabla: Datos maestros de RR. HH.
   - **Categoría** - z\_Vendor Insights.
   - **Fuente de datos** : carga de archivos.
   - **Fuente de datos inicial** : vaya a [[ %=GlobalVariables.CompanyName% ] Comunidad](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?documentkey=e2b877ae-b6b8-4bf4-9e2f-36e0caec62b3 "(se abre en una pestaña o una ventana nueva)") y descargue el archivo denominado HR Data Master Data.
   - **Uso** : datos maestros para añadir los datos brutos de RR. HH. Lista de usuarios, direcciones de correo electrónico y jerarquía organizativa de la fuente de datos original.
3. Añadir las tablas sin procesar a las tablas de datos maestros:
   - **Nombre de la tabla de datos maestros** - Datos maestros de RR. HH
   - **Nombre** de la tabla de datos sin procesar: Datos sin procesar de RR. HH
   - **Columnas asignadas de la tabla de datos maestros:**
     - Nombre completo
     - Correo electrónico
     - Centro de costes
     - Nombre del centro de costes
     - Responsable del centro de costes
     - Departamento
     - Descripción del departamento

Ejemplo de mapeo utilizando datos de demostración (mapeo de datos maestros de RR. HH. a datos brutos de RR. HH.):

- Nombre completo - Nombre completo
- Correo electrónico - Correo electrónico
- Centro de costes - Centro de costes
- Nombre del centro de costes - Nombre del centro de costes
- Responsable del centro de costes - Responsable del centro de costes
- Departamento - Departamento
- Descripción del departamento - Descripción del departamento

**Tarea 3: Crear tablas de coincidencia de estados Coupa- Apptio**

Los estados de las órdenes de compra de Coupa son más detallados que el informe de ejecución de órdenes de compra, que solo distingue entre órdenes de compra abiertas y cerradas.

Vaya a [[ %=GlobalVariables.CompanyName% ] Comunidad](https://community.apptio.com/community/user/apptio/communities/community-home/all-news/viewdocument?DocumentKey=e2b877ae-b6b8-4bf4-9e2f-36e0caec62b3 "(se abre en una pestaña o una ventana nueva)") y descargue el archivo denominado Estado de la orden de compra de Coupa a Tabla de correspondencias de estado de Apptio.

Cree una tabla de asignación y, a continuación, cargue la hoja de cálculo que contiene el estado predeterminado para el objeto de orden de compra de Coupa.

| Nueva tabla: nombre de la tabla | Categoría | Origen de datos | Fuente de datos inicial |
| --- | --- | --- | --- |
| Coupa\_Apptio\_Tabla\_de\_estado\_coincidente | z\_Coupa\_Transformación | Carga de archivo | Estado de la orden de compra de Coupa a estado de la orden de compra de Apptio |

**Tarea 4: Crear tablas de transformación de Coupa**

Cree tablas de transformación, añada los datos sin procesar de Coupa y transforme los datos. Cada una de estas tablas transformadas requerirá varios pasos para colocarlas en el formato final, listas para ser añadidas a los conjuntos de datos maestros.

Resumen de los pasos necesarios para transformar las tablas:

1. Cree las tablas de transformación.
2. Añadir la fuente de datos delta a la tabla.
3. Añadir fórmulas para garantizar que todos los campos esperados de Coupa estén presentes.
4. Elimine las filas duplicadas de la tabla para que solo queden los registros más recientes.
5. Añada fórmulas para calcular los campos adicionales necesarios para asignarlos a las tablas de Vendor Insights datos maestros.
6. Asigne la tabla de transformación sin procesar al conjunto de datos maestro adecuado.

**Tarea 4.1: Crear las tablas de transformación**

Antes de crear las tablas de transformación, vea las tablas sin procesar y asegúrese de que la columna **Type Override** esté rellenada. Si no es así, rellene cada celda de la columna con la sustitución de tipo adecuada.

1. Cree las siguientes tablas de transformación para cada uno de los objetos Coupa con el fin de fusionar los datos iniciales y delta, y garantizar que existan todos los campos necesarios para asignarlos a la tabla de datos maestros. Cree cada tabla de transformación como una nueva tabla utilizando los nombres de la siguiente tabla.   
    **CONSEJO** : Aprenda a [crear una tabla en TBM Studio](../../studio/data_studio/create-table.html "Aplicable a: TBM Studio 12.0 y posteriores").   

   | Nueva tabla: nombre de la tabla | Categoría | Origen de datos | Fuente de datos inicial |
   | --- | --- | --- | --- |
   | Coupa\_Transformar\_Proveedor | z\_Coupa\_Transformación | Tabla existente | <Datos sin procesar de Coupa (datos iniciales del proveedor)> |
   | Coupa\_Transformar\_Línea\_de\_factura\_Cuenta | z\_Coupa\_Transformación | Tabla existente | <Datos sin procesar de Coupa (datos iniciales de la cuenta de la línea de factura)> |
   | Coupa\_Transformar\_Línea\_de\_factura | z\_Coupa\_Transformación | Tabla existente | <Datos sin procesar de Coupa (datos iniciales de la línea de factura)> |
   | Coupa\_Transformar\_Factura | z\_Coupa\_Transformación | Tabla existente | <Datos sin procesar de Coupa (datos iniciales de la factura)> |
   | Coupa\_Transformar\_Línea\_de\_pedido\_Contabilidad | z\_Coupa\_Transformación | Tabla existente | <Datos sin procesar de Coupa (datos iniciales de la cuenta de la línea de pedido)> |
   | Coupa\_Transformar\_Línea\_de\_pedido\_de\_compra | z\_Coupa\_Transformación | Tabla existente | <Datos sin procesar de Coupa (datos iniciales de la línea de pedido)> |
   | Coupa\_Transformar\_PO | z\_Coupa\_Transformación | Tabla existente | <Datos sin procesar de Coupa (datos iniciales de la orden de compra)> |
   | Coupa\_Transformar\_Contrato | z\_Coupa\_Transformación | Tabla existente | <Datos sin procesar de Coupa (datos del contrato inicial)> |
2. Haga clic en el paso **Fuente** y, a continuación, haga clic en **Tabla existente**.
3. En el paso **Tabla existente**, seleccione los valores **de la Tabla de entrada** asociados a la tabla creada (consulte el paso 1 para ver estos valores).
4. Añade el paso Anexar a la transformación de datos.
   - Haga clic en **Añadir tabla** y, a continuación, seleccione el nombre de la tabla delta que desea añadir.   
        
      **Ejemplo** : Coupa\_Supplier\_Delta\_Raw)
   - Asigne los nombres de los campos delta a las tablas de transformación. Cada campo debe coincidir 1 a 1.
   - (Opcional) Si hay campos adicionales en los datos delta que no formaban parte de los datos iniciales, añada estos campos adicionales de los datos delta a esta tabla de transformación.
5. Añade el paso **Fórmulas** y, a continuación, añade la siguiente fórmula a las seis tablas de transformación:
   - **Nombre de columna** - Clave
   - **Tipo** - Etiqueta
   - **Fórmula** -  `=trim(Coupa ID)`
6. Añade el paso **Eliminar duplicados** y, a continuación, selecciona lo siguiente:
   - **Columna clave** - Clave
   - **Columna de comparación** - Actualizado el
   - **Tipo de comparación** - Mayor
7. Para la  `Coupa_Transform_PO_New`  tabla, añada el paso **Ocultar y Renombrar**. A continuación, haga clic en **Añadir columnas** y añada las siguientes columnas:   

   | Nombre de columna | Visible | Cambiar el nombre a |
   | --- | --- | --- |
   | Departamento | Comprobado | Descripción del departamento |
   | Fecha de la orden de compra | Comprobado | Fecha de pedido original |
   | Número de orden de compra | Comprobado | N.º de pedido |
8. Es posible que falten algunos campos de Coupa porque no se han rellenado o no se han configurado en Coupa. Si un campo no existe, añada el nombre del campo que falta y rellene el campo con un valor en blanco. Los datos de salida de Coupa pueden carecer de cualquiera de los siguientes campos:
   - Centro de costes
   - Departamento
   - Torre
   - Subtorre
   - Fondo común de costes
   - Subgrupo de costes
9. Se requieren fórmulas para combinar datos de múltiples fuentes y convertir el formato de datos al valor que necesitan las tablas de Vendor Insights datos maestros. Haga clic en **Fórmulas** y, a continuación, añada las siguientes fórmulas a las tablas de transformación:

**Tarea 4.2: Coupa\_Transform\_Supplier**

En este ejemplo, todos los campos con el valor "" no están presentes en los datos sin procesar de Coupa.

| Nombre de columna | Tipo | Fórmula |
| --- | --- | --- |
| Mercancía predeterminada | Etiqueta | `=if(Vendor Description = "Default Commodity:", "",Default Commodity Ref)` |
| Referencia predeterminada de productos básicos | Etiqueta | `=Right(Vendor Description, len(Vendor Description)-find(": ",Vendor Description))` |
| Servicio de proveedores | Etiqueta | `=Default Commodity` |
| ID de proveedor principal | Etiqueta | **NOTA** : En la lista **Seleccionar columna para editar**, seleccione el tipo de datos.    `=Parent Vendor Coupa ID & " - " & Parent Vendor ID` |
| Ubicación del proveedor | Etiqueta | `=Primary Address City&&Primary Address State&&Primary Address Country` |
| ID de proveedor | Etiqueta | **NOTA** : En la lista **Seleccionar columna para editar**, seleccione el tipo de datos.    `=Coupa ID & " - " & Vendor ID` |
| Recuento | Numérico | `=1` |
| Torre de TI | Etiqueta | `=""` |
| Subtorre de TI | Etiqueta | `=""` |
| Ciudad de la dirección principal | Etiqueta | `=""` |
| País de la dirección principal | Etiqueta | `=""` |
| Dirección principal Estado | Etiqueta | `=""` |
| Tipo de proveedor | Etiqueta | `=""` |

**Tarea 4.3: Coupa\_Transform\_Invoice\_Line\_Acct**

| Nombre de columna | Tipo | Fórmula |
| --- | --- | --- |
| Nombre del centro de coste de la línea | Etiqueta | `={Account Segment 02}` |
| Número de centro de coste de la línea | Etiqueta | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| Línea PO | Etiqueta | `=Purchase Order Number&" - " & PO Line Num` |
| Importe del pedido | Numérico | `=SumIf(PO Coupa ID,PO Coupa ID, Item Total)` |
| Recuento | Numérico | `=1` |

**Tarea 4.4: Coupa\_Transform\_Invoice\_Line**

Los datos del centro de costes pueden proceder de Coupa a través de un campo personalizado, un campo de segmento de cuenta, o pueden requerir que busque los datos utilizando los datos de RR. HH. El valor del centro de coste debe asignarse al nombre de campo previsto para que pueda ser utilizado por otras fórmulas.

En el siguiente ejemplo, el nombre del centro de coste se almacena en el campo **Segmento de cuenta 02** de los datos sin procesar de Coupa. Si el valor está en blanco, entonces el número del centro de costes debe buscarse en una tabla de referencia (Datos maestros de datos de RR. HH.).

Si los datos del centro de costes no existen en los datos sin procesar de Coupa, utilice la fórmula  `=""` .

| Nombre de columna | Tipo | Fórmula |
| --- | --- | --- |
| ID de cuenta | Etiqueta | `=Trim(Account ID If)` |
| ID de cuenta Si | Etiqueta | `=left(Account,Find(" - ",Account))` |
| ID de cuenta Ref | Etiqueta | `=right(Account,len(Account)- Find(" - ",Account)-2)` |
| Descripción de la cuenta | Etiqueta | `=trim(Account Desc If)` |
| Descripción de la cuenta Si | Etiqueta | `=if(Account CONTAINS " - ",Account Desc Ref,Account)` |
| Descripción de la cuenta Ref | Etiqueta | `=right(Account,len(Account)- Find(" - ",Account)-2)` |
| Recuento | Numérico | `=1` |
| Nombre del centro de coste de la línea | Etiqueta | `={Account Segment 02}` |
| Número de centro de coste de la línea | Etiqueta | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| Factura Coupa ID str | Etiqueta | `=trim(Invoice Coupa ID)` |

**Tarea 4.5: Coupa\_Transform\_Invoice**

| Nombre de columna | Tipo | Fórmula |
| --- | --- | --- |
| Centro de costes | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Center Number from Line)` |
| Nombre del centro de costes | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Center Name from Line)` |
| Responsable del centro de costes | Etiqueta | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Cost Center Owner)` |
| Torre | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Tower)` |
| Subtorre | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,{Sub-Tower})` |
| Fondo común de costes | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Pool)` |
| Subgrupo de costes | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Sub Pool)` |
| Departamento | Etiqueta | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Department)` |
| Descripción del departamento | Etiqueta | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Department Desc)` |
| Cuenta | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Account ID)` |
| Descripción de cuenta | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Account Desc)` |
| Fecha de factura abreviada | Formato de fecha:   mm   dd   aaaa | `=Dateformat(Split(Invoice Date,1,"T"),"MM/dd/yyyy")` |
| Fecha de la factura Texto abreviado | Etiqueta | `=Invoice Date Abridged` |
| Descripción | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Invoice Line Description)` |
| ID de contrato Coupa | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Contract Coupa ID)` |
| ID de proveedor principal de Coupa | Etiqueta | `=Lookup(Vendor Coupa ID,Coupa_Transform_Supplier,Coupa ID,Parent Vendor Coupa ID)` |
| N.º de pedido | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,PO No)` |
| Identificación PO Coupa | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,PO Coupa ID)` |
| Número de factura | Etiqueta | `=if(Invoice ID="", "Coupa Invoice ID: "&Coupa ID, Invoice ID)` |
| Número de orden de compra | Etiqueta | `=if(PO Coupa ID="" OR PO No ="","",PO Coupa ID & " - " & PO No)` |
| ID de proveedor | Etiqueta | **NOTA** : En la lista **Seleccionar columna para editar**, seleccione el tipo de datos.    `=Vendor Coupa ID & " - " & Vendor ID` |
| Nombre de distribuidor | Etiqueta | **NOTA** : En la lista **Seleccionar columna para editar**, seleccione el tipo de datos. |
| Identificación de cuentas por pagar | Etiqueta | `=Coupa ID` |
| Recuento | Numérico | `=1` |

**Tarea 4.6: Coupa\_Transform\_PO\_Line\_Acct**

| Nombre de columna | Tipo | Fórmula |
| --- | --- | --- |
| Nombre del centro de coste de la línea | Etiqueta | `={Account Segment 02}` |
| Número de centro de coste de la línea | Etiqueta | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| Línea PO | Etiqueta | `=Purchase Order Number&" - " & PO Line Num` |
| Importe del pedido | Numérico | `=SumIf(PO Coupa ID,PO Coupa ID, Item Total)` |
| Recuento | Numérico | `=1` |

**Tarea 4.7: Coupa\_Transform\_PO\_Line**

| Nombre de columna | Tipo | Fórmula |
| --- | --- | --- |
| Nombre del centro de coste de la línea | Etiqueta | `={Account Segment 02}` |
| Número de centro de coste de la línea | Etiqueta | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| Línea PO | Etiqueta | `=Purchase Order Number&" - " & PO Line Num` |
| Importe del pedido | Numérico | `=SumIf(PO Coupa ID,PO Coupa ID, Item Total)` |
| Recuento | Numérico | `=1` |

**Tarea 4.8: Coupa\_Transform\_PO**

| Nombre de columna | Tipo | Fórmula |
| --- | --- | --- |
| Centro de costes | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Cost Center Number from Line)` |
| Nombre del centro de costes | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Cost Center Name from Line)` |
| Responsable del centro de costes | Etiqueta | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Cost Center Owner)` |
| Torre | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Tower)` |
| Subtorre | Etiqueta | `=Lookup(Coupa ID,Coupa_PO_Line,PO Coupa ID,{Sub-Tower})` |
| Fondo común de costes | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Pool)` |
| Subgrupo de costes | Etiqueta | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Cost Sub Pool)` |
| Departamento | Etiqueta | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Department)` |
| Descripción del departamento | Etiqueta | **NOTA** : En la lista **Seleccionar columna para editar**, seleccione el tipo de datos. |
| Importe | Numérico | `=Requisition Total Amount` |
| Amount\_derivedFromPOLine | Numérico | `=Lookup(Coupa ID, Coupa_Transform_PO_Line,PO Coupa ID,PO Amount)` |
| Fecha de la orden de compra | Formato de fecha:   mm   dd   aaaa | `=Dateformat(Split(PO Date Orig,1,"T"),"MM/dd/yyyy")` |
| PO-1 | Etiqueta | `=PO No&" - 1"` |
| PO-2 | Etiqueta | `=PO No&" - 2"` |
| PO-3 | Etiqueta | `=PO No&" - 3"` |
| PO-4 | Etiqueta | `=PO No&" - 4"` |
| PO-1 Búsqueda | Etiqueta | `=Lookup({PO-1},Coupa_Transform_PO_Line,{PO-Line},Item Name)` |
| PO-2 Búsqueda | Etiqueta | `=Lookup({PO-2},Coupa_Transform_PO_Line,{PO-Line},Item Name)` |
| PO-3 Búsqueda | Etiqueta | `=Lookup({PO-3},Coupa_Transform_PO_Line,{PO-Line},Item Name)` |
| PO-2 Si | Etiqueta | `=if({PO-2 Lookup}="", "","; " & {PO-2 Lookup})` |
| PO-3 Si | Etiqueta | `=if({PO-3 Lookup}="", "","; " & {PO-3 Lookup})` |
| Descripción de la orden de compra | Etiqueta | `={PO-1 Lookup}&{PO-2 If}&{PO-3 If}` |
| Estado Superior | Etiqueta | `=Upper(Status)` |
| Estado del pedido de compra | Etiqueta | `=Lookup(Status Upper,Coupa_Apptio_Status_Tablematch,Coupa Status,Apptio Status)` |
| Número de orden de compra | Etiqueta | `=PO No` |
| ID de proveedor | Etiqueta | `=Vendor Coupa ID & " - " & Vendor ID` |
| Nombre de distribuidor | Etiqueta | **NOTA** : En la lista **Seleccionar columna para editar**, seleccione el tipo de datos. |
| Importe monetario anterior | Numérico | `=Accounts Payable Raw Historic:Prior Years Monetary Amount[PO=Purchase Order Number]` |
| Peticionario | Etiqueta | **NOTA** : En la lista **Seleccionar columna para editar**, seleccione el tipo de datos. |
| Recuento | Numérico | `=1` |

**Tarea 4.9: Coupa\_Transform\_Contract**

| Nombre de columna | Tipo | Fórmula |
| --- | --- | --- |
| Número del centro de costes | Etiqueta | `=""` |
| Búsqueda del número del centro de costes | Etiqueta | `=if(Cost Center Number!="",Cost Center Number,Cost Center HR Lookup)` |
| Centro de costes Búsqueda de RR. HH | Etiqueta | `=Lookup(Contract Owner Email,HR Data Master Data,Email,Cost Center)` |
| Búsqueda por departamento | Etiqueta | `=if(Cost Center Number!="",Department CC HR Lookup,Department Email HR Lookup)` |
| Departamento CC Búsqueda de RR. HH | Etiqueta | `=Lookup(Cost Center Number,HR Data Master Data,Cost Center,Department)` |
| Correo electrónico del departamento Búsqueda de RR. HH | Etiqueta | `=Lookup(Contract Owner Email,HR Data Master Data,Email,Department)` |
| Recuento | Numérico | `=1` |
| Fecha de inicio del contrato | Formato de fecha:   mm   dd   aaaa | `=DateFormat(split(Start Date,1,"T"),"MM/dd/yyyy")` |
| Fecha de finalización del contrato | Formato de fecha:   mm   dd   aaaa | `=DateFormat(split(End Date,1,"T"),"MM/dd/yyyy")` |
| ID de proveedor Coupa str | Etiqueta | `=Trim(Vendor Coupa ID)` |
| Gerente de proveedores | Etiqueta | `=Lookup(Vendor Coupa ID str,Vendor Master Data,Vendor ID,Vendor Manager)` |
| Tipo de proveedor | Etiqueta | `=Lookup(Vendor Coupa ID str,Vendor Master Data,Vendor ID,Vendor Type)` |
| Contrato para padres | Etiqueta | **NOTA** : En la lista **Seleccionar columna para editar**, seleccione el tipo de datos. |
| Planes de renovación | Etiqueta | `""` |
| Responsable del centro de costes | Etiqueta | Propietario del centro de costes JHL (buscar mediante el correo electrónico del propietario del contrato) |

Para la tabla **Coupa\_Transform\_Invoice** :

1. Añade el paso **Partición por fecha** a la transformación de datos.
2. Seleccione la casilla **Las fechas se representan en filas**.
3. En la lista **Columna de fecha de inicio**, seleccione **Texto abreviado de la fecha de factura**. Deje en blanco la lista **de la columna Fecha de finalización**.

**Tarea 4.10: Crear una tabla de asignación (PO a contrato)**

Además de las tablas de transformación anteriores, se necesita una tabla de asignación para vincular la orden de compra con los datos del contrato para Vendor Insights .

1. Cree la siguiente tabla de transformación como una nueva tabla.   
    **CONSEJO** : Aprenda a [crear una tabla en TBM Studio](../../studio/data_studio/create-table.html "Aplicable a: TBM Studio 12.0 y posteriores").
   - **Nombre de la tabla** : Coupa\_Transform\_PO-to-Contract
   - **Categoría** - z\_Coupa\_Transform
   - **Fuente de datos** - Tabla existente
   - **Fuente de datos** - Coupa\_Transform\_PO\_Line
2. Haga clic en el paso **Fuente** y, a continuación, haga clic en **Tabla existente**.
3. En el paso **Tabla existente**, seleccione el valor **Tabla de entrada** **Coupa\_Transform\_PO\_Line**.
4. Añade el paso Filtro y, a continuación, añade dos filtros utilizando los siguientes parámetros:
   - Nombre de columna: **ID de contrato Coupa**, Valor del filtro: **No es nulo**
   - Nombre de columna: **PO Coupa ID**, Valor del filtro: **No es nulo**
5. Añade el paso **Grupo** y, a continuación, añade la agrupación **PO-Contract Coupa ID**.
6. Añade el paso **Fórmulas** y, a continuación, añade las siguientes fórmulas:

   | Nombre de columna | Tipo | Fórmula |
   | --- | --- | --- |
   | ID de contrato | Etiqueta | `=Contract Coupa ID & " - " & Contract ID` |
   | Número de orden de compra | Etiqueta | `=PO Coupa ID & " - " & Purchase Order Number` |
7. Guarde sus cambios.
