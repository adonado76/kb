---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Dimensiones estándar"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
  - "Datos de referencia"
source_path: "it-planning/planning/manage-reference-data.html"
images:
  - "resources/images/icons/icon-options.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Dimensiones estándar

Se aplica a: Apptio Planning aplicaciones con [Project Financial Planning](pfp/gs-project-financial.html "◆ Se aplica a: Planificación con proyecto Planificación financiera."). Las tareas que se describen a continuación requieren una licencia de Project Financial Planning. Para activar las funciones de Project Financial Planning , consulte [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning."). Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Las dimensiones son las categorías de datos esenciales en las partidas presupuestarias. Muchas dimensiones integradas dependen de otras dimensiones. Véase [Atributo de datos de referencia y relación de dimensiones](#Referencedatadimensions__Referencedataattributeanddimensionsdependencies). En las aplicaciones de Apptio Planning , puede trabajar con datos de TBM Studio en Excel, trabajar con conjuntos de datos maestros y actualizar datos de referencia. Véase [Gestionar datos de referencia](manage-itfmf-reference.html "◆ Se aplica a: Planificación").

Para obtener información detallada sobre los datos y el formato de todos los datos financieros y de referencia necesarios para la planificación, consulte la [Guía de datos de referencia para la planificación](https://community.apptio.com/docs/DOC-8065 "(se abre en una pestaña o una ventana nueva)").

## Ver dimensiones por defecto

Vaya a Planning > Configuración > Datos de referencia. Si no ve la dimensión o el grupo que busca, es posible que tenga que activar estas funciones (véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.") ).

A continuación se describen las Dimensiones por defecto. Seleccione un título de dimensión para ver descripciones y ejemplos a nivel de campo.

## Dimensiones estándar

Las dimensiones estándar pueden incluir las siguientes categorías:

[Dimensiones financieras](manage-financial-dimensions.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") :

- Cuenta
- Categoría de cuenta
- Centro de costes
- Departamento
- Ubicación
- Desviación Conductor
- Proveedor

[Mano de obra Dimensiones de configuración](manage-labor-configuration.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") :

- Normas de asignación de mano de obra
- Tarifas laborales
- Funciones

[Dimensiones de la configuración del contrato](manage-contract-configuration.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") :

- Tipo de contrato
- Tipos del IVA

[Dimensiones de los permisos de los objetos de coste](manage-cost-object.html) :

- Permisos para objetos de coste

[Dimensiones de configuración de los activos](manage-asset-configuration.html) :

- Clase de activos

## Project Financial Planning dimensiones

A continuación se indican las dimensiones por defecto para los usuarios con licencia de Project Financial Planning :

[Dimensiones de configuración del proyecto](pfp/manage-project-configuration.html) :

- Proyecto
- Grupo de proyectos
- Puntuación

[Dimensiones laborales](manage-labor-configuration.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") :

- Bolsas de trabajo externas
- Bolsas de trabajo internas

[Dimensiones de la asignación](manage-allocation-configuration.html) :

- Cuenta de transferencia por defecto

## Service Demand Planning dimensiones

A continuación se indican las dimensiones por defecto para los usuarios con licencia de Service Demand Planning .

[Dimensiones del servicio](sdp/manage-service-reference.html) :

- Unidad de negocio
- Grupo de precios
- Servicio
- Categorías de servicios
- Ajustes de los precios de los servicios
- Unidad de medida

[Mano de obra Dimensiones de configuración](manage-labor-configuration.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") :

- Bolsas de trabajo externas
- Bolsas de trabajo internas
- Normas de asignación de mano de obra
- Tarifas laborales
- Rol

[Dimensiones de la asignación](manage-allocation-configuration.html) :

- Cuenta de transferencia por defecto

## Múltiples dimensiones monetarias

Las siguientes funciones sólo son visibles si está activada la compatibilidad con varias monedas Véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning."). A continuación se indican las dimensiones por defecto para el soporte de múltiples divisas. Véase [Soporte para múltiples monedas](support-multiple-currencies.html).

[Dimensiones de las tablas de tarifas](manage-multi-currency.html "Apptio La planificación admite configuraciones multidivisa que permiten introducir, visualizar y conciliar datos financieros en distintas divisas. Esto es especialmente útil para organizaciones globales que gestionan presupuestos en varias regiones.") :

- Tipo de cambio real
- Plan Tipo de cambio

## Relación entre atributos y dimensiones de los datos de referencia

Muchas dimensiones están relacionadas. La información de una dimensión puede depender de otra dimensión (dependencias) del sistema. Esto puede influir en los atributos que se pueden eliminar.

A continuación se indican las dimensiones y los atributos que pueden depender de otras dimensiones:

| Dimensión | Atributo dependiente | Dimensión de la fuente |
| --- | --- | --- |
| Departamento | Código del centro de costes | Centro de costes |
| Mano de obra externa | Proveedor | Proveedor |
| Bolsa de trabajo interna | Código de departamento | Departamento |
| Normas de asignación de mano de obra | Código de cuenta | Cuenta |
| Rol | Papel laboral |
| Ubicación | Ubicación |
| Proveedor | Proveedor |
| Tipos de contrato | Código de cuenta | Cuenta |
| Tipos del IVA | Ubicación | Ubicación |
| Clase de activos | Código de cuenta de amortización | Cuenta |
| Código de cuenta de compras |
| Cuenta de transferencia por defecto | Código de cuenta de transferencia | Cuenta |
| Código de cuenta de transferencia |
| Proyecto | Código del centro de costes | Centro de costes |
| Código paterno | Grupo de proyectos |
| Unidad de negocio | Código del centro de costes | Centro de costes |
| Servicios | Código del centro de costes | Centro de costes |
| Código paterno | Categorías de servicios |
| Código de unidad | Unidad de medida |

Las dimensiones sin dependencias incluyen las siguientes:

- Unidad de medida
- Ubicación
- Proveedor
- Rol

## Configurar los datos de referencia

1. Vaya a Planificación > Configuración > Datos de referencia.
2. Haga clic en la dimensión específica del grupo correcto.

Los detalles específicos de la dimensión se muestran en un formato tabular. Haga clic en ![img](../../../../../03-media/apptio-planning/resources/images/icons/icon-options.png) en el lado derecho para ver una lista de opciones. Según el tipo de dimensión, las opciones disponibles y aplicables pueden variar.

| Opción | Detalles |
| --- | --- |
| Plantilla de identificadores | [Cambiar el identificador de los objetos de coste y las dimensiones](change-identifier.html "La función Identificadores de cambio permite a los administradores actualizar los identificadores del sistema (códigos) utilizados por las dimensiones de datos de referencia, como centros de coste, cuentas, proyectos y departamentos.") |
| Cambiar identificadores | [Cambiar el identificador de los objetos de coste y las dimensiones](change-identifier.html "La función Identificadores de cambio permite a los administradores actualizar los identificadores del sistema (códigos) utilizados por las dimensiones de datos de referencia, como centros de coste, cuentas, proyectos y departamentos.") |
| Plantilla de exportación | [Editar y publicar tablas de datos de referencia.](edit-publish-reference.html) |
| Exportar | [Editar y publicar tablas de datos de referencia.](edit-publish-reference.html) |
| Importar | [Editar y publicar tablas de datos de referencia.](edit-publish-reference.html) |
| Publicar | [Editar y publicar tablas de datos de referencia.](edit-publish-reference.html) |
| Revertir | [Editar y publicar tablas de datos de referencia.](edit-publish-reference.html) |
| Importar desde Transparencia de costes | [Integración con transparencia de costes](integrate-ct.html "Si su organización utiliza tanto Apptio Costing Standard como una aplicación de planificación Apptio, puede integrarlas para compartir datos.") [Importar y publicar datos reales](import-publish-actuals.html) |
| Cerrar Mostrar/Ocultar columnas | Cerrar la barra Mostrar/Ocultar columnas |

VER TAMBIÉN :

- [Editar y publicar tablas de datos de referencia](edit-publish-reference.html)
- [Gestionar datos de referencia personalizados (dimensiones y listas)](manage-custom-reference.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.")
- [Forzar un plan para utilizar datos de referencia actualizados](force-plan-use.html)
- [Diagrama de dependencias de la tabla de referencia](https://community.apptio.com/docs/DOC-9956 "(se abre en una pestaña o una ventana nueva)")

**Tema principal:** [Descripción general de los datos de referencia](../../it-planning/planning/edit-publish-reference.html)
