---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Configuración del calendario fiscal"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/custom-calendars.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configuración del calendario fiscal

La configuración del calendario fiscal define cómo se estructura y se muestra el tiempo en Apptio Planning. Un año fiscal representa una estructura temporal recurrente que se utiliza para la planificación financiera, la elaboración de presupuestos y la presentación de informes. A diferencia del calendario gregoriano tradicional, un año fiscal no tiene por qué comenzar el 1 de enero ni terminar el 31 de diciembre. En su lugar, las organizaciones definen las fechas fiscales que mejor se ajustan a sus ciclos económicos y a las prácticas del sector.

Nota: Se requiere el rol de administrador para gestionar la configuración del calendario fiscal.

Dependiendo del tipo de calendario, un año fiscal puede organizarse de la siguiente manera:

- 12 meses consecutivos (calendario gregoriano),
- Períodos semanales, como las variantes 4-4-5, o
- 13 períodos iguales, normalmente diseñados para que cada período contenga el mismo número de días.

En todos los casos, los calendarios fiscales están diseñados para alinearse con el calendario gregoriano subyacente a lo largo del tiempo, teniendo en cuenta la duración estándar de los años y los años bisiestos, cuando corresponda. Esta configuración se aplica a todo el entorno y determina cómo se organizan y muestran los gastos, las previsiones y los resúmenes en todos los planes.

## Tipos de calendario compatibles

Apptio La planificación admite los siguientes tipos de calendario fiscal:

**Calendario gregoriano**

El calendario gregoriano es la estructura fiscal más común y consta de 12 meses consecutivos.

**Funcionalidades:**

- Admite tanto ejercicios fiscales tradicionales como no tradicionales
  - **Tradicional:** El año fiscal comienza en enero y termina en diciembre
  - **No tradicional:** el año fiscal comienza en cualquier mes seleccionado por el usuario
- Para los inicios que no sean en enero, elija si el año fiscal es:
  - **Definido por el período de inicio** (por ejemplo, FY2025 es julio de 2025-junio de 2026), o
  - **Definido por el período final** (por ejemplo, FY2025 es julio 2024-June2025 )
- Las etiquetas de período se pueden mostrar como:
  - **Mes** (enero, febrero, marzo), o
  - **Periodos** ( P1, P2, P3 )

Para **obtener más información**, consulte [*Configurar el calendario fiscal gregoriano.*](https://www.ibm.com/docs/en/apptio-platform/fcs/saas?topic=calendar-configure-gregorian "(se abre en una pestaña o una ventana nueva)")

**4-4-5 (4-5-4 / 5-4-4) Variante de calendario**

Los calendarios con variante 4-4-5 suelen utilizarse en organizaciones minoristas y manufactureras que requieren informes semanales coherentes.

**Características principales:**

- El año fiscal se divide en semanas en lugar de meses
- Los periodos siempre comienzan y terminan en el mismo día de la semana
- Organizado en cuartos con:
  - Dos períodos de cuatro semanas y un período de cinco semanas
- Estructuras compatibles:
  - **4-4-5**
  - **4-5-4**
  - **5-4-4**

Para **obtener más información**, consulte [*Configurar el calendario fiscal variante 4-4-5.*](https://www.ibm.com/docs/en/apptio-platform/fcs/saas?topic=calendar-configure-445-variant "(se abre en una pestaña o una ventana nueva)")

**Calendario de 13 períodos**

El calendario de 13 períodos divide el año fiscal en **13 períodos iguales**, normalmente de cuatro semanas cada uno.

**Por qué los clientes utilizan este calendario:**

- Garantiza que cada período tenga el mismo número de días
- Simplifica las comparaciones operativas y el análisis de tendencias
- Común en organizaciones dedicadas a la fabricación, la logística y las operaciones intensivas

Para **obtener más información**, consulte [*Configurar el calendario fiscal de 13 períodos.*](https://www.ibm.com/docs/en/apptio-platform/fcs/saas?topic=calendar-configure-13-period "(se abre en una pestaña o una ventana nueva)")

## Configurar calendario fiscal

Puede seleccionar un calendario fiscal al crear su entorno Apptio de planificación. El tipo de calendario seleccionado se aplica a todos los planes creados en el entorno y los usuarios no pueden cambiarlo directamente en la interfaz de usuario.

Para acceder a la configuración del calendario fiscal, vaya a **Configuración (icono de engranaje) →** **Configuración del calendario fiscal.**

**Modificación del calendario fiscal**

Para cambiar el calendario fiscal se necesita la ayuda del Apptio servicio de asistencia.

**Consideraciones importantes:**

- Los planes históricos siguen utilizando el calendario fiscal original
- **Los nuevos planes** creados después del cambio utilizan el **nuevo calendario.**
- **No** se admiten comparaciones de planes entre diferentes estructuras de calendario

Si necesita comparar los nuevos planes con los planes históricos, debe **volver a crear los planes históricos** utilizando la nueva configuración del calendario fiscal

Para solicitar un cambio: envíe una **solicitud de asistencia** a través de IBM Asistencia o póngase en contacto con su gestor de éxito del cliente
