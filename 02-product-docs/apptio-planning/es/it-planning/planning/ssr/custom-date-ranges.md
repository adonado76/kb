---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Intervalos de fechas personalizados"
breadcrumb: []
source_path: "it-planning/planning/ssr/custom-date-ranges.html"
images:
  - "resources/images/ssr_images/release_notes/bi-ct-customdaterange_722x582.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Intervalos de fechas personalizados

Los clientes de Costing & Planning pueden ahora crear informes plurianuales utilizando intervalos de fechas personalizados.

## Compatibilidad con intervalos de fechas personalizados con fuentes de datos de planificación

Ahora puede seleccionar los siguientes periodos personalizados para sus visualizaciones:

- Mes
- Trimestre
- Medio
- Año

Estos periodos personalizados se añaden a los intervalos de fechas existentes. También puede utilizar la opción Desplazar y comparar con estos periodos personalizados.

Para utilizar periodos de fechas personalizados en sus visualizaciones:

1. Abra el editor de visualización en Apptio BI y seleccione cualquier fuente de datos de Planning .
2. Añada las dimensiones y métricas aplicables.
3. En el selector Intervalo de fechas, seleccione uno de los siguientes periodos personalizados: Mes, Trimestre, Semestre o Año.
4. Si es necesario, configure la opción Rodar.
5. Desplazamiento: La opción Rolling hace que un intervalo de fechas sea relativo; el intervalo de fechas cambia a medida que se avanza en el tiempo. Para establecer un intervalo de fechas renovable, seleccione la casilla Renovable. Esta casilla no está seleccionada por defecto.
6. Comparar: La opción Comparar permite comparar dos periodos de tiempo para ver cómo ha cambiado una métrica determinada a lo largo de los periodos especificados. Para utilizar la opción Comparar, seleccione el primer intervalo de fechas y, tras marcar la casilla Comparar, seleccione el segundo intervalo de fechas. La casilla de comparación no está seleccionada por defecto.
7. Guarda la visualización.

La siguiente figura muestra un ejemplo de selección del periodo de comparación para una visualización.![Seleccione un intervalo de fechas entre enero y septiembre de 2021 y enero y septiembre de 2022.](../../../../../../03-media/apptio-planning/resources/images/ssr_images/release_notes/bi-ct-customdaterange_722x582.png)
