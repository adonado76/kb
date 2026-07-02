---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Definir las imputaciones del modelo de costes"
breadcrumb: []
source_path: "boit/define-cost-model1.html"
images:
  - "resources/images/boit_images/boit_define-cost-model.jpg"
  - "resources/images/boit_images/boit_define-cost-model2.jpg"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Definir las imputaciones del modelo de costes

Realice este paso si aún no ha asignado valor al objeto del modelo de Servicios Empresariales en el modelo de Costes.

![img](../../../../03-media/apptio-billing/resources/images/boit_images/boit_define-cost-model.jpg)

Para definir las asignaciones del modelo de costes, utilice Transparencia de costes para asignar sus costes.

Para utilizar tarifas basadas en costes, siga los siguientes pasos para proporcionar información de costes al modelo de tarifas.

1. Si aún no ha añadido datos al Feed de Consumo, consulte [Añadir datos de consumo para cálculos de Precio x Cantidad](add-consumption-data.html "Utilice los datos de consumo cuando desee cobrar a las unidades de negocio en función de su consumo de servicios en lugar de asignaciones de costes basadas en factores como el número de empleados. Si no se conocen datos de consumo adicionales, utilice una lista de los ID de servicio, que puede facilitarse adjuntando los datos brutos de la biblioteca de servicios. No añada la tabla de la propia biblioteca de servicios, pero sí los datos añadidos a la biblioteca de servicios."). Si no tiene intención de proporcionar cantidades, adjunte una lista de sus ID de servicio siguiendo los mismos pasos.
2. En el **Explorador de proyectos**, haga clic en el paso **Modelo** de la tabla Servicios empresariales.
3. Asegúrese de que la métrica **Coste** está seleccionada.
4. Añada una nueva asignación haciendo clic en **Añadir asignación**.
5. Establezca la asignación para asignar la métrica Coste a los Servicios Empresariales utilizando el Valor Ponderado, distribuyendo a través de una relación de datos basada en el ID de Servicio.

   ![img](../../../../03-media/apptio-billing/resources/images/boit_images/boit_define-cost-model2.jpg)
6. Consulte [Definir las asignaciones del modelo de tarificación](define-charge-price.html) para obtener instrucciones sobre cómo completar la tarificación basada en costes.
