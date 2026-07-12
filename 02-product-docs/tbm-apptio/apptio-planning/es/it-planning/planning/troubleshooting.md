---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Solución de errores de carga de datos de planificación"
breadcrumb:
  - "Planning"
  - "Solución de problemas y preguntas frecuentes"
source_path: "it-planning/planning/troubleshooting.html"
images:
  - "resources/images/it_planning_images/102-11870-20-228451_nl_invalidformatting.jpg"
  - "resources/images/it_planning_images/102-11870-20-228473_nl_unknowncolumns1.jpg"
  - "resources/images/it_planning_images/102-11870-20-228694_itperror2.jpg"
  - "resources/images/it_planning_images/102-11870-20-231306_nl_settingunknownlookupvalue.jpg"
  - "resources/images/it_planning_images/102-11870-20-232951_itperror3.jpg"
  - "resources/images/it_planning_images/102-11870-20-232952_itperror4.jpg"
  - "resources/images/it_planning_images/231008.jpg"
  - "resources/images/it_planning_images/231305.jpg"
  - "resources/images/it_planning_images/232953.jpg"
  - "resources/images/it_planning_images/246685.jpg"
  - "resources/images/it_planning_images/246687.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Solución de errores de carga de datos de planificación

Es posible que se encuentre con alguno de los siguientes errores al cargar datos en Planning. Consulte las siguientes secciones para identificar el error que está experimentando.

Modificaciones de filas

- [El archivo cargado contiene una o más columnas desconocidas que serán ignoradas](#TroubleshootPlanningdatauploaderrors__Uploaded)
- [Formato no válido de los datos cargados](#TroubleshootPlanningdatauploaderrors__Invalid)
- [No se han podido resolver una o varias referencias a otra tabla](#TroubleshootPlanningdatauploaderrors__Could)
- [Establecer el valor de búsqueda desconocido como predeterminado](#TroubleshootPlanningdatauploaderrors__Setting)
- [Los archivos cargados contienen más de una columna con nombres de alias reservados para la misma columna](#TroubleshootPlanningdatauploaderrors__Uploaded2)

Omisiones de filas

- [Asignaciones no válidas de centros de coste y objetos de coste](#TroubleshootPlanningdatauploaderrors__Invalid2)
- [No se han podido resolver una o varias referencias a otra tabla](#TroubleshootPlanningdatauploaderrors__Could2)
- [Los datos cargados incluyen partidas que han sido delegadas de otros objetos de coste, estas partidas serán excluidas](#TroubleshootPlanningdatauploaderrors__Uploaded3)

Otros errores

- [Lo sentimos, pero no podemos publicar... dimensión](#TroubleshootPlanningdatauploaderrors__Were)
- [No se han detectado cambios: 1 error detectado en <Dataset>, incluyendo lo siguiente: El archivo cargado no contenía ninguna columna en la fila de encabezado](#TroubleshootPlanningdatauploaderrors__No)
- [No se han detectado cambios: 1 error detectado en <Dataset>, incluyendo los siguientes: Cabecera vacía](#TroubleshootPlanningdatauploaderrors__No2)
- [Los datos reales del usuario no aparecen en la previsión.](#TroubleshootPlanningdatauploaderrors__useract)
- [Una dimensión específica está en blanco en la previsión](#TroubleshootPlanningdatauploaderrors__A)

## Modificaciones de filas

Los errores de Modificación de filas se producen cuando los valores no requeridos de los datos importados son incoherentes con las plantillas de la aplicación o los Datos de referencia. Planning modificará automáticamente los datos cuando se produzcan estos errores para garantizar que, por lo demás, la importación se realice correctamente. En la mayoría de las situaciones, los datos no válidos se modifican o eliminan de la importación, mientras que los datos restantes se importan.

## El archivo cargado contiene una o más columnas desconocidas que serán ignoradas

Síntoma
:   ![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/102-11870-20-228473_nl_unknowncolumns1.jpg)

    Las columnas de la lista no se importan a Planning, pero otras columnas válidas se importan normalmente.

¿Qué está pasando?
:   Los archivos cargados deben seguir la plantilla Planning y la colocación de las columnas. Las columnas que no forman parte de las plantillas de Planning no se reconocen y no se cargarán.

    El mensaje de error debe listar todas las instancias de columnas omitidas.

Solución
:   Asegúrese de que está importando datos utilizando la plantilla Planning asociada.

    1. Navegue hasta la página a la que desea importar datos.
    2. Haga clic en el botón Acciones y, a continuación, seleccione:
       - Exportar <Nombre de página> Plantilla... para descargar una plantilla en blanco.
       - Exportar <Nombre de página>... para descargar todos los datos actuales en formato de plantilla.
    3. Las plantillas están en el tipo de archivo.CSV, que puede editarse con Excel.
       - Todas las columnas aceptadas por Planning se incluirán en la plantilla.

## Formato no válido de los datos cargados

Síntoma
:   ![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/102-11870-20-228451_nl_invalidformatting.jpg)

    Los valores listados no se cargan en Planning, lo que puede dejar huecos en su conjunto de datos.

¿Qué está pasando?
:   Planning ha identificado datos con formato incorrecto. Como se explicó en la entrada anterior, Planning utiliza plantillas para la importación de datos. Cada columna del modelo requiere un tipo específico de datos (es decir, texto, numéricos, etc.). La causa más común de este error es la falta de correspondencia con el tipo de valor correcto para una columna.

    El mensaje de error debe enumerar todos los casos de datos formateados incorrectamente.

Solución
:   Investigue sus datos y confirme que todos los datos de las columnas están formateados correctamente para su respectiva columna.

    - Números: sin formato, puntuación ni símbolos (600000).
    - Texto: sin puntuación (Ejecutivo). Se admiten espacios si es necesario (Cuentas a Pagar).
    - Fecha: Para obtener más información, consulte [Resolución de problemas de formatos de fecha no válidos en Planificación](ts_invalid_date_formats.html).
    - Las ecuaciones o funciones de Excel no son válidas.

## No se han podido resolver una o varias referencias a otra tabla

Síntoma
:   ![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/102-11870-20-228694_itperror2.jpg)

    Planning

¿Qué está pasando?
:   Los datos importados deben correlacionarse con sus Datos de Referencia, que actúan como clave para vincular Departamentos, Cuentas e IDs. Los datos no obligatorios que está importando no se encuentran en sus Datos de referencia.

    El mensaje de error debe listar todas las instancias de datos que no pueden correlacionarse con los Datos de Referencia.

Solución
:   1. Compruebe que todos los valores del archivo importado se corresponden con los Datos de referencia publicados.
       - Si no es así, actualice su Referencia Data.For para obtener más información, consulte [Gestionar dimensiones de datos de referencia](manage-reference-data.html).
    2. Seleccione Actualizar datos de referencia sólo para los presupuestos a los que desee aplicar cambios.
    3. Vuelva a importar los datos y confirme que los cambios en los Datos de referencia se han realizado correctamente.

## Establecer el valor de búsqueda desconocido como predeterminado

Síntoma
:   ![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/102-11870-20-231306_nl_settingunknownlookupvalue.jpg)

¿Qué está pasando?
:   En Datos de referencia, puede crear listas y dimensiones personalizadas.

    Una vez establecidos, estos elementos personalizados actúan del mismo modo que el resto de Datos de Referencia.

    Este error es funcionalmente el mismo que el error anterior, "No se pudo resolver una o más referencias a otra tabla:", pero específico de las listas y dimensiones personalizadas.

Solución
:   1. Compruebe que todos los valores del archivo importado se corresponden con las dimensiones y listas personalizadas publicadas. Si no es así, actualice su información personalizada e impórtela en Planning.
    2. Haga clic en Actualizar datos de referencia sólo para los presupuestos a los que desee aplicar cambios.
    3. Vuelva a importar los datos y confirme que los cambios en los Datos de referencia se han realizado correctamente.

## Los archivos cargados contienen más de una columna con nombres de alias reservados para la misma columna

Síntoma
:   Se utilizará la primera columna de duplicados encontrada: <Column1>. Se omitirá la columna de duplicados: <Column2>.

    ![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/231305.jpg)

    <Column1> se importa mientras que <Column2> no se importa a Planning.

¿Qué está pasando?
:   Planning ha detectado varios nombres de columna que coinciden con el nombre de una columna de plantilla.

    En la imagen de ejemplo, hay dos columnas identificadas llamadas "Código de Centro de Coste" y "Centro de Coste" Ambas columnas incluyen el nombre de columna obligatorio "Centro de costes"

    Planning seleccionará por defecto la primera columna que coincida en orden de izquierda a derecha al leer el archivo.CSV. No se importará ninguna coincidencia de columna adicional.

Solución
:   Si desea utilizar un nombre en lugar del otro, cambie el orden de las columnas para que su nombre preferido se lea primero (en orden de izquierda a derecha).

## Omisiones de filas

Los errores de omisión de filas se producen cuando los valores requeridos en los datos importados son incoherentes con las plantillas de Planning o los Datos de referencia. Estos errores son significativos y pueden hacer que su importación de datos falle por completo. Es importante resolver estos errores cuando aparecen.

## Asignaciones no válidas de centros de coste y objetos de coste

Síntoma
:   ![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/102-11870-20-232951_itperror3.jpg)

¿Qué está pasando?
:   Los Departamentos y Proyectos pueden asociarse a Centros de Coste específicos. Si es así, sólo se consideran válidos esos Centros de Coste.

    Sus datos importados están asociando Centros de Coste con Departamentos que no están explícitamente permitidos en su configuración actual.

Solución
:   Para los Departamentos:

    1. Vaya a Datos de Referencia de Departamentos y actualice los Códigos de Centro de Coste asociados.
    2. Puede dejar en blanco la columna Código de Centro de Coste para permitir todos los Centros de Coste.

Para proyectos sin inversión Planning:

- Vaya a Datos de Referencia de Proyectos y actualice los Códigos de Centro de Coste asociados.

Para proyectos con inversión Planning:

- Vaya a la vista Listado de proyectos y modifique la columna Código de centro de coste.

Para Proyectos, puede activar la opción Permitir Cualquier Centro de Coste para desactivar la restricción de asignación. Esta opción está disponible en Datos de referencia del proyecto o Listado de proyectos, dependiendo de si tiene Inversión Planning.

## No se han podido resolver una o varias referencias a otra tabla

Síntoma
:   ![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/102-11870-20-232952_itperror4.jpg)

¿Qué está pasando?
:   Los datos importados deben correlacionarse con sus Datos de Referencia, que actúan como clave para vincular Departamentos, Cuentas e IDs. Los datos necesarios que está importando no se encuentran en sus Datos de referencia.

    El mensaje de error debe listar todas las instancias de datos que no pueden correlacionarse con los Datos de Referencia.

Solución
:   1. Compruebe que todos los valores del archivo importado se corresponden con los Datos de referencia publicados.
       - Si no es así, actualice su Referencia Data.For para obtener más información, consulte [Gestionar dimensiones de datos de referencia](manage-reference-data.html).
    2. Seleccione Actualizar datos de referencia sólo para los presupuestos a los que desee aplicar cambios.
    3. Vuelva a importar los datos y confirme que los cambios en los Datos de referencia se han realizado correctamente.

## Los datos cargados incluyen partidas que han sido delegadas de otros objetos de coste, estas partidas serán excluidas

## Síntoma

![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/232953.jpg)

## ¿Qué está pasando?

Los costes delegados se producen cuando un proyecto ha finalizado y sus costes de mantenimiento se han trasladado a otro Departamento. Los costes delegados seguirán apareciendo en su Departamento original como filas atenuadas de sólo lectura.

Los datos de los costes delegados deben actualizarse cuando el coste haya sido delegado.

## Solución

Identifique dónde se ha delegado el coste. Debe actualizar estos costes en su ubicación delegada, no en su ubicación de origen.

Para más información, consulte [Delegar costes de proyectos](pfp/delegate-project-costs.html).

## Otros errores

Otros tipos de errores que pueden producirse en Planning.

## Lo sentimos, pero no podemos publicar... dimensión

## Síntoma

Porque una o varias tablas de referencia utilizan valores que ya no están presentes en la versión que desea publicar

![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/231008.jpg)

## ¿Qué está pasando?

Error de publicación: Faltan los datos de referencia que existían en Planning . Como los elementos de su informe dependen de esos Datos de referencia, se produce un error importante y la operación de publicación falla.

## Solución

Consulte [Solucionar errores de eliminación de datos de referencia](ts-reference-data.html).

## No se han detectado cambios: 1 error detectado en <Dataset>, incluyendo lo siguiente: El archivo cargado no contenía ninguna columna en la fila de encabezado

## Síntoma

![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/246685.jpg)

## ¿Qué está pasando?

Costing Standard a Planning Error de integración: Este problema puede deberse a:

- Un error en los ajustes o la configuración de Costing Standard Integration.
- Una o varias tablas importadas están Checked Out en Costing Standard.

## Solución

Vaya a Planning, haga clic en el menú Configuración y, a continuación, en Integración Costing Standard . Verifica lo siguiente:

- Todas las tablas están escritas y nombradas correctamente en las secciones Integración plan, Integración real e Integración de datos de referencia.
- El campo Importar desde se establece en Desarrollo.

Vaya a Costing Standard y compruebe lo siguiente:

- Todas las mesas están registradas.
- Establezca el Ejercicio Fiscal actual en Abierto.

## No se han detectado cambios: 1 error detectado en <Dataset>, incluyendo los siguientes: Cabecera vacía

Síntoma

![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/246687.jpg)

¿Qué está pasando?

Costing Standard a Planning Error de integración: Planning está extrayendo datos del mes actual en Costing Standard. El mes debe estar abierto en Costing Standard; de lo contrario, la integración no podrá encontrar ningún dato.

Solución

1. Navegue hasta Costing Standard.
2. Abra el mes en curso en Costing Standard.
3. Haga clic en la opción para guardar.
4. Vuelva a Planning e intente importar de nuevo.

## Los datos reales del usuario no aparecen en la previsión.

Compruebe las siguientes razones por las que los datos reales pueden no aparecer en la previsión y tome las medidas correctoras oportunas

Razón

Los datos reales aparecen para los periodos hasta el mes de inicio de la previsión menos uno.

Solución

Vuelva a crear el plan de previsión seleccionando el mes de inicio de previsión correcto.

Razón

Los datos reales no están disponibles en Planning > Spend Management

Solución

Asegúrese de que el período de reales en la Gestión de gastos muestra los datos reales. Si no es así, rellene los datos reales en la Gestión de gastos utilizando la Integración de transparencia de costes o utilizando Data Management automatizado o cargando manualmente el archivo.csv en el período real.

## Una dimensión específica está en blanco en la previsión

Esto podría deberse a una de las siguientes razones:

Razón

Las dimensiones no están habilitadas para la integración de los datos reales en el perfil de la empresa.

Solución

Navegue a Perfil de la Compañía, seleccione la dimensión de Resumen de Reales y Guarde los cambios. Vuelva a crear el plan de previsiones después de guardar la dimensión para la integración.

Razón

La dimensión no tiene datos en la Gestión de gastos.

Solución

Asegúrese de que los datos reales de la dimensión están disponibles en la Gestión de gastos. Si no es así, rellene los datos reales en la Gestión de gastos utilizando la Integración de transparencia de costes o utilizando Data Management automatizado o cargando manualmente el archivo.csv en el período real.

Para más información, consulte:

- [Solución de problemas: imposibilidad de importar o exportar archivos Excel](ts_unable_imp_exp_xsl.html)
- [Solucionar problemas de formatos de fecha no válidos en Planificación](ts_invalid_date_formats.html)
- [Gestionar las dimensiones de los datos de referencia](manage-reference-data.html)
