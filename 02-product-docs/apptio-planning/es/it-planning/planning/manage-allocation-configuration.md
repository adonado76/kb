---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Asignación Datos de referencia de la configuración"
breadcrumb: []
source_path: "it-planning/planning/manage-allocation-configuration.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Asignación Datos de referencia de la configuración

◆ Se aplica a: Apptio Planning aplicaciones con Project Financial Planning (ver [Introducción al uso de Project Financial Planning módulo](pfp/gs-project-financial.html "◆ Se aplica a: Planificación con proyecto Planificación financiera.") ) o Service Demand Planning (ver [Introducción al uso de Service Demand Planning módulo](sdp/gs-service-demand.html) )

Las tareas que se indican a continuación requieren que obtenga una licencia para Project Financial Planning o Service Demand Planning y, a continuación, edite el perfil de la empresa para habilitar Project Financial Planning o Service Demand Planning. Véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning."). Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Vea este vídeo de Apptio Education Services: [Configuración de datos de referencia: Project
Financial Planning Dimensiones](https://community.ibm.com/community/user/viewdocument/configuring-reference-data-labor-d?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)"). SUGERENCIA: Vaya a 4:30 para ver información sobre el tipo de cuenta de transferencia.

Las dimensiones son las categorías de datos esenciales en las partidas presupuestarias. Muchas dimensiones incorporadas tienen dependencias con otras dimensiones (para más información, véase [Atributo de datos de referencia y dependencias de dimensiones](manage-reference-data.html) ). Puede importar datos de referencia de dimensiones desde un archivo.csv o desde Costing Standard y exportar plantillas de datos de referencia de dimensiones y datos de tablas (véase [Gestionar dimensiones](manage-reference-data.html) ).

La dimensión Predeterminada de la Cuenta de Transferencia permite al Propietario del Proyecto, Propietario del Servicio, Gerente de Relaciones Comerciales y Propietario de la Unidad de Negocio determinar la asignación correcta de dinero para consumir o apoyar varios proyectos o servicios. Esta función requiere que Service Demand Planning o Project Financial Planning estén activados. Véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.").

1. En el menú de navegación, seleccione Configuración > Datos de referencia > Transferir cuenta por defecto.
2. Seleccione ![más](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) en la esquina superior derecha de la tabla, seleccione Exportar > Exportar todo.
3. Abra el archivo.csv descargado y actualice los valores de la tabla de datos según sea necesario:
   - Tipo de consumidor : objeto de coste que consume los recursos de otro objeto de coste
   - Tipo de proveedor : objeto de coste que proporciona recursos a otro objeto de coste
   - Cuenta de transferencia - La cuenta que recibe el pago (requiere código de cuenta)
   - Cuenta de transferencia - La cuenta utilizada para pagar (requiere código de cuenta)
4. Ahora, Configuración > Datos de referencia > Transferir cuenta por defecto y, a continuación, importe el archivo.csv actualizado.

Cuando introduzca los datos del Proveedor y del Consumidor, consulte esta tabla de combinaciones permitidas:

| Proveedor | Consumidor |
| --- | --- |
| Mano de obra externa | Proyecto |
| Mano de obra externa | Servicios |
| Bolsa de trabajo interna | Proyecto |
| Bolsa de trabajo interna | Servicios |
| Servicios | Unidad de negocio |
| Servicios | Servicios |
| Servicios | Proyecto |
| Servicios | Departamento |

Consejo: Puede integrar esta dimensión con Costing Standard para importar datos de cuentas de transferencia desde Costing Standard.
