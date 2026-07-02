---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Solución de problemas: imposibilidad de importar o exportar archivos Excel"
breadcrumb: []
source_path: "it-planning/planning/ts_unable_imp_exp_xsl.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Solución de problemas: imposibilidad de importar o exportar archivos Excel

## Antes de empezar

No es posible cargar datos de archivos de Microsoft Excel en la herramienta Planning ni exportar datos de archivos de Excel desde Planning.

## Acerca de esta tarea

Planning utiliza el formato de archivo.CSV para los datos cargados y no admite los formatos de archivo Excel predeterminados, como.XLS y.XLSX.

Adopte.CSV como formato de archivo de datos estándar cuando utilice la herramienta Planning . Puede exportar su presupuesto.CSV a su ordenador, realizar cambios en el archivo.CSV en Excel y, a continuación, volver a importar el nuevo archivo.CSV a Apptio.

## Procedimiento

- **Guardar archivos Excel como.CSV**
  1. Abra Microsoft Excel y abra el archivo que desea cargar en Apptio. Realice los ajustes necesarios.
  2. Haga clic en Guardar como y seleccione el formato de archivo ( \*.csv ).

     Se crea un nuevo archivo.CSV. Puede editar archivos.CSV dentro de Excel, lo que le permite realizar los ajustes necesarios antes de cargar sus archivos.
- **Importar archivos.CSV a Planning**

  Al importar archivos.CSV, se sustituyen todos los datos actuales de las partidas por los del archivo importado. Al importar archivos a Planning no se fusionan ni se añaden datos.

  Para obtener más información, consulte [Más información sobre cómo ingresar o importar datos de artículos de línea en Planning.](enter-import-line.html)
- **Exportar archivos.CSV desde Planning**

  Los archivos exportados desde Planning a su ordenador estarán por defecto en formato.CSV.

  Para obtener más información, [consulteMás información sobre la exportación y el relleno de tablas de partidas individuales o layouts en Planificación.](export-populate-line.html)
