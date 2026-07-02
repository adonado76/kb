---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Rellenar la tabla de datos maestros de fuentes de costes"
breadcrumb: []
source_path: "cost-transparency/configuration/populatecostsource.html"
images:
  - "resources/images/ct_images/6843_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Rellenar la tabla de datos maestros de fuentes de costes

La tabla de datos maestros de fuentes de costes define los datos necesarios para los informes relacionados con costes y presupuestos. Para rellenar la tabla, debe cargar las cifras de los costes y del presupuesto. Para rellenar la tabla de Datos Maestros de la Fuente de Costes, cargue dos conjuntos de datos: Costes reales y Costes presupuestados. Asigne los conjuntos de datos a la tabla de datos maestros de fuentes de costes.

Se aplica a: Costing Standard en TBM Studio 12.0 y posteriores

## Fuentes de datos habituales

Las cifras de costes y presupuestos suelen extraerse de fuentes como el libro mayor y el plan contable. Estos datos suelen proporcionarlos aplicaciones como Oracle, SAP, Lawson y Cognos Financial Statement Reporting. Los datos que utilice determinarán el nivel de detalle disponible y las columnas que asignará a la tabla Datos maestros de la fuente de costes.

## Varias mesas

Es posible que tenga que cargar varias tablas. A continuación se describen los cuadros típicos.

- Libro mayor (CG) - El libro mayor es la fuente de la verdad financiera en la mayoría de las empresas. Es un registro contable temporal que se utiliza para llevar la cuenta de las transacciones financieras. Las transacciones se clasifican en varias cuentas y, a menudo, por propietarios regionales o centros de costes.
- Plan de cuentas - Un plan de cuentas proporciona un listado completo de todas las cuentas de un sistema contable. Una cuenta es un registro único para cada tipo de activo, pasivo, capital, ingreso y gasto.
- Jerarquía organizativa: una jerarquía organizativa identifica cada puesto de trabajo, su función y de quién depende dentro de la organización
- Presupuesto - El presupuesto es el gasto previsto por varios niveles de granularidad en función de cómo un cliente realiza el seguimiento de sus finanzas. En la aplicación Costing Standard , el presupuesto se controla por centro de coste y por cuenta.

Las tablas se añaden a la tabla Datos maestros de origen de costes. Las tablas deben contener campos que puedan asignarse a los campos apropiados de la tabla Datos maestros de la fuente de costes.

## Datos maestros

Para una descripción de los campos de la tabla de datos maestros, véase la información en la página del componente CTF - Fuente de costes en el producto. Para visualizar la página:

1. Haga clic en la pestaña Proyecto de la cinta de opciones.
2. Haga clic en Componentes en la cinta de opciones.
3. Haga clic en el componente CTF - Fuente de costes.

## Campos obligatorios y recomendados

A continuación se enumeran los campos obligatorios y recomendados necesarios para iluminar los informes estándar de Costing Standard .

- Cuenta (obligatorio)
- Descripción de la cuenta (recomendada)
- Grupo de cuentas (recomendado)
- Subgrupo de cuentas (recomendado)
- Importe (obligatorio)
- Índice de referencia % Asignación (obligatorio)
- Subtorre de referencia (obligatorio)
- Centro de costes (obligatorio)
- Nombre del centro de costes (recomendado)
- Propietario del centro de coste (recomendado)
- Pool de costes (obligatorio)
- Subgrupo de costes (recomendado)
- Tipo de gasto (obligatorio)
- Fijo Variable (obligatorio)
- Es Depr (obligatorio)
- Es Trabajo (obligatorio)
- ID de la revista (obligatorio)
- Descripción de la línea del diario (recomendado)
- ID de la línea del periódico (obligatorio)
- Propietario (obligatorio)
- ID del proyecto (recomendado)
- Nombre del proyecto (recomendado)

## Campos de asignación de claves

La tabla Datos maestros de la fuente de costes tiene varios campos clave que se utilizan para asignar valor de la tabla Fuente de costes a las tablas Mano de obra, Libro de activos fijos, Proveedores, Otros pools de costes y Proyectos. La siguiente tabla muestra cómo se asignan los campos clave. Los metacampos son opcionales, pero si introduce un valor en un metacampo en el conjunto de datos del Maestro de orígenes de costes, deberá introducir el mismo valor en el conjunto de datos de destino.

| Este campo de la tabla de datos de Cost SourceMaster : | Debe coincidir con este campo: | En esta tabla de objetivos: |
| --- | --- | --- |
| Coste Fuente\_Labor Clave | Coste Fuente\_Labor Clave | Datos maestros de trabajo |
| Clave laboral Metafield | Fuente de costes Metacampo clave |
| Fuente de costes\_Clave de activos fijos | Fuente de costes\_Clave de activos fijos | Datos maestros de activos fijos |
| Metacampo Clave Activo Fijo | Fuente de costes Metacampo clave |
| Coste Fuente\_Vendedor Clave | Coste Fuente\_Vendedor Clave | Datos maestros de proveedores |
| Metacampo Clave de vendedor | Fuente de costes Metacampo clave |
| Fuente de costes\_Otro Pool de costes Clave | Fuente de costes\_Otro Pool de costes Clave | Fuente de costes a datos maestros de ITResource |
| Otros costes Pool Clave Metafield | Fuente de costes Metacampo clave |
| Coste Fuente\_Proyecto Clave | Coste Fuente\_Proyecto Clave | Datos maestros de proyectos |

## Mapear los datos del plan contable

Hay cinco campos en la tabla de Datos Maestros de la Fuente de Costes que deben ser mapeados para que el valor fluya correctamente desde la tabla de la Fuente de Costes al resto del modelo. Los campos son:

- **Grupo** de costes - Uno de los grupos de costes estándar de ATUM.
- **Subpool** de costes - Uno de los subpools de costes estándar de ATUM.
- **Is Depr** - Identifica una entrada como depreciada o no depreciada.
- **Fijo Variable** - Identifica un asiento como fijo o variable.
- **Discrecional/No discrecional** - Identifica una entrada como discrecional o no discrecional.

Si los datos que introduce en la aplicación no incluyen campos que se puedan asignar a los campos anteriores, tendrá que crear una tabla de asignación para proporcionar la información. Normalmente, la tabla de asignación asigna valores a cada una de las cuentas de su plan contable. A continuación se muestra una tabla de ejemplo. Fíjate en las tres últimas columnas.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6843_1.png)

A partir de esta tabla, puede utilizar la función Búsqueda para determinar los valores de cada cuenta. Por ejemplo, puede utilizar la siguiente fórmula para el campo Variable fija:

```
=Lookup(Account,Chart of Accounts
        Mapping,Account,{Fixed/Variable})
```

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
