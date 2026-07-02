---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Crear un proyecto"
breadcrumb:
  - "Costing Standard"
  - "Configuración"
source_path: "cost-transparency/configuration/config-create.html"
images:
  - "resources/images/studio_images/2a.png"
  - "resources/images/studio_images/4a.png"
  - "resources/images/studio_images/ad1.png"
  - "resources/images/studio_images/ad6.png"
  - "resources/images/studio_images/config1.png"
  - "resources/images/studio_images/config2b.png"
  - "resources/images/studio_images/config6.png"
  - "resources/images/studio_images/da.png"
  - "resources/images/studio_images/load4a.png"
  - "resources/images/studio_images/load6.png"
  - "resources/images/studio_images/load7.png"
  - "resources/images/studio_images/load9.png"
  - "resources/images/studio_images/lod2a.png"
  - "resources/images/studio_images/map3.png"
  - "resources/images/studio_images/mapcol2.png"
  - "resources/images/studio_images/master2.png"
  - "resources/images/studio_images/pt1.png"
  - "resources/images/studio_images/pt3.png"
  - "cost-transparency/configuration/clip_image002_-1253255458.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Crear un proyecto

Los proyectos agrupan conjuntos de datos, métricas, modelos e informes. Al crear un nuevo proyecto, puede elegir entre estos tipos principales: Estándar de costes, Personalizado. Puedes crear varios proyectos

1. Acceder a TBM Studio
   1. Inicie sesión en **IBM Apptio**.
   2. En el lanzador de aplicaciones, seleccione **TBM Studio**.
   3. Asegúrate de tener los permisos necesarios (normalmente, de administrador)

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/config1.png)
2. **Paso 2: Crear un nuevo proyecto**
   1. En TBM Studio, ve al icono **de** ![](../../../../../03-media/apptio-costing-standard/cost-transparency/configuration/clip_image002_-1253255458.png) Configuración situado en la parte superior derecha.
   2. Haga clic en **Nuevo proyecto**.

      ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/config2b.png)
   3. **Se abrirá el cuadro de diálogo Nuevo proyecto.**
   4. Introduzca un **nombre para el proyecto** que identifique claramente su finalidad (por ejemplo, «*Norma de cálculo de costes* ACME»).
   5. A continuación, elija un **tipo de proyecto.**
   6. Haga clic en **Crear**.

      ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/config6.png)

## Tipo de proyecto

Cuando creas un nuevo proyecto, tienes dos opciones:

- **Crear un proyecto de aplicación.** Los proyectos de aplicación sirven como plantillas para nuevos proyectos. Cuando se crea un proyecto de aplicación, la aplicación crea automáticamente conjuntos de datos, métricas, modelos e informes basados en la plantilla de la aplicación. Las plantillas de solicitud incluyen: Transparencia de costes para el proyecto Costing Standard, Costing Essentials para el proyecto Essentials
- **Crea un proyecto personalizado.** Un proyecto en blanco no tiene conjuntos de datos, modelos, métricas ni informes. Cree un nuevo proyecto personalizado si no desea basarse en trabajos anteriores. Esto incluye: Personalizado (Plataforma, v120+ )

Nota: Los proyectos Costing Essentials y Custom (Platform, v200+ ) se licencian por separado.

Para obtener más información sobre la configuración adicional del proyecto, vaya [aquí.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-about-studio-project "(se abre en una pestaña o una ventana nueva)")

## Establecer tiempo

El tiempo del proyecto define las fechas de inicio y finalización de un proyecto, así como el tipo de períodos que se utilizarán.

En un proyecto con plazos, se establecen las fechas de inicio y finalización para los datos y se define el año fiscal. En un proyecto con plazos, puede introducir datos de forma periódica, asignarlos a un periodo de tiempo específico y ver las tendencias a lo largo de la duración del proyecto. Puede ver los datos del informe del mes o periodo actual, o de periodos trimestrales, semestrales o anuales. La aplicación es compatible con los calendarios gregoriano, 445, 454, 544 y 13.

Para obtener más información sobre cómo IBM Apptio apoya proyectos relacionados con el tiempo, haga clic [aquí.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-enable-time-project "(se abre en una pestaña o una ventana nueva)")

**Establecer el tiempo del proyecto**

1. En el estudio TBM.
2. Haga clic en la pestaña Proyecto de la cinta de opciones.
3. Haga clic en Configuración de tiempo. El cuadro de diálogo Configurar ajustes de tiempo del proyecto se muestra como se indica a continuación.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/pt3.png)
4. Seleccione un período de inicio del proyecto y un período de finalización del proyecto. Seleccione las fechas que incluyen datos históricos que importará al proyecto.

   Nota: Una vez establecida la fecha de inicio del proyecto, no se puede modificar. Sin embargo, puede cambiar la fecha de finalización del proyecto.
5. Configure cualquier otro ajuste de tiempo del proyecto que sea adecuado para su proyecto.
6. Haga clic en Configurar hora.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/pt1.png)

Para obtener más información sobre las opciones de calendario disponibles y cómo configurarlas, haga clic [aquí.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-configure-project-time-settings "(se abre en una pestaña o una ventana nueva)")

## Instalación de componentes

Un componente de la aplicación Costing Standard agrupa informes y métricas para proporcionar información detallada sobre su negocio. Un componente también puede instalar una o más tablas de modelos en su proyecto

****Instalar un componente****

1. Comprueba que te encuentras al inicio del tiempo en tu proyecto.
2. En la pestaña Proyecto, haga clic en **Componentes**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/2a.png)
3. En el área Disponible de la pantalla Configuración de componentes, haga clic en el icono correspondiente al componente que desea instalar.
4. En la página de detalles del componente, haga clic en **Instalar**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/4a.png)

Nota: No se puede desinstalar un componente una vez que se ha instalado. Puede desactivar un componente, lo que eliminará los informes asociados, pero dejará las tablas y las métricas.

Una vez que instale todos los componentes en Costing Standard, se añadirán todos los informes de nivel superior. Si el cliente no desea ver ninguno de estos informes de nivel superior, tendrá que crear un proyecto personalizado o desactivar los informes de forma individual.

**Cargar datos**

Las tablas de datos maestros proporcionan una forma de asignar sus datos a los datos requeridos por la aplicación CT.

Cada componente de Costing Standard (CT) tiene una tabla de datos maestros. La tabla de datos maestros proporciona estructura a los datos relacionados. Los informes, las asignaciones y otros elementos de configuración están vinculados a la estructura de la tabla de datos maestros. No se cargan datos directamente en las tablas de datos maestros. En su lugar, se añaden o se asignan datos (utilizando el paso Map en el canal de datos) a las tablas. Esto garantiza que no se modifique la estructura de las tablas de datos maestros.

Debe cargar sus datos de origen en la aplicación. Después de cargar los datos, puede asignarlos a la tabla de datos maestros de un componente. Las tablas de datos que suba deben contener campos que puedan asignarse a los campos obligatorios de las tablas de datos maestros. Las tablas de datos no necesitan contener todos los campos de las tablas de datos maestros.

Para obtener más información sobre los tipos de datos que se pueden cargar y los diferentes métodos disponibles para cargar datos, haga clic [aquí.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload "(se abre en una pestaña o una ventana nueva)")

A continuación se describe el procedimiento general para cargar una tabla de origen:

1. Haga clic en la pestaña **Inicio** de la cinta de opciones.
2. Haga clic en el menú **Nuevo** y, a continuación, haga clic en **Tabla**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/lod2a.png)
3. En el cuadro de diálogo Crear tabla, introduzca un nombre para la tabla.
4. Introduzca una categoría. A medida que empieces a escribir, se mostrarán los nombres de las categorías que ya existen y que coincidan con lo que escribas. Además, puede introducir un nuevo nombre de categoría. Las categorías se utilizan para organizar las tablas en el Explorador de proyectos.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load4a.png)
5. Pulse **Aceptar**. La aplicación crea la tabla y muestra el paso Fuente en el canal de transformación, tal y como se muestra a continuación.
6. Haga clic en la opción «**Subir archivo** ». Para obtener más información sobre otras opciones, haga clic [aquí](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload "(se abre en una pestaña o una ventana nueva)").

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load6.png)
7. Se creará un paso de carga en el que el usuario podrá hacer clic/arrastrar el archivo o hacer clic con el botón derecho para pegarlo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load7.png)
8. Se añade un paso de importación al proceso.
9. Haga clic en el paso **Importar** en el proceso y revise la configuración:
   - Iniciar importación en la fila: indique la primera fila de la tabla que se incluirá en la importación.
   - Columnas que se deben excluir: indique si hay columnas que desea excluir.
   - Codificación de texto: si el archivo de datos utiliza una codificación de caracteres concreta, seleccione el esquema de codificación de la lista. Si no está seguro del tipo de codificación, seleccione la opción Detectar automáticamente la codificación.
   - Delimitado: seleccione el carácter que separa los campos de datos en el archivo. En la mayoría de los casos, será una coma.
   - Calificador de texto: si hay caracteres de texto especiales en los datos, indique el calificador de texto que se utiliza para rodear esos caracteres.
   - Columnas: revise las columnas que aparecen a la derecha y, si lo desea, cambie los tipos de columna. Para filtrar por tipo de columna (clave, texto, número, fecha), haga clic en el icono de tipo en el campo de búsqueda de la columna Tipo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load9.png)
10. Para revisar la tabla cargada, haga clic en el paso **Tabla** en el proceso.
11. Si la tabla es aceptable, haga clic en **Guardar** en la cinta.
12. Si ha terminado de realizar las modificaciones, haga clic en **«Check In»** (Registrar) en la cinta de opciones. Para obtener más información sobre el registro de entrada y salida, haga clic [aquí.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-best-practices-check-out-check-in "(se abre en una pestaña o una ventana nueva)")

Para obtener más información sobre funciones adicionales relacionadas con la carga de tablas, haga clic [aquí.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload-file "(se abre en una pestaña o una ventana nueva)")

**Eliminar una tabla**

1. Echa un vistazo a la tabla.
2. En la pestaña **Inicio**, en el grupo **Documento**, haga clic en **Eliminar**.
3. Consulte la tabla.

## Asignar datos a datos maestros

Después de cargar una tabla de datos de origen y transformarla si es necesario, puede asignarla a una tabla de datos maestros. Siga las siguientes instrucciones para asignar datos a una tabla de datos maestros.

Hay dos métodos disponibles para asignar datos a conjuntos de datos maestros:

- Columnas del mapa (preferidas)
- Anexar tablas

**Columnas del mapa**

El método principal (y preferido) para mapear datos es utilizar Map Columns.The La función Map Columns está diseñada para transformar su conjunto de datos de origen.

Si los datos se reutilizan para varios conjuntos de datos maestros, cree una nueva tabla utilizando la fuente de la tabla existente para cada conjunto de datos maestros y, a continuación, añada columnas de mapa.

**Añade el paso de canalización Columnas del mapa y elige un destino.**

1. Cree o consulte una tabla y añada datos a la misma. Además, puede aplicar pasos de canalización transformadores, como la partición por fecha.
2. Pasa el cursor por encima de los pasos del proceso y haz clic en **+** para añadir un nuevo paso. **Las columnas del mapa** estarán disponibles a menos que se añada un paso Modelo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/mapcol2.png)

   Nota: Si se ha revertido la tabla y no se ha revertido la carga de datos, el paso no estará disponible hasta que añada cualquier otro paso y, a continuación, añada Map Columns (Asignar columnas).
3. Haga clic en **Columnas del mapa** y seleccione un destino. Si no ve el conjunto de datos maestros que esperaba, vaya a **Componentes** e instale el componente necesario.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/map3.png)

## Asignar a una columna del conjunto de datos maestros

1. Revise las columnas de destino. Estas son las columnas de los conjuntos de datos maestros que se pueden asignar. Es posible que algunas ya estén asignadas porque el encabezado de una columna de la tabla coincide con un valor esperado en el destino.
2. Seleccione **Elegir fuente** en la columna Fuente o, para cambiar una asignación, seleccione uno de los otros valores de esa columna.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/master2.png)
3. Seleccione uno de los nombres de columna de la lista desplegable. Esta lista muestra todas las columnas de la tabla con un tipo de columna que coincide con el destino.

   Nota: La siguiente tabla de vista previa no se actualizará hasta que se guarde el cambio.

   Consejo: Si no ves las columnas que deseas en la lista desplegable, es posible que no sean del tipo adecuado para el destino. Vaya al paso Importar y cambie la opción Anular tipo según sea necesario. Si la columna esperada se creó en el canal de transformación, utilice o modifique el paso Fórmulas.
4. Para introducir una cadena o un número para todas las filas, seleccione **Introducir un valor fijo para todas las filas**. Como resultado, cada fila de la tabla muestra el mismo valor para esa columna. Esta opción no evalúa fórmulas. Para utilizar una fórmula, añada el paso **Fórmulas** y, a continuación, asigne la columna adicional resultante.
5. Introduzca el valor y haga clic **en Aceptar**. Ahora ha asignado dos columnas adicionales al conjunto de datos maestros seleccionando una columna de la tabla e introduciendo un valor.

**Añadir una columna personalizada al conjunto de datos maestros**

1. Para añadir una columna que no existe en el conjunto de datos maestros, haga clic en **Añadir columna personalizada**. Estas adiciones se mantendrán entre actualizaciones sin necesidad de realizar ninguna acción especial.
2. Introduzca el nombre de la columna que desea añadir y, a continuación, seleccione el tipo. Seleccione una fuente para esa columna, ya sea eligiendo otra columna de la tabla o un valor fijo.
3. Pulse **Aceptar**. Las columnas añadidas son siempre opcionales. Guarde la tabla para ver la columna en la vista previa.

**Añadir datos**

Este método es menos recomendable porque personaliza el conjunto de datos maestros, lo que aumenta el tiempo de actualización para recibir nuevos contenidos.

1. En el **Explorador de proyectos**, haga clic en la tabla de datos maestros que desee.
2. Echa un vistazo a la tabla.
3. En la canalización de transformación, haga clic en el paso **Añadir**.
4. Haga clic en **Añadir tabla** en el área de detalles.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ad1.png)
5. Seleccione una tabla de datos de origen y haga clic en **Siguiente.**
6. Asigne las columnas de origen a las columnas del conjunto de datos maestros utilizando la siguiente **opción Añadir a...** Imagen de datos maestros.

   Nota: Un asterisco (\*) en la columna Datos maestros indica que el campo es obligatorio para completar los informes relacionados con ese conjunto de datos. Se permite el mapeo parcial. Si no dispone de todos los datos necesarios, puede asignar un subconjunto de los campos obligatorios, aunque esto podría provocar que falten datos en uno o varios informes.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ad6.png)
7. Haga clic en la opción para guardar.

## Validar asignaciones de modelos

Utilice la vista de tabla del modelo para validar el flujo de valor en un modelo. Una vez que haya cargado y asignado los datos de origen a la tabla de datos maestros adecuada, las tablas modeladas asociadas deberían comenzar a mostrar tanto los impulsores unitarios como las asignaciones.

Una tabla modelada según el estándar de costes es una tabla a la que se ha añadido un paso de modelo. La tabla modelada es una transformación de una tabla de datos maestros. Por ejemplo, la tabla «Cost Source» es una transformación de la tabla «Cost Source Master Data». No se pueden añadir pasos adicionales al proceso de transformación en las tablas modeladas con Costing Standard. Los únicos pasos de transformación que se muestran para las tablas modeladas son **Origen** y **Modelo**.

**Diagrama de asignación de conductores**

Si hace clic en una tabla de modelos en **el Explorador de proyectos** y, a continuación, hace clic en el paso Modelo en el canal de transformación, se muestra un diagrama de asignación de controladores como se muestra a continuación. Utilice el diagrama para comprobar el flujo de valores hacia y desde la tabla.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/da.png)

El diagrama muestra el flujo de valor para la métrica del modelo seleccionada en el campo **Seleccionar una métrica** situado encima del diagrama. En la figura A anterior, la métrica es el coste. Puede seleccionar cualquiera de las métricas de modelo definidas para el proyecto.

**Realizar cambios**

Puede realizar cambios en las asignaciones del modelo de cálculo de costes estándar. Puede modificar las asignaciones existentes y añadir nuevas asignaciones. Antes de realizar cambios en un modelo, debe comprender a fondo cómo crear y modificar modelos.

Para obtener información sobre cómo trabajar con modelos, consulte [Acerca de Model Studio.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-about-model-studio "(se abre en una pestaña o una ventana nueva)")

## Instalación de nuevas soluciones de cálculo de costes IBM Apptio en proyectos de plantillas antiguas

Utiliza la página existente: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=configuration-installing-new-apptio-costing-solutions-older-template-projects
