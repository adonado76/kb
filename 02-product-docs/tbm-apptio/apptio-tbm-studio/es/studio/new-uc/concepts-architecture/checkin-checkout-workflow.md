---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Proceso de salida y llegada"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Ciclo de vida de la compilación y la implementación"
source_path: "studio/new-uc/concepts-architecture/checkin-checkout-workflow.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Proceso de salida y llegada

En TBM Studio, todos los elementos —incluidas las tablas de datos, las métricas, las perspectivas, los modelos y los informes— son documentos. Para editar cualquier documento, primero debes sacarlo. Este exclusivo mecanismo de bloqueo evita conflictos cuando varios usuarios trabajan en el mismo proyecto.

**Sacar un documento**

Al extraer un documento, se establece un bloqueo exclusivo que impide que otros lo editen al mismo tiempo. Para sacar un documento:

1. Selecciona el documento en el Explorador de proyectos.
2. En la pestaña Inicio, en el grupo Documento, haz clic en Desproteger.
3. Aparecerá un icono de salida junto al nombre del documento, y el nombre del documento se mostrará en naranja en la pestaña situada en la parte inferior del espacio de trabajo.

Mientras el documento esté desprotegido, puedes guardar los cambios sin que se actualicen los cálculos. Esto te permite realizar múltiples modificaciones de forma eficiente antes de compartirlas con el equipo.

**Registrar un documento**

Al guardar un documento, se libera el bloqueo y se inicia un nuevo cálculo. Los cambios que realices serán visibles para los demás usuarios en el entorno de prueba. Para registrar un documento:

1. En la pestaña Inicio, en el grupo Documento, haz clic en Archivar.
2. El documento se envía a Staging y comienzan los cálculos.

Aviso:

Comprueba siempre los cambios antes de guardarlos. Revisa las tablas de datos en busca de errores, comprueba las repercusiones de la asignación y comprueba los informes afectados. Las entradas de datos mal validadas pueden provocar problemas de rendimiento o cálculos incorrectos en el entorno de prueba.

**Deshacer, Rehacer y Revertir**

Mientras los documentos están en proceso de revisión, dispones de varias opciones para gestionar los cambios:

**Las funciones «Deshacer» y «Rehacer»** son útiles para revertir cambios pequeños y aislados, como por ejemplo:

- Colocación de los elementos del informe dentro de un informe
- Modificaciones puntuales en la configuración de los elementos (texto de los botones, contenido HTML)
- Modificaciones en las fórmulas del paso de fórmulas de una tabla

**«Deshacer cambios»** descarta todos los cambios realizados en los documentos seleccionados que se han extraído y anula por completo la extracción. Para revertir:

1. En la pestaña «Inicio», en el grupo «Documento», haz clic en «Deshacer cambios».
2. Selecciona los documentos que deseas revertir y haz clic en «Revertir desglose».

**Buenas prácticas para el registro**

Seguir una rutina constante de comprobación ayuda a mantener la estabilidad del proyecto:

|  |  |
| --- | --- |
| **Práctica** | **Por qué es importante** |
| Revisa los datos antes de subirlos | Comprueba que los archivos contengan datos, estén correctamente delimitados y tengan las columnas esperadas |
| Habilitar la validación de cardinalidad | Detecta los problemas de calidad de los datos en una fase temprana, antes de que se extiendan por todo el modelo |
| Validar los efectos de la asignación | Los cambios en los datos o en la configuración pueden afectar a las asignaciones de formas imprevistas |
| Comprobar los informes afectados | Comprueba que los informes se carguen correctamente y muestren los valores esperados |
| Coordinar los registros de llegada | Acordad los momentos de comprobación (por ejemplo, a la hora del almuerzo y al final de la jornada) para reducir al mínimo las colas de cálculo |
| No realices el check-in durante las promociones | Asegúrate de que nadie esté a la espera de pasar a producción antes de que realices el check-in |
