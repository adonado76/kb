---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Configuración del perfil de la empresa"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/edit-company-profile.html"
images:
  - "resources/images/studio_images/studioimages/icons/setting-icon.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configuración del perfil de la empresa

El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.

Nota: Se requieren roles de administrador o responsable del proceso presupuestario para gestionar la configuración del perfil de la empresa.

## Acceder al perfil de la empresa

1. Selecciona el botón **Configuración** (![img](../../../../../03-media/apptio-planning/resources/images/studio_images/studioimages/icons/setting-icon.jpg)) en la esquina superior derecha y elige **Perfil de la empresa**.
2. Introduzca o edite la información según sea necesario.
3. Seleccione **Guardar y Salir para** aplicar los cambios.

## Configuración general

|  |  |  |
| --- | --- | --- |
| **Sección** | **Característica** | **Descripción** |
| Moneda | Moneda predeterminada | Establece la moneda principal utilizada en todos los planes. Todos los valores monetarios se establecen por defecto en esta moneda, a menos que se habilite la función multidivisa. |
| Moneda | Habilitar multidivisa | Permite a los usuarios planificar en múltiples divisas. Las reglas de conversión de divisas se aplican cuando están habilitadas. |
| Moneda | Mostrar los códigos ISO de las divisas en lugar de los símbolos de las divisas. | Reemplaza los símbolos monetarios (por ejemplo, $, £) por códigos ISO (por ejemplo, USD, GBP). |
| Formato numérico | Habilitar precisión de números decimales | Controle el número de decimales que se muestran en los campos numéricos de los planos. |
| Formato numérico | Decimales | Especifica el número de decimales (por ejemplo, 1-8) que se utilizarán cuando se habilite la precisión decimal. |
| Acceso y permisos | Habilitar permisos de visualización obligatorios | Restringe la visibilidad del departamento en función de los permisos del usuario. Los usuarios solo ven los objetos de coste a los que tienen autorización para acceder. |
| Acceso y permisos | Habilitar la nueva experiencia de la página Gastos (Beta) | Habilita la página de gastos rediseñada, que ofrece un rendimiento, un filtrado y una navegación mejorados. |
| Acceso y permisos | Habilitar permisos de objetos de coste a nivel de plan | Habilita la página Permisos de usuario en el nivel de plan individual para gestionar los permisos por plan. |
| Flujos de trabajo de aprobación y notificaciones | Flujo de trabajo de aprobación | Define cómo avanzan las presentaciones de planes a través del proceso de aprobación.    Elija entre la aprobación multinivel (aprobadores secuenciales) o la aprobación jerárquica (estructura organizativa de informes).    Para las aprobaciones jerárquicas, puede optar por desactivar los envíos del departamento del grupo. |
| Flujos de trabajo de aprobación y notificaciones | Enviar notificaciones por correo electrónico para eventos del proceso de planificación | Envía alertas por correo electrónico cuando se envían, aprueban o devuelven planes. |
| Análisis de varianza | Habilitar análisis de varianza | Habilita el análisis de variaciones, lo que permite a los usuarios capturar los factores que provocan variaciones y añadir comentarios. |
| Previsiones | Resumir datos reales | Selecciona los atributos utilizados para acumular y resumir los datos de transacciones reales para la previsión. |
| Data Management | Habilitar código externo | Permite almacenar identificadores de sistemas externos para partidas de plan. |
| Data Management | Desactivar restricciones de actualización de datos de referencia | Permite actualizar los valores de los datos de referencia incluso cuando los cambios puedan eliminar datos del plan existentes. El sistema genera una copia de seguridad antes de aplicar la actualización. |
| Data Management | Habilitar la Data Management integración automatizada | Permite la importación y sincronización de datos a través de ADM. |
| Actualizaciones y mantenimiento | Día de actualización | Especifica el día en que su entorno recibe las actualizaciones del producto. |
| Mostrar intervalos de fechas | Mostrar el intervalo de fechas para las columnas de período | Muestra la fecha de inicio y la fecha de finalización de las columnas de periodo de la tabla «Gastos». Las fechas se formatean según la configuración regional del usuario. Nota: Disponible únicamente en «Gastos > Nueva vista» |
| Configuración de la distribución de datos para otros gastos | Establecer el margen de días del calendario como valor predeterminado | Cuando esta opción está activada, los importes introducidos en las columnas **trimestrales** o **anuales** se distribuyen automáticamente entre los meses en función del número de días naturales de cada mes.  Los usuarios pueden modificar esta configuración predeterminada en la tabla «Gastos» y seleccionar entre **«Distribución uniforme» o** **«Distribución por días naturales».** |

## Planificación laboral

|  |  |  |
| --- | --- | --- |
| **Sección** | **Característica** | **Descripción** |
| Planificación de la plantilla laboral | Plantilla laboral | Permite planificar la plantilla, lo que permite a los usuarios planificar los niveles de personal, los puestos y los costes asociados en la pestaña «Personal». |
| Planificación de la plantilla laboral | Método de resumen del recuento de personal | Determina cómo se consolidan los registros de mano de obra múltiples (por ejemplo, calculando el promedio o seleccionando el valor del período inicial o final). |
| Planificación de la plantilla laboral | Fecha de inicio laboral predeterminada | Establece una fecha de inicio predeterminada para las nuevas entradas de mano de obra. |
| Planificación de la plantilla laboral | Desactivar la advertencia de compensación base | Desactiva las advertencias del sistema que se activan cuando los valores de compensación base están en blanco. |
| Ajuste de compensación | Ajuste de la remuneración variable | Permite modelar ajustes de compensación variable. |
| Ajuste de compensación | Ciclos de ajuste | Define la frecuencia y el momento predeterminados para los ajustes de compensación. Estos ajustes pueden anularse a nivel del plan. |
| Resumen laboral | Resumen laboral | Seleccione las dimensiones utilizadas para agregar las partidas financieras generadas desde la pestaña «Labor» cuando se muestran en la pestaña «Summary». |

## Planificación de contratos

|  |  |  |
| --- | --- | --- |
| **Sección** | **Característica** | **Descripción** |
| Planificación de contratos | Contratos | Permite la planificación a nivel de contrato, lo que permite a los usuarios modelar contratos nuevos y existentes dentro de la pestaña Contratos. |
| Planificación de contratos | Contrato de actualización automática Total | Recalcula automáticamente el total del contrato cuando cambian los importes periódicos, garantizando que el valor del contrato refleje siempre la suma de los pagos programados. |
| Planificación de contratos | Incluir el impuesto sobre el valor añadido (IVA) | Permite aplicar el IVA a los pagos de los contratos. Cuando está habilitado, el IVA se calcula en función del tipo impositivo definido. |

## Planificación de activos

|  |  |  |
| --- | --- | --- |
| **Sección** | **Característica** | **Descripción** |
| Planificación de activos | Habilitar la planificación de activos | Habilita el nivel de activos, lo que permite a los usuarios modelar activos de capital y calcular la depreciación y los gastos de capital dentro de la pestaña Activos. |

## Planificación de inversiones

|  |  |  |
| --- | --- | --- |
| **Sección** | **Característica** | **Descripción** |
| Planificación de proyectos | Habilitar la planificación integrada de inversiones | Permite la planificación basada en proyectos, lo que permite a los usuarios definir inversiones y vincular los gastos a los proyectos. |
| Planificación de la actividad laboral | Habilitar actividad laboral | Permite a los usuarios asignar el esfuerzo laboral (horas o FTE) a los proyectos y generar datos financieros de cargos cruzados basados en los tipos de actividad dentro de la pestaña Actividad laboral. |
| Planificación de la actividad laboral | Asignación de mano de obra | Permite configurar reglas de sobreasignación y subasignación para los recursos laborales. Cuando esté habilitado, defina los umbrales para cuando un recurso se asigne por encima o por debajo de su capacidad disponible. |
