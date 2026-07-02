---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Gestionar datos de referencia en TBM Studio"
breadcrumb: []
source_path: "it-planning/planning/manage-itfmf-reference.html"
images:
  - "resources/planning_images/studio_check-out_upload.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gestionar datos de referencia en TBM Studio

◆ Se aplica a: Planning

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Las dimensiones son las categorías de datos esenciales en las partidas presupuestarias. Muchas dimensiones integradas dependen de otras dimensiones. Para más información, véase [Atributo de datos de referencia y dependencias de dimensiones](manage-reference-data.html). En las aplicaciones Apptio Planning , puede trabajar con datos de TBM Studio en Microsoft Excel, trabajar con conjuntos de datos maestros y actualizar datos de referencia.

## Sobrescribir los datos de referencia de TBM Studio

Puede modificar los datos de referencia de TBM Studio en Data Studio. Descargue los datos de referencia existentes en TBM Studio, modifíquelos en Excel y, a continuación, sobrescriba los datos en TBM Studio siguiendo estos pasos:

1. En **TBM Studio**seleccione la vista Entorno de desarrollo.
2. En el Explorador de proyectos, abra y edite la información de la tabla según sea necesario y, a continuación, haga clic en Exportar.
3. Abra y modifique los datos de referencia en Excel y, a continuación, guarde el archivo como archivo.csv.
4. En el Explorador de proyectos, seleccione la tabla y haga clic en Check Out. El nombre de la tabla cambia a naranja para indicar que se ha retirado.
5. En el panel Pasos, haga clic en Cargar.

   ![imagen](../../../../../03-media/apptio-planning/resources/planning_images/studio_check-out_upload.png)
6. Haga clic con el botón derecho en Carga inicial y seleccione Sobrescribir.
7. Busque y seleccione el archivo.csv guardado.
8. En el panel Pasos, haga clic en Tabla para inspeccionar los datos y confirmar los cambios.
9. Repita este proceso según sea necesario.

## Confirmar datos maestros

Confirme los datos en los conjuntos de datos maestros integrados y promueva los datos a Producción siguiendo los siguientes pasos. Observe que los conjuntos de datos maestros integrados están agrupados.

1. En el Explorador de proyectos, abra el Maestro de cuentas ITP e inspeccione los datos. Si los nuevos datos contenían un nombre de columna distinto del nombre de columna inicial, es posible que los datos no se abrieran. En este caso, compruebe el conjunto de datos maestro y vuelva a ejecutar el paso Append para corregir este problema.
2. Pulse Check In.
3. Haga clic en la pestaña Proyecto y, a continuación, en Cola de cálculo para ver el estado del registro más reciente. Una vez completado el cálculo de puesta en escena, el estado se muestra como Finalizado, lo que indica que puede pasar los cambios a Producción.
4. Cambie la vista del entorno de En desarrollo a Puesta en escena.
5. Haga clic en Bloquear para impedir las entradas.
6. Haga clic en Opciones de promoción.
7. Haga clic en Promover ahora para promover su cálculo de Puesta en escena a Producción.
8. Haz clic en Desbloquear.

## Actualizar dimensiones y atributos

La siguiente tabla proporciona información sobre dónde actualizar las dimensiones (datos que Planning introduce en las columnas) y los atributos de configuración (cálculos que Planning utiliza para calcular el precio o el coste).

| Módulo asociado | Obligatorio u opcional | Actualizar en TBM Studio y luego empujar a Planning | Actualizar en Planning y luego empujar a TBM Studio |
| --- | --- | --- | --- |
| Planning | Obligatorio | Cuenta | Permisos para objetos de coste |
| Planning | Obligatorio | Centro de costes | Normas de asignación de mano de obra |
| Planning | Obligatorio | Departamento |  |
| Planning | Obligatorio | Tarifas laborales |  |
| Planning | Obligatorio | Rol |  |
| Planning | Opcional | Ubicación |  |
| Planning | Opcional | Proveedor |  |
| Planning | Opcional | Tipo de contrato |  |
| Planning | Opcional | Clase de activos |  |
| Multidivisa | Obligatorio | Tipo de cambio real |  |
| Multidivisa | Obligatorio | Plan Tipo de cambio |  |
| Project Financial Planning | Obligatorio | Proyecto |  |
| Project Financial Planning | Obligatorio | Grupo de proyectos |  |
| Project Financial Planning | Obligatorio | Mano de obra externa |  |
| Project Financial Planning | Obligatorio | Bolsa de trabajo interna |  |

Nota: Los Permisos de Objetos de Coste y las Reglas de Imputación de Mano de Obra son procesos manuales opcionales para exportarlos a Excel y cargarlos en TBM Studio.

La siguiente tabla muestra dónde actualizar los datos del plan, las previsiones y los datos reales:

| Módulo asociado | Obligatorio u opcional | Actualizar en TBM Studio y luego empujar a Planning | Actualización en Planning  y empuje a TBM Studio |
| --- | --- | --- | --- |
| Planning | Obligatorio | Actual | Datos del plan |
| Planning | Obligatorio |  | Datos previstos |

VER TAMBIÉN :

- [Gestionar los datos de referencia de los centros de costes](manage-cost-center.html)
- [Actualizar jerarquía de departamentos](update-department-hierarchy.html)
- [Forzar un plan para utilizar datos de referencia actualizados](force-plan-use.html)
