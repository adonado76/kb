---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Notificación de vencimiento del contrato"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso del informe"
  - "Cobro a proveedores"
source_path: "cost-transparency/vi_content/report-contract-expiration-notification.html"
images:
  - "resources/images/vi_images/vi/alertsicon.jpg"
  - "resources/images/vi_images/vi/contract-expiration-notification_kpis.jpg"
  - "resources/images/vi_images/vi/export.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Notificación de vencimiento del contrato

◆ Se aplica a: Vendor Insights en TBM Studio 12.8 y posteriores ( v107 )

Con el crecimiento de las TI aumenta el número de contratos con proveedores, gastos prenegociados, renovaciones y vencimientos de contratos. Los contratos con proveedores requieren una atención constante para evitar la renovación automática accidental y los aumentos de precio inesperados. Además, es difícil mantener informados a los interesados sobre los contratos que expiran para que puedan tomar decisiones informadas sobre renovaciones y negociaciones. El informe de notificación de vencimiento de contrato en Vendor Insights está diseñado para proporcionar dicha información y facilitar la gestión de contratos.

**NOTA** : El informe de notificación de vencimiento de contrato puede adjuntarse a las alertas por correo electrónico que se generan antes del vencimiento de los contratos, en función de los umbrales definidos por el usuario. Para más información, consulte [Alertas de expiración de contratos de proveedores](alerts.html).

Este informe está diseñado para las funciones, como las que se enumeran a continuación, que deciden si dejar expirar los contratos, renegociar los términos y proporcionar información como partes interesadas:

- Propietarios de contratos
- Gestores de proveedores
- Aplicaciones Propietarios
- Servicios Propietarios

Casos de uso

- ¿Qué contratos expiran y cuándo?
- ¿Cómo puedo saber qué contratos necesitan atención sin tener que consultar diariamente el informe de vencimiento de contratos?
- Se ha renovado o dejado expirar un contrato. ¿Requiere seguimiento?
- ¿Cómo puedo asegurarme de que todas las partes interesadas están al tanto de los cambios contractuales?
- ¿Cuáles son mis contratos críticos y qué servicios soportan?

**Visualizar el informe de aviso de vencimiento de contrato**

El informe de notificación de vencimiento de contrato puede abrirse a partir de un correo electrónico generado cuando se alcanza un umbral de vencimiento de contrato. También puede navegar hasta el informe en Vendor Insights :

En el menú Aplicación, seleccione  Vendor Insights .

1. Vaya a Recopilaciones de informes > Contratos.
2. En la barra de la parte superior de la página, seleccione Aviso de vencimiento de contrato.
3. Opcionalmente, filtre el informe utilizando las opciones de la parte superior del informe.
4. Para exportar o enviar por correo electrónico sus datos, seleccione Exportar ( ![imagen](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/export.jpg) ) en la parte superior derecha de la página y seleccione un formato de exportación.
5. Para crear una alerta que le notifique si un contrato va a expirar, seleccione Alerta ( ![imagen](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/alertsicon.jpg) ) en la parte superior derecha de la página. Para obtener más información, consulte [Crear alertas para contratos de proveedores que expiran](alerts.html).
6. Seleccione cualquier elemento de la columna Título del contrato de la tabla para abrir el informe Detalle del contrato correspondiente a ese contrato. Consulte [el informe Detalle del contrato](report-contract-detail.html).

El informe contiene los siguientes elementos:

![imagen](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/contract-expiration-notification_kpis.jpg)

**(1) Recogida de informes**

Esta colección de informes proporciona los detalles que necesita para analizar el gasto de su cartera de proveedores en función del tipo de proveedor y del tiempo:

- [Informe resumido del contrato](report-contract-summary.html)
- [Informe de vencimiento de contrato (TBM Studio 12.6 y posteriores)](report-contract-expiration-12-6.html)
- [Informe de contrato a aplicaciones](report-contract-applications.html)
- Notificación de vencimiento de contrato (descrita en este artículo)

**(2) Cortadoras**

Los siguientes filtros globales están disponibles en esta colección de informes:

- **Gestor de proveedores** - Filtre por una persona específica para poder ver el impacto de los proveedores gestionados por esa persona.
- **Nombre de proveedor normalizado** - Filtrar por un proveedor específico.

**(3) Filtros**

Utilice los siguientes filtros locales para limitar los contratos que se muestran en la tabla Detalles **del vencimiento del contrato** :

- Renovación **automática** : filtre la columna **Renovación** automática para ver los contratos configurados para renovarse automáticamente (configurados como **Sí** ) frente a los contratos que no se renovarán automáticamente (configurados como **No** ). Elimine el filtro para ver todos los contratos.
- **Criticidad del** contrato - Filtre la columna **Criticidad del contrato** para ver los contratos etiquetados con diferentes niveles de criticidad (como Misión crítica, Esencial para el negocio, Discrecional o Estratégico). Elimine el filtro para mostrar todos los contratos independientemente de su criticidad.
- **Propietario** del contrato: filtre la columna **Propietario del contrato** para ver los contratos por propietario. Elimine el filtro para mostrar todos los contratos independientemente del propietario.
- **Tipo** de proveedor: filtre la columna **Tipo de proveedor** para ver los contratos en función del tipo de proveedor (por ejemplo, si el contrato es de un proveedor con un tipo de proveedor preferente o estratégico). Elimine el filtro para mostrar todos los contratos independientemente del tipo de proveedor.

**(3) por fecha de expiración**

Utilice esta pestaña para ver los datos del contrato en función de la fecha de finalización del mismo. Los contratos se ordenan por fecha de vencimiento, enumerando primero los que vencen hoy. La tabla ofrece una vista rápida de la información más crítica sobre los contratos, incluida la fecha de finalización, el propietario, los días que faltan para el vencimiento, los días de notificación y el importe del contrato.

Para obtener más información sobre un contrato concreto, haga clic en la columna Título del contrato para abrir el [informe Detalle del contrato](report-contract-detail.html).

**(4) por nombre de proveedor**

Esta vista muestra los mismos datos que la pestaña **Fecha de caducidad**, excepto que al hacer clic en esta pestaña, la columna Nombre de **proveedor** se desplaza a la columna situada más a la izquierda y se ordena por Nombre de proveedor de forma ascendente.

**(5) Icono de alerta**

Haga clic en este icono para abrir la página **Alertas de umbral**, que enumera todas sus alertas y su estado. En esa página, puede hacer clic en cualquier alerta para abrir la página **Configuración de umbrales** y editar los umbrales. Para obtener más información sobre la configuración de alertas, consulte [Crear alertas para contratos de proveedor que expiran](alerts.html).
