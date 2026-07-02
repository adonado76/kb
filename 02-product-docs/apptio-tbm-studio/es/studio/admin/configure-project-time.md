---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar los ajustes de tiempo del proyecto"
breadcrumb: []
source_path: "studio/admin/configure-project-time.html"
images:
  - "resources/images/studio_images/custom_calendar/append-1.png"
  - "resources/images/studio_images/custom_calendar/click-to-upload.png"
  - "resources/images/studio_images/custom_calendar/fiscal-calendar-1.png"
  - "resources/images/studio_images/custom_calendar/time-setting-dates.png"
  - "resources/images/studio_images/studioimages/studio/stu040.png"
  - "resources/images/studio_images/studioimages/studio/stu179.png"
  - "resources/images/studio_images/studioimages/studio/stu180.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar los ajustes de tiempo del proyecto

**Se aplica a** : TBM Studio 12.0 y posteriores. Las opciones que aparecen en el cuadro de diálogo **Configurar ajustes de hora del proyecto** dependen del tipo de calendario que seleccione.

Al configurar los ajustes de tiempo del proyecto, tenga en cuenta las siguientes directrices:

- Cuando guarde la configuración, no podrá volver atrás y cambiar la definición del año fiscal.
- Si desea incluir datos históricos en su proyecto, elija una fecha de inicio del proyecto que abarque las fechas de los datos.

## Tipos de calendario admitidos

La aplicación admite los siguientes tipos de calendario:

- Gregoriano
- 445, 454 y 544
- 13 periodo (444)

El tipo de calendario que seleccione determina los campos que aparecen en la sección **Definición del ejercicio** del cuadro de diálogo **Configurar ajustes de tiempo del** proyecto que se muestra en la siguiente imagen. No puede cambiar el tipo de calendario una vez establecido.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu040.png)

Nota: Debe utilizarse el mismo tipo de calendario en todos los proyectos.

Los campos de cada tipo de calendario se describen en la siguiente información. En primer lugar se describen los campos de la sección **Definición del ejercicio**, seguidos de las descripciones de las secciones **Definición del intervalo de tiempo del proyecto**, **Períodos de tiempo visibles** y **Períodos editables**. Estas últimas secciones son similares para todos los tipos de calendarios.

## Definición de ejercicio fiscal - Calendario gregoriano

A continuación se describen los campos del calendario gregoriano.

- **Tipo de calendario** - Seleccione el tipo de calendario gregoriano.
- **El Ejercicio Fiscal se Define Por** - Seleccione **Período Inicial** o **Período Final**. Si selecciona **Período inicial**, el ejercicio se basa en el primer período del calendario. Si selecciona **Período final**, el ejercicio se basa en el último período del calendario.
  - Por ejemplo, supongamos que tiene un ejercicio fiscal que va de junio de 2016 a mayo de 2017. Si selecciona **Período inicial**, el ejercicio será 2016. Si selecciona **Período final**, el ejercicio será 2017.
- **Mes de inicio del año fiscal** - Seleccione un mes/período que será el inicio del año fiscal.

  Nota: Una vez que guarde esta configuración, no podrá cambiarla.
- **Mostrar nombres de mes o período** - Elija si las fechas mostrarán el nombre del mes (e. g.: Ene 2016, Feb 2016), o del período (e. g.: P1 2016, P3 2016). Esta configuración se aplica a muchas áreas del producto, incluido el selector de fechas.
  - Si su año fiscal comienza en un mes distinto de enero, puede que desee mostrar períodos en lugar de meses para eliminar la confusión sobre a qué año fiscal pertenece un mes to.For ejemplo, suponga que su año fiscal comienza el 1 de abril y el año fiscal se define por la fecha de inicio. La fecha 15 de abril de 2016 pertenecería al ejercicio 2016 y aparecería como Periodo 1. La fecha 15 de marzo de 2016 pertenecería al ejercicio 2015 y se mostraría como Periodo 12.

## Definición de ejercicio fiscal - 445, 454 y 544

A continuación se describen los campos de los calendarios 445, 454 y 544.

- **Tipo de** calendario - Seleccione un tipo de calendario 445, 454 o 544. Las cifras representan el número de semanas de cada uno de los cuatro trimestres del año fiscal. Por ejemplo, 445 representa 4 semanas, 4 semanas, 5 semanas.
- **El Ejercicio Fiscal se Define Por** - Seleccione **Período Inicial** o **Período Final**. Si selecciona **Período inicial**, el ejercicio se basa en el primer período del calendario. Si selecciona **Período final**, el ejercicio se basa en el último período del calendario.
- Por ejemplo, supongamos que tiene un ejercicio fiscal que va de junio de 2016 a mayo de 2017. Si selecciona **Período inicial**, el ejercicio será 2016. Si selecciona **Período final**, el ejercicio será 2017.
- **El calendario** fiscal - Utilice los cuatro campos de esta sección para definir el día inicial o final del calendario fiscal. Seleccione valores de cada una de las listas desplegables.
- **Mostrar nombres de mes o período** - Elija si las fechas mostrarán el nombre del mes (e. g.: Ene 2016, Feb 2016), o del período (e. g.: P1 2016, P2 2016). Esta configuración se aplica a muchas áreas del producto, incluido el selector de fechas.

## Calendario personalizado 454

**¿Cómo configurar el calendario del cliente? (Configuración por primera vez)**

1. Puede seleccionar el Tipo de Calendario como 445 o variante y cambiar el **Calendario Fiscal** de Estándar a Personalizado. Aparecerá un widget de carga con el texto "Haga clic para cargar".

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/custom_calendar/fiscal-calendar-1.png)
2. El widget Haga clic para cargar tiene un aspecto similar al de la tubería de transformación:

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/custom_calendar/click-to-upload.png)
3. Puede consultar el archivo de calendario personalizado haciendo clic en la opción Añadir del menú desplegable. Una vez que subas el nombre del archivo, aparecerá el nombre del archivo en el cuadro de diálogo de ajuste de la hora.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/custom_calendar/append-1.png)
4. Una vez que haya terminado con la selección de otros campos, puede seleccionar el botón **Configurar hora**. Después de cargar su archivo de calendario, la hora de Inicio del proyecto y Fin del proyecto se actualizará para reflejar el archivo de calendario.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/custom_calendar/time-setting-dates.png)
5. Desde el cuadro de diálogo de configuración de la hora, puede **Descargar** el calendario personalizado configurado o **Añadir** más configuraciones de calendario.
6. La reconfiguración del calendario puede hacerse a través de la configuración del proyecto. Como parte de una reconfiguración, puede **anexar** el archivo de calendario existente que, a su vez, ampliará las fechas del calendario. Cuando vuelva a cargar el archivo de calendario, la hora de finalización del proyecto se actualizará según la nueva hora de finalización del archivo de calendario.

Nota: La fecha de **inicio del proyecto** no se modificará durante la reconfiguración. Sólo cambiará una vez cuando configures el proyecto por primera vez. Sólo el **final del proyecto** cambiará con cada nueva carga del archivo.

## ¿Cómo se migra?

La información histórica del calendario se migra mediante una acción en /data. La migración será sólo para proyectos que tengan el tipo de calendario 445. Para emigrar:

- Para migrar a la configuración del calendario personalizado, debe tener un proyecto estándar con el tipo de calendario 445 configurado.
- Póngase en contacto con el equipo de atención al cliente para migrar la información de su calendario estándar y su configuración personalizada.

Nota: Dado que el inicio y el final del proyecto vienen dictados por la tabla de calendario cargada, ya no son configurables a través del cuadro de diálogo de ajustes de tiempo. Esto significa que una vez que usted a bordo en este Calendario Personalizado 454, no se puede volver atrás y cambiar las fechas. La fecha de inicio del proyecto sólo se configura una vez al configurar el proyecto por primera vez. Sólo se actualiza el final del proyecto con cada nueva carga del archivo.

## Tabla de calendarios

1. Columnas obligatorias: FiscalYear, StartsOnInclusive
2. La tabla no está versionada en el tiempo, y cargada en el periodo inicial.
3. La validación de la columna y el formato se realiza al cargar correctamente el archivo de calendario.
4. La tabla debe tener el primer período del año n + 1, para calcular el final del año n.
5. Si desea corregir errores en una tabla de calendario registrada, vuelva a establecer la hora de registro.

   Por ejemplo, la tabla Calendario.

   | Año fiscal | Comienza en Inclusive |
   | --- | --- |
   | 2021 | 4 de febrero de 2021 |
   | 2021 | 4 de marzo de 2021 |
   | 2021 | 8 de abril de 2021 |
   | 2021 | 6 de mayo de 2021 |
   | 2021 | 3 de junio de 2021 |
   | 2021 | 8 de julio de 2021 |
   | 2021 | 5 de agosto de 2021 |
   | 2021 | 2 de septiembre de 2021 |
   | 2021 | 7 de octubre de 2021 |
   | 2021 | 4 de noviembre de 2021 |
   | 2021 | 2 de diciembre de 2021 |
   | 2021 | 6 de enero de 2022 |
   | 2022 | 3 de febrero de 2022 |

**Notas** :

- Sólo se puede migrar a Calendario Personalizado en el límite de Fin de Año y antes de que se carguen datos o se realicen cambios de configuración en el año siguiente.
- Si se han cargado datos o se han realizado cambios en la configuración, será necesario revertirlos.
- Los clientes que utilicen un calendario no gregoriano (por ejemplo, 445, 454, 544 o 13 periodos), deben empezar a planificar la transición antes de fin de año.

## Definición del ejercicio - 13 Período (444)

A continuación se describen los campos de los calendarios de 13 periodos (444).

- **Tipo de calendario** - Seleccione el tipo de calendario de 13 periodos (444). Los números representan el número de semanas de cada uno de los periodos del ejercicio: 4 semanas, 4 semanas, 4 semanas.
- **El Ejercicio Fiscal se Define Por** - Seleccione **Período Inicial** o **Período Final**. Si selecciona **Periodo inicial**, el ejercicio se basa en el primer peri del calendario. Si selecciona **Período final**, el ejercicio se basa en el último período del calendario.
  - Por ejemplo, supongamos que tiene un ejercicio fiscal que va de junio de 2016 a mayo de 2017. Si selecciona **Período inicial**, el ejercicio será 2016. Si selecciona **Período final**, el ejercicio será 2017.
- **El calendario** fiscal - Utilice los cuatro campos de esta sección para definir el día inicial o final del calendario fiscal. Seleccione valores de cada una de las listas desplegables.
- **El trimestre con 4 periodos es el cuarto** - En un calendario de 13 periodos, tres trimestres tienen tres periodos cada uno. El cuarto trimestre tiene cuatro periodos. Seleccione el trimestre que tendrá cuatro periods.In el ejemplo siguiente, el primer trimestre tiene cuatro períodos:![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu179.png)

Nota: El próximo Servicio de Calendario Fiscal (FCS) centralizado utilizará una tabla cargada similar a la configuración del Calendario Personalizado. **TBM Studio** > **La configuración de tiempo** ya no se utilizará para administrar las actualizaciones del calendario fiscal. En su lugar, la tabla se cargará y gestionará en FCS y funcionará con otros productos de Apptio a medida que se integren con FCS.

## Definición de la duración del proyecto

A continuación se describen los campos de **la Definición del intervalo de tiempo del proyecto**.

- **Inicio del proyecto** - Haga clic en el campo y seleccione un mes y un año para la fecha de inicio del proyecto. Utilice las flechas de los márgenes izquierdo y derecho del selector de fechas para desplazarse entre años.

  Nota: Una vez guardada la fecha de inicio de un proyecto, no podrá modificarla. El campo **Inicio del proyecto** también se utiliza para seleccionar períodos de tiempo visibles, consulte [Períodos de tiempo visibles](#Configureprojecttimesettings__ViewablePeriodsofTime)
- **Fin del proyecto** - Haga clic en el campo y seleccione un mes y un año para la fecha de fin del proyecto. Utilice las flechas de los márgenes izquierdo y derecho del selector de fechas para desplazarse entre años. Puede modificar esta fecha en cualquier momento.
- Cuando fije la fecha de finalización, tenga en cuenta que la aplicación realiza cálculos hasta la fecha de finalización. Cuantos más meses haya que calcular, más tiempo llevarán los cálculos. Por esta razón, es mejor fijar la fecha de finalización del proyecto con suficiente antelación para cubrir las necesidades de planificación y previsión, pero no tanto como para provocar cálculos innecesarios.
- **Activar periodo** de tiempo predeterminado: si se marca esta opción, se activa el campo Periodo de tiempo predeterminado.
- Período de **tiempo por defecto** - El período que seleccione será el período de tiempo por defecto que se mostrará a todos los usuarios cuando abran un proyecto. Puede seleccionar un periodo, trimestre, semestre o año completo. Los usuarios pueden cambiar el periodo de tiempo utilizando el selector de fechas. Establecer el periodo de tiempo por defecto es útil para proyectos que dependen del tiempo, como la elaboración de presupuestos y previsiones.
- Si no establece un periodo de tiempo por defecto, cuando un usuario abre un proyecto, se muestra el último periodo de tiempo activo.

## Períodos de tiempo visibles

Seleccione los periodos que se mostrarán en el selector de fechas. Serán meses para los calendarios gregorianos y periodos para el resto de tipos de calendario. Debe seleccionar al menos una opción del grupo, pero también puede seleccionar cualquier combinación de opciones. Por ejemplo, puede seleccionar sólo meses, meses y trimestres, o trimestres y semestres. Puedes cambiar esta configuración en cualquier momento.

Para seleccionar un mes o un período, utilice los siguientes campos de **Definición del intervalo de tiempo del proyecto** :

- **Inicio del proyecto** - Haga clic en el campo y seleccione un mes y un año para el período de tiempo que desea ver. Utilice las flechas de los márgenes izquierdo y derecho del selector de fechas para desplazarse entre años.
- **Fin de proyecto** - Haga clic en el campo y seleccione un mes y un año para el período de tiempo que desea ver. Utilice las flechas de los márgenes izquierdo y derecho del selector de fechas para desplazarse entre años.

Los periodos seleccionados controlan los periodos incluidos en el preprocesamiento. Los años tardarán menos en procesarse que las mitades o los cuartos. Puede seleccionar cualquier combinación de las tres. Los cálculos mensuales/periódicos se realizan por defecto. Si los usuarios sólo van a ver informes por meses o períodos, no seleccione estas opciones.

## Periodos editables

Puede haber proyectos en los que desee cerrar la entrada de datos durante determinados periodos. Por ejemplo, si está elaborando un presupuesto, es posible que desee cerrar el período de presupuestación actual una vez finalizado el presupuesto. En el selector de fechas, los nombres de los periodos cerrados aparecen en cursiva y la barra situada en la parte superior del periodo es de color gris. En el ejemplo siguiente, enero, febrero y marzo están cerrados:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu180.png)

Mediante el campo **Períodos cerrados**, puede seleccionar los períodos que desea cerrar. Haga clic en el campo para mostrar un selector de fechas en el que puede seleccionar meses o periodos, trimestres, semestres o años completos. Este ajuste cierra el periodo para los conjuntos de datos, la entrada de datos a través de tablas editables en los informes y las cuadrículas de asignación en los modelos. Puedes cambiar esta configuración en cualquier momento.
