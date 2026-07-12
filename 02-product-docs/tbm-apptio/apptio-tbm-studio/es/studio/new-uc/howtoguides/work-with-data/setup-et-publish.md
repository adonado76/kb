---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar la publicación de tablas editables"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Introducción manual de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/setup-et-publish.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar la publicación de tablas editables

**Objetivo:** Configurar cómo los datos introducidos por el usuario en las tablas editables se transfieren a las tablas de transformación y, en última instancia, a su modelo de costes, incluyendo la publicación manual, programada y automatizada.

**Cuándo se utiliza**

- Después de crear tablas editables que deben alimentar tablas de transformación
- Al establecer los intervalos de actualización automática de los datos
- Para la elaboración conjunta de previsiones o la planificación de escenarios
- Para que los usuarios de la empresa puedan actualizar los datos de entrada de los modelos sin necesidad de intervención del departamento de TI

**Por qué es importante** : Las tablas editables se encuentran fuera del proceso de transformación estándar. La publicación transfiere los datos introducidos por el usuario a tablas de transformación, donde pueden utilizarse en cálculos y asignaciones. Si no se configura correctamente la publicación, las actualizaciones de los usuarios quedan aisladas y no se reflejan en el modelo.

## Requisitos previos

- Una tabla editable (vacía o con datos) ya creada con columnas definidas
- Conocer cuándo deben actualizarse los datos (de forma puntual, diaria, semanal o mensual)
- Saber para qué periodos se necesitan datos
- Permisos de administrador o de creador para la programación

## Estimación de tiempo

15-25 minutos

## A Crea una tabla de transformación a partir de tu tabla editable

1. **Crear la tabla de transformación**
   - Accede a **Data Studio**
   - En la pestaña **Inicio**, selecciona **Nuevo > Tabla**
   - Introduzca un nombre para la tabla de transformación (por ejemplo, «Transformación de categorías de proveedores»)
   - Haz clic **en Aceptar**
2. **Selecciona «Tabla editable» como origen**
   - En la ventana emergente «**Crear tabla** », selecciona el mosaico **«Tabla editable»**
   - En el menú desplegable «**Tabla editable** », selecciona el nombre de tu tabla editable
3. **Elige el método de publicación inicial**
   - **Método de carga:** Selecciona **«Reemplazar»** (las nuevas publicaciones sustituyen por completo los datos existentes; es la opción más habitual)
   - Selecciona una **programación de publicación periódica** en el menú desplegable o utiliza «Predeterminado: sin actualizaciones periódicas»
   - Haz clic **en Aceptar**
4. **Guardar y registrarse**
   - Haz clic en **«Guardar»** en la pestaña **«Inicio»**
   - Haz clic **en «Check-in»**

## B. Publicar manualmente desde TBM Studio

Utiliza este método cuando quieras controlar exactamente cuándo se actualizan los datos.

1. **Ve a tu tabla de transformaciones**
   - En **el Explorador de proyectos**, busca la tabla de transformación derivada de tu tabla editable
   - Consulta la tabla si es necesario
2. **Accede al paso «Tabla editable»**
   - Haz clic en **«Pasos» > «Tabla editable»** en el flujo de trabajo
   - Verás marcadores de posición para cada periodo definido en tu proyecto
3. **Publicar durante un periodo determinado**
   - Haz clic con el botón derecho del ratón en el periodo que quieras actualizar (por ejemplo, «Ene. 2025»)
   - Selecciona **«Actualizar este periodo»**
   - El sistema publica los datos actuales de la tabla, que se pueden editar, correspondientes a ese periodo
4. **Verificar y registrarse**
   - Haz clic en el paso **«Tabla»** y comprueba que los datos se muestran correctamente
   - Haz clic **en «Check-in»**

## C. Publicar manualmente desde los informes

Los usuarios con los permisos adecuados pueden publicar cambios en tablas editables directamente desde los informes.

**Requisitos previos:** El usuario debe tener **acceso de desarrollo** y **acceso al entorno de prueba** (no se requiere acceso a TBM Studio ni de administrador).

**Flujo de trabajo del usuario:**

1. Abre un informe que contenga la tabla editable
2. Realice los cambios que desee en los datos
3. Haz clic en **«Guardar»** para guardar los cambios en la tabla editable
4. Haz clic en **«Publicar»** en la parte inferior del informe
5. Confirma la acción de publicación en la ventana emergente de advertencia
6. Introduce una descripción en la **ventana** emergente de registro
7. Haz clic **en «Check-in»**

Importante: Al publicar desde un informe, se publican TODOS los cambios realizados en las tablas editables, no solo las filas visibles en la vista actual del informe. Si varios usuarios están editando secciones diferentes, al publicar, un usuario actualiza todos los cambios.

## D. Configurar programas de publicación automática

La publicación automática permite actualizar los datos de forma periódica y sin intervención manual.

1. **Activa la función de publicación periódica** (si aún no está activada)
   - Ve a la pestaña **«Proyecto»** > **«Habilitar funciones»** ( 12.11.7 ) o **«Configuración del proyecto»** ( 12.11.8 +)
   - Selecciona **«Habilitar publicación periódica» para las tablas de transformación**
   - Haz clic **en Aceptar**
2. **Acceder a la configuración de publicaciones periódicas**
   - Ve a la pestaña **«Build»** > **«Publicación periódica»**
   - Verás dos pestañas: **«Transformar tabla»** y **«Programas recurrentes»**
3. **Crear un nuevo horario**
   - Selecciona la pestaña **«Programaciones periódicas»**
   - Haz clic **en «Añadir horario»**
4. **Configurar los ajustes de programación**
   - **Nombre de la programación:** Introduzca un nombre descriptivo (por ejemplo, «Mapeo de mano de obra - Diario»)
   - **Periodicidad:** Selecciona la frecuencia (cada hora, cada día, cada semana o cada mes)
   - **Publicar en el periodo:** Selecciona el periodo al que se aplicarán los datos (mes actual, mes anterior, periodo específico, etc.)
   - **Habilitar:** marca esta casilla para activar la programación
   - **Promoción automática a producción** ( 12.11.10 +): marque esta casilla para que los datos publicados se transfieran automáticamente a producción
5. **Guarda y asigna el horario**
   - Haz clic en **Guardar**
   - Ve a la pestaña **«Transformar tabla»**
   - Busca tu tabla de conversión y asigna el nuevo calendario

## Resultados previstos

Una vez configurada la publicación:

- **Publicación manual:** los datos de las tablas editables se transfieren a las tablas de transformación cuando se activa explícitamente la publicación
- **Publicación basada en informes:** los usuarios empresariales pueden actualizar los datos de entrada de los modelos sin necesidad de acceder a Studio
- **Publicación programada:** los datos se actualizan automáticamente a intervalos definidos
- **Autopromoción** (si está habilitada): cambia el flujo a producción sin intervención manual

## Errores habituales

|  |  |
| --- | --- |
| **Emitir** | **Solución** |
| **Los datos publicados no aparecen en la tabla de transformación** | Comprueba que el periodo que estás viendo coincide con el periodo en el que realizaste la publicación. Marca tanto la tabla editable como la tabla de transformación. Asegúrate de que no haya errores en los datos de la tabla editable. |
| **La programación no funciona como se esperaba** | Comprueba que la casilla «Habilitar» esté marcada en la programación. Comprueba la fecha y la hora de la última publicación: si aparece «Inicial», significa que la programación aún no se ha ejecutado. Comprueba que la hora de inicio y la zona horaria sean correctas. |
| **La edición simultánea por parte de varios usuarios provoca la sobrescritura de datos** | Es el comportamiento esperado: prevalece la última publicación. Implementar la gestión: asignar usuarios distintos a cada sección. Utilice la seguridad a nivel de fila para distribuir las responsabilidades de edición. |
| **La autopromoción introduce datos erróneos en el entorno de producción** | Desactivar la promoción automática para las tablas que requieran validación manual. Aplica reglas de validación de datos para detectar errores antes de publicar. |

## ¿Qué viene ahora?

Una vez configurada la publicación:

- [Crear informes para la introducción de datos](../create-reports/report-basic.html)
- [Aplicar seguridad a nivel de fila](htg-arls.html)
- [Integrar con el modelo de costes](../build-cost-model/model-basics.html)
- Configurar la gestión de promociones (Sección 6.1 )

**Tema principal:** [Introducción manual de datos](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
