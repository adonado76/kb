---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Ayuda complementaria para la acreditación de la funcionalidad de compromiso"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Configurar la funcionalidad de optimización"
source_path: "product/supplementary_credentialing_help_for_commitment_functionality.html"
images:
  - "images/details.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Ayuda complementaria para la acreditación de la funcionalidad de compromiso

Nota: Nota: La funcionalidad de gestión de compromisos solo admite vistas basadas en proveedores y cuentas. Al seleccionar una vista cuya lógica se basa en asignaciones comerciales y etiquetas más allá del proveedor y la cuenta, la página dará un error. Este comportamiento se debe a las siguientes razones: - Las métricas de rendimiento a menudo no se pueden calcular de forma determinista a través de diversas métricas y etiquetas empresariales. Si mostráramos estas pantallas sin estos datos, la página de la cartera carecería de la mayor parte de la información de interés. - Es recomendable que los compromisos se gestionen de forma centralizada. Cuando se activa el uso compartido, o cuando el tipo de compromiso solo se encuentra en el nivel de la cuenta del pagador, resulta imposible determinar el rendimiento en los mapeos/etiquetas empresariales de nivel inferior a cambio de que la organización obtenga mejores resultados. Los mapeos de etiquetas y los mapeos empresariales contienen reglas que restringen al usuario a solo una parte de una cuenta. Para proteger la privacidad de los clientes, solo permitimos que los usuarios con los permisos adecuados vean las páginas de compromisos, ya que los compromisos se refieren a cuentas completas. Se trata de una limitación relacionada con los datos y su interacción con el filtrado de vistas.

Nota:

Debe tener derechos de administrador en Cloudability para ver o habilitar las credenciales. Si no tienes derechos de administrador, ponte en contacto con el administrador principal de Cloudability de tu organización para obtener ayuda.

## Gestión del compromiso de acreditación para AWS

**Generar recomendaciones para AWS EC2**

La suite de productos « Cloudability » permite optimizar el uso de las instancias reservadas convertibles (CRI) de AWS EC2, lo que incluye la supervisión de costes, la generación de informes y recomendaciones, entre ellas las relativas al intercambio de CRI. La siguiente información trata sobre cómo habilitar y utilizar las recomendaciones de intercambio de instancias reservadas convertibles.

**Verificar permisos**

Antes de empezar, asegúrate de que tienes habilitado el permiso adecuado **ec2:GetReservedInstancesExchangeQuote**. Este permiso es necesario para que Cloudability genere recomendaciones de intercambio convertibles para CRI parciales o totales por adelantado.

Para comprobar el estado del permiso requerido:

1. Vaya a **Configuración > Credenciales del proveedor**.
2. En la **AWS** pestaña, seleccione ![icono de detalles de la imagen](../../../../03-media/cloudability-premium/images/details.jpg) para ver los permisos de cualquier cuenta relevante.

   Las cuentas que no tienen habilitados los permisos necesarios se identifican con cualquier símbolo que no sea una marca de verificación verde junto a la línea « **ec2:GetReservedInstancesExchangeQuote** » (Permisos de acceso de la aplicación).

   Si el permiso necesario no está habilitado, puedes habilitarlo volviendo a generar una plantilla de CloudFormation y aplicándola a las cuentas correspondientes. Para obtener más información, consulta [Cloudability Gestionar las credenciales de AWS](../admin/manage-aws-credentials.html).

   Nota: Una vez que la plantilla CloudFormation haya sido aplicada y verificada por la plataforma Cloudability, las recomendaciones tardarán aproximadamente 1 hora en aparecer.

Ver el inventario del plan de ahorro propio

Iniciación

Antes de comenzar, asegúrese de que se hayan habilitado los permisos necesarios, que proporcionan acceso a la funcionalidad del Plan de Ahorros.

La acreditación debe ser revisada y realizada por un usuario con derechos de administrador para su cuenta de Cloudability. Si no tienes acceso de administrador o no estás seguro de si tienes derechos de administrador, consulta con el administrador principal de Cloudability de tu organización.

Para comprobar el estado de las credenciales necesarias:

1. Vaya a Configuración > Credenciales del proveedor.

   En la vista de cuentas principales de las pestañas « AWS » (Cuentas de ahorro) y « Azure » (Cuentas de ahorro), cualquier pagador principal o cuenta vinculada que posea ahorros (o que usted tenga intención de utilizar para adquirir ahorros) tiene un cuadro verde con un indicador de estado de verificación blanco en «Advanced Features» (Funciones avanzadas).
2. Si una cuenta presenta cualquier indicador de estado distinto del recuadro verde con una marca de verificación blanca, selecciona ![icono de estado](../../../../03-media/cloudability-premium/images/details.jpg) para comprobar las credenciales individuales. x
3. En la ventana Detalles de credenciales, si el permiso savings plans:DescribeSavingsPlans en la pestaña Reservaciones muestra una x roja, es necesario actualizarlo (regenerando y aplicando plantillas de CloudFormation ) antes de poder ver el inventario de sus planes de ahorro.

## Gestión del compromiso de acreditación para Azure

**Valida el acceso a tu cuenta**

Las recomendaciones de compromiso generan recomendaciones de compromiso basadas en los recursos de Azure mediante el acceso a la API en la nube de Azure. Dado que Azure Cloud limita el acceso a la API a las cuentas empresariales, debe asegurarse de lo siguiente:

- Tu cuenta está cubierta por un acuerdo empresarial
- Tiene acceso al portal empresarial Azure

Si no tiene una cuenta empresarial, acceda al portal empresarial Azure o, si no está seguro, póngase en contacto con su representante de cuentas de Azure para obtener ayuda.

**Habilita tus credenciales de Azure**

1. Para comprobar el estado de tus credenciales de Azure, ve a **Configuración > Credenciales de proveedor**.
2. Seleccione la pestaña **AZURE**.
3. Asegúrate de que **los informes de facturación** y **las funciones avanzadas** estén habilitados para la cuenta principal (de inscripción). Deberías ver dos casillas verdes en la fila de la cuenta principal.

Nota:

- Aunque lo mejor es tener habilitados **los informes de facturación** y **las funciones avanzadas** tanto para las cuentas maestras (inscripción) como para las vinculadas (suscripción), solo es necesario habilitar estos permisos para la cuenta maestra a fin de utilizar las recomendaciones de compromiso para Azure.

- Aunque lo mejor es tener habilitados **los informes de facturación** y **las funciones avanzadas** tanto para las cuentas maestras (inscripción) como para las vinculadas (suscripción), solo es necesario habilitar estos permisos para la cuenta maestra a fin de utilizar las recomendaciones de compromiso para Azure.

**Tema principal:** [Configurar la funcionalidad de optimización](../product/configure_optimization_functionality.html)
