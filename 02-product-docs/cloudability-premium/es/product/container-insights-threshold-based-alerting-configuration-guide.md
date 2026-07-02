---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Container Insights: Guía de configuración de alertas basadas en umbrales"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Imputación de los costes de los contenedores"
source_path: "product/container-insights-threshold-based-alerting-configuration-guide.html"
images:
  - "images/threshold-based_alerting1.jpg"
  - "images/threshold-based_alerting2.jpg"
  - "images/threshold-based_alerting3.jpg"
  - "images/threshold-based_alerting4.jpg"
  - "images/threshold-based_alerting5.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Container Insights: Guía de configuración de alertas basadas en umbrales

Descripción general

Container Insights admite ahora alertas basadas en umbrales que pueden configurarse de dos maneras:

1. Directamente a través de los widgets del salpicadero

   ![Icono Notas](../../../../03-media/cloudability-premium/images/threshold-based_alerting1.jpg)
2. A través de la pestaña dedicada a las Alertas

   ![Icono Notas](../../../../03-media/cloudability-premium/images/threshold-based_alerting2.jpg)

Métodos de configuración

Método 1: Configurar a través de los widgets del salpicadero

1. Navegue hasta el panel de control de Container Insights
2. Haga clic en la elipsis horizontal (⋯) de cualquier widget
3. Seleccione Crear alerta en el menú desplegable
4. En la plantilla Configuración de alertas:
   - Introduzca el nombre y la descripción de la alerta
   - Establecer valores de consulta
   - Definir condiciones de activación y filtrado
   - Asignar usuarios para las notificaciones
   - Guarde la configuración

     ![Icono Notas](../../../../03-media/cloudability-premium/images/threshold-based_alerting3.jpg)

Método 2: Configurar a través de la página de alertas

1. Vaya a la página de información sobre contenedores
2. Haga clic en la pestaña Alertas (situada junto a las vistas "Cuadro de mandos" y "Mapa de árbol")
3. Seleccione la subpestaña Configuración y, a continuación, Nueva alerta en el extremo derecho
4. En la plantilla Configuración de alertas:
   - Introduzca el nombre y la descripción de la alerta
   - Establecer valores de consulta
   - Definir condiciones de activación y filtrado
   - Asignar usuarios para las notificaciones
   - Guarde la configuración

Gestión de alertas

- Ver todas las alertas configuradas en la pestaña Alertas
- Acceda a la subpágina Alertas configuradas para ver la lista completa
- Editar o eliminar las alertas existentes según sea necesario
- Supervisar el estado y el historial de las alertas

  ![Icono Notas](../../../../03-media/cloudability-premium/images/threshold-based_alerting4.jpg)

Notas importantes

- El número máximo de alertas por organización es de 100
- El correo electrónico es actualmente el único canal de notificación admitido
- Todos los usuarios pueden crear alertas para sí mismos
- Cloudability Los administradores pueden asignar alertas a otros usuarios

Si tiene preguntas o necesita ayuda adicional, póngase en contacto con nuestro equipo de asistencia.

![Icono Notas](../../../../03-media/cloudability-premium/images/threshold-based_alerting5.jpg)p

**Tema principal:** [Imputación de costes de contenedores](../product/k8s-cost-allocation.html)
