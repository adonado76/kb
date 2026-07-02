---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Descripción general de la planificación de API REST"
breadcrumb:
  - "Planning"
  - "Las API"
source_path: "it-planning/planning/plan-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Descripción general de la planificación de API REST

**Las API REST de planificación** de « Apptio » proporcionan un acceso seguro y programático a los planes, los datos de planificación, los metadatos y los elementos relacionados dentro de « Apptio Planning». Estas API están diseñadas para facilitar la automatización y las integraciones de sistemas en casos de uso relacionados con la planificación, la previsión, el análisis, la gobernanza y el intercambio de datos.

**Mediante las API de Planning, los usuarios pueden:**

- Descubre los planes disponibles en el entorno de planificación de Apptio
- Exportar e importar datos de gastos del plan mediante archivos de « CSV »
- Obtener resultados analíticos, como análisis de varianza y el estado del plan
- Gestionar y validar los permisos de los usuarios a nivel de plan o a nivel global
- Integrar la importación de datos reales en la gestión del gasto
- Acceder a los metadatos de diseño utilizados para estructurar los datos de planificación

Todas las API siguen los principios REST, utilizan métodos estándar de la Interfaz de Programación de Aplicaciones ( HTTP ) e intercambian datos a través de respuestas JSON y archivos de la Interfaz de Programación de Aplicaciones ( CSV ). Las API de exportación devuelven archivos « CSV » descargables, mientras que las API de importación aceptan archivos « CSV » y devuelven resultados de validación detallados para facilitar integraciones a gran escala y repetibles.

## Requisitos previos

Para utilizar las API del plan, debe:

1. [Crea claves API](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-api-overview-api-keys-faq "(se abre en una pestaña o una ventana nueva)") para el entorno desde la administración de Apptio.
2. [Generar un token abierto de Apptio](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-enhanced-access-administration-api-authentication-via-api-keys "(se abre en una pestaña o una ventana nueva)") utilizando claves API.
3. [Obtén el **identificador de entorno**](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=apis-how-access-r12-api-through-enhanced-access-administration-via-curl#HowtoaccessR12APIthroughEnhancedAccessAdministrationviacurl__GetaenvIDuseopentoken__title__1 "(se abre en una pestaña o una ventana nueva)"), que es obligatorio en todos los encabezados de la API.

Nota: La cuenta de usuario utilizada para generar claves API debe tener privilegios **de «Responsable del proceso presupuestario»** o **de «Administrador»** para poder acceder a todas las API disponibles. Si se utiliza una cuenta de servicio para crear claves de API, póngase en contacto con el servicio de asistencia de Apptio para asegurarse de que se han concedido los permisos necesarios a dicha cuenta.

**Encabezados de autenticación**

- Todas las solicitudes de la API requieren los siguientes encabezados:
  - apptio-opentoken
  - Token de autenticación generado mediante claves API
- apptio-entorno-actual
  - ID del entorno que identifica el entorno de planificación de Apptio

  Nota: Las solicitudes que no incluyan estos encabezados o que utilicen credenciales no válidas darán lugar a errores de autorización o de acceso.

**Puntos finales regionales**

- Las solicitudes de API deben enviarse al punto de conexión regional correspondiente a tu implementación de Apptio (por ejemplo, app.apptio.com, app-eu.apptio.com o app-au.apptio.com ).
- Asegúrate de que la base URL coincida con tu región antes de enviar solicitudes.

- **[API](../../it-planning/planning/plan-data-api.html)**  
   de planes: **Las API de planes** te permiten consultar los planes disponibles y gestionar los datos de gastos a nivel de plan mediante operaciones de importación y exportación. Estas API constituyen la base de la mayoría de las integraciones de datos de planificación con « Apptio Planning».
- **[API](../../it-planning/planning/variance-analysis-api.html)**  
   **de análisis de desviaciones Las API de análisis de desviaciones** permiten exportar de forma programática los datos de análisis de desviaciones de un plan concreto.
- **[API](../../it-planning/planning/pln-status-api.html)**  
   **de estado de los planes Las API de estado de los planes** te permiten exportar información sobre la aprobación y el estado de los planes. Estas API se utilizan habitualmente con fines de gobernanza, auditoría y elaboración de informes para conocer el ciclo de vida y el estado de aprobación de los planes.
- **[API](../../it-planning/planning/spnd-mgmt-api.html)**  
   **de gestión** del gasto Las API de gestión del gasto permiten exportar e importar datos reales que se utilizan en la planificación y el análisis financiero.
- **[API](../../it-planning/planning/user-perm-api.html)**  
   **de permisos de usuario Las API de permisos de usuario** permiten exportar e importar datos de permisos globales y a nivel de plan. Estas API permiten la gestión automatizada del acceso y la validación de los permisos de los usuarios en « Apptio Planning».
- **[API](../../it-planning/planning/chng-hist-api.html)**  
   **de historial de cambios** Las API de historial de cambios le permiten exportar datos del registro de eventos que recogen los cambios realizados en Apptio Planning.Change. Los datos del historial se exportan como un archivo CSV y pueden utilizarse para auditar las modificaciones de un plan específico, incluyendo **qué cambios se realizaron**, **quién los realizó** y **cuándo se produjeron**.
- **[API](../../it-planning/planning/tab-lay-api.html)**  
   de diseños de tablas: **La API de diseños de tablas** permite acceder a los metadatos de diseño que se utilizan para mostrar y organizar los datos de gastos en la planificación de « Apptio ». Los esquemas definen cómo se estructuran y presentan los datos del plan en los distintos tipos de gastos.
