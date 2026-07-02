---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Comparar versiones o planes"
breadcrumb:
  - "Planning"
  - "Trabajar con planos"
source_path: "it-planning/planning/compare-versions-plans.html"
images:
  - "resources/images/it_planning_images/compver1.png"
  - "resources/images/it_planning_images/compver2.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Comparar versiones o planes

Puede comparar los datos financieros entre dos períodos o versiones del mismo plan, o entre dos planes diferentes. Estas comparaciones muestran las diferencias entre periodos y partidas para ayudarle a comprender los cambios y las desviaciones.

## Comparación entre periodos

Nota: Requiere la nueva vista de gastos.

Permite comparar periodos dentro del mismo plan —año tras año, trimestre tras trimestre o mes tras mes—, lo que facilita el análisis de tendencias y cambios a lo largo del tiempo.

Para comparar el plan mediante la comparación de un periodo a otro, siga estos pasos:

1. Ve a **Gastos > Nueva vista**.
2. Selecciona la **pestaña «Gastos»** que quieras comparar.
3. En la **columna «Período»**, abre el **menú** y selecciona «**Añadir comparación** ». Se abrirá el cuadro de diálogo «**Añadir comparación** ».
4. Selecciona el botón de opción «**De período a período** ».
5. Elige el periodo de comparación en función de dónde se realice la comparación:
   1. **Cuando se invoca desde la columna «Mes»**
      - **Plan anual** : Selecciona el **mes** de referencia.
      - **Plan plurianual** : Seleccione el **año** de referencia y el **mes** correspondiente dentro de ese año.
   2. **Cuando se invoca desde la columna «Quarter»**
      1. **Plan anual** : Selecciona el **trimestre** de comparación.
      2. **Plan plurianual** : Seleccione el **año** de referencia y el **trimestre** correspondiente dentro de ese año.
   3. **Cuando se invoca desde la columna «Año»**
      1. **Plan de un año** : la opción **«De periodo a periodo»** no está disponible.
      2. **Plan plurianual** : Selecciona el **año** de referencia.
6. Haz clic en **«Comparar»** para iniciar la comparación.
7. Revisa los resultados de la comparación que figuran en la tabla, donde se muestran **el total**, **la desviación** y **el porcentaje de desviación**, agrupados por atributos comunes como **el objeto de coste** y **la cuenta**.
8. Para eliminar la comparación, abre el **menú del periodo** en la **columna de origen** y selecciona «**Eliminar comparación** ».

## Comparación entre planes

Permite comparar periodos o versiones entre dos planes, lo que facilita el análisis de las diferencias entre distintos ejercicios financieros y de los escenarios hipotéticos.

## Comparación Método de alineación

Al comparar planes, puede elegir entre dos métodos de alineación. Debe seleccionar uno cuando añada una comparación desde la tabla de Gastos o utilizando los Atajos de Comparación.

1. Año de inicio del plan

   Alinea los planes en función de sus ejercicios fiscales iniciales.

   Ejemplo:
   - **El Plan A** cubre FY2019–2020
   - **El Plan B** cubre FY2020–2021
   - Utilizando este método, **FY2019 del Plan A** se compara con **FY2020 del Plan B**.
2. **Correspondencia Ejercicio**

   Alinea los planes comparando el **mismo ejercicio fiscal** en ambos planes.

   Ejemplo:
   - **El Plan A** cubre FY2019–2020
   - **El Plan B** cubre FY2020–2021
   - Con este método, compara **FY2020 del Plan A** con **FY2020 del Plan B**.

## Cómo comparar versiones o planes

1. Abra el plan que desea comparar desde el menú **Plan**.
2. En la tabla de Gastos, pase el ratón sobre una columna de **Mes**, **Trimestre** o **Ejercicio** y abra el **menú de cabecera de columna**, a continuación seleccione **Añadir Comparación....**
3. Elija la **versión o el plan** con el que desea comparar. *Nota: las versiones sólo están disponibles cuando se visualizan los Departamentos de hojas.*
4. Seleccione el Método de Alineación: **Año de inicio del plan** o **Ejercicio de alineación**.
5. *(Opcional)* Habilite **Incluir trimestres** o **Incluir años** para añadir comparaciones a lo largo de varios periodos de tiempo.
6. Haz clic en **Comparar**.
7. Aparecerán nuevas columnas **Total**, **Desviación** y **% de desviación** junto al periodo de tiempo seleccionado para mostrar los resultados de la comparación.
8. Para ajustar la granularidad de la comparación, cambie la **agrupación de la tabla** - por defecto, las comparaciones se muestran por **Objeto de Coste y Cuenta**.

   Nota: La vista heredada admite la función de comparación para las pestañas «Otros» y «Resumen» en todos los periodos, y para la pestaña «Mano de obra» solo en las columnas de totales del ejercicio fiscal. Para añadir comparaciones en Contratos, Activos, Mano de obra y Actividad laboral en todos los periodos, utilice la Nueva vista.

## Atajos de comparación

Los accesos directos de comparación le permiten comparar rápidamente su plan actual con hasta otros cuatro planes. Los administradores también pueden optar por activar un plan de comparación por defecto para todos los usuarios. Los usuarios pueden activar o desactivar las comparaciones en cualquier momento desde el menú Comparar con.

## Cómo establecer atajos de comparación

Nota: Los usuarios con **ManagePlan** pueden configurar accesos directos de comparación.

1. En **el menú Ellipsis**, seleccione **Comparar accesos directos**.
2. En la ventana **Gestionar accesos directos de comparación**, elija los planes con los que desea comparar y seleccione un Método de alineación para cada uno.
3. Opcionalmente, active **Mostrar por defecto** para mostrar automáticamente las comparaciones a todos los usuarios.
4. Haga clic en **Aceptar** para guardar la configuración.

![imagen de comparación de versiones](../../../../../03-media/apptio-planning/resources/images/it_planning_images/compver1.png)

Una vez configuradas, los usuarios pueden alternar las comparaciones en cualquier momento desde el menú **Comparar con.** Las comparaciones aparecerán automáticamente en todas las columnas visibles de Trimestre, Año y YTD. Los accesos directos de comparación se configuran por plan, lo que significa que puede establecer diferentes planes de comparación para cada plan individual.

![imagen de comparación de versiones](../../../../../03-media/apptio-planning/resources/images/it_planning_images/compver2.png)
