---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Configuración de las preferencias de zona horaria"
breadcrumb:
  - "Cloudability Premium"
  - "Configuración"
source_path: "product/manage-profile.html"
images:
  - "images/Default_Cost_Metric_Config.png"
  - "images/share_and_subscribe_to_reports,_alerts,_and_emails_6.jpg"
  - "images/share_and_subscribe_to_reports,_alerts,_and_emails_7.jpg"
  - "images/share_and_subscribe_to_reports,_alerts,_and_emails_8.jpg"
  - "images/share_and_subscribe_to_reports,_alerts,_and_emails_9.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configuración de las preferencias de zona horaria

En Cloudability, se puede configurar o actualizar la zona horaria siguiendo estos pasos:

1. Haz clic en el icono **«Usuario»** situado en la esquina superior derecha y selecciona «**Gestionar perfil** ».
2. Haz clic en la pestaña **PREFERENCIAS** y configura la vista y la zona horaria predeterminadas en la sección **Vista y zona horaria**. La zona horaria se utilizará como tu zona horaria de Cloudability.

**Suscríbete a los resúmenes por correo electrónico**

Envía los datos más importantes que tengas en la nube a tu correo electrónico con la periodicidad que tú mismo definas.

Para configurar los correos electrónicos con el resumen de gastos en la nube:

1. Para definir con qué frecuencia deseas recibir los correos electrónicos, en la sección «Correos electrónicos con el resumen de gastos en la nube», selecciona una opción de la lista «FRECUENCIA DE ENVÍO»: Diariamente, Semanalmente, Mensualmente, Trimestralmente o Desactivado.
2. Selecciona la pestaña PREFERENCIAS.
3. Para definir con qué frecuencia deseas recibir tus correos electrónicos, en la sección «Correos electrónicos con el resumen de gastos en la nube », selecciona una opción de la lista «FRECUENCIA DE CORREOS ELECTRÓNICOS ».   

   ![Captura de pantalla del correo electrónico con el resumen de gastos en la nube](../../../../03-media/cloudability-premium/images/share_and_subscribe_to_reports,_alerts,_and_emails_6.jpg)

   Si seleccionas «Desactivado», dejarás de recibir los correos electrónicos con resúmenes.
4. Para configurar tu métrica de costes, haz clic en la lista que aparece debajo de «Métrica de costes para el correo» y selecciona una opción.   
    ![Captura de pantalla centrada en los costes](../../../../03-media/cloudability-premium/images/share_and_subscribe_to_reports,_alerts,_and_emails_7.jpg)   
    Cuando se tienen cuentas vinculadas dentro de una familia de cuentas de facturación consolidada, AWS incluye una tarifa combinada y una tarifa no combinada en los informes detallados de facturación. Si utilizas instancias reservadas, puede que te resulte más conveniente basar tus informes principalmente en el coste sin ajustar.   
      
    NOTA : Para utilizar los costes amortizados, la vista predeterminada no puede incluir un filtro basado en etiquetas. Las estimaciones reflejarán el «Coste (total)» si se selecciona «Coste (amortizado) ».
5. Para establecer tu presupuesto, haz clic en el menú desplegable situado debajo de «Presupuesto para correo» y selecciona una opción.   
    ![presupuesto para la captura de pantalla del correo electrónico](../../../../03-media/cloudability-premium/images/share_and_subscribe_to_reports,_alerts,_and_emails_8.jpg) El correo electrónico con el resumen de tus gastos en la nube tendrá un aspecto similar al siguiente: ![Captura de pantalla de éxito](../../../../03-media/cloudability-premium/images/share_and_subscribe_to_reports,_alerts,_and_emails_9.jpg)

**Opciones de entrega para empresas con retrasos**

*Se trata de una configuración personalizada para las cuentas que utilizan « Cloudability Enterprise» y debe ser activada por el equipo de « Cloudability Success».*

Si tus datos sufren retrasos constantes al proceder de AWS (debido al volumen de datos o al procesamiento previo a su envío a Cloudability), esto podría dar lugar a una situación en la que los usuarios reciban constantemente el nuevo correo electrónico «Data Delayed». Para evitarlo, hemos añadido una opción que permite a tus usuarios elegir cuándo recibir su correo. Pueden elegir entre recibir su correo con los datos más recientes (independientemente de su actualidad) u optar por esperar hasta que tengamos el último día completo. La primera es la opción predeterminada.

**Comprender las métricas**

- Gasto en lo que va de mes : comprueba cuánto has gastado este mes y compáralo con lo que gastaste en esta misma fecha del mes pasado.
- Fundada en... Gasto  mensual: consulta cuál es el gasto estimado para este mes, calculado a partir de una media móvil sobre un número de días definido por el usuario, y compáralo con el total del mes pasado.
- Gasto de ayer : esta cifra refleja el gasto estimado del día anterior a la recepción del correo electrónico.
- Coste : En esta sección del Daily Mail se enumerarán las cuentas de AWS y los servicios de AWS (como RDS, Elastic Compute Cloud, etc.) que han generado el mayor gasto en lo que va de mes.
- Horas de uso en lo que va de mes : comprueba cuántas horas de uso has acumulado este mes y compáralas con las horas de uso registradas en esta misma fecha del mes pasado.
- Horas de uso de ayer : esta cifra refleja el número de horas de uso que has generado durante el día anterior a la recepción del correo electrónico, y compara ese total con el del día anterior.
- Recuento de instancias en ejecución de ayer : comprueba en cuántas instancias se distribuyeron las horas de uso de ayer y compara ese total con el del día anterior.
- Uso : Consulta las cinco instancias más recientes que se han iniciado en tu cuenta.
- Configuración del correo electrónico : Analiza en profundidad los datos que te interesan gracias a una configuración que te permite filtrar por vista, excluir determinados tipos de gastos —como impuestos o gastos puntuales— y elegir si tus datos se calculan utilizando el coste combinado o el coste no combinado.

Nota: Si los datos que te proporciona tu proveedor de servicios en la nube están incompletos debido a los horarios de actualización de los datos, es posible que se retrase el envío del correo electrónico diario con el desglose de tus gastos en la nube. Por ejemplo, si no dispones de datos completos hasta el final del día anterior (UTC), puedes esperar que el correo electrónico se envíe alrededor de las 10:00 h, hora del Pacífico, para que se puedan recibir y procesar los datos completos. De este modo se minimizan los casos en los que el «gasto estimado de ayer» se registre por debajo de lo real debido a que los datos facilitados por el proveedor de servicios en la nube para ese periodo sean incompletos.

Configuración de las métricas de costes predeterminadas para tu organización

Cada módulo de « Cloudability » (por ejemplo: «True Cost Explorer», «Rightsizing», etc.) admite un conjunto específico de métricas de costes, como «Coste (total)», «Coste (de catálogo)», «Coste (amortizado)», etc. Aunque «Coste (total)» es la métrica de coste predeterminada para estos módulos, un usuario administrador puede modificarla y establecer una métrica de coste predeterminada diferente accediendo a la página «**Gestionar perfil > Configuración de la organización** ».

![Captura de pantalla de la configuración predeterminada de la métrica de costes](../../../../03-media/cloudability-premium/images/Default_Cost_Metric_Config.png)

Esta pantalla mostraría todos los módulos de Cloudability que admiten más de una métrica de costes, junto con un menú desplegable que contiene la lista de métricas que admite actualmente cada módulo. Como usuario administrador, puedes seleccionar la métrica de costes que prefieras para cada uno de los módulos y hacer clic en el botón **«Guardar métricas de costes predeterminadas»** situado en la parte inferior; de este modo, los cambios se aplicarán a todos los usuarios de tu organización de Cloudability.
