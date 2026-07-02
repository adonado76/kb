---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "GCP Etiquetas y rótulos"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectar Google Cloud"
source_path: "admin/gcp-tags.html"
images:
  - "images/gcp-tags.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Etiquetas y rótulos

Cloudability admite los siguientes tipos de etiquetas y rótulos para GCP

- **GCP Etiquetas**
  - Estos datos forman parte del extracto de datos de facturación de « GCP » y no se requieren permisos adicionales en Cloudability para habilitarlos. Cloudability admite las siguientes etiquetas:
    - Etiquetas de recursos
    - Etiquetas de proyectos
    - Etiquetas del sistema

Nota: Si se configura la misma clave para las etiquetas de proyecto, sistema y recurso, el orden de prioridad para mostrar la etiqueta en la interfaz de usuario de Cloudability es el siguiente:

- Recurso

- Proyecto
- Sistema

- **GCP Etiquetas**
  - Estos datos forman parte del extracto de datos de facturación de « GCP » y no se requieren permisos adicionales en Cloudability para habilitarlos

GCP Las etiquetas se están convirtiendo en un mecanismo de etiquetado muy popular entre un gran número de clientes de GCP para la asignación de costes y el etiquetado basado en políticas. Cloudability Ahora admite etiquetas de « GCP », además de las de « GCP ». Ahora los usuarios pueden utilizar ambas opciones en diversos casos de uso.

Para obtener más información sobre las etiquetas « GCP », haz clic en [https://cloud.google.com/resource-manager/docs/tags/tags-overview#inheritance](https://cloud.google.com/resource-manager/docs/tags/tags-overview#inheritance "(se abre en una pestaña o una ventana nueva)")

## Cambios clave en las asignaciones de etiquetas de « GCP »:

- Opciones de asignación mejoradas: ahora puedes asignar costes utilizando tanto las etiquetas de « GCP » (a nivel de organización o carpeta) como las de « GCP » (a nivel de recurso) para lograr una asignación de costes más exhaustiva.
- Asignación jerárquica de costes: asigna las etiquetas heredadas a las unidades de negocio o departamentos, utilizando etiquetas para las asignaciones específicas de cada proyecto.
- Configuración de prioridades: Establece la prioridad entre las etiquetas y los identificadores de « GCP » en los casos en que ambos existan para una misma dimensión de costes.

Para poder utilizar las etiquetas de « GCP », los clientes deberán habilitar las etiquetas de « GCP » en la consola de GCP. Una vez activada, la opción « Cloudability » (Incluir datos de facturación) durante la importación de los datos de facturación también incorporará las etiquetas « GCP ».

Una vez importadas, las etiquetas de « GCP » aparecerán como nuevas dimensiones de etiquetas en la configuración de «Asignaciones de etiquetas» de la página «Etiquetas y etiquetas», junto a las etiquetas existentes de « GCP ». Los verás tal y como se muestra a continuación:

- **cldy:gcp:tag:<tagkey>** para asignaciones directas de etiquetas
- **cldy:gcp:tag:<clave de etiqueta>:inherited** para las etiquetas heredadas
- **cldy:gcp:tag:<tagKey>:namespace** para el nivel de fijación de la etiqueta

![Etiquetas de GCP](../../../../03-media/cloudability-premium/images/gcp-tags.png)

GCP Las etiquetas se pueden utilizar en otras funciones, como las asignaciones empresariales, el explorador de etiquetas de vistas, los paneles de control y los informes, para profundizar aún más en diversos escenarios de asignación de costes.

## Resolución de problemas

**¿Cómo puedo decidir qué es más importante: las etiquetas de « GCP » o las de « GCP »?**

GCP Tanto las etiquetas como las etiquetas de clasificación aparecerán en la página «Etiquetas y etiquetas de clasificación» de Cloudability, dentro de la sección «Organizar». Actualmente, la página sigue un orden de prioridad basado en las etiquetas mencionadas. Si ya tienes etiquetas GCP y quieres dar prioridad a las etiquetas GCP, tendrás que eliminar las antiguas etiquetas GCP y añadir las etiquetas GCP como primera opción, seguidas de las etiquetas. Una vez hecho esto, es necesario volver a procesar los datos para que este cambio se refleje en los informes de Cloudability y en todas partes.

**He añadido una nueva etiqueta « GCP », pero no consigo ver el valor asociado a ella en Cloudability. ¿A qué se debe esto?**

Comprueba el orden de las etiquetas « GCP », tal y como se ha explicado anteriormente. Asegúrate de que las etiquetas « GCP » tengan prioridad en el orden de «ETIQUETAS» de la página de etiquetas y rótulos. En caso de conflicto entre las etiquetas de GCP y las etiquetas de GCP, comprobaremos el orden de prioridad de las etiquetas configuradas.

**En el momento del lanzamiento, ¿cuántos meses de etiquetas « GCP » estarían disponibles?**

En el momento del lanzamiento, empezaremos a extraer los datos de las etiquetas « GCP » del mes en curso.

**¿Cómo se pueden rellenar las etiquetas « GCP »?**

Los clientes deberán abrir un caso de « GCP » para solicitar la recuperación de las etiquetas « GCP ». A continuación, el equipo interno de asistencia técnica o de ingeniería deberá iniciar una nueva recuperación de datos para cargar los datos correspondientes a los meses especificados.

**¿Cómo cambiará Tag Explorer con la compatibilidad con las etiquetas « GCP »?**

Tag Explorer ofrecerá ahora información tanto sobre las etiquetas como sobre los « GCP », con las siguientes funciones:

**Análisis de cobertura mejorado:**

- **Visibilidad de doble capa** : visualiza tanto las etiquetas heredadas de GCP como las etiquetas aplicadas directamente de GCP
- **Seguimiento de la herencia** : Identificar qué costes se asignan mediante etiquetas heredadas y cuáles mediante el etiquetado directo de los recursos
- **Lagunas en la cobertura** : identificar los recursos que carecen de etiquetas o identificadores para una asignación completa de los costes

**Nuevas opciones de filtrado y análisis:**

- **Filtrado de fuentes de etiquetas** : filtrar por etiquetas directas frente a etiquetas heredadas
- **Análisis jerárquico** : Conoce los patrones de asignación de costes en toda la estructura organizativa de GCP

**Tema principal:** [Conectar Google Cloud](../admin/connect-google-cloud-premium.html)
