---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear perspectivas personalizadas"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Personalización de informes"
source_path: "studio/new-uc/howtoguides/create-reports/create-cust-pers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear perspectivas personalizadas

**Objetivo:** Crear una perspectiva personalizada que organice los campos seleccionados para los usuarios empresariales, facilitando la elaboración de informes y garantizando una mayor coherencia.

**Cuándo utilizarlas:** Utiliza las perspectivas personalizadas cuando quieras:

- Proporcionar a los analistas un conjunto seleccionado de campos de uso habitual
- Añade campos de varias tablas a una única ubicación de fácil acceso
- Asigna los campos a tablas específicas para obtener resultados predecibles en los informes de producción
- Ocultar la complejidad técnica a los usuarios empresariales que elaboran informes

**Requisitos previos:**

- Rol de usuario avanzado o administrador (o rol personalizado con permiso para editar modelos)
- Acceder a Report Studio en modo de edición
- Saber qué campos utilizan con más frecuencia tus analistas

**Tiempo estimado:** entre 15 y 30 minutos por perspectiva

## Comprender las perspectivas personalizadas

El Explorador de proyectos de Report Studio muestra varias secciones estándar: Tablas, Métricas y Tiempo. Aunque estas secciones permiten acceder a todos los datos disponibles, pueden resultar abrumadoras, sobre todo para los analistas de negocios que solo necesitan una parte de los campos.

Las perspectivas personalizadas resuelven este problema al permitirte crear grupos de campos seleccionados. Piensa en una perspectiva personalizada como una lista de «favoritos» que contiene exactamente lo que tus usuarios necesitan. Una ventaja es que puedes añadir campos de varias tablas diferentes y vincular cada campo a su tabla de origen. Esto permite crear informes que contengan datos de varias tablas en distintos niveles del modelo.

**Conceptos clave:**

- **Los usuarios avanzados** pueden ver todas las secciones: Tablas, Métricas, Tiempo y Perspectivas
- **Los analistas** solo ven las perspectivas personalizadas y la sección «Tiempo», lo que simplifica su visualización
- Todos los analistas pueden ver todas las perspectivas personalizadas; no es posible crear conjuntos de perspectivas diferentes para distintos grupos de analistas
- Las perspectivas personalizadas aparecen en orden alfabético en la parte superior del área «Perspectivas»

## Paso a paso: Crear una perspectiva personalizada

1. En el **Explorador de proyectos**, busca la sección «**Perspectivas** ».
2. Haz clic con el botón derecho del ratón en la sección **«Perspectivas»** y selecciona «**Añadir nueva perspectiva** ».
3. En el cuadro de diálogo «**Crear perspectiva** », introduzca un nombre descriptivo para la perspectiva (por ejemplo, «Análisis financiero de TI» o «Revisión mensual de costes») y haga clic en **Aceptar**.

**Consejo:** *Elige nombres que transmitan claramente a tus analistas el objetivo de la perspectiva.*

## Paso a paso: añadir campos a una perspectiva personalizada

Puedes añadir campos a una perspectiva mediante cualquiera de estos métodos:

**Método 1: Arrastrar desde el Explorador de proyectos**

1. Busca un campo en la sección **«Tablas»**, «**Métricas** » o **«Tiempo»** del **Explorador** de proyectos.
2. Arrastra el campo al encabezado **«Perspectivas»** en el **Explorador de proyectos**.
3. Cuando se le solicite, seleccione la perspectiva de destino y haga clic en **Aceptar**.
4. Rellene el cuadro de diálogo **«Campo de publicación»** (consulte las opciones de campo más abajo).
5. Haz clic en «**Publicar** ».

**Método 2: Arrastrar desde la configuración de componentes**

1. Al configurar un componente de informe, busca un campo útil en el panel «**Configuración del componente** ».
2. Arrastra el campo a la barra de título de la sección «Perspectivas».
3. Rellene el cuadro de diálogo **«Publicar campo»** y haga clic en «**Publicar** ».

**Método 3: Haz clic con el botón derecho del ratón en «Configuración de componentes»**

1. Haz clic con el botón derecho del ratón en un campo del panel «**Configuración de componentes** ».
2. Selecciona «**Publicar** ».
3. Rellene el cuadro de diálogo **«Publicar campo»** y haga clic en «**Publicar** ».

## Opciones del cuadro de diálogo «Publicar campo»

Al publicar un campo, se configuran varias opciones importantes:

|  |  |
| --- | --- |
| **Campo** | **Descripción** |
| Nombre | El nombre que se muestra para el campo. Si se vincula a un objeto, se recomienda incluir el nombre del objeto para mayor claridad. |
| Tipo de datos | Permite controlar el formato básico. Elige entre «Moneda», «Número», «Porcentaje», etc. |
| Anclar a objeto | Si se marca, garantiza que el campo se aplique únicamente al objeto específico seleccionado al publicar. Recomendación: Bloquea siempre los campos en los informes de producción. |
| Representa un código jerárquico | Solo se aplica a las cortadoras. Si se marca esta casilla, el campo crea agrupaciones jerárquicas basadas en los caracteres de búsqueda. |
| Mostrar todas las filas en una consulta basada en el tiempo | Si se marca esta opción, se muestran todas las filas de las tablas basadas en el tiempo, incluso si algunos periodos tienen valores nulos. Es necesario para realizar cálculos con las funciones « PreviousYear, », « YearToDate, » y otras funciones de tiempo similares. |
| Descripción | Se muestra como una ventana emergente cuando el usuario pasa el cursor por encima del campo. Ofrece explicaciones claras para ayudar a los analistas a comprender los datos. |
| Notas | Información visible únicamente para otros usuarios avanzados en este cuadro de diálogo; resulta útil para documentar las decisiones relativas a la configuración de los campos. |

## Paso a paso: Organizar campos con grupos

Agrupa los campos relacionados dentro de una perspectiva para una mejor organización:

1. Haz clic con el botón derecho del ratón dentro de una perspectiva personalizada y selecciona «**Añadir nuevo grupo** ».
2. Introduzca un nombre para el grupo (por ejemplo, «Métricas de costes» o «Dimensiones de la unidad de negocio»).
3. Arrastra los campos desde cualquier otro lugar de la vista a este grupo.

Para eliminar un campo de un grupo, arrástralo a un área vacía dentro de la perspectiva personalizada.

Consejo: Los grupos resultan especialmente útiles para los filtros jerárquicos. El orden de los campos dentro de un grupo determina la jerarquía del filtro.

## Paso a paso: Crear una perspectiva exclusiva para administradores

A veces es necesario crear vistas para usuarios avanzados y administradores que los analistas no deben ver:

1. Crea una nueva perspectiva tal y como se ha descrito anteriormente.
2. Al nombrar la perspectiva, escribe el nombre entre paréntesis; por ejemplo, **(Campos de administración)** o **(Métricas técnicas)**.
3. Pulse **Aceptar**.

Las perspectivas cuyo nombre aparece entre paréntesis solo son visibles para los usuarios con roles de administrador.

## Gestión de perspectivas personalizadas

**Cambiar el nombre de una perspectiva:** haz clic con el botón derecho del ratón en el nombre de la perspectiva y selecciona «**Cambiar nombre** ».

**Eliminar un campo:** haz clic con el botón derecho del ratón en el campo dentro de la perspectiva y selecciona «**Eliminar campo** ».

**Eliminar una perspectiva:** haz clic con el botón derecho del ratón en la barra de título de la perspectiva y selecciona «**Eliminar** ».

**Editar un campo publicado:** haz clic con el botón derecho del ratón en el campo y selecciona **«Editar»** para modificar sus propiedades.

## Errores habituales

- **Los campos sin bloquear dan lugar a resultados incoherentes:** si no se vincula un campo a su objeto, este puede aplicarse a cualquier objeto que esté seleccionado en ese momento en el informe, lo que da lugar a datos inesperados.
- **La falta de descripciones confunde a los analistas:** dedica tiempo a redactar descripciones útiles, ya que es posible que los analistas no conozcan tu modelo de datos.
- **Si hay demasiados campos, se pierde el sentido:** sé selectivo. Una vista con 100 campos no es mucho mejor que la vista «Tablas» sin formato.
- **Opción «Omitir consulta basada en el tiempo»:** si publicas métricas calculadas que hacen referencia a otros periodos de tiempo, marca la casilla «Mostrar todas las filas en la consulta basada en el tiempo» para garantizar que se muestren todos los datos.

**Tema principal:** [Personalización de informes](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
