---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Habilitar tiempo para un proyecto"
breadcrumb: []
source_path: "studio/admin/enable-time.html"
images:
  - "resources/images/studio_images/studio_admin_enable_time_sui.png"
  - "resources/images/studio_images/studioimages/studio/stu040_sui.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Habilitar tiempo para un proyecto

**Se aplica a** : TBM Studio 12.0 y posteriores. Uno de los conceptos más importantes de la aplicación son los proyectos que permiten ganar tiempo. En un proyecto temporal, se fijan las fechas de inicio y fin de los datos y se define el ejercicio fiscal. En un proyecto habilitado por tiempo, puede:

- Introducir datos periódicamente
- Asignarlo a un periodo de tiempo específico
- Ver las tendencias a lo largo de la duración del proyecto
- Ver los datos del informe del mes o periodo en curso, o de periodos trimestrales, semestrales o anuales
- La aplicación es compatible con los calendarios gregoriano y periódico. Sin embargo, debe utilizarse el mismo tipo de calendario en todos los proyectos.

No hay reglas fijas sobre cuándo se debe habilitar tiempo para un proyecto. Sin embargo, habilitar tiempo en un proyecto crea un entorno más complejo. Por esa razón, debe identificar las tablas clave, construir el modelo básico y definir las principales asignaciones antes de habilitar el tiempo. Sólo se puede activar el tiempo una vez para un proyecto, y la acción es irreversible. Una vez que haya activado el tiempo en un proyecto, no podrá desactivarlo.

La habilitación temporal de un proyecto afecta a algunas áreas de la aplicación, pero no a todas. El siguiente cuadro muestra las zonas afectadas y no afectadas.

| Zonas afectadas | Zonas no afectadas |
| --- | --- |
| Conjuntos de datos  - Modelos de - Notas - Datos mostrados en los informes | - Métricas - Definiciones de los informes |

## Habilitar tiempo para un proyecto

Nota: Para activar la hora, debe estar asignado a un rol que incluya el permiso **Configurar Ajustes de Hora**.

1. En la pestaña **Proyecto**, seleccione **Ajustes de tiempo**. Aparecerá la ventana **Configurar los ajustes de tiempo del proyecto**. Las opciones de campo de la ventana dependen del tipo de calendario que seleccione. Para obtener una descripción de los campos, consulte [Configurar los ajustes de tiempo del proyecto](configure-project-time.htm "(se abre en una pestaña o una ventana nueva)").

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu040_sui.png)
2. Seleccione los valores que desee y seleccione **Configurar hora**. La fecha aparece en la cabecera.

## Los nuevos proyectos no están habilitados temporalmente

Cuando se crea un nuevo proyecto por primera vez, no está activado el tiempo. Puede cambiar sus conjuntos de datos, transformaciones y modelos, y cada cambio sobrescribe la información actual del proyecto. Esto está representado por el lado No Activado por Tiempo de este diagrama:

![](../../resources/images/studio_images/studioimages/visio%20diagrams/time-enabling_597x336.png)

Cuando se activa el tiempo en un proyecto, todos los cambios realizados en la estructura de las tablas de datos crean un nuevo estado para los datos del proyecto. En la aplicación, los estados se conocen como Versiones. El nuevo estado se aplica a partir del periodo actualmente seleccionado hasta que se encuentre otro estado para los datos. En el diagrama anterior, esto está representado por el lado Time-Enabled.

## Determinar si se ha activado la hora

Puede saber si se ha activado la hora en un proyecto mirando la cabecera Global. Antes de que se haya activado la hora, si tiene privilegios para activar la hora, el encabezado Global mostrará Configurar fechas. Si no tiene privilegios para activar la hora, la cabecera Global no mostrará Configurar fechas.

Cuando se ha activado el tiempo en un proyecto, la cabecera Global muestra el periodo actualmente seleccionado, como se muestra en la siguiente imagen:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_admin_enable_time_sui.png)

## Buenas prácticas para proyectos con plazos definidos

Trabajar con proyectos temporales puede tener a veces resultados inesperados. Tenga en cuenta lo siguiente:

- Si realiza un cambio en un modelo o una tabla, asegúrese de que se encuentra en el mes o period.For deseado. Por ejemplo, si desea realizar un cambio efectivo a partir del mes/período más antiguo de su proyecto, asegúrese de seleccionar dicho mes/período en el selector de fechas antes de realizar el cambio. Si desea realizar un cambio efectivo a partir del mes/periodo actual, asegúrese de que está seleccionado el mes/periodo actual.
- La aplicación admite los siguientes tipos de calendario para proyectos personalizados y proyectos de aplicación. Para aplicaciones distintas de las personalizadas y Costing Standard, sólo se admite el calendario gregoriano.
  - Gregoriano
  - 445, 454 y 544
  - 13 periodo

Nota: Debe utilizarse el mismo tipo de calendario en todos los proyectos.

## Ver datos en diferentes periodos de tiempo

Si el tiempo está activado para un proyecto, puede ver tablas y modelos para diferentes periodos, y puede ver informes para meses y otros periodos de tiempo. Por ejemplo, si cargaste datos de enero de 2016 a diciembre de 2016, podrías seleccionar cualquier periodo y mirar las métricas de tu modelo con los datos del periodo seleccionado. También podría seleccionar Fiscal Q1 de 2016 y consultar sus informes con los datos del trimestre.

Para ver los datos en diferentes periodos de tiempo:

1. En la cabecera Global, haga clic en el periodo de tiempo que se muestra actualmente. Aparece el selector de fechas. Los periodos de tiempo del selector de fechas reflejan el ejercicio fiscal definido para el proyecto.
2. Utilice el selector de fechas para seleccionar un mes o período, trimestre, semestre o año completo.
3. Haga clic en el mes o periodo que desee consultar.
4. Puede seleccionar los botones Q1 - Q4 en la parte izquierda del cuadro de diálogo, los botones H1 y H2 en la parte derecha del cuadro de diálogo, y el botón FY (Año Fiscal) en la parte inferior del cuadro de diálogo.
   - Para retroceder o avanzar por los años, haga clic en las flechas situadas a la izquierda y a la derecha de los años en la parte superior del cuadro de diálogo y, a continuación, seleccione una de las fechas mostradas. Si una flecha aparece en gris y no puede pulsarse, significa que se ha alcanzado la fecha de inicio o fin del proyecto.
   - Si el selector de fechas muestra periodos en lugar de meses, puede señalar uno de los periodos y se mostrará un tooltip con las fechas de inicio y fin del periodo.
5. El periodo de tiempo que seleccione aparecerá en la parte superior de la ventana del navegador. Los datos mostrados en un informe corresponden al periodo de tiempo seleccionado.
