---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller sobre inmovilizado"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/fixedassetsworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller sobre inmovilizado

## Preparación de los datos del inmovilizado

Puede empezar a preparar sus Activos Fijos revisando los siguientes puntos de control:

1. Si aún no lo ha hecho, cargue su Registro de Inmovilizado.
2. Siguiendo las prácticas habituales de Apptio las prácticas habituales, clasifique cada conjunto de datos brutos en la categoría de Activos Fijos.
3. Si procede, aplique un filtro de fechas a sus datos de inmovilizado.

## Acerca del identificador del ledger de activos fijos

El Identificador para el objeto del Libro de activos fijos se rellena cuando se asignan datos al conjunto de Datos maestros de activos fijos. Considere el nivel de detalle que necesita tanto para el modelado como para la elaboración de informes y establezca el Identificador. Si dispone de un Registro de Activos Fijos, éste suele enumerar cada activo fijo individual, por lo que puede utilizar el ID de cada activo.

## Acerca de las claves del inmovilizado

Las claves para el conjunto de datos maestros de activos fijos son todas generadas por el sistema y no deben ser alteradas.

| Clave | La clave de campo se basa en | Lógica |
| --- | --- | --- |
| **Fuente de costes\_Clave de activos fijos** | Fuente de costes Metacampo clave | Añada el texto FA\_Key al metacampo Clave de la fuente de costes |
| **Clave Asset\_Resource** | Torre de recursos informáticos  Subtorre de recursos informáticos | Añada el texto Recurso\_activo a la Torre de recursos informáticos y a la Subtorre de recursos informáticos |
| **Asset\_Storage Clave** | Sin campos predefinidos | Considere la posibilidad de utilizar el ID de activo fijo suponiendo que cada uno de sus dispositivos de almacenamiento utilice el mismo ID para identificar de forma exclusiva cada activo. |
| **Clave\_Servidor\_de\_activos** | Sin campos predefinidos | Considere la posibilidad de utilizar el ID de activo fijo suponiendo que cada uno de sus servidores utilice el mismo ID para identificar de forma exclusiva cada activo. |

Sólo necesita rellenar la Clave Asset\_Storage y la Clave Asset\_Server si está implementando los componentes Storage y Servers. De lo contrario, esas teclas pueden dejarse en blanco.

## Columnas computadas comunes necesarias para los activos fijos

No es necesario crear ninguna columna de cálculo específica. Variará en función de sus datos. Sin embargo, aquí hay un par a tener en cuenta:

- Búsqueda de la torre de recursos de TI desde un centro de costes al conjunto de datos de asignación de torres de TI en el conjunto de datos de activos fijos
- Búsqueda de la subtorre de recursos de TI desde un centro de costes al conjunto de datos de asignación de torres de TI en el conjunto de datos de activos fijos

Según proceda, cree las columnas calculadas que necesite para asignar sus datos al conjunto de datos maestros de activos fijos. Recuerde que puede consultar el conjunto de datos maestros para determinar qué columna puede ser necesaria.

Asegúrese de que está creando las columnas en la transformación de los datos de activos fijos (no en el conjunto de datos sin procesar).

## Asignar datos a los datos maestros de activos fijos

Asigne sus datos de activos fijos al conjunto de datos maestros de activos fijos. La mayor parte de la cartografía debería explicarse por sí misma en este punto.

Si ha rellenado el metacampo Clave de activo fijo en el conjunto de datos maestros Fuente de coste, asegúrese de rellenar el valor correspondiente en el metacampo Clave de fuente de coste en el conjunto de datos maestros Activos fijos. En 12.7 puede utilizar la función de asignación de columnas en su conjunto de datos sin procesar para asignarlos a los datos maestros de activos fijos (Asignar columnas)

Puntos a tener en cuenta:

- Asigne su conjunto de datos de activos fijos al conjunto de datos maestros de activos fijos.

## Revise el objeto Libro de activos fijos en los modelos

| Modelo | Acciones |
| --- | --- |
| **Coste** | Asegúrese de que los valores fluyen desde el objeto Fuente de coste al objeto Libro de activos fijos.  De la Fuente de costes al Libro de activos fijos, asigne utilizando la Referencia basada en datos ponderada por el Importe de la amortización (esta es la configuración por defecto).Las claves que unen los dos conjuntos de datos incluyen los Metacampos Fuente de costes/Clave de activos fijos. |
| **Presupuesto** | Asegúrese de que los valores fluyen desde el objeto Fuente de coste al objeto Libro de activos fijos.  Si los valores no fluyen, es posible que tenga que marcar la casilla de verificación Crear automáticamente una relación de muchos a muchos.  De la Fuente de costes al Libro de activos fijos, asigne utilizando la Referencia basada en datos ponderada por el Importe de la amortización (esta es la configuración por defecto).Las claves que unen los dos conjuntos de datos incluyen los Metacampos Fuente de costes/Clave de activos fijos. |
| **Previsión** | Asegúrese de que los valores fluyen desde el objeto Fuente de coste al objeto Libro de activos fijos.  Si los valores no fluyen, es posible que tenga que marcar la casilla de verificación Crear automáticamente una relación de muchos a muchos.  De la Fuente de costes al Libro de activos fijos, asigne utilizando la Referencia basada en datos ponderada por el Importe de la amortización (esta es la configuración por defecto).Las claves que unen los dos conjuntos de datos incluyen los Metacampos Fuente de costes/Clave de activos fijos. |

Las torres de TI aún no se han asignado, por lo que todavía no fluirán valores al objeto Torres de recursos de TI.

## Informes sobre activos fijos

Realice un seguimiento de la depreciación del inmovilizado y utilice los nuevos informes de depreciación del inmovilizado para tomar decisiones más informadas sobre los costes actuales de las infraestructuras y los costes de sustitución previstos.

Lo que Apptio responde:

- ¿Qué amortización queda para el inmovilizado existente por periodos de tiempo?
- ¿Qué activos están totalmente amortizados?

Activos fijos

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
