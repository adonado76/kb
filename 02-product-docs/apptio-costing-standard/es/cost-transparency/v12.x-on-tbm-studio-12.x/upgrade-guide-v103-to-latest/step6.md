---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Paso 6: Actualizar todos los demás componentes de la rama de actualización"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step6.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Paso 6: Actualizar todos los demás componentes de la rama de actualización

Todos los componentes instalados deben actualizarse a la nueva versión de la plantilla. Se recomienda empezar por los componentes de nivel inferior (por ejemplo, componentes CTF-, luego CT Apps, etc.). Sin embargo, no es necesario seguir un orden exacto. En este ejemplo, los componentes instalados corresponden a una configuración CT Base en la plantilla v103.

Nota: Si abre el proyecto Costing Standard durante el proceso de actualización, observará que algunos de los enlaces de navegación están rotos en la rama de actualización. Se resolverán cuando se hayan actualizado todos los componentes.

Repita los pasos 4 y 5 para seguir actualizando el resto de componentes. Se recomienda el siguiente orden; sin embargo, es posible que no tenga todos estos componentes instalados en su entorno:

- Componente de **revisión de la tuneladora** :
  - Desactivar el componente.
  - Marque en el cambio, "Revisión TBM: desactivar componente"
- **ATUM v2.0** componente:
  - Desactivar el componente.
  - Compruebe en el cambio, " ATUM v2.0: desactivar componente"
- **CTF-Componente Fuente de Costo** :
  - Revertir cualquier métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Reasigne los archivos de origen al conjunto de datos maestros de origen de costes, si ha revertido los cambios del conjunto de datos.
  - Marque en el cambio, "CTF- Fuente de costes: revertir métricas calculadas, actualizar componente"
- **CT- Componente de calidad** :
  - Revertir cualquier métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Marque en el cambio, "CT- Calidad: actualizar componente"
- Componente **CTF-Laboral** :
  - Revertir cualquier métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Reasigne los archivos de origen al conjunto de datos maestros de mano de obra, si revirtió los cambios del conjunto de datos.
  - Marque en el cambio, "CT- Mano de obra: actualizar componente"
- Componente **CTF- IT Towers** :
  - Revertir cualquier métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Reasigne los archivos de origen al conjunto de datos maestros de la torre de recursos de TI.
  - Compruebe en el cambio, "CTF- IT Towers: revertir métricas calculadas, actualizar componente"
- **CTF-Componente de seguimiento del tiempo** :
  - Revertir cualquier métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Reasigne los archivos de origen al conjunto de datos maestros de seguimiento del tiempo, si revirtió los cambios del conjunto de datos.
  - Marque en el cambio, "CTF- Seguimiento Horario: actualizar componente"
- Componente **Proyectos del FTL** :
  - Revertir cualquier métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Reasigne los archivos de origen al conjunto de datos maestros de proyectos, si revirtió los cambios del conjunto de datos.
  - Marque en el cambio, "CTF- Proyectos: actualizar componente"
- Componente **CTF-Servicio en la nube** :
  - Revierta cualquier conjunto de datos, métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Compruebe en el cambio, "CTF- Cloud Service: revertir métricas calculadas, actualizar componente"
- Componente **CTF- Amazon Web Services** :
  - Revierta cualquier conjunto de datos, métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Compruebe en el cambio, "CTF- Amazon Web Services : componente de actualización"
- Componente **CTF- Azure** :
  - Revierta cualquier conjunto de datos, métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Compruebe en el cambio, "CTF- Azure : componente de actualización"
- **CT Apps-Componente de aplicaciones** :
  - Revertir cualquier métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Reasigne los archivos de origen al conjunto de datos maestros de aplicaciones, si revirtió los cambios del conjunto de datos.
  - Compruebe en el cambio, "CT Apps- Aplicaciones: revertir métricas calculadas, actualizar componente"
- Componente **CT- Unidades de Negocio** :
  - Revertir cualquier métrica calculada o personalización de informes.
  - Actualiza el componente.
  - Reasigne los archivos de origen al conjunto de datos maestros de la unidad de negocio, si revirtió los cambios del conjunto de datos.
  - Marque en el cambio, "CT- Unidades de Negocio: revertir métricas calculadas, actualizar componente"

## Información relacionada

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
