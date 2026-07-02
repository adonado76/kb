---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar una conexión ServiceNow Egress"
breadcrumb: []
source_path: "studio/data_studio/configure-servicenow-egress.html"
images:
  - "resources/images/datalink_images/sn-egress-connector.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar una conexión ServiceNow Egress

Los conectores de salida permiten el flujo de datos de la aplicación de Coste Total de Propiedad (TCO) entre Apptio y ServiceNow.

ServiceNow Para mostrar información sobre el coste total de propiedad de las aplicaciones en los cuadros de mando correspondientes de ServiceNow, puede utilizar la integración certificada de Apptio. La integración aporta estructuras de costes detalladas, transparentes y defendibles a las ofertas de aplicaciones y servicios en ServiceNow. Es compatible con las versiones de Quebec, París y Orlando de ServiceNow.

Hay dos integraciones ServiceNow :

- ServiceNow El conector de salida permite enviar datos de Apptio a ServiceNow.
- ServiceNow El conector de entrada permite enviar datos de ServiceNow a Apptio.

  [DataLink ServiceNow Conector de entrada](/docs/SSEXLU7/datalink/c-servicenow-about-connector.html)

## Para configurar una conexión ServiceNow Egress

1. En la plataforma ServiceNow, instale la aplicación Apps and Services TCO.

   [Más información sobre la instalación de la aplicación Apps & Services TCO](#ConfigureaServiceNowEgressconnection__InstalltheApptioAppsandServicesTCOintegrationontheServiceNowplatform)
2. En TBM Studio, configure los informes TCO de las aplicaciones.

   [Más información sobre la configuración de los informes TCO de las aplicaciones](#ConfigureaServiceNowEgressconnection__SetuptheappsservicesTCOreportsinTBMStudio)
3. En DataLink, configure el conector de salida DataLink .

   [Más información sobre la configuración del conector de salida DataLink](#ConfigureaServiceNowEgressconnection__ToconfigureaServiceNowEgressconnection)

Cuando configure la conexión ServiceNow Egress, podrá ver los datos de Apptio TCO en ServiceNow.

[Más información sobre la visualización de los datos del TCO de Apptio en ServiceNow](#ConfigureaServiceNowEgressconnection__ToconfigureaServiceNowEgressconnection)

## Instale la integración de Apptio Apps and Services TCO en la plataforma ServiceNow

Nota: La instalación de la integración es un requisito previo para ejecutar el conector de salida.

Para utilizar la aplicación de integración del Coste Total de Propiedad de Aplicaciones y Servicios ServiceNow, los usuarios deben tener la función x\_appti\_app\_servic.user. Los administradores con la función x\_appti\_app\_servic.admin también pueden ver la página de la interfaz de usuario de asistencia, eliminar los datos de las tablas de preparación o personalizadas y ejecutar la integración.

1. En ServiceNow, navegue hasta Plugins.
2. En la página de inicio de Plugins, seleccione Buscar en la tienda.
3. En la tienda de aplicaciones ServiceNow, busque Apptio Application and Services IT TCO.
4. Seleccione Instalar.

Obtenga más información sobre las dependencias de la aplicación en [la documentación de la aplicación en la tienda ServiceNow](https://store.servicenow.com/sn_appstore_store.do#!/store/application/88307d7d1b7b6010f78ba8e22a4bcbad/1.0.0?referer=%2Fstore%2Fsearch%3Flistingtype%3Dallintegrations%25253Bancillary_app%25253Bcertified_apps%25253Bcontent%25253Bindustry_solution%25253Boem%25253Butility%25253Btemplate%26q%3Dapptio&sl=sh "(se abre en una pestaña o una ventana nueva)").

## Configurar los informes de TCO de aplicaciones y servicios en TBM Studio

Es necesario crear informes en Apptio que se adapten a la tabla de destino en ServiceNow. ServiceNow permite representar el TCO de la aplicación con diferentes desgloses. Dado que Apptio sólo puede realizar de dos a tres ejercicios de objeto, con elementos de informe de un máximo de dos objetos, es necesario crear dos informes, configurados con las columnas que se indican a continuación:

- [TCO de la aplicación (incluida la composición del grupo de costes)](#ConfigureaServiceNowEgressconnection__Applicat)
- [Coste total de propiedad de las aplicaciones (incluida la composición de la torre de recursos informáticos)](#ConfigureaServiceNowEgressconnection__Applicat2)

[Más información sobre la creación de informes en TBM Studio](../reports/create-a-report.htm "(se abre en una pestaña o una ventana nueva)")

## Informe sobre el coste total de propiedad de la aplicación (incluida la composición del grupo de costes)

Este informe es un desglose desde Aplicaciones a Fuente de Coste.

**Columnas obligatorias**

Nota: Debe seguir exactamente la sintaxis indicada.

- Modelo de costes: código duro para el cálculo de costes de aplicaciones empresariales
- Período fiscal: utilice la siguiente fórmula:

  ```
  = "FY"& CurrentDate("YY") &": "&"Q"&
          gettimeoffset("Quarter","Start","Year") +1
  ```
- Desglose Id: código duro a Unidad de Negocio <--> Aplicación de Negocio
- Aplicación empresarial: Nombre de la aplicación (de Aplicaciones)

  Nota: Debe coincidir con el campo de nombre de la tabla `cmdb_ci_business_app` ServiceNow.
- Cubo: Pool de costes (de la fuente de costes)
- Subpool: Subconjunto de costes (de la fuente de costes)
- Unidad de negocio: hard code to `Check Apptio`
- Importe: `= QuarterToDate(Cost)`

## Columnas opcionales

- Aprobado para ServiceNow Egress: puede utilizarlo como filtro en el informe para filtrar las aplicaciones que no desea compartir con la comunidad de ServiceNow. Esto debe añadirse como una bandera al objeto Aplicaciones.

## Coste total de propiedad de las aplicaciones (incluida la composición de la torre de recursos informáticos)

Este informe es un desglose de Aplicaciones a Torres de Recursos de TI.

**Columnas obligatorias**

Nota: Debe seguir exactamente la sintaxis indicada.

- Modelo de costes: código duro para el cálculo de costes de aplicaciones empresariales
- Período fiscal: utilice la siguiente fórmula:

  ```
  = "FY"& CurrentDate("YY") &": "&"Q"&
          gettimeoffset("Quarter","Start","Year") +1
  ```
- Desglose Id: código duro a `Business Application <--> IT Shared Service`
- Aplicación empresarial: Nombre de la aplicación (de Aplicaciones)

  Nota: Debe coincidir con el campo de nombre de la tabla `cmdb_ci_business_app` ServiceNow.
- Servicio compartido de TI: Nombre de la torre de recursos de TI (de las torres de recursos de TI)
- Unidad de negocio: hard code to `Check Apptio`
- Importe: `= QuarterToDate(Cost)`

## Columnas opcionales

- Aprobado para ServiceNow Egress: puede utilizarlo como filtro en el informe para filtrar las aplicaciones que no desea compartir con la comunidad de ServiceNow. Esto debe añadirse como una bandera al objeto Aplicaciones.

## Configurar la conexión

Obtener un token OAuth 2.0
:   Si utilizas la autenticación OAuth 2.0 para tu conector, debes obtener un token de ServiceNow antes de configurarlo, como se indica a continuación:

    1. Registre DataLink como aplicación cliente con su fuente ServiceNow OAuth 2.0.
    2. Anote los valores **Client\_ID** y **Client\_Secret**.
    3. Introduzca una redirección URL. Utilice la dirección URL que corresponda a su región:
       - NA: [datalink.apptio.com/apptioconnect/app](http://datalink.apptio.com/apptioconnect/app "(se abre en una pestaña o una ventana nueva)")
       - UE: [datalink-eu.apptio.com/apptioconnect/app](http://datalink-eu.apptio.com/apptioconnect/app "(se abre en una pestaña o una ventana nueva)")
       - APAC: [datalink-au.apptio.com/apptioconnect/app](http://datalink-au.apptio.com/apptioconnect/app "(se abre en una pestaña o una ventana nueva)")

Crear la conexión
:   1. Abra Datalink y seleccione Nueva conexión.
    2. Introduzca un Nombre de conexión y seleccione Siguiente.
    3. Seleccione ServiceNow Apps & Services TCO Egress connector y, a continuación, Siguiente.
    4. Seleccione el agente.

    Puede elegir un agente basado en la nube o local para su conexión de salida. Para configurar un agente local, consulte [Configuración de un agente local en DataLink para ServiceNow](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=db52ac1b-a916-40e2-a6cf-6d4fb63d36c4&Step=1&ReturnUrl=%2fcommunities%2fcommunity-home%2flibrarydocuments%2fviewdocument%3fDocumentKey%3ddb52ac1b-a916-40e2-a6cf-6d4fb63d36c4%26Step%3d1%26ReturnUrl%3d%252fcommunities%252fcommunity-home%252flibrarydocuments%252fviewdocument%253fDocumentKey%253ddb52ac1b-a916-40e2-a6cf-6d4fb63d36c4%2526Step%253d1%2526CommunityKey%253dd640115c-5870-485f-947d-fdb02dcbf248%2526ReturnUrl%253d%25252fcommunities%25252fcommunity-home%25252flibrarydocuments%25253fCommunityKey%25253dd640115c-5870-485f-947d-fdb02dcbf248%2526Action%253dnew "(se abre en una pestaña o una ventana nueva)").

    Consejo: Los agentes locales suelen cargar más rápido que los agentes en la nube.

Configurar la autenticación
:   1. Seleccione el tipo de autenticación para conectarse a su instancia ServiceNow : Básica u OAuth 2.0.

       ![](../../../../../03-media/apptio-tbm-studio/resources/images/datalink_images/sn-egress-connector.png)

       Nota: Sólo puedes utilizar la autenticación OAuth 2.0 con agentes en la nube.
    2. Introduzca la base ServiceNow URL (por ejemplo, https://{instance}. service-now.com ).
    3. Introduzca sus datos de autenticación:
       - Si utiliza la autenticación básica, introduzca el nombre de usuario y la contraseña.
       - Si utiliza la autenticación OAuth 2.0, haga lo siguiente:
         1. Introduzca la información del token:
            - En **Autorización URL**, introduzca el URL utilizado para la autorización OAuth 2.0 (por ejemplo, https://{instance}. service-now.com/oauth\_auth.do ).
            - En **Token URL**, introduzca el URL para recuperar y actualizar los tokens de acceso (por ejemplo, https://{instance}. service-now.com/oauth\_token.do ).
            - En los campos ID de **cliente** y Secreto de **cliente**, introduzca el ID de cliente y el secreto de cliente que obtuvo de ServiceNow.

              [Más información sobre cómo obtener un token OAuth 2.0](https://help.apptio.com/en-us/studio/data%20studio/configure-servicenow-egress.htm?state=ec394c57-8eaa-41ed-8ec5-1e9319c4ba68#Obtain "(se abre en una pestaña o una ventana nueva)")
         2. Si desea limitar el nivel de acceso concedido al token de acceso, especifique el Alcance como LECTURA y acceso de ESCRITURA o LECTURA.
         3. Seleccione **Obtener código de acceso**.

         DataLink encripta el token de acceso y lo utiliza mientras se ejecuta el conector.

       Nota: Cuando el token de acceso OAuth 2.0 caduca, DataLink intenta actualizarlo automáticamente.

Introducir detalles del informe
:   1. En Rellene los detalles del informe, seleccione el host BIIT donde reside el informe Costing
       Standard . Si sólo tiene una instancia BIIT, DataLink la selecciona automáticamente.
    2. Seleccione los informes de Costing Standard que desea cargar en ServiceNow, a partir de los informes que configuró en Configurar los informes de TCO de aplicaciones y servicios en TBM Studio.
    3. Introduzca las URL de los informes en Costing Standard para cada uno de los informes, como se indica a continuación:
       1. Vaya a Costing Standard y abra el informe.
       2. Haga clic con el botón derecho en el informe y seleccione Mostrar URI de API.
       3. Copie el informe URL en formato JSON en el campo DataLink Informe URL para el informe.
    4. Seleccione el periodo de tiempo para los informes. Puede elegir el mes actual o el anterior, o un periodo de tiempo personalizado.
    5. Seleccione "Next".

Programar la conexión
:   Seleccione su opción de horario y rellene los datos:

    - Programar por tiempo
    - Programar por evento, por ejemplo, ejecutar la conexión después de que se haya ejecutado una conexión específica.

Guardar la conexión
:   Seleccione Completar en la esquina inferior derecha para guardar la conexión. DataLink añade el conector a la lista.

Ejecutar la conexión
:   Para ejecutar la conexión, seleccione la flecha de la columna Ejecutar situada junto a la conexión en la lista. Una vez ejecutada correctamente la conexión, los datos de TCO de TBM Studio se transfieren a su instancia de ServiceNow.

## Consulte los datos del TCO de Apptio en ServiceNow

Para sacar el máximo partido a sus datos de TCO, le recomendamos que instale la tabla `itfm_allocation_breakdown` en su instancia ServiceNow. La instalación de la tabla le da acceso a los siguientes cuadros de mando, donde puede analizar el gasto en aplicaciones y servicios:

- TCO de la aplicación
- Cálculo de costes de aplicaciones empresariales

Puede instalar la tabla con uno de varios plugins, por ejemplo:

- `com.snc.financial_management`
- `com.snc.financial_management_for_apm`
- `com.snc.financial_management_for_spm`

Nota: Estos plugins son de pago. Para obtener información sobre los costes y solicitar ayuda para instalar el complemento, póngase en contacto con su representante en ServiceNow. La instalación de los plugins no es obligatoria para que la aplicación y el conector de salida funcionen.

Paneles de control personalizados
:   El conector de salida crea los datos de TCO en Apptio tabla personalizada `x_appti_app_servic_apptio_tco`. Puede utilizar esta tabla para crear cuadros de mando personalizados que muestren información sobre el coste total de propiedad. Más información sobre la creación de cuadros de mando personalizados en [la documentación de ServiceNow](https://docs.servicenow.com/ "(se abre en una pestaña o una ventana nueva)")
