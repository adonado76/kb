---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Calendarios de trabajo"
breadcrumb:
  - "Planning"
  - "Planificación laboral"
source_path: "it-planning/planning/configure-working-days.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Calendarios de trabajo

El calendario laboral define cuántos días y horas laborables se utilizan para la planificación laboral, lo que influye en la conversión del equivalente a tiempo completo (ETC), la amortización de los costes laborales y los cálculos de gastos mensuales.

Puede configurar varios calendarios en el sistema (por ejemplo: a tiempo completo, a tiempo parcial, calendario global de vacaciones) y designar un calendario laboral por defecto. Los cambios en el calendario afectan a la modelización de los gastos laborales y deben gestionarse con cuidado.

Nota: Para configurar calendarios de trabajo se requieren los roles de Administrador o Propietario de Proceso Presupuestario.

## Tipos de calendarios laborales

**Calendario fijo**

- Defina un número determinado de horas de trabajo al mes (por ejemplo: 168 horas al mes).
- Utilícelo cuando su organización utilice un modelo estándar de horas de trabajo mensuales independientemente de los días de trabajo reales.

**Calendario variable**

- Defina los días laborables por día de la semana, fije las horas por día y especifique los días no laborables (festivos, paros).
- Utilícelo cuando su planificación laboral refleje días laborables reales, vacaciones u horarios no estándar.

## Configurar calendarios de trabajo

1. Navegue hasta **Configuración → Configurar calendario**.
2. Haga clic en **Añadir** y seleccione **Calendario fijo** o **Calendario variable**.
3. Introduzca un **nombre** para el calendario y haga clic en **Añadir**.
4. Haga clic en el icono **Editar (lápiz** ) situado junto al nombre del calendario para configurar los detalles.

**Para calendarios fijos:**

- Introduzca el valor de **horas de trabajo al mes**.

**Para calendarios variables:**

1. Seleccione los **días laborables de la semana**.
2. Introduzca las **horas por jornada laboral** (por ejemplo, 8 para una jornada laboral estándar).
3. Para añadir días no laborables:
   1. Haga clic en **Editar en** *Días no laborables*.
   2. Elija el **año** y, a continuación, introduzca un **nombre** y una **fecha** (MM/DD) para cada día festivo o no laborable.
   3. Pulse **Guardar**.

Cuando pase el ratón por encima de un calendario, seleccione **Marcar como predeterminado** para establecerlo como calendario de trabajo predeterminado. El calendario por defecto se aplicará automáticamente a las nuevas partidas de mano de obra.

## Asignación y uso de calendarios de trabajo

- El calendario laboral por defecto se asigna automáticamente a las líneas de trabajo a menos que se seleccione un calendario diferente.
- Si dispone de varios calendarios (por ejemplo, para diferentes regiones o tipos de trabajo), los usuarios pueden anular el calendario para partidas de trabajo específicas.
- Utilizar el calendario laboral en la amortización de gastos laborales: Actualice el **Método de Amortización de Mano de Obra** en **las Reglas de Asignación de Mano de Obra** y publique los cambios. Consulte [las Reglas de asignación de mano de obra](manage-labor-allocation-rules.html) para obtener más información.

## Solución de problemas y consideraciones

|  |  |  |
| --- | --- | --- |
| **Problema** | **Descripción** | **Recomendación** |
| La conversión de horas a ETC parece incorrecta | Es posible que el calendario no refleje correctamente las horas/día o los días laborables/semana. | Revise el calendario asignado, compruebe los ajustes de horas por día y días laborables. |
| Días no laborables que faltan (por ejemplo, vacaciones) | Es posible que la lista de días no laborables no esté rellenada para ese año o región. | Añada las fechas de vacaciones en Días no laborables y Guardar. |
| Múltiples calendarios que confunden a los usuarios | Es posible que los usuarios no sepan qué calendario seleccionar para las partidas. | Establezca una convención de nomenclatura clara (por ejemplo, “US-FullTime”, “EU-PartTime” ) y fije un valor por defecto. |
| La amortización de los gastos laborales no refleja el calendario | La regla de amortización no puede hacer referencia al calendario laboral. | Actualice las normas de asignación de mano de obra para utilizar el calendario laboral y vuelva a publicar los cambios. |
