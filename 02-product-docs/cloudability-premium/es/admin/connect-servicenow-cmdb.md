---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conectarse a ServiceNow CMDB"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "admin/connect-servicenow-cmdb.html"
images:
  - "images/cldy-key-secret.png"
  - "images/cloudability-home-page.png"
  - "images/cloudability-list-page.png"
  - "images/cloudability-workspace.png"
  - "images/connection-credentials.png"
  - "images/create-connection.png"
  - "images/create-new-business-dimension.png"
  - "images/new-api-key.png"
  - "images/new-business-dimension.png"
  - "images/new-dimension-statement.png"
  - "images/new-statement-condition.png"
  - "images/new-statement-group.png"
  - "images/new-statement-template.png"
  - "images/publish-servicenow-business-dimension.png"
  - "images/servicenow-cross-scope.png"
  - "images/workflow-studio.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectarse a ServiceNow CMDB

## Visión general

La integración ServiceNow de CMDB para Cloudability permite una sincronización perfecta entre su base de ServiceNow datos de gestión de la configuración (CMDB) y IBMCloudability. Esta integración le permite crear asignaciones empresariales automatizadas en Cloudability basadas en elementos de configuración y datos organizativos almacenados en su ServiceNow CMDB, lo que proporciona capacidades mejoradas de asignación de costes y gobernanza en la nube.

## Ventajas claves

- **Mapeo empresarial automatizado** : cree y mantenga automáticamente los mapeos empresariales en Cloudability utilizando sus datos CMDB ServiceNow existentes, lo que reduce el esfuerzo de configuración manual y mejora la precisión.
- **Centralizado Data Management** : Aproveche su ServiceNow CMDB como fuente única de información veraz sobre la estructura organizativa, las aplicaciones y los centros de costes que impulsan la asignación de costes de la nube.
- **Sincronización en tiempo real** : mantenga sus asignaciones Cloudability empresariales actualizadas con los cambios en su ServiceNow CMDB mediante procesos de sincronización automatizados.
- **Mejora de la gobernanza de costes** : mejora la visibilidad y la responsabilidad de los costes de la nube alineando los recursos de la nube con la estructura de tu organización tal y como se define en ServiceNow

## Requisitos previos

Antes de instalar y configurar la ServiceNow integración CMDB, asegúrese de que cumple los siguientes requisitos:

**ServiceNow Requisitos**

- ServiceNow instancia (se recomienda la versión Paris o posterior)
- Privilegios de administrador o equivalentes para instalar aplicaciones desde la ServiceNow Tienda
- Complemento CMDB activado en su ServiceNow instancia
- CMDB correctamente configurada con elementos de configuración relevantes (aplicaciones, servicios empresariales, centros de costes, etc.)

**Cloudability Requisitos**

- Cuenta IBMCloudability activa con privilegios administrativos
- Acceso a la API habilitado en su Cloudability instancia
- Credenciales API Cloudability válidas

## Instalación

**Paso 1: Descargar desde ServiceNow Store**

1. Inicie sesión en su ServiceNow instancia como administrador
2. Navega a **Aplicaciones del sistema** > **Todas las aplicaciones disponibles** > **Todas**
3. Buscar «» Cloudability en la ServiceNow Tienda
4. Haga clic en **Instalar** y siga las instrucciones de instalación
5. Espere a que finalice la instalación y reinicie los servicios necesarios

**Paso 2: Configuración posterior a la instalación**

1. **Configurar la clave Cloudability de acceso**
   - Navegue hasta IntegrationHub > Conexiones y credenciales > Alias de conexiones y credenciales![](../../../../03-media/cloudability-premium/images/connection-credentials.png)
   - Busca « KeyAccess"Cloudability y ábrelo
   - Haga clic en «Nuevo» para añadir nuevas credenciales
   - Cuando se le pregunte «¿Qué tipo de credenciales desea crear?», Selecciona «Credenciales de clave API»
   - Introduzca "KeyAccess" como nombre y pegue la clave API de Cloudability

     ![](../../../../03-media/cloudability-premium/images/new-api-key.png)
2. **Configurar el secreto Cloudability de clave**
   - En «Alias de conexión y credenciales», busca « KeySecret"Cloudability y ábrelo
   - Haga clic en «Crear nueva conexión y credencial»

     ![](../../../../03-media/cloudability-premium/images/cldy-key-secret.png)
   - Añadir Cloudability «Conexión de radios» como «Nombre de la conexión»
   - Añade «<Dominio específico de la región>/service/apikeylogin» como «Conexión URL ». Reemplace «<Dominio Frontdoor específico de la región>» por el dominio Frontdoor Cloudability adecuado, por ejemplo « https://frontdoor.apptio.com/service/apikeylogin »
   - Añade el secreto API desde la página de perfil de usuario de Frontdoor

     ![](../../../../03-media/cloudability-premium/images/create-connection.png)

**Paso 3: Probar la configuración**

- Navegar a Workflow Studio

  ![](../../../../03-media/cloudability-premium/images/workflow-studio.png)
- Navega hasta la sección «Acciones», busca «Integración: Cloudability obtener token de Frontdoor» y ábrela
- Haga clic en «Prueba» y, a continuación, en «Ejecutar prueba»
- Cuando la prueba haya finalizado, haga clic en «Ver los detalles de la ejecución de la acción»
- Si la variable «Status» devuelve «Success», significa que las credenciales se han configurado correctamente

**Paso 4: Configuración de privilegios entre ámbitos**

- Proporcione privilegios de ámbito cruzado para que la Cloudability aplicación pueda leer datos de las tablas/vistas especificadas en las propiedades de integración. Estas tablas/vistas se utilizan en la página de creación de la dimensión empresarial. Consulte el ServiceNow [documento](https://www.servicenow.com/docs/bundle/xanadu-application-development/page/build/applications/reference/c_CrossScopePrivilegeRecord.html "(se abre en una pestaña o una ventana nueva)"). El siguiente ejemplo muestra la configuración necesaria. El permiso de lectura es suficiente para la aplicación.

  ![](../../../../03-media/cloudability-premium/images/servicenow-cross-scope.png)

## Navegación

Puede acceder a la aplicación Cloudability Business Mapping a través de un espacio de trabajo o de la lista Todos los menús.

![](../../../../03-media/cloudability-premium/images/cloudability-workspace.png)

Todas las funciones de usuario están disponibles desde el espacio de trabajo, y este es el método recomendado para acceder a la aplicación.

Las funciones de administrador no están disponibles en el espacio de trabajo. Se debe acceder a ellos a través de la lista «Todos los menús».

El usuario necesita acceso de administrador para realizar funciones de administrador. Sin embargo, para todas las demás operaciones de los usuarios no se requiere acceso de administrador.

La página de inicio muestra una lista de las dimensiones empresariales ServiceNow publicadas y pendientes.

![](../../../../03-media/cloudability-premium/images/cloudability-home-page.png)

La página Lista le permite ver listas de ServiceNow dimensiones empresariales agrupadas por estado. Hacer clic en una lista para mostrar las dimensiones empresariales con ese valor de estado.

![](../../../../03-media/cloudability-premium/images/cloudability-list-page.png)

## Casos de uso

**1. Crear/actualizar dimensiones empresariales**

ServiceNow Las dimensiones empresariales le permiten definir y modificar las dimensiones Cloudability empresariales desde dentro ServiceNow utilizando datos de la ServiceNow CMDB. Puede crear nuevas ServiceNow dimensiones de negocio o actualizar borradores de dimensiones de negocio existentes. Para crear una nueva ServiceNow dimensión de negocio, haga clic en [+] y seleccione Nueva dimensión de negocio.

![](../../../../03-media/cloudability-premium/images/new-business-dimension.png)

Rellene los campos del formulario tal y como se describe en la tabla siguiente:

![](../../../../03-media/cloudability-premium/images/create-new-business-dimension.png)

|  |  |
| --- | --- |
| **Campo** | **Descripción** |
| Nombre | Seleccione una Cloudability dimensión empresarial. |
| Fecha efectiva | Establezca la fecha en la que esta ServiceNow dimensión empresarial debe actualizarse Cloudability.  Este campo está inicialmente configurado con la fecha actual. |
| Tabla | Seleccione una ServiceNow tabla. Los datos de la tabla se utilizarán para elaborar los estados de la dimensión empresarial. |
| Consulta de plantilla de declaración | Defina una consulta que se utilizará para filtrar los datos utilizados para crear los estados de la dimensión empresarial. |

Haga clic en el botón Guardar para guardar los cambios.

**2. Crear/actualizar plantillas de extractos**

Las plantillas de extractos le permiten definir extractos dinámicos para su Cloudability dimensión empresarial. Son dinámicos en el sentido de que los valores de campo de las ServiceNow filas de la tabla pueden sustituirse en la expresión de valor de la instrucción o en la expresión coincidente.

Puede crear nuevas plantillas de extractos o actualizar las existentes a partir de un borrador de dimensión empresarial. Abrir un borrador de dimensión empresarial. Haga clic en la pestaña «Plantillas de extractos».

Para crear una nueva plantilla de extracto, vaya a «Plantillas de extracto» desde un contexto de dimensión empresarial determinado y haga clic en el botón «Nuevo». Para actualizar una plantilla de extracto existente, haga clic en su valor «Número».

![](../../../../03-media/cloudability-premium/images/new-statement-template.png)

Rellene los campos del formulario tal y como se describe en la tabla siguiente:

![](../../../../03-media/cloudability-premium/images/new-dimension-statement.png)

|  |  |
| --- | --- |
| **Campo** | **Descripción** |
| Utilizar valor dinámico | Marque este campo si desea utilizar una Cloudability dimensión empresarial, un grupo de cuentas, una etiqueta o una medida interna como valor para esta declaración |
| Valor dinámico | Seleccione una Cloudability dimensión empresarial, grupo de cuentas, etiqueta o medida interna |
| Valor | Introduzca un valor de texto. El texto puede incluir variables de la lista Columnas. |

**Variables como valores**

Puede añadir valores variables (columnas) al campo Valor haciendo clic en el botón Columnas. Seleccione una o más columnas y cierre el cuadro de diálogo. Los nombres de las columnas se copian automáticamente al portapapeles. Puede pegar el contenido del portapapeles en el campo Valor.

Las variables del campo Valor deben tener el siguiente formato:

${<column name>}

Si utiliza el botón Columnas para seleccionar los nombres de las columnas, estos se formatearán correctamente cuando los pegue en el campo Valor.

**3. Crear/actualizar grupos de instrucciones**

Cada plantilla de instrucción se compone de uno o más grupos de instrucciones que se utilizan para formar la expresión de coincidencia de instrucciones. Cada grupo se combinará lógicamente con AND cuando se determine la expresión de coincidencia. Puede crear nuevos grupos de extractos o actualizar los existentes a partir de una plantilla de extracto en una dimensión empresarial preliminar. Abre una plantilla de declaración. Haga clic en la pestaña «Grupos de extractos». Para crear un nuevo grupo de extractos, haga clic en el botón «Nuevo». Para actualizar un grupo de extractos existente, haga clic en su valor Número.

![](../../../../03-media/cloudability-premium/images/new-statement-group.png)

Haga clic en «Establecer condiciones» y configure las condiciones de coincidencia que se aplicarán a un grupo de extractos determinado.

![](../../../../03-media/cloudability-premium/images/new-statement-condition.png)

|  |  |
| --- | --- |
| **Campo** | **Descripción** |
| Dimensión | Seleccione una Cloudability dimensión empresarial, grupo de cuentas, etiqueta o medida interna |
| Operador | Seleccione el operador que se utilizará para comparar la dimensión con el valor |
| Valor | Introduzca un valor de texto. El texto puede incluir variables de la lista Columnas. |

**4. Publicar una ServiceNow Dimensión empresarial**

Para actualizar una Cloudability dimensión empresarial desde, primero ServiceNow debe publicar la ServiceNow dimensión empresarial. Solo se pueden publicar las dimensiones empresariales con el estado «Borrador».

Abrir un borrador de dimensión empresarial. Haga clic en el botón Publicar.

![](../../../../03-media/cloudability-premium/images/publish-servicenow-business-dimension.png)

El estado de la dimensión empresarial cambiará a uno de estos dos valores:

**Publicado**

Si la fecha de vigencia en la dimensión de negocio es actual o pasada, el estado cambia a «Publicado» y Cloudability se actualiza inmediatamente.

**Pendiente**

Si la fecha de entrada en vigor de la dimensión empresarial es futura, el estado cambia a «Pendiente». Cloudability no se actualiza inmediatamente.

Cuando la fecha de entrada en vigor sea actual, el estado cambiará a «Publicado», Cloudability se actualizará y cualquier versión publicada anteriormente quedará retirada.
