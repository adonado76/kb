---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Planificación de activos"
breadcrumb:
  - "Planning"
  - "Planificación de activos"
source_path: "it-planning/planning/manage-assets.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planificación de activos

El módulo de planificación de activos le permite presupuestar, prever y gestionar las inversiones de capital en activos fijos. Los activos fijos son recursos tangibles a largo plazo -como servidores, hardware o equipos- que una empresa posee y utiliza durante varios años. Estos activos se capitalizan y se amortizan a lo largo del tiempo, en lugar de cargarse a gastos inmediatamente.

Con Asset Planning, puede:

- Realice un seguimiento de **las compras en CapEx** y de la transición a la **depreciación en OpEx** una vez que los activos se pongan en servicio.
- Modele el **ciclo de vida completo de los activos**, desde su adquisición hasta su amortización, mantenimiento y retirada.
- Asigne los **gastos de depreciación** por departamento o centro de costes para obtener informes financieros precisos.
- Aplicar **reglas y métodos de amortización** para prever el impacto de los costes a largo plazo en periodos futuros.

## Configurar la planificación de activos

Nota: Se requieren los roles de Administrador o Propietario del Proceso Presupuestario.

**Habilitar activos**

- Asegúrese de que la función **Activos** está activada en: **Ajustes** (icono de engranaje) **→ Perfil de empresa**.

**Datos de referencia de la clase de activos**

La clase de activos es una dimensión clave que controla cómo se gestionan las adquisiciones y las amortizaciones.

- Vaya a **Configuración → Datos de referencia → Clase de activos**.
- Puede exportar una plantilla: **Menú desplegable de tres puntos→** **Exportar plantilla**.
- Rellene o actualice las columnas del archivo.csv:
- **Clase de** activos - Nombre de la categoría de activos. Debe ser único.
- **Cuenta de depreciación** - OpEx cuenta utilizada para la depreciación.
- **Cuenta de compras** - CapEx cuenta utilizada para la adquisición de activos.
- **Método de depreciación** - Seleccione el método utilizado para depreciar el activo. (por ejemplo, línea recta, doble decreciente o saldo decreciente). Consulte la sección Métodos de amortización para obtener más información.
- **Vida útil del** activo (meses) - Vida útil del activo en meses
- **Valor residual %** - Porcentaje del coste original del activo que se espera que permanezca al final de su vida útil (también conocido como valor de salvamento). Introdúzcalo como decimal - por ejemplo, 1 = 100%, 0.1 = 10%.
- **Tasa de Saldo %** - La tasa para depreciar el activo. Se utiliza para el método de saldo decreciente. Introdúzcalo como decimal - por ejemplo, 1 = 100%, 0.1 = 10%.
- Importe el archivo actualizado y **publíquelo**.

## Introducción y gestión de partidas individuales de activos fijos

- Abra su plan y navegue hasta la pestaña **Activos** dentro de la página **Gastos**.
- Añade un nuevo activo:
- Utilizando la **fila vacía** de la parte inferior de la tabla, o bien
- **Haga clic con el botón derecho** y seleccione **Insertar fila**
- Introduzca los siguientes datos para cada activo:
- **Clase de activo -** Seleccione la categoría que define cómo se capitalizará y depreciará el activo. Determina las reglas y cuentas de amortización por defecto.
- **Centro de costes -** Seleccione el centro de costes que será responsable financieramente del coste y la depreciación del activo.
- **Proveedor** (opcional): especifique el proveedor o vendedor asociado con la compra de activos. Esto es opcional pero útil para informar
- **Método de depreciación** - Regla de depreciación que determina cómo se imputa el coste del activo a lo largo del tiempo. Se asigna automáticamente en función de la clase de activo, pero puede anularse manualmente si es necesario.
- **Fecha de compra -** Fecha en la que se adquirió o capitalizó el activo.
- **Fecha de entrada en servicio -** Fecha en la que el activo entra en funcionamiento. La amortización comienza a partir de esta fecha.
- **Precio de compra -** El coste de capital del activo que se adquiere. Este valor se utiliza para calcular la depreciación y el impacto financiero total.
- **Cantidad:** número de unidades de activos que se compran.

Una vez introducido, Apptio Planning generará automáticamente el plan de depreciación basado en las entradas de activos y el método de depreciación. Verá los importes de amortización distribuidos en las columnas de periodos de tiempo.

En la pestaña **Resumen**, Apptio Planning crea automáticamente dos asientos financieros:

- Una **entrada de compra** utilizando la *cuenta de compra* configurada
- Un **asiento de amortización** utilizando la *cuenta de amortización* configurada

## Amortización imputada a un centro de coste diferente

Si el gasto de amortización debe asignarse a un centro de coste distinto del que posee el activo, puede utilizar el campo **Centro de coste de amortización**. Esto redirige el coste de amortización a un centro de coste alternativo.

Esto es útil en situaciones como cuando un activo es adquirido por un centro de costes de proyecto, pero el mantenimiento continuo es financiado por un centro de costes diferente.

En este caso, el activo sigue perteneciendo al centro de coste original, mientras que la depreciación se carga en otro lugar.
