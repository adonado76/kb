---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Editar la configuración del proyecto"
breadcrumb: []
source_path: "studio/admin/edit-project-settings.html"
images:
  - "resources/images/studio_images/3707-edit.jpg"
  - "resources/images/studio_images/studio_auto_calculate.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Editar la configuración del proyecto

**Se aplica a** : TBM Studio 12.0 y posteriores. Algunos ajustes están disponibles en versiones posteriores de TBM Studio, como se indica a continuación.

Después de crear un proyecto, puede editar la configuración del mismo.

1. Para mostrar la cinta en el menú Aplicaciones/Proyectos, haga clic en **TBM Studio**.
2. En la pestaña **Proyecto**, en el grupo **Configuración del proyecto**, haga clic en **Configuración del proyecto**. Aparecerá el cuadro de diálogo Editar configuración del proyecto.

Nota: El campo Mensaje de inicio de sesión quedó obsoleto en TBM Studio 12.4.1.

A continuación se describen los campos del cuadro de diálogo **Editar configuración del proyecto**. Los campos que requieren la función Admin de Apptio están marcados con un asterisco (\*). Si no tiene asignada la función Admin, no verá estos campos.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/3707-edit.jpg)

- **Dominio** - El dominio es el entorno Apptio establecido para su organización. Todos los proyectos se crean en el mismo dominio. Este campo no se puede editar.
- **Nombre** - El nombre del proyecto y de la compilación creados para su organización. Este campo no se puede editar.
- **Derivado de** - Si el proyecto se derivó de un proyecto existente, en este campo se muestra el nombre del proyecto de origen**.NOTICE**

  En TBM Studio R12, no puede crear un nuevo proyecto a partir de un proyecto existente. Si actualiza de v11 a R12, los proyectos derivados mostrarán el proyecto fuente en este campo, pero no podrá cambiar la derivación.
- **Versión de** componentes - Especifique qué versión utilizar para las actualizaciones de componentes. Para obtener más información, consulte [Especificar la versión para las actualizaciones de componentes](specify-version-component.html "◆ Se aplica a: TBM Studio 12.3.1 y versiones posteriores. Al actualizar aplicaciones dentro de TBM Studio, puede especificar qué versión utilizar para las actualizaciones de componentes. Esta configuración se aplica a todas las actualizaciones de componentes y a las nuevas instalaciones de componentes.").
- **Color Spec** - Introduzca una cadena de formato de color para cambiar el color de una entidad en todos los gráficos. Para obtener más información, consulte [Establecer los colores predeterminados para las métricas del proyecto](set-default-colors.html "Se aplica a: TBM Studio 12.0 y posteriores").
- **Moneda base** - Si el proyecto utiliza varias monedas, seleccione la moneda por defecto que se utilizará para mostrar los valores en los informes. Los usuarios pueden anular esta configuración eligiendo una moneda diferente para los informes que visualizan. Para obtener más información, consulte [Configurar la multidivisa](configure-multi-currency.html "Se aplica a: TBM Studio v12.1 y posteriores").
- Activar Servicio Multidivisa - Introducido en TBM Studio 12.10.5, este ajuste le permite activar el Servicio Multidivisa para su proyecto. El Servicio Multidivisa proporciona una plataforma centralizada para gestionar las tablas de cambio de divisas de sus productos Apptio.

  [¿Qué es el servicio multidivisa?](/docs/SSPA2JP/multi-currency/gettingstarted/mcs-overview.html)

  El servicio multidivisa se activa automáticamente para todos los nuevos proyectos que utilizan un calendario gregoriano. Para los proyectos existentes que utilizan un calendario gregoriano, puede activar manualmente el Servicio Multidivisa seleccionando esta casilla. Actualmente, el Servicio Multidivisa no admite proyectos que utilicen calendarios de 13 periodos o de 454 variantes.

  Nota: Tenga en cuenta que una vez activado el Servicio Multidivisa desde el cuadro de diálogo Configuración del proyecto, no podrá revertirlo sin una reversión.

  Una vez habilitado el servicio multidivisa y comprobada la configuración del proyecto, las tablas de cambio se sincronizan automáticamente para que coincidan con los datos almacenados en las tablas del servicio multidivisa. La moneda base también se actualiza para que coincida con los datos almacenados en el Servicio Multidivisa. Una vez activado el Servicio Multidivisa, las tablas de cambio de divisas del proyecto ya no son editables desde TBM Studio; sólo puede editar estas tablas desde la interfaz del Servicio Multidivisa.

  [Sincronización de la tabla de cambio de divisas](/docs/SSPA2JP/multi-currency/admin/currency-exchange-table-sync.html)
- **Localidad** - Seleccione un país. La selección determina los formatos de número, moneda y fecha utilizados en el proyecto para los informes y las métricas.
- **Localidad de ordenación** - Se utiliza en proyectos localizados para determinar cómo ordenar los datos. Seleccione un país. Las opciones actuales son Estados Unidos y Japón. La clasificación es insensible a mayúsculas/minúsculas/insensible a kana/insensible a anchura y sensible a diacríticos.
- **Actualización diferida** - Se utiliza para diferir el tiempo para que los usuarios seleccionen filtros, selectores o rebanadores y vean los resultados actualizados basados en el informe. Para más información, consulte [aquí](../reports/delayed-refresh.html).
- **Legacy Date Parsing** - Esto es necesario para la compatibilidad con versiones anteriores para que el análisis de la fecha funcione de la misma manera después de las actualizaciones. Habilite el check in para el icono Legacy Date Parsing.
- **Activar Apex UI** - Este ajuste se introdujo en TBM Studio 12.11.0. Esto se utiliza para activar o desactivar el aspecto de la interfaz de usuario a GWT. Para más información, consulte [aquí](../getting_started_with_tbm_studio/apex-ui-uplift.html "Se aplica a: 12.11.0 y posteriores").
- **Activar publicación periódica** - Esta opción se introduce en TBM Studio 12.11.8. Permite al TBMA publicar los datos editables de la tabla a su transformador configurando un calendario. Para más información, consulte [Publicación periódica](recurring-publish-et.html "Se aplica a: 12.11.7 y posteriores. La opción Publicación recurrente permite a la TBMA programar calendarios de publicación recurrentes automáticos para tablas editables que tienen tablas de transformación. Una vez activada esta función, la opción 'Publicar en periodo' se convierte en programación por defecto, y se adjuntará en el pipeline de Tabla Editable, bajo Transformar Tabla. Todos los 'Publicar en periodo' se convertirán en programación por defecto en la página de Programación Recurrente, y la Transformación vinculada a la programación estará disponible en la página de Tabla de Transformaciones.").
- **Desactivar el flujo de datos en Transformación enriquecida** - Esta opción impide que los datos de la tabla sin procesar se muevan automáticamente a la tabla Transformación, en el entorno de desarrollo, sólo si la tabla se comprueba. para más información, consulte [Desactivar el flujo de datos](../data_studio/create-table-from-et.html).
- **Permitir Guardar Tabla Editable con Errores de Validación** - Esta opción le permite guardar las filas en el informe incluso si hay algún error de validación.
- **Compactación de números** - (Este ajuste se introdujo en TBM Studio 12.3. Para más información, consulte las notas de la versión. Algunas industrias (como la del petróleo y el gas) utilizan miles y millones de notaciones financieras diferentes (como K, KK o MM) que no se emplean en otras industrias. Esta notación es la que utilizan los KPI. Para personalizar las abreviaturas de compactación, haga clic en Personalizar y, a continuación, introduzca los valores de abreviatura que desee.
- **Símbolos de divisa** - Si el proyecto utiliza varias divisas, seleccione la opción de visualización de divisas que desee. Para obtener más información, consulte [Configurar la multidivisa](configure-multi-currency.html "Se aplica a: TBM Studio v12.1 y posteriores").
- **Tamaño de página por defecto\* -** Establece el tamaño de página por defecto de los informes cuando se imprimen. Este campo sólo está disponible para el rol Apptio Admin.
- **Activar pestañas de aplicación\*-** Esta opción no se aplica en la versión actual del producto. El campo sólo está disponible para el rol Apptio Admin.
- **Plugin** - Este campo sólo está disponible para el rol Apptio Admin.
- **Métrica por defecto** - La métrica por defecto del modelo es Coste. Si tiene otras métricas definidas, estarán disponibles en la lista desplegable.
- **Proyecto presupuestario\*** - Este campo sólo está disponible para el rol Apptio Admin. Controla el comportamiento de desplazamiento temporal para las métricas de planificación de TI heredadas de varios proyectos. La activación de esta opción mejora considerablemente la velocidad de procesamiento. Si utiliza el Asistente de planificación informática para crear un proyecto, este campo se configura automáticamente.
- **Activar acceso anticipado** : si se marca esta opción, los usuarios pueden acceder a funciones que aún están en fase de desarrollo. En general, no debe marcar esta opción.
- Autocalcular **espacios de trabajo\*** - Determina la configuración por defecto del icono Autocalcular en la pestaña **Inicio**. Si se marca esta opción, el cálculo automático se activará cuando un usuario inicie sesión en un proyecto. Cuando un usuario registra un documento, la aplicación actualiza todos los documentos que el usuario ha retirado. Cuando la opción está desactivada, el usuario puede ejecutar actualizaciones manualmente utilizando las otras opciones de Actualización: Actualizar documento y Actualizar área de trabajo. El usuario también puede activar la opción Cálculo automático haciendo clic en el icono.

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_auto_calculate.png)

  Para proyectos con grandes bases de datos que requieren mucho tiempo de cálculo, le recomendamos que desactive la opción y deje que el usuario determine si desea activar el cálculo automático.
- **Activar Descripciones Obligatorias** de Registro - (Se aplica a TBM Studio 12.7.1. y posteriores) Esta opción puede obligar a los usuarios a introducir una descripción cada vez que registran el trabajo. Cuando se marca la casilla de esta opción, los usuarios no podrán hacer clic en Registrarse hasta que se escriba algo en el cuadro de mensaje (mostrado arriba). Antes de escribir un mensaje, el cursor aparecerá como un círculo tachado en rojo con una pantalla: Por favor, añada un mensaje para registrarse.

  ![imagen](../../resources/images/studio_images/studioimages/studio_check%20in_check%20in_sui.png)
- **Mostrar valor (en blanco) en tablas/rebanadoras** - (Se aplica a TBM Studio 12.7.1. y posteriores). Esta opción actualiza el modo en que las tablas y las rebanadoras muestran los valores en blanco, del mismo modo que los gráficos rellenan automáticamente los valores en blanco con (En blanco). Por defecto, las tablas y los slicers no mostrarán un valor si un campo está vacío, lo que se ve en el lado Desmarcado más abajo. Cuando esta casilla está marcada, el sistema rellenará las celdas vacías de las tablas y las rebanadoras con (En blanco), como se muestra en la parte marcada de abajo. Esto facilita el filtrado y la realización de operaciones en campos con un valor en blanco.

  ![imagen](../../resources/images/studio_images/studioimages/studio_project%20settings_unchecked%20checked_sui.png)
- **Mostrar valores con signo para**.No asignados - La columna "No asignados" de la tabla.No asignados mantiene el valor absoluto de los Costes asignados, ya que es necesario para calcular correctamente los % de valores asignados.
- **Utilizar expresiones regulares en Lookup Wild** - Las expresiones regulares en columnas que utilizan valores de retorno de Lookup\_Wild ayudan a obtener la granularidad deseada en la asignación de proveedores.
- **¡Manejar automáticamente!ALL\_ROWS** - Añade y quita automáticamente permisos donde sea necesario. Es decir, elimina la necesidad de marcar la casilla de todas las filas en las perspectivas.
- **Informe por defecto para la página** de aterrizaje o de inicio - Este es el informe por defecto que aparece para el usuario en su página de aterrizaje o de inicio.
- **Métrica AUM** - Esta es la lista de métricas modeladas a utilizar para los cálculos de Gasto Bajo Gestión. Es una variable del sistema que se puede utilizar en el panel de Configuración de Componentes Ad Hoc para una Tabla Publicada.
- **Objeto modelado AUM** : esta es la lista de objetos modelados que se utilizarán para los cálculos de gasto bajo gestión. Es una variable del sistema que se puede utilizar en el panel de Configuración de Componentes Ad Hoc para una Tabla Publicada.
- **Canal de artefactos del catálogo** : el canal de catálogo que debe seleccionarse es Estable.

- **[Crear una tabla a partir de una tabla editable](../../studio/data_studio/create-table-from-et.html)**
