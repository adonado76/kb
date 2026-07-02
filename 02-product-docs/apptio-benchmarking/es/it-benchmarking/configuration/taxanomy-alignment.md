---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Taxonomía y alineación de versiones"
breadcrumb:
  - "Benchmarking"
  - "Guía de configuración"
source_path: "it-benchmarking/configuration/taxanomy-alignment.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Taxonomía y alineación de versiones

El benchmarking utiliza estructuras TBM para interpretar sus datos. Si el modelo de su proyecto de cálculo de costes no se ajusta a la versión « ATUM » (Coste total de propiedad) de su benchmarking interactivo, las métricas serán inexactas e incompletas.

**Seleccione la versión de TBM ( ATUM**  
) En la configuración de Interactive Benchmarking, se puede elegir la versión de TBM ( ATUM ).

![Configuración de Interactive Benchmarking: selección de la versión de ATUM](../../resources/images/it%20benchmarking_images/benchmarking-atum.png)

  
Directrices

- Coincida con la versión utilizada en su proyecto de cálculo de costes.
- Si se encuentra en medio de la migración, elija la versión de destino y termine primero la parte de cálculo de costes
- Evita cambiar de versión sin pensarlo bien. Considérelo como un cambio estructural con un año de vigencia claro.

  
La versión seleccionada controla:

- ¿Qué grupos de costes, torres de recursos y subtorres existen?
- Cómo se agrupan y etiquetan las métricas de infraestructura
- ¿Qué definiciones de referencia hay disponibles?

**Valide la alineación de su**   
modelo TBM Una vez seleccionada una versión en Interactive Benchmarking:

- Confirme que su modelo de cálculo de costes utiliza la misma versión con los mismos grupos de costes y torres de recursos.
- Identifique estructuras personalizadas o fusionadas, por ejemplo:
  - Categoría local «Centro de datos» que combina varias torres de recursos estándar.
  - Grupos de costes personalizados que combinan mano de obra y servicios externos.
  - Subtorres adicionales no presentes en la taxonomía estándar de TBM.

  
Documente cómo va a asignar esas estructuras locales a las estructuras de referencia estándar.   
Enfoques típicos:

- Cree tablas de asignación en Costing que asignen códigos locales a grupos de costes y torres de recursos estándar.
- Cuando no se pueda asignar 1-to-1, decida si:
  - Localice la torre estándar más cercana y añada una anotación.
  - Excluir del ámbito de la evaluación comparativa.  
  Si omite este paso, pasará meses discutiendo por qué su estructura no se parece a la de sus compañeros.
