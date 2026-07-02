---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Configurar un conector REST d Datalink"
breadcrumb:
  - "Planning"
  - "Las API"
source_path: "it-planning/planning/config-data-rest.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar un conector REST d Datalink

[El conector REST](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-rest-service-connector "(se abre en una pestaña o una ventana nueva)") de Datalink le permite integrar Apptio Planning con Apptio Costing, u otros sistemas externos, mediante el intercambio seguro de datos a través de API REST.

1. **Tipo de conector**

   Seleccionar: **Servicio REST / Servicio REST 2.0**
2. **Destino**

   Antes de configurar la conexión API, defina dónde se almacenarán los datos en Apptio :
   - Vaya a la pestaña **« Apptio Destination»** (Destino de la aplicación).
   - Configurar:
     - **Nombre del destino:** por ejemplo, Nuevo destino 1
     - **Aplicación:** seleccione la aplicación (por ejemplo, Apptio Costing)
     - **Dominio:** por ejemplo, acme.apptio.com
     - **Proyecto:** seleccione el proyecto (por ejemplo, Transparencia de costes)
     - **Categoría:** establecido en REST
   - Seleccione el **período de tiempo** (mes actual, mes anterior o calendario personalizado).
3. **Método HTTP**

   Puede ser **GET** o **POST**, dependiendo del punto final al que estés llamando:
   - **GET** : para recuperar datos (solo lectura).
   - **POST** : para exportar datos (generar un archivo CSV).
4. **REST URL**

   En el campo **REST URL**, introduzca: [https://app.apptio.com](https://app.apptio.com/ "(se abre en una pestaña o una ventana nueva)")

   Nota: Asegúrese de que URL coincida con su región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ).

   En el campo **Introducir ruta de recurso URL**, añada el punto final de la documentación, por ejemplo:

   `planning/api/v1/plans/<planId>/expenses/export`

   **Descripción:** Este punto final exporta datos de gastos para un plan específico en formato CSV.
5. **Autenticación**

   **Tipo:** Seleccione el adecuado según [el conector de servicio REST](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-rest-service-connector "(se abre en una pestaña o una ventana nueva)") de Datalink

   Especifique:
   - **Clave de puerta principal** (clave pública)
   - **Secreto de la puerta principal** (clave secreta)

   **¿** Comprobar si se necesita actualizar el token? → **Sí** (permite múltiples ejecuciones sin necesidad de volver a autenticarse).
6. **Cabeceras**

   Añadir un encabezado:

   **Clave:** apptio-entorno-actual

   **Valor:** <valor del entorno, por ejemplo, GUID>
7. **Parámetros de consulta**

   Añade el parámetro requerido. Consulte la documentación de la API:

   **Clave:** tipo

   **Valor:** por ejemplo, RESUMEN

   Se pueden añadir otros parámetros opcionales (por ejemplo, departmentCode, columnDelimiter ) en la misma sección.
8. **Paginación**

   **Configuración:** Sin paginación (u otra basada en [el conector de servicio REST](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-rest-service-connector "(se abre en una pestaña o una ventana nueva)") Datalink ).
9. **Guardar y probar**

   Haga clic en **«Probar API»** para verificar la configuración.

   Guarde la conexión y configure una programación si desea automatizar la exportación.
