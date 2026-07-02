---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Solución de problemas de los informes principales"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Informes principales"
source_path: "studio/new-uc/reference/report-studio-reference/troubleshoot-master-reports.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Solución de problemas de los informes principales

**Problemas habituales y soluciones**

|  |  |  |
| --- | --- | --- |
| **Emitir** | **Posible causa** | **Solución** |
| El maestro no aparece en el menú desplegable | El informe no se ha guardado ni registrado tras habilitar la opción «Informe maestro» | Guarda y confirma el informe maestro; espera a que finalice el cálculo |
| Los componentes situados dentro del cuadro de grupo principal no están agrupados | Comportamiento esperado: los cuadros de grupo pierden la función de agrupación en los informes secundarios | Utiliza los cuadros de grupo en las plantillas únicamente para dar estructura visual; añade grupos funcionales en los informes secundarios |
| El contenido secundario se muestra en todas las pestañas | Componentes colocados sobre un componente con pestañas en un informe secundario | Añade el contenido de las pestañas solo en el informe maestro; evita colocar componentes en las pestañas de los informes secundarios |
| No se puede eliminar el informe maestro | Intento de eliminar un maestro estándar (OOTB) | Las plantillas estándar no se pueden eliminar; utiliza la opción «Guardar como» para crear una versión personalizada que puedas modificar o eliminar |
| El botón «Master» lleva a un informe incorrecto | El botón «Texto de la wiki» sin «Datos» URL utiliza el contexto actual del informe | Especificar un « URL » explícito para los botones de navegación en los informes maestros |

**Tema principal:** [Informes maestros](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
