---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller de unidades de negocio"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/buworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller de unidades de negocio

Preparación de los datos de su Unidad de Negocio

1. Si aún no lo ha hecho, cargue los datos de su unidad de negocio incluyendo:
   - Lista de unidades de negocio, incluidos los efectivos
2. Siguiendo las prácticas habituales de Apptio las prácticas habituales, clasifique cada conjunto de datos brutos en la categoría de Unidades de Negocio.
3. Si procede, aplique un filtro de fechas a los datos de su unidad de negocio.

## Acerca del identificador de unidad de negocio

El identificador del conjunto de datos maestros de unidades de negocio es la columna Ident. Puede tener hasta cinco niveles integrados en la jerarquía de su unidad de negocio. Los cinco niveles definidos en Apptio son:

- Consejo de Administración
- Unidad de negocio
- Programa
- Proyecto
- Ubicación

La columna Ident suele ser una concatenación de estas cinco columnas. Sin embargo, puede decidir que no necesita los cinco niveles como el nivel de detalle que necesita en sus informes. Por ejemplo, puede decidir utilizar sólo la columna Unidad de Negocio como columna Ident.

## Acerca de las Claves de las Unidades de Negocio

La mayoría de las claves del conjunto de datos maestros de asignación de unidades de negocio están definidas por el usuario. La lógica recomendada figura en el cuadro siguiente.

| Clave | La clave de campo se basa en | Lógica recomendada |
| --- | --- | --- |
| **Asignaciones de servicio Clave Direct\_BU (En 11.6 )** | Definida por el usuario | ="Service Allocations\_BU" && Identificador de unidad de negocio |
| **Clave Proyecto\_BU** | Unidad de negocio | ="Project\_BU"&&Business Unit&&Project\_BU Metacampo clave |

## Columnas computadas comunes necesarias para la unidad de negocio

La única columna computada que puede necesitar crear es la columna Ident si desea concatenar datos.

## Asignación de datos a los datos maestros de asignación de unidades de negocio

Asigne los datos de su unidad de negocio al conjunto de datos maestros Asignaciones de unidades de negocio. La mayor parte de la cartografía debería explicarse por sí misma en este punto. En 12.7 puede utilizar la función de asignación de columnas en su conjunto de datos sin procesar para asignarlos a los datos maestros de asignación de unidades de negocio ([asignar columnas](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") )

## Revisar el objeto Asignación de unidades de negocio en los modelos

| Modelo | Acciones |
| --- | --- |
| **Coste** | Asegúrese de que los valores fluyen hacia el objeto Asignación de unidad de negocio. Desde Asignaciones de servicio directas a Asignación de unidad de negocio, asigne utilizando la Referencia basada en datos con una ponderación par (esta es la configuración por defecto). Las claves que unen la Asignación Directa de Servicios con la Asignación de Unidades de Negocio son las columnas Clave de Asignación Directa de Servicios\_BU en ambos conjuntos de datos.  Desde Asignación indirecta de servicios a Asignación de unidades de negocio, asigne utilizando el recuento de personal u otras opciones de asignación.  De Proyectos a Asignación de unidades de negocio, asigne utilizando la Referencia basada en datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen los Proyectos con las Asignaciones de las Unidades de Negocio son las columnas Clave\_Proyecto\_BU en ambos conjuntos de datos. |
| **Presupuesto** | Asegúrese de que los valores fluyen hacia el objeto Asignación de unidad de negocio. Desde Servicios Empresariales a Imputación de Unidades de Negocio, puede imputar costes utilizando dos opciones posibles:   - Por efectivos - Por ingresos   Para asignar por recuento, pondere la asignación por Maestro de Asignación de Unidades de Negocio Data.Employees. |
| **CapEx** | Asegúrese de que los valores fluyen hacia el objeto Asignación de unidad de negocio. Desde Asignaciones de servicio directas a Asignación de unidad de negocio, asigne utilizando la Referencia basada en datos con una ponderación par (esta es la configuración por defecto). Las claves que unen la Asignación Directa de Servicios con la Asignación de Unidades de Negocio son las columnas Clave de Asignación Directa de Servicios\_BU en ambos conjuntos de datos.  Desde Asignaciones de servicios indirectos a Asignación de unidades de negocio, asigne utilizando la asignación basada en tablas.  De Proyectos a Asignación de unidades de negocio, asigne utilizando la Referencia basada en datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen los Proyectos con las Asignaciones de las Unidades de Negocio son las columnas Clave\_Proyecto\_BU en ambos conjuntos de datos. |

## Revisar los informes de las unidades de negocio

Los siguientes informes se actualizan una vez configurado el objeto Unidades de Negocio:

- Revisión de las unidades de negocio
- Revisión de la Unidad de Negocio - Detalles
- Cartera de unidades de negocio
- Lista de unidades de negocio
- Impacto de la retirada de aplicaciones
- Validez de la asignación de unidades de negocio
- Unidad de negocio
- Unidad de negocio - Departamento
- Factura de la Unidad de Negocio
- Servicio - BU Tendencia de consumo
- Dimensiones de los datos - Unidades de negocio

Para ver los detalles de estos informes (incluida la navegación, las funciones, los objetivos y las preguntas a las que responde cada informe), consulte la Guía del usuario de Costing Standard disponible en la Ayuda en línea.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
