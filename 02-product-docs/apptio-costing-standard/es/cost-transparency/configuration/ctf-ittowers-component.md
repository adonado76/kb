---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "CTF - Componente IT Towers: instalar y configurar"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-ittowers-component.html"
images:
  - "resources/images/ct_images/gear_icon.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - Componente IT Towers: instalar y configurar

El componente CTF - Torres de TI (Recursos) forma parte del módulo Costing Standard Foundation. El componente proporciona información sobre los costes de las torres y subtorres de recursos de TI, y compara el gasto en torres y subtorres de TI con el presupuesto en apoyo de las revisiones operativas y estratégicas mensuales, trimestrales y anuales.

Se aplica a: TBM Studio 12.4 y posteriores, con Plantilla v103 y posteriores

## Usos

Debe instalar el componente CTF - Cost Source antes de instalar el componente IT Towers. El componente instala los datos maestros de las torres de recursos informáticos.

- Identificar los principales cambios de la torre de TI en los gastos mensuales y trimestrales
- Identificar las principales desviaciones de la torre de TI con respecto al presupuesto
- Gestionar el gasto en torres de TI de acuerdo con el presupuesto
- Identificar las principales fuentes de costes

## Instalar el componente

Para instalar el componente:

1. Abra el proyecto Costing Standard .
2. En la pestaña Proyecto, haga clic en **Componentes**.
3. Haga clic en el componente **CTF - Torre IT**.
4. Haga clic en **Instalar**.

## Sistemas de fuentes comunes

La estructura (o taxonomía) de las torres y subtorres de TI se define en Apptio 's TBM Unified Model ( ATUM ). La taxonomía se carga con su proyecto Costing Standard en la lista de recursos de las torres de recursos informáticos.

Algunos de los valores necesarios para las torres y subtorres de TI no se asignan automáticamente a través de los demás componentes de CTF (es decir, los componentes Mano de obra, Activos fijos y Proveedores). En consecuencia, deberá hacer lo siguiente para extraer los datos adecuados de sus sistemas de origen y cargarlos en Apptio :

- Asigne sus centros de costes a torres y subtorres de TI
- Definir un porcentaje de asignación real para los centros de coste asignados a varias torres y subtorres de TI
- Definir un porcentaje de asignación presupuestado para los centros de costes asignados a varias torres y subtorres de TI

Su equipo de Success Management trabajará con usted para determinar cómo asignar sus centros de costes y códigos contables y cómo definir los porcentajes de asignación que mejor se adapten a su organización.

## Datos maestros

Para obtener una descripción de los campos de la tabla de datos maestros, consulte la información de la página del componente CTF - Torres de TI del producto. Para visualizar la página:

1. En la pestaña Proyecto, haga clic en **Componentes**.
2. Haga clic en el componente **CTF - Torres de TI**.

## Campos obligatorios y opcionales

Los siguientes campos son obligatorios para los informes estándar de la Torre IT:

- Nombre de la subpotencia de recursos informáticos
- Torre de recursos informáticos Nombre
- Propietario de la Torre de Recursos de TI
- Cantidad de torres de recursos informáticos
- Unidad de medida

|  |  |  |
| --- | --- | --- |
|  |  |  |

Los siguientes campos son opcionales:

- Objetivo de coste unitario anual
- Indicador de enrutamiento de activos
- Activo)Metacampo Clave de recurso
- Entrega
- Activo fijo\_ITRT Clave
- Activo fijo\_ITRT Metacampo clave
- Metacampo ITRT\_Cloud\_Key
- Clave ITRT\_LPARs
- ITRT\_SaaS Clave
- Metacampo clave Labor\_ITRT
- Mapa de referencia
- Proveedor de servicios\_ITRT Clave
- Asignación de tipos de servicio
- Sub-Tower Tablematch
- Metacampo clave Time Tracking\_ITRT
- Coste unitario Objetivo
- Metacampo clave Vendor\_ITRT

Para más información, consulte el Asesor de datos. Para abrir el Asesor de datos, abra una instancia activa de Apptio, haga clic en el icono Configuración (![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/gear_icon.png)) y, a continuación, haga clic en **Asesor de datos > Torres de TI**.

Además, hay columnas para el propietario de la torre, la cantidad y el objetivo de coste unitario. Si está aplicando la evaluación comparativa, deberá completar la columna Cantidad. Puede descargar la Lista de referencia de torres de recursos informáticos, actualizar los datos y cargar el archivo como un nuevo conjunto de datos. A continuación, puede asignar la nueva lista de referencias al conjunto de datos maestros de las torres de TI. Mientras no modifique la lista de torres y subtorres de recursos informáticos, cumplirá con la taxonomía ATUM.

## Identificadores de torre de recursos informáticos

El identificador de objeto Otros pools de costes incluye el centro de costes, la torre de recursos de TI y la subtorre.

El identificador de objeto Torres de recursos informáticos incluye la torre y la subtorre de recursos informáticos.

## Columnas necesarias para vincular conjuntos de datos

También tendrá que considerar cómo enlazar con los datos maestros de las torres de recursos informáticos desde otros conjuntos de datos. La siguiente lista destaca algunos elementos de datos específicos necesarios para vincular conjuntos de datos:

- Datos maestros de la fuente de costes:
  - Centro de costes
  - Torre de recursos informáticos
  - Subtorre de recursos informáticos
- Datos maestros de trabajo:
  - Torre de recursos informáticos
  - Subtorre de recursos informáticos
- Datos maestros de activos fijos
  - Torre de recursos informáticos
  - Subtorre de recursos informáticos
- Public Cloud Datos maestros
  - Torre de recursos informáticos
  - Subtorre de recursos informáticos
- Datos maestros de proveedores
  - Torre de recursos informáticos
  - Subtorre de recursos informáticos

Si no dispone de datos suficientes para la imputación entre Fuente de Coste y Otros Pools de Costes, deje esos costes en el objeto Fuente de Coste y no los impute sin la asignación adecuada.

Para más información sobre imputaciones, véase [Imputación de costes entre proyectos y torres de recursos de TI en el modelo de costes](https://community.apptio.com/docs/DOC-4330 "(se abre en una pestaña o una ventana nueva)").

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
