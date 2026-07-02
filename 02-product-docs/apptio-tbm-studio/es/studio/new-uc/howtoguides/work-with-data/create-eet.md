---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear tablas enriquecidas y editables"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Introducción manual de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/create-eet.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear tablas enriquecidas y editables

**Objetivo:** Crear una tabla editable cuyas filas se generen automáticamente a partir de una tabla de transformación existente, lo que permitirá a los usuarios enriquecer los datos con clasificaciones o anotaciones adicionales.

**Cuándo se utiliza**

- Tienes datos generados por el sistema que requieren una clasificación manual (por ejemplo, asignar etiquetas a instancias en la nube con los proyectos correspondientes)
- Asignación de cuentas del libro mayor a categorías de costes de TI
- Incorporación de contexto empresarial a los flujos de datos automatizados
- Mapeo de personal (asignación de empleados a torres y servicios de TI)
- Casos en los que las filas deben coincidir con un sistema de origen, pero requieren campos adicionales introducidos por el usuario

**Cuándo NO utilizarlo**

- Para tablas de consulta pequeñas sin fuente previa (utiliza tablas en blanco editables)
- Cuando los usuarios necesitan añadir o eliminar filas libremente (las tablas enriquecidas heredan las filas de la fuente)
- Para datos totalmente automatizados que no requieren intervención humana

Atención: En las tablas editables enriquecidas, las filas proceden de la tabla de transformación de origen y los usuarios no pueden eliminarlas. Los usuarios solo pueden añadir columnas e introducir valores en ellas. Si se añade una fila a la tabla de origen, dicha fila aparece automáticamente en la tabla enriquecida. Si se elimina una fila de la tabla de origen, esta desaparece de la tabla enriquecida.

## Requisitos previos

- Una tabla de transformación ya existente que servirá como fuente de datos
- Saber qué columnas de la tabla de origen deben ver los usuarios
- Planifica qué columnas adicionales deberán rellenar los usuarios
- Data Studio acceso con permisos para crear tablas

**Tiempo estimado:** 15-20 minutos

**Pasos**

1. **Crea la tabla enriquecida y editable**
   - Accede a **Data Studio**
   - En la pestaña **Inicio**, selecciona **Nuevo > Tabla editable**
   - En el cuadro de diálogo «**Nueva tabla introducida manualmente** », seleccione **«Tabla enriquecida»**
   - Introduzca un nombre descriptivo (por ejemplo, «Asignación de cuentas contables», «Ampliación de mano de obra»)
   - Haz clic **en Aceptar**
2. **Selecciona la tabla de transformación de origen**
   - Ve a **«Pasos» > «Generados»** en el proceso
   - Haga clic en **«Configurar tabla de origen»**
   - En el menú desplegable **«Tabla de origen»**, selecciona la tabla de transformación cuyos datos se utilizarán para rellenar esta tabla editable
   - El sistema carga todas las columnas y filas de la tabla de origen
3. **Selecciona las columnas de origen que deseas incluir**
   - Consulte la lista de columnas disponibles de la tabla de origen
   - Selecciona las columnas que los usuarios deben ver al introducir datos
   - **Práctica recomendada:** incluye columnas de identificación (nombres, identificadores, descripciones), pero excluye los campos calculados
   - **Nota:** Estas columnas de origen son de solo lectura; los usuarios no pueden editarlas
4. **Añadir columnas editables**
   - Ve a **Pasos > Configurar columnas**
   - Haz clic en **«Añadir una nueva columna»** para cada campo que vayan a rellenar los usuarios
   - Columnas editables comunes: campos de clasificación, destinos de asignación, métricas introducidas por el usuario, comentarios
5. **Configura cada columna editable**
   - **Nombre de la columna:** Utiliza nombres claros y fáciles de entender
   - **Descripción:** Explica qué deben introducir los usuarios y por qué
   - **Valores posibles:** define menús desplegables para controlar la calidad de los datos (muy recomendable)
   - **Valor obligatorio:** comprueba si los usuarios deben introducir un valor antes de publicar
6. **Configura las dependencias de las columnas** (si es necesario)
   - Para los menús desplegables en cascada (por ejemplo, Torre → Servicio → Subservicio), configura las fórmulas de «Valores posibles»
   - Establece **el contexto de valores posibles** en «Fila actual» para los casos de menús desplegables dependientes
7. **Revisa la vista previa de los datos**
   - Haz clic en el paso **«Tabla»** para ver cómo queda la tabla mejorada
   - Comprueba que las columnas de origen se muestren correctamente y que haya columnas editables
8. **Guardar y registrarse**
   - Haz clic en **«Guardar»** en la pestaña **«Inicio»**
   - Haz clic en **«Registrarse»** y añade un comentario descriptivo

## Resultados previstos

Tu tabla editable mejorada contiene ahora todas las filas de la tabla de transformación de origen (sincronizadas automáticamente), columnas de solo lectura de la tabla de origen para referencia del usuario y columnas edibles vacías listas para que el usuario introduzca datos. Cuando se actualiza la tabla de transformación de origen, la tabla editable enriquecida refleja automáticamente esos cambios, conservando al mismo tiempo los datos introducidos por el usuario en las columnas editables.

**Errores habituales**

|  |  |
| --- | --- |
| **Emitir** | **Solución** |
| **Los usuarios no tienen claro qué columnas pueden editar** | En los informes, identifica claramente o agrupa las columnas editables y las de solo lectura. Considera la posibilidad de utilizar la propiedad «Nombre para mostrar» para añadir «(Solo lectura)» a las columnas de origen. |
| **Se han eliminado filas de la tabla de origen; se ha perdido la información añadida por el usuario** | Es el comportamiento esperado. Si se eliminan los datos de origen, el enriquecimiento de esas filas desaparece. Mantenga la estabilidad de la tabla de origen o indique que es posible que se pierda la información añadida. |
| **Los usuarios esperan poder añadir nuevas filas manualmente** | Las tablas enriquecidas no admiten filas añadidas manualmente. Si los usuarios necesitan esta función, asegúrese primero de que todas las filas necesarias estén presentes en la tabla de transformación de origen o utilice, en su lugar, una tabla editable en blanco. |
| **Las columnas editables carecen de menús desplegables** | Para cualquier columna que se utilice en asignaciones o en la generación de informes, añade restricciones al menú desplegable. Las entradas de texto libre dan lugar a clasificaciones incoherentes. |

## ¿Qué viene ahora?

Una vez creada tu tabla enriquecida y editable:

- [Configurar menús desplegables y validación](config-dd-valid.html)
- [Configurar la publicación de tablas editables](setup-et-publish.html)
- [Crear informes para la introducción de datos por parte de los usuarios](../create-reports/create-basic-report.html)
- [Guía práctica 1: Aplicar la seguridad a nivel de fila a las tablas](htg-arls.html)

**Tema principal:** [Introducción manual de datos](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
