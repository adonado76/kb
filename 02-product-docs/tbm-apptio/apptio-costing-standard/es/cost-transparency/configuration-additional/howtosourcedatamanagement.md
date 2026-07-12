---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Cómo: Fuente Data Management Configuración y tabla de errores del proyecto"
breadcrumb: []
source_path: "cost-transparency/configuration-additional/howtosourcedatamanagement.html"
images:
  - "resources/images/ct_images/4826_1.png"
  - "resources/images/ct_images/4826_2.png"
  - "resources/images/ct_images/4826_3.png"
  - "resources/images/ct_images/4826_4.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cómo: Fuente Data Management Configuración y tabla de errores del proyecto

*Ficha Informes (Proyecto SDM/Datos de promoción)*

**Aplicación** : El proyecto SDM se utiliza para copiar datos de un proyecto a otro dentro de la misma instancia. Sin embargo, se necesita la configuración adecuada para garantizar que se copian/pegan los datos correctos desde y hacia el proyecto específico. La tabla "Errores del proyecto" del menú desplegable del proyecto es una gran herramienta para ayudar a solucionar problemas de configuración.

**Configuración SDM:**

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/4826_1.png)

Para acceder a las propiedades de un botón tendrás que estar en modo edición y hacer clic con el botón derecho y elegir propiedades. Esto abrirá una vista de Propiedades que se muestra a continuación. Esa vista le permitirá elegir Acciones del visor y mirar el código fuente.

Nota:

Asegúrese de hacer clic sólo con el botón derecho, ya que si hace clic con el botón izquierdo, el botón ejecutará la copia desde el destino de origen/destino seleccionado.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/4826_2.png)

**Tabla de errores del proyecto:**

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/4826_3.png)

Si el código fuente no es correcto, aparecerá un mensaje de error después de pulsar el botón de copiar tabla. Como se muestra a continuación, el error en cuestión es que no se encuentra la tabla de respaldo. El código debe incluir la tabla de respaldo "Mainframe Storage Mapping" para que el botón se ejecute correctamente.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/4826_4.png)

Existen numerosos tipos de errores, pero todos se identificarán en la tabla de errores del proyecto, en la columna de errores.
