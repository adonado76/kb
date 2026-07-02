---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "CTF - Componente Fuente de Costes: instalar y configurar"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-cs-component.html"
images:
  - "resources/images/ct_images/ctfcostsource.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - Componente Fuente de Costes: instalar y configurar

Tras instalar los componentes y configurar el tiempo para el proyecto, el siguiente paso es cargar los datos de la Fuente de Costes en la aplicación y asignarlos a las tablas de datos maestros.

## Introducción

Cuando creó el proyecto Costing Standard , la aplicación creó las tablas de datos de apoyo y las tablas de datos maestros. Varias tablas se rellenan con entradas estándar. La mayoría de las tablas están en blanco y deben rellenarse con sus datos.

## Conjuntos de datos poblados

Los siguientes conjuntos de datos contienen entradas estándar:

- Lista de referencia del fondo de costes
- Lista de referencia de la Torre de Recursos Informáticos

No es necesario cargar datos en estos conjuntos de datos.

## Conjuntos de datos en blanco

Las siguientes tablas de datos maestros están en blanco y debe rellenarlas con sus datos:

- Datos maestros de fuentes de costes
- Datos maestros de activos fijos
- Datos maestros de trabajo
- Datos maestros de proyectos
- Fuente de costes a datos maestros de recursos de TI

## Cargar datos en una tabla de datos maestros

Hay varios pasos para cargar datos en una tabla de datos maestros:

Cargue los datos en la aplicación como una tabla independiente.

1. Si necesita modificar la tabla (por ejemplo, g.: añadir columnas), añada pasos al proceso de transformación de la tabla. El objetivo es asegurarse de que la tabla incluye todos los datos que necesitará cuando asigne los datos a la tabla de datos maestros. No debería tener que utilizar sentencias IF o Lookups al asignar el conjunto de datos al conjunto de datos maestro.
2. Asigne el conjunto de datos cargado al conjunto de datos maestro.

Para obtener más información sobre cómo realizar estos pasos, consulte [Cargar datos en la aplicación Costing Standard](loaddata.html "Las tablas de datos maestros proporcionan una forma de asignar sus datos a los datos requeridos por la aplicación CT. La siguiente información describe cómo cargar datos en la aplicación.")  y [Asignar datos a una tabla de datos maestros](maptomaster.html "Después de cargar una tabla de datos de origen y transformarla si es necesario, puede asignarla a una tabla de datos maestros. Siga las siguientes instrucciones para asignar datos a una tabla de datos maestros.").

Las instrucciones paso a paso para cargar sus datos en cada una de las tablas de datos maestros se describen en los siguientes temas:

- [Rellenar la tabla de datos maestros de fuentes de costes](populatecostsource.html "La tabla de datos maestros de fuentes de costes define los datos necesarios para los informes relacionados con costes y presupuestos. Para rellenar la tabla, debe cargar las cifras de los costes y del presupuesto. Para rellenar la tabla de Datos Maestros de la Fuente de Costes, cargue dos conjuntos de datos: Costes reales y Costes presupuestados. Asigne los conjuntos de datos a la tabla de datos maestros de fuentes de costes.")
- [Rellenar la tabla de datos maestros de activos fijos](populatefixedasset.html "La tabla Datos maestros de inmovilizado define los datos necesarios para \"iluminar\" los informes relacionados con costes y presupuestos. Para rellenar el conjunto de datos, debe cargar las cifras de los costes de los activos fijos y asignarlas a la tabla de datos maestros de activos fijos")
- [Rellenar la tabla de datos maestros de mano de obra](populatelabor.html "La tabla de Datos Maestros de Mano de Obra define los datos necesarios para \"iluminar\" los informes relacionados con costes y presupuestos. Los datos ofrecen un análisis en profundidad de los costes laborales, tanto de los ETC como de los empleados contratados, incluida la comparación de los costes reales y los efectivos con el plan. Para rellenar la tabla de datos maestros de mano de obra, cargue una tabla de datos de mano de obra y asígnela a la tabla de datos maestros de mano de obra.")
- [Rellenar la tabla Fuente de costes en datos maestros de recursos de TI](populatecostsource2.html "Para rellenar la tabla Fuente de costes a datos maestros de recursos de TI, cargue una tabla de datos que defina el porcentaje de los otros costes a asignar a cada centro de coste. Después de crear la tabla, asígnela a la tabla Fuente de costes a datos maestros de recursos de TI.")

## ¿Debo transformar los datos antes o después de importarlos?

Cuanto más se ajusten sus datos a las tablas de datos maestros, más fácil será asignar los datos. Cuando sea posible, genere los datos necesarios desde sus aplicaciones externas antes de importarlos a la aplicación CTF. Si no es posible, puede transformar los datos después de importarlos. Ambos enfoques son satisfactorios.

## Utilizar tablas de asignación

Si los datos que introduce en la aplicación no incluyen los datos necesarios para asignar los campos a la tabla de datos maestros de destino, deberá crear una tabla de asignación para proporcionar la información. Normalmente, la tabla de datos de asignación asigna valores a cada una de las unidades de una tabla de datos maestra. Por ejemplo, puede que necesite añadir información sobre amortización, inmovilizado /var iable y discrecional/no discrecional a una tabla del libro mayor basada en el número de cuenta. Las tres últimas columnas de la tabla de asignación que se muestra a continuación pueden utilizarse para proporcionar esta información utilizando la función de búsqueda.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ctfcostsource.png)

A partir de la tabla anterior, puede utilizar la función Búsqueda para determinar los valores de cada cuenta. Por ejemplo, puede utilizar la siguiente fórmula para el campo Variable fija:

```
=Lookup(Account,Chart of Accounts
        Mapping,Account,{Fixed/Variable})
```

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
