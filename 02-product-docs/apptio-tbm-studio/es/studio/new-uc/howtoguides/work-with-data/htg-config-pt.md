---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía práctica: Configurar tablas publicadas"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Exportación de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-config-pt.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía práctica: Configurar tablas publicadas

**Objetivo:** Crear y configurar una tabla publicada que los sistemas externos puedan consultar para obtener datos del modelo de costes

**Cuándo utilizarlo:** cuando necesites proporcionar un conjunto de datos estable y actualizado automáticamente a herramientas de BI externas, almacenes de datos u otros proyectos de planificación y cálculo de costes

**Requisitos previos:**

- TBM Studio, versión 12.11.3 o posterior
- Permisos de administrador para crear y modificar tablas publicadas
- Un modelo de costes completo con datos calculados
- (Opcional) Una tabla de informes existente que se va a convertir

**Tiempo estimado:** 15-20 minutos

## Cómo interpretar las tablas publicadas

Las tablas publicadas son entidades de exportación específicas de TBM Studio, distintas de los informes y las tablas de transformación. Resuelven un problema habitual: antes de la introducción de las tablas publicadas, los usuarios tenían que crear informes bloqueados para exportar datos, lo que aumentaba la carga del proceso de cálculo provisional y complicaba la gestión de permisos.

Las tablas publicadas ofrecen varias ventajas:

- Elimina la necesidad de gestionar los permisos de los informes para la exportación de datos
- Permitir la exportación tan pronto como finalice el cálculo de desarrollo
- Proporcionar un esquema estable en el que puedan confiar los sistemas externos
- Eliminar la dependencia de la superficie de presentación de informes para la salida de datos

Importante: Las tablas publicadas reflejan únicamente los valores de los modelos implementados; no muestran los valores preliminares de las ramas de desarrollo. Los datos se actualizan cada vez que se completa con éxito un cálculo en el entorno de prueba o de producción.

## Método 1: Crear una nueva tabla publicada

Sigue estos pasos para crear una tabla publicada desde cero:

1. Ve a la pestaña **«Inicio»** y selecciona «**Nuevo** ».
2. Selecciona **«Tabla publicada»** en el menú.
3. En el cuadro de diálogo que aparece:
   - Introduzca un **nombre** descriptivo para la tabla (por ejemplo, «Resumen de costes mensuales - PowerBI" »)
   - Selecciona una **categoría** para organizar la tabla en el Explorador de proyectos
   - Haz clic **en Aceptar**
4. Busca la tabla recién creada en el Explorador de proyectos, dentro de la categoría indicada.
5. Configure la tabla publicada definiendo su contenido:
   - Selecciona el objeto del modelo de origen o la tabla de transformación
   - Elige qué columnas quieres incluir
   - Aplica las reglas de formato o conversión que sean necesarias

Nota: El proceso de configuración es similar al que se seguiría para configurar una tabla de informes. Para obtener instrucciones detalladas sobre las opciones de configuración de las tablas, consulte la sección «Tablas en los informes» de la documentación de Report Studio (sección 5.3 ).

- Guarda los cambios para que la tabla publicada forme parte de tu proyecto.

## Método 2: Crear a partir de una tabla de informe existente

Si ya tienes una tabla de informes configurada con los datos que deseas exportar, puedes convertirla directamente en una tabla publicada:

1. Ve al informe que contiene la tabla que deseas exportar.
2. Haz clic con el botón derecho del ratón en la tabla del informe.
3. Selecciona **«Crear tabla publicada»** en el menú contextual.
4. En el cuadro de diálogo:
   - Introduzca un **nombre** para la nueva tabla publicada
   - Selecciona una **categoría**
   - Haz clic **en Aceptar**
5. La nueva tabla publicada aparece en el Explorador de proyectos y hereda la configuración de la tabla del informe original.

Consejo: Este método es ideal cuando ya has perfeccionado la selección de columnas y el formato de una tabla de informe, ya que te evita tener que volver a crear esa configuración.

## Configurar los ajustes de precálculo

Por defecto, las tablas publicadas se calculan previamente durante el proceso de compilación, lo que garantiza que los datos estén disponibles de inmediato cuando se soliciten. Puedes modificar este comportamiento:

1. En el Explorador de proyectos, echa un vistazo a la tabla publicada.
2. Selecciona la pestaña **«Tabla publicada»** para ver sus propiedades.
3. Busca la opción «**Activo** »:
   - **Marcado (por defecto):** El sistema calcula previamente la tabla durante las compilaciones. Los datos están disponibles de inmediato al llamar a la API URL.
   - **Sin marcar:** El sistema no realiza cálculos previos. La API sigue funcionando, pero la primera solicitud activa el cálculo, lo que puede retrasar la respuesta.
4. Guarda los cambios.

**Cuándo desactivar el precálculo:** Considere la posibilidad de desactivar el precálculo en las tablas publicadas a las que se accede con poca frecuencia o que se utilizan únicamente para la resolución de problemas. Esto reduce el tiempo de compilación de tus exportaciones principales.

## Obtener el URL de la API URL para una tabla publicada

Una vez configurado, obtenga el « URL » que utilizarán los sistemas externos para acceder a los datos:

1. En el Explorador de proyectos, haz clic con el botón derecho del ratón en la **tabla publicada**.
2. Selecciona **«Mostrar API» ( URL )** en el menú contextual.
3. Copia la dirección URL del cuadro de diálogo.
4. Utiliza este enlace URL en:
   - DataLink conexiones para la extracción programada de datos
   - Scripts personalizados para el acceso programático
   - Configuraciones de fuentes de datos de herramientas de BI

Consejo: La API URL seguirá funcionando correctamente siempre y cuando no cambie el nombre de la tabla publicada. Si cambia el nombre de la tabla publicada, actualice todos los sistemas que la utilizan con el nuevo URL.

## Resultados previstos

Una vez completados estos pasos:

- La tabla publicada aparece en el Explorador de proyectos dentro de la categoría que se le ha asignado
- Los datos se actualizan automáticamente tras cada cálculo satisfactorio en el entorno de prueba o de producción
- Los sistemas externos pueden recuperar datos mediante la API URL en formato CSV o JSON
- El esquema se mantiene estable a menos que modifiques explícitamente la configuración de la tabla publicada

## Errores habituales

**Datos que no aparecen en la tabla publicada** : las tablas publicadas solo reflejan los valores del modelo implementado. Si estás trabajando en una rama de desarrollo, los datos no aparecerán hasta que publiques los cambios y ejecutes un cálculo.

**Primera solicitud lenta** : si el precálculo está desactivado, la primera solicitud a la API activa el cálculo. En el caso de conjuntos de datos de gran tamaño, esto puede llevar bastante tiempo. Habilita el precálculo para las tablas publicadas a las que se accede con frecuencia.

**Cambios en el esquema que provocan fallos en los sistemas posteriores** : cuando se modifican las selecciones de columnas en una tabla publicada, los sistemas posteriores pueden dejar de funcionar correctamente. Comunique los cambios en el esquema a todos los usuarios de los datos antes de realizar modificaciones.

**Errores que impiden la actualización** : si las tablas de transformación de origen contienen errores o discrepancias en los datos, la actualización de la tabla publicada fallará. Revisa los registros de cálculo y resuelve primero los problemas en las etapas anteriores.

**Tema principal:** [Exportación de datos](../../../../studio/new-uc/howtoguides/work-with-data/data-export.html)
