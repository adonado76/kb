---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Visión general de la gestión de gastos"
breadcrumb:
  - "Planning"
  - "Gestión de gastos"
source_path: "it-planning/planning/spend-management.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Visión general de la gestión de gastos

La Gestión de Gastos le permite gestionar los datos reales importando las transacciones mensuales a Apptio Planning. La integración de los datos reales permite alinear los modelos de planificación y previsión con el rendimiento real, lo que mejora la visibilidad, el seguimiento de las desviaciones y la toma de decisiones.

## Fuentes de datos reales

- **Importación CSV** - Cargue transacciones reales mediante archivos CSV (por ejemplo, desde su sistema ERP o GL).
- **Apptio Integración del cálculo** de costes - Importe transacciones reales automáticamente desde Apptio Costing si está configurado.
- Independientemente de la fuente, los datos importados entran en la Gestión de Gastos y pueden utilizarse para crear planes de previsión.

## Pasos para importar datos reales mediante CSV

1. Vaya a **Gestión de gastos → Transacciones** en el panel de navegación izquierdo.
2. Utilice la **barra de navegación superior** para seleccionar el período de tiempo para el que desea importar los datos reales.
3. Haga clic en **Acciones → Importar reales...** o seleccione **Exportar plantilla** para descargar una plantilla CSV.
4. Elija un **tipo de importación** :
   1. **Sustituir todos los datos** : sobrescribe todos los datos existentes en el periodo seleccionado.
   2. **Añadir datos** : añade nuevas filas sin borrar los datos existentes.
5. Cargue su **archivo CSV con** los campos obligatorios.
6. Haga clic en **Importar** y, a continuación, seleccione **Importar** o **Importar con incidencias** para finalizar la carga.
7. Las transacciones importadas aparecerán inmediatamente en la **tabla Transacciones**.

## Pasos para importar datos reales de Apptio Costing

1. Compruebe que la conexión de datos está configurada en **Ajustes** (icono de engranaje) **→ Apptio Integración de cálculo de costes**.
2. Navegue hasta **Gestión de gastos → Transacciones.**
3. Utilice la **barra de navegación superior** para seleccionar el período de tiempo para el que desea importar los datos reales.
4. Haga clic en **Acciones → Importar desde Apptio Cálculo de costes....**
5. Haz clic en **Importar**.
6. Las transacciones importadas aparecerán en la **tabla Transacciones**.

   Para más información, véase [Importar datos reales](import-publish-actuals.html)

## Estados del período de gestión de gastos

Cada período contable en la Gestión de gastos tiene uno de los siguientes estados: **Nuevo**, **Abierto** o **Final**.

**Abrir un periodo**

1. Haga clic en **Abrir mes** en la esquina superior derecha.
2. El estado del periodo cambia de **Nuevo → Abierto**.

**Finalizar un período**

1. Haga clic en **Cerrar mes** en la esquina superior derecha.
2. El estado del periodo cambia de **Abierto → Final**.

**Reabrir un periodo**

1. Haga clic en **Reabrir mes** en la esquina superior derecha.
2. El estado del periodo cambia de **Final → Nuevo**.

***Notas de comportamiento***

- Los estados **Nuevo** y **Abierto** funcionan igual: los datos se pueden importar o modificar.
- Una vez que un periodo se marca **como Final**, no se permiten más importaciones ni ediciones, incluidos los datos importados automáticamente fromApptio Costing.
- Los Propietarios de Presupuestos pueden ver las transacciones de cualquier Departamento al que tengan acceso, independientemente del estado del periodo.
- Después de importar datos a un período, si hay datos de referencia (por ejemplo, Cuentas, Centros de Coste, etc.) se actualiza, debe hacer clic en **Actualizar datos de referencia** para aplicar esos cambios al periodo.
- La estructura de la **tabla Transacciones** puede gestionarse en **Configuración → Esquema → Reales**.
