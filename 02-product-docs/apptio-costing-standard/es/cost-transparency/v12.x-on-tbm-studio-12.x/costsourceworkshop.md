---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller sobre fuentes de costes"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/costsourceworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller sobre fuentes de costes

Los costes se introducen en el Objeto Fuente de Coste en la parte inferior del modelo, normalmente desde el libro mayor de su organización. A continuación, los costes se asignan a los objetos del modelo mediante estrategias basadas en las mejores prácticas de gestión empresarial de la tecnología.

## Preparación de los datos de la fuente de costes

Puede empezar a preparar los datos de su fuente de costes revisando los siguientes puntos de comprobación:

1. Si aún no lo ha hecho, cargue sus datos de Fuente de Coste Actual incluyendo:
   - GL Actuals ( OpEx y ( CapEx )
   - Presupuesto GL (si procede)
   - Previsión GL (si procede)
   - Plan contable
   - Lista de centros de coste

   Necesitamos al menos el primer mes de datos GL cargados en Apptio antes de proceder.
2. Siguiendo las prácticas habituales de Apptio, clasifique cada conjunto de datos brutos en la categoría de Fuente de Coste.
3. Si procede, aplique un filtro de fechas a sus datos reales de CG.

## Acerca del identificador de fuente de costes

El identificador del objeto Fuente de costes está predefinido y no debe modificarse. Incluye:

- Pool de costes
- Subgrupo de costes
- Cuenta
- Centro de costes
- ID de proyecto
- ID de proveedor
- Metacampo UID
- Fijo Variable
- Tipo de gasto
- Identificador de referencia

Si necesita una mayor granularidad (por ejemplo, hasta las partidas individuales del libro mayor), puede rellenar el metacampo UID con el nivel de detalle adecuado.

## Acerca de las claves de las fuentes de costes

Las claves del conjunto de datos maestros de la fuente de costes están predefinidas y no deben modificarse.

| Clave | La clave de campo se basa en | Lógica |
| --- | --- | --- |
| Fuente de **costes\_Clave de activos fijos** | Es Depr Metacampo Clave Activo Fijo | IF Es Depr es "sí"  THEN  Añadir el texto del prefijo FA\_Key al metacampo Clave de activo fijo  ELSE  Establecer el texto en CS\_FA\_null |
| **Coste Fuente\_Labor Clave** | Es Trabajo Centro de costes  Pool de costes  Subgrupo de costes  Clave laboral Metafield | IF Es Labor es "sí"  THEN  Añada el texto del prefijo de Labor\_Key al centro de coste, al grupo de coste, al subgrupo de coste y al metacampo de clave de mano de obra  ELSE  Fijar el texto en CS\_Labor\_null |
| **Coste Fuente\_Vendedor Clave** | Es Vendedor Es Trabajo  Es Depr  ID de proveedor  Metacampo Clave de vendedor | IF Is Vendor es "sí" e Is Labor es "no" e Is Depr es "no"  THEN  Añada el texto del prefijo CS\_Vendor a los metacampos Vendor ID y Vendor Key  ELSE  Establecer el texto en CS\_Vendor\_null |
| **Coste Fuente\_Proyecto Clave** | Es Proyecto ID de proyecto | IF Es Proyecto = "sí"  THEN  Añadir el texto del prefijo de Project\_Key al ID del proyecto  ELSE  Establecer texto en CS\_Project\_null |
| **Fuente de costes\_Otro Pool de costes Clave** | Fuente de costes\_Clave de activos fijos Coste Fuente\_Labor Clave  Coste Fuente\_Vendedor Clave  Coste Fuente\_Proyecto Clave  Centro de costes  Otros costes Pool Clave Metafield | IF Fuente de costes\_Clave de activos fijos = CS\_FA\_null AND  Coste Fuente\_Labor Clave = CS\_Labor\_null AND  Coste Fuente\_Vendedor Clave = CS\_Vendedor\_null AND  Cost Source\_Project Clave = CS\_Project\_null  THEN  Añada el texto del prefijo CC.Map al metacampo del centro de costes y de la clave de otros grupos de costes  ELSE  Establecer el texto en CC\_ITRT\_null |
| **Coste Fuente\_Benchmark Clave** | Subtorre de referencia | Añada el prefijo de texto "Benchmark" con la subpotencia Benchmark |

Las claves anteriores están predefinidas y no deben modificarse. Si necesita una mayor granularidad, rellene el metacampo correspondiente con el nivel de granularidad que necesite. Algunas sugerencias son:

- Metacampo Clave de Activo Fijo - Código de Centro de Coste
- Metacampo Clave de proveedor - Código de centro de coste

## Origen de los costes

El objeto Fuente de coste tiene controladores de unidad que determinan qué valores se introducen en el objeto Fuente de coste. Para el modelo de costes, hay dos impulsores. La tabla siguiente describe la lógica de cada uno de los controladores. En 12.6 actualizamos los Drivers para incluir Plane y no tener la complejidad que tenemos con los drivers actuales: ( [R12.6 Change - Expense Type Change](https://community.apptio.com/docs/DOC-10629 "(se abre en una pestaña o una ventana nueva)") )

| Conductor de la unidad | El conductor se basa en | Lógica |
| --- | --- | --- |
| **OpEx Fijo** | Tipo de gasto Fijo Variable  Importe | IF El tipo de gasto es "OpEx" Y la variable fija es "Fija"  THEN  Introduzca la cantidad  ELSE  Alimentación en 0 |
| **OpEx Variable** | Tipo de gasto Fijo Variable  Importe | IF El tipo de gasto es "OpEx" Y  Variable fija es "Variable"  THEN  Introduzca la cantidad  ELSE  Alimentación en 0 |

Los otros modelos que contienen el objeto Fuente de costes (Presupuesto, Previsión, CapEx, CapEx Presupuesto, CapEx Previsión) contienen una lógica similar basada todavía en los campos Tipo de gasto, Variable fija e Importe. Esto significa que debe rellenar estos campos para introducir valores en el objeto Fuente de coste.

Normalmente, los datos de Tipo de Gasto y Variable Fija se asignan como parte del Plan de Cuentas y luego se trasladan (mediante una columna LOOKUP) al Libro Mayor.

## Columnas computadas comunes necesarias para la fuente de costes

A continuación encontrará una lista de columnas computadas que puede necesitar crear. En la mayoría de los casos, las columnas están traduciendo datos de su Plan de Cuentas y Lista de Centros de Coste al conjunto de datos del Libro Mayor. En 12.7 hemos llegado a dos nuevas características con respecto a la configuración de la Fuente de Coste y esto puede ayudar con la creación de las columnas de abajo:

- Los datos maestros del plan de cuentas se utilizarán ahora en Machine Learning para ayudar a asignar cuentas a grupos de costes en lugar de tener que pasar una hoja de cálculo de un cliente a otro. ( [Machine Learning para grupos de costes](https://community.apptio.com/docs/DOC-11548 "(se abre en una pestaña o una ventana nueva)") ).
- Además de aprovechar el Plan General de Contabilidad, ahora se puede aprovechar el Paso Unir ([Unir datos](https://community.apptio.com/docs/DOC-5078 "(se abre en una pestaña o una ventana nueva)") ) en el Libro Mayor, el Presupuesto y la Previsión de los clientes para extraer las columnas que normalmente se encuentran en el Plan General de Contabilidad. ([Asignar grupos de costes y asignar columnas](https://community.apptio.com/docs/DOC-11359 "(se abre en una pestaña o una ventana nueva)") )

Nota: Aprovechando el Paso Unir para esto eliminará la necesidad de todas las Búsquedas que contienen el Plan de Cuentas a continuación

- Búsqueda de la descripción de la cuenta del plan contable en el conjunto de datos del libro mayor
- Búsqueda de grupos de costes del plan contable en el conjunto de datos del libro mayor
- Búsqueda de la subcarpeta de costes del plan contable en el conjunto de datos del libro mayor
- Búsqueda de fijos/variables del plan contable en el conjunto de datos del libro mayor
- Búsqueda de discrecional/no discrecional del plan contable en el conjunto de datos del libro mayor
- Búsqueda del grupo de cuentas del plan contable en el conjunto de datos del libro mayor
- Búsqueda de subgrupos de cuentas del plan contable en el conjunto de datos del libro mayor
- Búsqueda del Propietario del Centro de Coste de la lista de Unidades Funcionales en el conjunto de datos GL
- Búsqueda del propietario de TI de la lista de unidades funcionales en el conjunto de datos de GL
- ¿Está el indicador Depreciación Sí/No basado en la Subcartera de Costes en el conjunto de datos GL?
- ¿Está el indicador Mano de obra Sí/No basado en la subcarpeta de costes en el conjunto de datos GL?
- El indicador Proyecto Sí/No se basa en el código de proyecto del conjunto de datos GL

Para todas estas columnas calculadas, es posible que también tenga que crearlas en los conjuntos de datos de previsión y presupuesto correspondientes.

## Asignar datos a los datos maestros de fuentes de costes

Asigne sus datos de origen de costes al conjunto de datos maestros de origen de costes. La mayor parte de la cartografía se explica por sí misma. No hay requisitos cartográficos inusuales. En 12.7 puede utilizar la función Column Map de su conjunto de datos brutos para asignarlos a los datos maestros de la fuente de costes ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") )

Puntos a tener en cuenta:

- Asigne su conjunto de datos reales GL al conjunto de datos maestros de la fuente de costes.

## Revisar el objeto Fuente de costes en los modelos

Una vez que haya asignado sus datos a los datos maestros de la fuente de costes, puede seguir adelante y revisar los objetos de la fuente de costes en los modelos. Revise los siguientes modelos y asegúrese de que los valores fluyen al objeto Fuente de Coste adecuadamente.

- Coste
- Presupuesto
- Previsión
- CapEx
- CapEx Presupuesto
- CapEx Previsión

## Revisar los informes de las fuentes de costes

Los siguientes informes se actualizan una vez configurado el objeto Fuente de coste:

- Análisis de grupos de costes
- Detalles del análisis del pool de costes
- Coste Fuente Validez
- Costing Standard Cargar conjunto de datos
- Dimensiones de los datos - Fuente de costes
- Cuadro de mando de las dimensiones de los datos
- Cuadro de mandos de Data Dimensions - Inicio
- Análisis financiero
- Análisis financiero - CapEx Transaction
- Análisis financiero - CapEx Trend
- Análisis financiero - OpEx Transaction
- Análisis financiero - OpEx Trend
- Análisis financiero
- Revisión de las desviaciones financieras
- Ayuda - Tabla de asignación
- IT Finanzas - Transacción contable - CapEx Detail
- Finanzas de TI
- Cuadro de mandos de la tuneladora
- Detalles de la transacción
- Transacciones
- Detalle de la desviación

Para ver los detalles de estos informes (incluida la navegación, las funciones, los objetivos y las preguntas a las que responde cada informe), consulte la Guía del usuario de Costing Standard en la Ayuda en línea.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
