---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "«Primeros 60 minutos» con Benchmarking"
breadcrumb:
  - "Benchmarking"
  - "Inicio rápido"
source_path: "it-benchmarking/quick-start/sixty-minutes.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# «Primeros 60 minutos» con Benchmarking

La siguiente guía paso a paso da por sentado que usted es el administrador, TBMA o analista responsable de la configuración inicial.

1. **Abre Benchmarking interactivo, identifica tu punto de partida** y selecciona **Ajustes** > **Configuración.**

   ![Configuración de referencia](../../resources/images/it%20benchmarking_images/config-settings.png)

     
   Deberías poder responder: ¿Dónde cambio la configuración?
2. **Introducir o validar los datos del perfil organizativo**  
   . Los datos del perfil organizativo son necesarios para la industria y muchas métricas de TI OpEx. No se extrae de Costing. Se introduce manualmente.   
   Entradas:
   - Organización (anual) Ingresos
   - Organización (anual) OpEx
   - Número de empleados como FTE (equivalente a tiempo completo) para la organización apoyada  
   Directrices
   - Utilice valores que se ajusten al alcance de los costes de TI. Si la organización de TI presta apoyo exclusivamente a Norteamérica, no utilice los ingresos globales.
   - Utilice el último ejercicio fiscal completado en lugar de un año previsto o un gasto anualizado.
   - Si tiene varias entidades jurídicas pero una única función/organización de TI, adapte su perfil al alcance de los costes de TI.   
     Puede perfeccionarlo más adelante. El primer objetivo es que la dirección sea correcta, por lo que se aceptan estimaciones aproximadas.
3. **Proporcione datos anuales sobre costes de TI, volúmenes y ETC.** Tiene dos opciones:  
   - **PATH 1** Conectarse a Costing (recomendado)   
     En la configuración de Benchmarking interactivo:
     - Integre con la plataforma de cálculo de costes seleccionando «Transparencia de costes».
     - Validar la conexión.
     - Seleccione el proyecto de cálculo de costes principal que contiene su gasto real en TI.
     - Seleccione el período fiscal del año fiscal que debe utilizarse para sus puntos de referencia de referencia.
     - Recuperar los datos.

     ![Apptio Configuración de la fuente para integrarla con IBM Proyecto de cálculo de costes de Apptio](../../resources/images/it%20benchmarking_images/path1-benchmarking.png)

     Una vez conectado, Benchmarking se conectará al entorno de producción de su proyecto de cálculo de costes y
     - Extraiga el coste anual de TI por grupo de costes.
     - Extraiga el coste anual de TI por torre de recursos y, cuando esté asignado, por subtorre.

     Nota: Asegúrese de que el proyecto de cálculo de costes utilice los grupos de costes y las torres de recursos de TBM alineados con la versión de TBM seleccionada definida en Interactive Benchmarking.
   - **PATH 2** Entrada manual de costes (si el cálculo de costes no está listo o no se utiliza)

     Si aún no puede integrarse con Costing, abra el área de configuración y
     - Introduzca manualmente los datos en la sección Datos de costes.
     - Introduzca manualmente los datos en la sección Volúmenes.
     - Introduzca manualmente los datos en la sección FTE.

       ![Configuración interactiva de benchmarking: grupos de costes, volúmenes de torres de recursos y FTE](../../resources/images/it%20benchmarking_images/manual-cost-input-benchmarking.png)

     Independientemente del método de integración:
     - Confirme que el coste total de TI cargado en Benchmarking concuerda con el de Finanzas para el año seleccionado.
     - Confirme que todas las torres principales que espera realmente tienen valores distintos de cero.
     - Si falta algún valor o cree que merece una sustitución, introduzca los valores manualmente y guárdelos antes de continuar.
4. **Realizar una comparación básica de referencia.**

   Ahora, comprueba que la configuración produce resultados útiles.

   En la evaluación comparativa interactiva:
   - Elija hasta tres grupos de pares que reflejen su conjunto de comparación.
     - Industria similar.
     - Rango de ingresos similar.
     - Región adecuada.
   - Abre la vista «Puntos de referencia del sector».
     - Comprueba métricas como el gasto en TI como porcentaje de los ingresos o el gasto en TI por empleado.
     - Comprueba que las métricas reales de tu organización aparecen en el gráfico.   
       Sugerencia: busca las líneas punteadas.

       ![Referencias del sector: gasto en TI como porcentaje de los ingresos](../../resources/images/it%20benchmarking_images/benchmarking-views.png)
   - Seleccione « OpEx es de referencia de TI» en el menú de recopilación de informes.
     - Observe las distribuciones por grupo de costes y por torre de recursos.
     - Confirme que los valores parecen plausibles y que las torres de recursos están presentes.

       ![Puntos de referencia de los e OpEx es de TI: por grupo de costes](../../resources/images/it%20benchmarking_images/itopex-benchmarking.png)
   - Si se proporcionaron los costes y volúmenes de infraestructura, abra «Puntos de referencia de infraestructura» en el menú de recopilación de informes y revise los costes unitarios, como el coste por servidor o el coste por TB y la eficiencia de los empleados a tiempo completo.
     - Aún no estás afinando, solo comprobando si hay valores atípicos absurdos causados por problemas de unidad o volumen.

       ![#: Indicadores de referencia de infraestructura: costes unitarios](../../resources/images/it%20benchmarking_images/infrastructure-benchmarking-unit-cost.png)

     En este paso, se buscan problemas evidentes:
     - Gráficos en blanco donde debería haber datos.
     - Números que difieren en órdenes de magnitud.
     - Filtros de pares que no coinciden con la historia que quieres contar.

     Si algo parece estar roto, anótelo y luego utilice las secciones Guía de configuración y Solución de problemas y preguntas frecuentes para repararlo o solucionar el problema.
5. **Marcar y compartir opiniones iniciales**

   Una vez que tengas algunas opiniones que tengan sentido:
   - Captura un pequeño conjunto de capturas de pantalla o exportaciones para tu primera conversación con las partes interesadas.

     Paquete básico mínimo:
     - Una vista de referencia del sector que muestra el gasto en TI frente a los ingresos.
     - Una vista de distribución de IT OpEx s que muestra la estructura de costes por grupo de costes o torre de recursos.
     - Una vista de infraestructura, si está disponible, que muestre una torre en la que sospecha que hay huecos interesantes.

     Lo importante no es ser perfecto. El objetivo es tener un conjunto pequeño y coherente de opiniones al que puedas volver y sobre el que puedas iterar.
