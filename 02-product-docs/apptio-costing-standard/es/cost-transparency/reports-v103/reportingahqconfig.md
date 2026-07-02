---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Informes - Configuración de AHQ y mensajes de error comunes"
breadcrumb: []
source_path: "cost-transparency/reports-v103/reportingahqconfig.html"
images:
  - "resources/images/ct_images/reportingahqconfig_1.png"
  - "resources/images/ct_images/reportingahqconfig_2.png"
  - "resources/images/ct_images/reportingahqconfig_3.png"
  - "resources/images/ct_images/reportingahqconfig_4.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Informes - Configuración de AHQ y mensajes de error comunes

## Ficha Informe (AHQ)

**Aplicación**

La configuración de la consulta Ah-hoc aparece al insertar una tabla, gráfico, cascada, etc. La configuración del uso del AHQ determinará el aspecto de los informes dentro de la superficie de informes.

**Objetos AHQ**

La siguiente imagen muestra en qué objeto se basará el informe. Los objetos elegidos actualmente son "Aplicaciones" y "Proyectos" Esto rellenará todas las perspectivas dentro del AHQ basándose en los valores de los objetos de respaldo. Apptio sólo permite informar a partir de dos objetos y filtrar a partir de un tercer objeto.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_1.png)

**NOTA** : Cuando el AHQ está bloqueado a un objeto, la opción aparecerá en gris y bloqueada al objeto de respaldo. Esto no significa necesariamente que sean los datos de ese objeto.

**Error común nº 1**

El siguiente error aparecerá cuando tenga valores de slicer/picker que estén haciendo una búsqueda a través de tres objetos diferentes.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_2.png)

**Error común nº 2**

- Este error se producirá cuando un valor slicer/picker tenga una métrica calculada asociada a los resultados del informe.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_3.png)

- La métrica calculada del tipo de modelo puede verse en la pestaña **Métricas**. El siguiente ejemplo utiliza la métrica **Fija**.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_4.png)
