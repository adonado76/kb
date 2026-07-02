---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Valores de las etiquetas en Azure a Apptio Schema"
breadcrumb: []
source_path: "cost-transparency/configuration/tagazuretoschema.html"
images:
  - "resources/images/ct_images/azure_ea.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Valores de las etiquetas en Azure a Apptio Schema

Este artículo le ayudará a etiquetar valores en Azure según el esquema Apptio. Aunque este artículo explica cómo analizar los valores de la columna Etiqueta de la factura de Azure para que pueda proporcionar información de etiquetado relevante en Apptio, tenga en cuenta que otras columnas de Azure, incluidas Cuenta, Suscripción, Centro de costes y Departamento, pueden asignarse directamente a Apptio. El objetivo de este artículo es orientarle sobre cómo asignar columnas o etiquetas a Apptio desde Azure.

Se aplica a: Apptio Costing Standard en TBM Studio 12.3.3 y posteriores

## Analizar los valores de las etiquetas en Azure

Las etiquetas de recursos están disponibles en el archivo de facturación detallada Azure disponible en su portal EA e ingerible en Apptio a través de Datalink (Classic). Estas etiquetas se codifican como una cadena con formato JSON dentro de la columna Etiquetas de la factura. El análisis sintáctico de los valores de las etiquetas para convertirlos en atributos utilizables requiere alguna configuración adicional en Apptio. Este documento le guiará a través de los pasos necesarios para analizar los valores de etiqueta deseados a partir de la cadena con formato JSON y convertirlos en nuevas columnas en el conjunto de datos Apptio.

Ejemplo:

{ "Dept": "Engineering", "Function": "Product Development", "Environment": "Development", "CostCenter": "4739"}

Los pasos descritos a continuación funcionarán para una sola etiqueta y deben repetirse para cada etiqueta que desee analizar de la columna Etiquetas.

Nota: **Definiciones utilizadas en los pasos siguientes** - Cada etiqueta se compone de una estructura común denominada par clave-valor. Con respecto a las etiquetas, piense en la clave del par clave-valor como el nombre de la columna y el valor como los datos almacenados en esa columna. En el ejemplo incluido en los pasos siguientes, analizaremos los valores de una etiqueta Entorno, donde la clave es igual a Entorno y el valor son los datos asociados a la clave Entorno.

## Resumen de tareas

1. Abra TBM Studio en Apptio y consulte Azure EA Detailed Bill Raw.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/azure_ea.png)
2. En Pasos, añada un paso Fórmulas.
3. Cree una nueva columna llamada "Entorno".
4. Set Entorno =IF(FIND("Entorno", Etiquetas)>0, split((RIGHT(Etiquetas,LEN(Etiquetas)-FIND("Entorno", Etiquetas)-(LEN("Entorno")+2))),1,""""), "")
5. Para aplicar esto a otras etiquetas en su entorno Apptio, copie la fórmula del paso 2 anterior y copie/sustituya "Entorno" por el valor clave de la etiqueta que desee analizar de la columna Etiquetas.
6. Guarde y compruebe los cambios una vez que haya completado todas las ediciones en su área de trabajo.

Nota:

- La operación básica aquí consiste en encontrar la palabra "Medio ambiente" y, a continuación, a partir de dos caracteres después de su final, agarrar todo lo que hay en la columna de etiquetas hasta el siguiente símbolo **"**. Tenga en cuenta que Apptio distingue entre mayúsculas y minúsculas, por lo que tanto el valor como las mayúsculas deben coincidir.
- Apptio recomienda una columna por etiqueta. Evite realizar esta operación en varias columnas porque es más difícil limpiar y optimizar su configuración en el futuro, y puede tener un impacto negativo en el rendimiento.

## Asigne las etiquetas Azure al esquema Apptio

Una vez analizadas las etiquetas Azure en la tabla Azure EA Detailed Bill Raw, estas columnas se pueden utilizar para mapearlas en el esquema Apptio mapeándolas en el conjunto de datos maestros Azure EA Detailed Bill. Tenga en cuenta que puede seguir los siguientes pasos para asignar también otras columnas de Azure (Cuenta, Suscripción, Centro de costes, Departamento, etc.).

Para asignar etiquetas Azure al esquema Apptio :

1. Vaya a Azure EA Detailed Bill Master Data y compruébelo.
2. En Pasos, seleccione Añadir > Editar.
3. Asigne las columnas que se analizaron desde la columna Etiqueta en la sección anterior y cualquier otra columna que desee asignar. A continuación se muestran algunas columnas de ejemplo que se pueden asignar:
   - Aplicación
   - Centro de costes
   - Entorno
   - Proyecto
   - Finalidad
   - Propietario del sistema
4. Guarda las asignaciones.
5. Guarde Azure EA Detailed Bill Master Data y compruébelo.

Esto rellenará los datos en el conjunto de datos maestros según lo configurado.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
