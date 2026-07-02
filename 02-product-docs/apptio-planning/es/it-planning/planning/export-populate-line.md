---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Exportar datos del plan"
breadcrumb:
  - "Planning"
  - "Trabajar con planos"
source_path: "it-planning/planning/export-populate-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Exportar datos del plan

En cualquier vista de tabla de Gastos que muestre tablas de partidas (por ejemplo, Resumen, Mano de Obra, Actividad Laboral, Contratos, Activos u Otros), los usuarios con los permisos adecuados pueden exportar esos datos a un archivo.csv.

Hay **tres modos de exportación** disponibles:

|  |  |
| --- | --- |
| **Modo exportación** | **Descripción** |
| **Exportar todo** | Exporta el conjunto de datos completo, incluidas todas las dimensiones y atributos definidos en el esquema del plan. |
| **Exportar diseño** | Exporta sólo los datos visibles actualmente en la presentación, incluidas las columnas aplicadas, los filtros y groupings.If Si se aplican agrupaciones, la exportación incluirá subtotales a nivel de grupo en lugar de partidas individuales secundarias. |
| **Exportar para reimportar** | Exporta todos los campos editables en un formato adecuado para reimportar los cambios. Esta opción ignora los filtros y selectores de tiempo (pero respeta las restricciones de permisos). Nota: En el formato Exportar para reimportar se incluyen columnas de nombre adicionales y campos generados por el sistema para mejorar la legibilidad. Estos campos no son obligatorios y puede ignorar cualquier advertencia relacionada con ellos durante el proceso de importación. |

## Antes de exportar

- Los resultados de la exportación están limitados por el acceso a los datos, por ejemplo, el alcance de la propiedad del objeto de coste o los permisos del rol de usuario.
- Para controlar qué campos se incluyen o cómo se organizan los datos, primero ajuste y guarde el diseño de la tabla.
- Los administradores y el propietario del proceso presupuestario pueden establecer un diseño predeterminado para todos los usuarios.

## Cómo exportar datos de partidas individuales

1. En el plan, seleccione el Departamento que desea exportar.
2. Si lo desea, elija la presentación correspondiente en el menú **Presentación**.
3. Seleccione la pestaña adecuada (por ejemplo, Resumen, Mano de obra, Actividad laboral, Contratos, Activos u Otros).
4. Haga clic en el menú **Acciones** de la parte superior derecha y seleccione **Exportar...**
5. Elija el modo de exportación que prefiera (Exportar todo, Exportar diseño o Exportar para reimportar) y los ajustes de formato de exportación (Delimitador coma, Formato de fecha, Separador de fecha, Símbolo decimal, Precisión decimal, Visualización de porcentaje, Codificación de caracteres).
6. Pulse **Aceptar**.
