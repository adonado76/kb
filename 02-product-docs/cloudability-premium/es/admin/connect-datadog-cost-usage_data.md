---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conectarse a Datadog - Datos sobre costes y uso"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectarse a Datadog - Datos de utilización"
source_path: "admin/connect-datadog-cost-usage_data.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectarse a Datadog - Datos sobre costes y uso

Puede conectar su cuenta de Datadog a Cloudability para habilitar la ingestión de datos de costes y uso. Si ya ha acreditado una cuenta de Datadog para obtener datos de utilización para nuestra función de optimización, puede editar esta cuenta existente para obtener también datos de costes. Simplemente seleccione coste en la sección de informes de la página de credenciales y añada la clave API y la clave de aplicación.

Nota: Pueden pasar hasta 24 horas antes de que los datos iniciales sobre costes y consumo aparezcan en Cloudability. Durante este tiempo, un mensaje indica que el proceso aún no ha finalizado.

Resumen de la integración

Datadog nos permite volver atrás y extraer los datos de costes de los últimos 15 meses. Si la factura está finalizada, verá los costes imputados a primeros de mes. Si la factura no se ha finalizado, verá los costes diarios asociados a los productos y servicios que ha adquirido. Esto significa que, por lo general, verá los datos diarios del mes en curso y del último mes, hasta la fecha en que se haya finalizado la factura.

Nuestras integraciones respetan los principios del mínimo privilegio, por lo que hemos diseñado los conectores para que funcionen con el mínimo nivel de permiso necesario para que podamos extraer los datos pertinentes en Cloudability.

Nota: Si adquiere Datadog a través del mercado de un proveedor de servicios en la nube y añade datos de costes y uso para Datadog con esta integración, verá los costes mostrados dos veces en los informes de Cloudability. Por ejemplo, si compraste Datadog a través del mercado AWS, tendrías:

Las partidas de alto nivel por mes para AWS

Las partidas con los costes detallados de Datadog y « AWS Marketplace» como «Vendedor»

Tendrás que configurar filtros o vistas para ocultar tus costes del Mercado. Los costes del mercado están excluidos de la facturación.

Antes de empezar

Antes de empezar, asegúrate de lo siguiente:

- Usted es administrador de Cloudability.
- Tienes permisos de administrador en la consola Datadog.

  - Recomendamos **que** un administrador cree un nuevo usuario y cambie su categoría **de** administrador **a** solo lectura para los fines de esta integración.
  - Si usted es un administrador actual de Datadog y está configurando esta integración, le recomendamos que cree un nuevo inicio de sesión mediante la creación de un nuevo usuario, utilizando una dirección de correo electrónico diferente (distinta a la utilizada para su función de administrador). Cambie el nivel de este usuario a **usuario** de solo lectura.

Pasos para la integración

Recomendamos que un administrador cree un nuevo usuario y lo cambie de usuario administrador a usuario de sólo lectura a efectos de esta integración.

Si usted es un administrador actual de Datadog y está configurando esta integración, le recomendamos que cree un nuevo inicio de sesión mediante la creación de un nuevo usuario, utilizando una dirección de correo electrónico diferente (distinta a la utilizada para su función de administrador). Degradar este usuario a un usuario de sólo lectura.

Crea nuevas claves en Datadog

En la consola de Datadog :

1. Invite a un nuevo miembro como usuario administrador de la integración.

   Consulte la [sección Roles de usuario y permisos de Datadog](https://docs.datadoghq.com/account_management/users/ "(se abre en una pestaña o una ventana nueva)") para obtener más información.
2. Inicie sesión como usuario administrador recién creado.
3. Vaya a Integraciones > APIs > Nueva clave API.
4. Cree una nueva clave API.
5. Vaya a la sección Nueva clave de aplicación y cree una nueva clave de aplicación.

Añade tus claves Datadog a Cloudability

1. En Cloudability, vaya a Configuración > Credenciales de proveedor.
2. Seleccione la pestaña Datadog.
3. Seleccione «Sí, estoy listo» para confirmar que tiene sus claves de Datadog.
4. Copie y pegue la nueva clave API y la clave de aplicación en el campo correspondiente.
5. Introduzca su límite de API en Límite de tarifa. a 300, que es el límite de velocidad por defecto.

   Nota: Las etiquetas aún no son compatibles con Datadog

   En caso de que necesite listas blancas de IP, los siguientes rangos de IP le darán acceso a Cloudability :

   - 185.115.88.0/22
   - 103.195.128.0/22

**Tema principal:** [Conectar Datadog - Datos de utilización](../admin/connect-datadog-premium.html)
