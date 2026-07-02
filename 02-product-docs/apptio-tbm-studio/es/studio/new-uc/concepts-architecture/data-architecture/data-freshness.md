---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Actualidad y validación de los datos"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura de datos"
source_path: "studio/new-uc/concepts-architecture/data-architecture/data-freshness.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Actualidad y validación de los datos

Un análisis preciso de los costes depende de que se disponga de datos puntuales y de alta calidad. TBM Studio ofrece varios mecanismos que le ayudan a supervisar la actualidad de los datos y a validar su calidad a lo largo de todo el proceso.

## Actualidad de los datos

La actualidad de los datos permite comprobar si estos se han actualizado según el calendario de actualización previsto. Cuando se configura una tabla con un ciclo de actualización mensual, TBM Studio comprueba si los datos de cada mes se han cargado realmente a tiempo.

**Por qué es importante la frescura**

Los datos obsoletos dan lugar a modelos de costes inexactos. Si no se ha cargado el archivo del libro mayor de enero y el modelo realiza los cálculos utilizando los datos de diciembre (o sin datos), las asignaciones y los informes resultantes serán engañosos. El control de la actualidad de los datos te ayuda a detectar estas lagunas antes de que afecten a la toma de decisiones.

**Control de la frescura**

TBM Studio ofrece dos funciones de control de la frescura:

- **Comprobación de caducidad de datos:** notificaciones por correo electrónico configurables que avisan a los usuarios designados cuando los datos cargados han caducado, según el ciclo de actualización de la tabla. Puedes indicar las direcciones de correo electrónico de los destinatarios, el número de días tras la fecha de caducidad en los que se enviará la primera notificación y si se deben enviar recordatorios diarios hasta que se carguen datos actualizados.
- **Panel de control de actualidad de los datos:** accesible desde la pestaña «Proyecto», este panel muestra un resumen de todas las tablas con su estado de caducidad y una lista de las reglas de actualidad configuradas.

## Validación de datos

La validación garantiza que los datos que se introducen en el proceso cumplan con los estándares de calidad esperados. TBM Studio ofrece validación en varios niveles:

**Validación de esquemas**

- **Detección del tipo de columna:** La plataforma detecta automáticamente si las columnas son de tipo «Etiqueta» (texto), «Numérico» o «Estado». Las detecciones erróneas se detectan durante la importación y pueden anularse manualmente.
- **Campos obligatorios:** Las tablas de transformación que se asocian a conjuntos de datos maestros deben contener campos específicos. Los campos obligatorios que faltan provocan errores en el proceso que bloquean los cálculos posteriores del modelo.
- **Validación de cardinalidad:** comprueba que los datos se ajusten a los patrones esperados durante la carga.

**Validación de tablas editables**

Las tablas editables admiten reglas de validación configurables que detectan las entradas de usuario no válidas antes de que lleguen al proceso:

- Validación del rango numérico (por ejemplo, los valores deben estar comprendidos entre 0 y 100).
- Compulsión de los campos obligatorios.
- Listas de valores predefinidos mediante menús desplegables (enumeraciones estáticas o valores dinámicos basados en fórmulas).
- Lógica de menús desplegables en cascada que filtra los valores permitidos en función de las selecciones realizadas en otras columnas.

Las filas no válidas se resaltan con mensajes de error y no se pueden publicar en la tabla de transformación hasta que el usuario las corrija.

**Manejo de errores**

TBM Studio detecta problemas de calidad de los datos a través de un panel de errores centralizado que recopila los errores de todas las tablas del proyecto. Entre los tipos de errores más comunes se incluyen:

- Discrepancias de tipo (un valor de texto en una columna numérica)
- Faltan campos obligatorios en los objetos del modelo de nivel inferior
- Valores de fecha no válidos que impiden la asignación correcta del período
- Errores en la configuración de los pasos de transformación

Los errores se propagan hacia arriba: un error en los datos de una transformación anterior puede bloquear los cálculos del modelo para cualquier objeto del modelo que dependa de dicha transformación. El panel «Errores» te ayuda a identificar y localizar rápidamente el origen de los problemas.

## Buenas prácticas en materia de calidad de los datos

- **Validar en el momento de la importación:** Confirmar los tipos de columna durante la importación. Detectar a tiempo los errores de tipo evita que se produzcan errores en cadena más adelante.
- **Activar el control de la vigencia de los datos:** Configurar notificaciones por correo electrónico para todas las tablas de datos críticos, especialmente los datos financieros que se utilizan en los procesos de cierre mensual.
- **Utiliza entradas restringidas en las tablas editables:** los menús desplegables y las reglas de validación evitan los errores de texto libre en los campos que alimentan las dimensiones del modelo.
- **Revisa los errores con regularidad:** comprueba el panel «Errores» después de cada carga de datos. Los errores no resueltos pueden reducir la precisión del modelo sin que nos demos cuenta.
- **Elimina las tablas que no se utilizan:** utiliza la función de análisis de documentos no utilizados para identificar las tablas a las que ya no se hace referencia. Quitarlos reduce el ruido y facilita la resolución de problemas.
