---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Carga masiva de valores de partidas"
breadcrumb:
  - "Planning"
  - "Trabajar con planos"
source_path: "it-planning/planning/enter-import-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Carga masiva de valores de partidas

Cargue datos de forma masiva subiendo un archivo de texto delimitado por comas ( CSV ) a su plan financiero.

## Permisos

- **Los administradores** y **propietarios de procesos presupuestarios** pueden cargar datos de partidas en toda la organización.
- **Los Propietarios de Centros de Coste** pueden cargar para los departamentos a los que tienen acceso de edición.
- **Los gestores de proyectos** pueden realizar cargas para los proyectos a los que tienen acceso de edición.

## Modos de importación

Al realizar una carga masiva, podrás elegir entre los siguientes modos de importación:

|  |  |
| --- | --- |
| **Modo** | **Comportamiento** |
| Sustituir todos los datos | Borra los valores existentes y los sustituye por completo por los valores del archivo de importación. Cada línea importada tendrá un nuevo Código de Partida. |
| Reemplazar todos los datos con filtro de dimensión | Permite importar partidas individuales para sustituir selectivamente los datos solo para las dimensiones específicas. Los usuarios pueden seleccionar una o más dimensiones para sustituir los datos de forma selectiva. Cada línea importada tendrá un nuevo Código de Partida.  Se admite el filtrado por las siguientes dimensiones   1. Cuenta 2. Centro de costes 3. Objeto de coste 4. Proyecto 5. Proveedor 6. Ubicación 7. Dimensiones personalizadas 8. Columnas personalizadas del tipo de datos Lista |
| Actualizar datos | Actualiza las líneas existentes mediante el código de partida. Si el Código Externo está activado, el sistema comparará el Código de Partida y el Código Externo durante el proceso de actualización. Todas las líneas del archivo de importación que no coincidan con un Código de Partida o Código Externo existente se añadirán como nuevas partidas y se generará automáticamente un nuevo Código de Partida. |
| Añadir datos | Añade todas las partidas del archivo al Plan sin modificar ni eliminar los datos existentes. Utilice esta opción para importar solo registros nuevos. A cada nueva fila se le asignará un código de línea único. |

## Pasos para la carga masiva de valores de partidas

1. Abra el plan y navegue hasta la pestaña de Gastos correspondiente (por ejemplo, **Mano de obra**, **Actividad laboral**, **Contratos**, **Activos** u **Otros** ).
2. Seleccione el **Departamento** al que desea importar los datos en el menú Departamento.
3. Abra el menú **Acciones** en la esquina superior derecha y seleccione **Importar...**
4. Cargue su **archivo** CSV y seleccione el **modo de importación** deseado (Reemplazar todos los datos, Actualizar datos, Añadir datos o Reemplazar todos los datos con filtro de dimensión).
   1. **Usar Reemplazar todos los datos con filtro de dimensión**
      1. En el cuadro de diálogo Importar, haga clic en el botón **Añadir** **filtro** **de dimensión.**
      2. Seleccione **una dimensión** **.**
      3. Seleccione uno o más valores para la dimensión seleccionada.
      4. *(Opcional)* **Añada dimensiones adicionales** y especifique valores para cada una de ellas.
      5. Cuando se aplican varios filtros, los datos solo se sustituirán en las filas que cumplan *todos* los criterios de filtrado.
   2. **Para utilizar cualquier otro modo de importación** (Reemplazar todos los datos, Actualizar datos o Añadir datos), seleccione la opción de importación deseada.
5. *(Opcional)* Ajuste la configuración de importación, como el delimitador de columna, el formato de fecha, el símbolo decimal, la visualización de porcentaje y la codificación de caracteres.
6. Haga clic en **Importar** para generar una vista previa.
7. Revise la vista previa para confirmar que los datos están asignados y formateados correctamente.
8. Si es correcto, haga clic en **Importar** para finalizar, o en **Importar con problemas** si desea continuar a pesar de las advertencias. También puede **Exportar Archivo de Ayuda** para revisar en detalle cualquier error de importación.
9. Una vez completado, los datos se añaden correctamente al plan y se hacen visibles en la tabla de **Gastos**.

Nota: Las columnas «Período» y «Mes» se rellenan automáticamente en función de la **fecha de inicio**, **la fecha de finalización** y **la cantidad** introducidas. El sistema distribuye la cantidad especificada entre los meses del intervalo de fechas seleccionado. Los usuarios pueden modificar estos valores generados automáticamente si es necesario.

## Exportar una plantilla para importarla

1. Abra el plan y navegue hasta la pestaña de Gastos correspondiente (por ejemplo, **Mano de obra**, **Actividad laboral**, **Contratos**, **Activos** u **Otros** ).
2. Haga clic en el menú **Acciones** de la parte superior derecha y seleccione **Exportar plantilla...**
3. Haga clic en **Aceptar** para descargar el archivo de plantilla generado. **No modifique las cabeceras ni la estructura de las columnas**, ya que son necesarias para la coherencia de la importación.
4. Rellene la plantilla con los datos de sus partidas.
5. Guarde su archivo en formato.csv e impórtelo de nuevo en Apptio Planning cuando esté listo.
