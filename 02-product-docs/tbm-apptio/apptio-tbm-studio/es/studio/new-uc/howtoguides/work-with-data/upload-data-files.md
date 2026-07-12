---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Importar datos desde archivos (Excel, CSV )"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Importación y gestión de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/upload-data-files.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Importar datos desde archivos (Excel, CSV )

**Objetivo:** Importar datos de archivos de Excel o de « CSV » a las tablas de TBM Studio para que estén disponibles para la elaboración de modelos de costes y la generación de informes.

**Cuándo utilizar este procedimiento:** Utilice la carga de archivos cuando necesite:

- Importar conjuntos de datos puntuales o ad hoc
- Importar datos de costes mensuales desde los sistemas financieros
- Importar datos externos que no están disponibles a través de conectores automatizados
- Comprueba las estructuras de datos antes de configurar las fuentes automatizadas

**Requisitos previos:**

- Permisos para extraer y editar tablas (rol « AccessDev »)
- Archivo de datos en un formato compatible (Excel,. xlsx/.xls, CSV, TSV u otros formatos delimitados)
- El nombre del archivo contiene solo un punto antes de la extensión (por ejemplo, cost\_data.xlsx, no cost.data.xlsx )
- Saber en qué tabla se deben cargar los datos (o tener permiso para crear una nueva tabla)

**Tiempo estimado:** entre 10 y 15 minutos para la primera subida; 5 minutos para las siguientes subidas

## Pasos

**Crea una tabla y sube tu primer archivo**

1. **Crea una nueva tabla** (si aún no existe):
   - En el **Explorador de proyectos**, haz clic en **Nuevo** → **Tabla**
   - Introduzca un **nombre** para la tabla (por ejemplo, «Libro mayor», «Costes del servidor»)
   - Introduce o selecciona una **categoría** para organizar la tabla en el Explorador de proyectos
   - Haz clic **en Aceptar**
2. **Configura la tabla de origen:**
   - La aplicación muestra el paso **«Fuente»** en el proceso de transformación
   - En el campo «**Descripción de la tabla** », introduzca una breve descripción del propósito de la tabla
   - Haz clic **en «Subir archivo»**
   - Se añade un paso **de carga** al proceso
3. **Sube tu archivo de datos:**
   - Haz clic en el panel **«Detalles»** y busca el archivo, o bien arrastra el archivo desde el Explorador de Windows al panel **«Detalles»**
   - El sistema añade un paso **de importación** al proceso y comienza a analizar el archivo
4. **Configurar los ajustes de importación:**

   Haz clic en el paso **«Importar»** del flujo de trabajo para revisar la configuración:

   **Configuración básica:**

   - **Iniciar la importación en la fila:** especifica qué fila contiene el primer registro de datos (por defecto es la fila 1, suponiendo que la fila 0 es el encabezado)
   - **Columnas que se deben excluir:** Selecciona las columnas que no quieras importar
   - **Codificación del texto:** Elige la codificación de caracteres (selecciona «Detectar codificación automáticamente» si no estás seguro)
   - **Delimitado:** Selecciona el carácter delimitador (coma, tabulación, barra vertical, etc.)
   - **Calificador de texto:** especifica el carácter utilizado para enmarcar el texto con caracteres especiales (por defecto, comillas dobles)

   **Configuración de columnas:**

   - Consulte la sección **«Columnas»**
   - Comprueba que los tipos de columna se detecten correctamente (Clave, Texto, Número, Fecha)
   - Cambia los tipos de columna según sea necesario haciendo clic en el tipo
   - Para filtrar las columnas por tipo, haz clic en el icono del tipo correspondiente en el campo de búsqueda de la columna **«Tipo»**
5. **Configurar la validación de datos** (opcional, TBM Studio v12.1+ ):
   - **La validación de datos** comprueba si se han producido cambios en el esquema al cargar datos en tablas existentes: columnas añadidas, columnas eliminadas, cambios en el tipo de columna o cambios en la cardinalidad de las columnas
   - **La validación de cardinalidad** comprueba el contenido de la columna:
     - **Cualquiera:** sin validación de cardinalidad (por defecto)
     - **Uno:** Garantiza que todos los valores sean únicos (sin duplicados)
     - **Muchos:** garantiza que cada entrada se duplique
6. **Selecciona un ciclo de actualización:**

   En la parte superior de la pantalla, selecciona la frecuencia con la que se actualizarán los datos:

   - **Actualizaciones puntuales:** sin calendario fijo; se publicarán según sea necesario
   - **1 versión; sin actualizaciones programadas:** una sola versión, se sustituye al subirla
   - **1 versión; Actualización mensual:** actualización mensual, sustituye los datos existentes
   - **1 versión; Actualización anual:** actualización anual
   - **Versiones mensuales; Actualización mensual:** nueva versión cada mes (véase «Tablas de versiones para datos mensuales»)
   - **Versiones anuales** (varias opciones): conjuntos de datos anuales con diferentes frecuencias de actualización
7. **Revisa y guarda:**
   - Haz clic en el paso **«Tabla»** del flujo de trabajo para obtener una vista previa de los datos importados
   - Comprueba que los datos se muestren correctamente
   - Haz clic en **«Guardar»** en la pestaña «Inicio»
   - Haz clic en **«Check In»** para que la tabla quede disponible para el proyecto

**Subir datos adicionales a una tabla existente**

Cuando necesites añadir más datos a una tabla existente (por ejemplo, para introducir los gastos del mes siguiente):

1. **Extraer la tabla:** ve a la tabla en el **Explorador de proyectos**, haz clic con el botón derecho y selecciona **«Extraer».**
2. **Selecciona el periodo de tiempo deseado** (para tablas con versiones mensuales o anuales): utiliza el selector de fechas situado en la parte superior de la pantalla para seleccionar el periodo al que se deben añadir los datos. En el paso «Subir» aparece un marcador de posición.
3. **Sube el nuevo archivo:** haz clic en el espacio reservado y busca el archivo, o arrástralo hasta ese espacio.
4. **Guardar y registrar:** haz clic **en «Guardar»** en la pestaña «Inicio» y, a continuación, haz clic en «**Registrar** ».

## Resultados previstos

- Tu archivo de datos se ha importado correctamente a TBM Studio
- Los tipos de columna se identifican correctamente (o se corrigen manualmente)
- Los datos aparecen en la vista previa de la tabla con el formato adecuado
- La tabla está disponible para su uso en transformaciones, modelos e informes
- En el caso de las tablas con versiones, cada periodo contiene su propio conjunto de datos

## Errores habituales y solución de problemas

**Problema:** Error «Extensión de archivo no compatible»

- **Causa:** El nombre del archivo contiene varios puntos (por ejemplo, cost.data.xlsx )
- **Solución:** Cambia el nombre del archivo para que solo tenga un punto antes de la extensión (por ejemplo, cost\_data.xlsx )

**Problema:** Los datos aparecen en columnas equivocadas o con un formato incorrecto

- **Causa:** La configuración del delimitador o del calificador de texto es incorrecta
- **Solución:** Revisa la configuración del paso de importación y ajusta el delimitador y el calificador de texto para que se adapten al formato de tu archivo

**Problema:** Los datos numéricos se muestran como texto

- **Causa:** Se ha detectado incorrectamente el tipo de columna, o los datos contienen caracteres no numéricos
- **Solución:** En el paso «Importar», cambia el tipo de columna a «Número». Si el problema persiste, comprueba si hay caracteres especiales en tus datos de origen.

**Problema:** La subida de archivos falla o los datos parecen estar dañados

- **Causa:** El archivo de Excel contiene macros, formato especial o fórmulas
- **Solución:** Con el analizador de Excel mejorado ( v12.11.16+ ), el sistema lee los valores sin procesar directamente. Guarde el archivo de Excel como un archivo de TBM Studio ( CSV ), elimine el formato especial o las macros, o aplique el formato en TBM Studio mediante pasos de transformación.

## ¿Qué viene ahora?

Una vez que hayas subido los datos correctamente, podrás:

- [Transforma los datos](transform-enrich-data.html) : añade pasos de transformación para limpiar, asignar, filtrar o unir datos.
- [Añadir a un modelo](../build-cost-model/model-basics.html) : Incorporar la tabla a un modelo de costes (véase la sección 3.2 )
- Configurar la supervisión de la actualidad de los datos: configurar alertas para datos que faltan o están desactualizados (véase la sección 6.4 )
- [Automatizar las subidas](connect-external-dl.html) : pasa a utilizar subidas a través de DataLink o mediante API para las transferencias de datos periódicas

**Tema principal:** [Importación y gestión de datos](../../../../studio/new-uc/howtoguides/work-with-data/data-import-mgmt.html)
