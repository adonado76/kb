---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Datos de referencia del servicio"
breadcrumb: []
source_path: "it-planning/planning/sdp/manage-service-reference.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Datos de referencia del servicio

◆ Se aplica a: Planificación con [Service Demand Planning](gs-service-demand.html). Las tareas que se indican a continuación requieren que obtenga la licencia de Service Demand Planning y, a continuación, [edite el perfil de la empresa](../edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.") para activar las funciones de Service Demand Planning . Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

NOTA : El módulo Service Demand Planning ya no está disponible en Apptio. La información que figura a continuación se facilita en beneficio de los usuarios actuales de Service Demand Planning.

Las dimensiones son las categorías de datos esenciales en las partidas presupuestarias. Muchas dimensiones incorporadas tienen dependencias con otras dimensiones (para más información, véase [Atributo de datos de referencia y dependencias de dimensiones](../manage-reference-data.html) ). Puede importar datos de referencia de dimensiones desde un archivo.csv o desde Costing Standard y exportar plantillas de datos de referencia de dimensiones y datos de tablas (véase [Gestionar dimensiones](../manage-reference-data.html "(se abre en una pestaña o una ventana nueva)") ).

![imagen](../../../resources/images/it%20planning_images/icon_video.png): Vea este vídeo de Apptio Education Services: [Configuración de Datos de Referencia: Service Demand Planning Dimensiones](https://community.apptio.com/videos/1996 "(se abre en una pestaña o una ventana nueva)"). O vea todos los [vídeos y recursos de formación de Apptio Planning](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(se abre en una pestaña o una ventana nueva)") .

## Gestionar los datos de referencia de las unidades de negocio

Los Propietarios de Servicios pueden utilizar las Unidades de Negocio para ayudar a prever la demanda de servicios a áreas adicionales dentro de su organización. Antes de configurar los datos de referencia de las Unidades de Negocio, asegúrese de que publica las dimensiones Unidad de Medida, Categorías de Servicio y Servicios (a continuación encontrará las instrucciones).

1. En el menú de navegación, seleccione Configuración > Datos de referencia.
2. Seleccione la pestaña Servicio en la página Datos de referencia.
3. Seleccione > Unidad de negocio.
4. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
5. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
6. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
7. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los valores de la tabla de datos según sea necesario:
   - Código (obligatorio) - Identificador único abreviado de la Unidad de Negocio.
   - Nombre (obligatorio) - El nombre de la Unidad de Negocio.
   - Código Padre - Representa la jerarquía de su Unidad de Negocio. Un valor de Código Padre es el valor de código de su Unidad de Negocio inmediata superior o padre (si existe).
   - Código de Centro de Coste - El identificador de los Centros de Coste correspondientes. Al importar los reales, se asignan por Centro de Coste y luego se asignan a un Objeto de Coste. Una Unidad de Negocio puede estar asociada a múltiples Centros de Coste y puede incluir partidas (volúmenes, mano de obra o gastos) registradas para más de un Centro de Coste. Añada múltiples Centros de Coste a la celda de la tabla utilizando una coma para separarlos.
   - Código de moneda - La moneda común para la Unidad de Negocio. Requerido cuando se activa el soporte para múltiples monedas. El valor de la moneda común de la Unidad de Negocio debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
   - Grupo de Precios - Determina el grupo de precios para la Unidad de Negocio para modelos de precios basados en regiones o en niveles.
   - Precio unitario - Define el importe a cobrar cuando se utiliza una unidad de una Unidad de Negocio.
8. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > ficha Servicio > Unidad de negocio**.
9. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo > Importar.
10. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
11. Para cancelar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Revertir > Revertir**.

## Gestionar los datos de referencia de los grupos de precios

La dimensión Grupo de precios permite al administrador establecer modelos de precios regionales o por niveles para sus propietarios de servicios. El grupo de precios se asigna al proveedor y a los consumidores, lo que ayuda a categorizar los precios de servicios personalizados para regiones o consumidores. Antes de configurar los datos de referencia del grupo de precios, asegúrese de actualizar la estrategia de precios.

1. En el menú de navegación, seleccione Configuración > Datos de referencia.
2. Seleccione la pestaña Servicio en la página Datos de referencia.
3. Seleccione > Grupo de precios. La tabla de datos de referencia Grupo de precios incluye el nombre de la región o grupo de consumidores o proveedores a los que desea aplicar un precio específico. Los nombres de los modelos de precios regionales se abrevian como AU, EU y US. Los nombres de los modelos de tarificación por niveles son Externo e Interno. Puede omitir el valor utilizado para la etiqueta Precio base en el Perfil de empresa
4. Seleccione ![imagen](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
5. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
6. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
7. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los Departamentos, Proyectos, Unidades de Negocio o Servicios relevantes con el Grupo de Precios.
8. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > ficha Servicio > Grupo de precios**.
9. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo > Importar.
10. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
11. Para cancelar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Revertir > Revertir**.

## Gestionar la unidad de medida en los datos de referencia

Los datos de referencia de la Unidad de Medida determinan cómo se miden los volúmenes de Servicios. Antes de definir los Servicios, defina primero su Unidad de Medida.

1. En el menú de navegación, seleccione Configuración > Datos de referencia.
2. Seleccione la pestaña Servicio en la página Datos de referencia.
3. Seleccione > Unidad de medida.
4. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
5. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
6. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
7. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los valores de la tabla de datos según sea necesario:
   - Código (obligatorio) - Identificador único abreviado de la Unidad de Negocio.
   - Nombre (obligatorio) - El nombre de la Unidad de Negocio.
8. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > ficha Servicio > Unidad de medida**.
9. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo > Importar.
10. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
11. Para cancelar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Revertir > Revertir**.

## Gestionar los datos de referencia del Servicio

Los Servicios, Departamentos y Proyectos son tipos de Objetos de Coste.

1. Actualizar los datos de referencia de la Unidad de Medida para incluir la tabla de datos de referencia del Código del Servicio. Consulte la sección anterior: "Gestionar los datos de referencia de la Unidad de Medida"
2. En el menú de navegación, seleccione Configuración > Datos de referencia.
3. Seleccione la pestaña Servicio en la página Datos de referencia.
4. Seleccione > Servicio.
5. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
6. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
7. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
8. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los valores de la tabla de datos según sea necesario:
   - Código (obligatorio) - El valor único para el Servicio.
   - Nombre (obligatorio) - Nombre del servicio.
   - Código padre - Representa la jerarquía de sus servicios. El valor de un código padre es el valor del código de su cuenta inmediatamente superior o padre (si existe). Los servicios enumerados con un valor de código principal de SC CNC, SC LOB o SC CC están subordinados a los servicios de informática de cliente, línea de negocio y comunicación y colaboración.
   - Código de moneda - La moneda común para el servicio. Requerido cuando se activa el soporte para múltiples monedas. El valor de la moneda común debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
   - Grupo de precios - Determina el grupo de precios del servicio para los modelos de precios por regiones o por niveles. Déjelo en blanco para utilizar el precio original.
   - Estrategia de fijación de precios - El método utilizado para fijar el precio de su servicio. Las opciones son:
     - Fijo - Importe a cobrar (definido mediante la columna Precio unitario). Esta opción es necesaria si ha seleccionado Fijo como modelo de tarificación en el Perfil de empresa.
     - Dinámico - Calcule dinámicamente el precio unitario en función de la composición del coste del servicio y de la demanda. Utilice esta opción sólo si ha seleccionado Dinámico como modelo de tarificación en el Perfil de empresa.
   - Código de unidad - El identificador único del artículo a cuantificar para este servicio.
   - Precio unitario - Importe a cobrar por una unidad de servicio.
   - Código de Centro de Coste - El identificador de los Centros de Coste correspondientes. Al importar los reales, se asignan por Centro de Coste y luego se asignan a un Objeto de Coste. Un proyecto puede estar asociado a múltiples Centros de Coste y puede incluir partidas (volúmenes, mano de obra o gastos) registradas para más de un Centro de Coste. Añada múltiples Centros de Coste a la celda de la tabla utilizando una coma para separarlos.
9. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > ficha Servicio > Servicio**.
10. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo > Importar.
11. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
12. Para cancelar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Revertir > Revertir**.

## Gestionar los datos de referencia de las categorías de servicio

Los datos de referencia de las Categorías de Servicio representan la estructura jerárquica de servicios de su organización. Las Categorías de Servicio son visibles en el menú de la Subsección del Plan y en la página de Servicios, Resumen.

1. En el menú de navegación, seleccione Configuración > Datos de referencia.
2. Seleccione la pestaña Servicio en la página Datos de referencia.
3. Seleccione > Categorías de servicio.
4. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
5. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
6. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
7. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los valores de la tabla de datos según sea necesario:
   - Código (obligatorio) - Valor único de la categoría de servicio.
   - Nombre (obligatorio) - Nombre de la categoría de servicio.
   - Código Padre - Representa su jerarquía de Categorías de Servicio. El valor de un código padre es el valor del código de su cuenta inmediatamente superior o padre (si existe). Las categorías de servicios con un valor de código superior de SCPS y SCEUCS están subordinadas a esas categorías de servicios.
   - Código de moneda - La moneda común para el servicio. Requerido cuando se activa el soporte para múltiples monedas. El valor de la moneda común debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
   - Grupo de precios - Determina el grupo de precios del servicio para los modelos de precios por regiones o por niveles. Déjelo en blanco para utilizar el precio original.
   - Código de Centro de Coste - El identificador de los Centros de Coste correspondientes. Al importar los reales, se asignan por Centro de Coste y luego se asignan a un Objeto de Coste. Un proyecto puede estar asociado a múltiples Centros de Coste y puede incluir partidas (volúmenes, mano de obra o gastos) registradas para más de un Centro de Coste. Añada múltiples Centros de Coste a la celda de la tabla utilizando una coma para separarlos.
8. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > ficha Servicio > Categorías de servicio**.
9. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo > Importar.
10. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
11. Para cancelar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Revertir > Revertir**.

## Gestionar los datos de referencia de los Ajustes del Precio del Servicio

Los datos de referencia de los ajustes de precios de los servicios permiten establecer normas de tarificación para los modelos de tarificación regional o por niveles.

1. En el menú de navegación, seleccione Configuración > Datos de referencia.
2. Seleccione la pestaña Servicio en la página Datos de referencia.
3. Seleccione > Ajustes del precio del servicio.
4. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
5. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
6. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
7. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los valores de la tabla de datos según sea necesario:
   - Grupo de precios al consumo - Aparece para categorías escalonadas de un servicio, como Interno o Externo.
   - Moneda - La moneda común para el servicio. Requerido cuando se activa el soporte para múltiples monedas. El valor de la moneda común debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
   - Grupo de precios del proveedor : determina el grupo de precios del proveedor de servicios.
   - Importe de ajuste - El precio o el importe porcentual para ajustar el importe base. Para aplicar descuentos, introduzca un número negativo. Por ejemplo, un valor de -20 equivale a un descuento de 20$ o 20% (dependiendo del Tipo de Ajuste seleccionado) sobre la unidad de servicio.
   - Tipo de ajuste - Determina cómo se aplican los ajustes. Existen las siguientes opciones:
     - Absoluto - Tasa monetaria fija que se aplica al precio unitario base.
     - Porcentaje - Variación porcentual de la tarifa de precios unitarios.
     - Importe - Se utiliza sólo para precios escalonados. Se trata de una cantidad fija que se aplica al precio unitario base.
8. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > ficha Servicio > Ajustes del precio del servicio**.
9. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo > Importar.
10. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
11. Para cancelar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Revertir > Revertir**.

SUGERENCIA: Los datos de referencia de Permisos de objetos de coste determinan quién puede editar cada servicio y quién puede aprobar presentaciones de planes presupuestarios. Véanse [los datos de referencia de los Permisos para Gestionar Objetos de Coste](../manage-cost-object.htm "(se abre en una pestaña o una ventana nueva)").
