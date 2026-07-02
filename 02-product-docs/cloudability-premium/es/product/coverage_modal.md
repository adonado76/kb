---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Modalidad de cobertura"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Guía sobre la funcionalidad avanzada de compromiso"
source_path: "product/coverage_modal.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Modalidad de cobertura

## Finalidad

Como ya se ha comentado, la cobertura es un indicador clave de rendimiento (KPI) importante. Ofrece información tanto sobre el rendimiento —lo que ya tienes optimizado en cuanto a tarifas a través de los compromisos— como sobre el riesgo —qué porcentaje de tu gasto total comprometible está cubierto actualmente—. La ventana modal de cobertura explica cómo se calcula este KPI para que nuestros usuarios tengan confianza y puedan obtener información sobre el rendimiento y las oportunidades.

## Cómo acceder

Actualmente, puedes acceder a la ventana modal de cobertura a través del botón «Detalles» que aparece en el indicador de rendimiento clave (KPI) de cobertura de la página de la cartera. Tenemos previsto ofrecer acceso a esta ventana emergente en las páginas de recomendaciones y de gestión. La ventana modal hereda la selección actual del encabezado y aplica filtros a la página, de modo que los datos de la ventana modal siempre se ajustan al contexto de lo que estabas viendo anteriormente.

## Diseño de la ventana modal de cobertura

**Cálculo de la cobertura:** La ventana emergente mostrará en primer lugar qué dos valores del gráfico siguiente se han utilizado para calcular la métrica de cobertura.

**Desglose de los indicadores de cobertura** : A continuación, el modelo desglosa cada uno de los costes cubiertos y no cubiertos. Inspirándose en un estado financiero, los valores que aparecen en cada línea son la suma de los valores anteriores.

**Resumen de la cobertura del proveedor** : Para ofrecer una idea de la importancia relativa a la hora de evaluar diferentes métricas de cobertura de servicios, facilitamos los valores de ODE «cubiertos», «no cubiertos» y «no elegibles» correspondientes al proveedor seleccionado. Ten en cuenta que esta sección no varía en función de la selección actual del encabezado ni de los filtros de la página subyacente.

**Importante** : Todas las cantidades que figuran en el «Modal de cobertura» se expresan en términos de costes equivalentes a la demanda (ODE). En el caso de los valores «sin cubrir», esto significa que se expresan en términos de «a la demanda» y, por lo tanto, el valor «a la demanda» = ODE. En el caso de los valores «incluidos», esto significa que el valor que se muestra no es el coste, sino el ODE. Esto permite realizar una comparación equitativa entre los costes cubiertos y los no cubiertos.

## Terminología relativa a las modalidades de cobertura

Todos los valores se expresan en términos de ODE. En primer lugar, un recordatorio de dos términos importantes:

**Compromisos basados en los recursos:**  Abreviados como «compromisos de recursos». Ofrece un descuento a cambio del compromiso de alcanzar un determinado volumen de uso de un producto o servicio (instancia reservada, CUD).

**Compromisos basados en el gasto: Se denominan** «compromisos de gasto» para abreviar. Ofrece un descuento a cambio del compromiso de gastar una cantidad determinada en un producto o servicio (Plan de Ahorro, CUD flexible).

*Desglose de las métricas de cobertura - Cubierto*

- **Recursos cubiertos** : Importe cubierto por los compromisos basados en recursos.
- **Gasto cubierto** : El importe cubierto por los compromisos basados en el gasto.
- **Gasto cubierto, recurso elegible** : Porcentaje cubierto por compromisos de gasto que podría haber sido cubierto por compromisos de recursos, aplicándose las mismas normas de elegibilidad.
- **Recurso cubierto, gasto subvencionable** : Porcentaje cubierto por compromisos de recursos que podría haber sido cubierto por compromisos de gasto, aplicándose las mismas normas de subvencionabilidad.
- **Importe total cubierto** : el ODE del importe total cubierto.

*Desglose de los indicadores de cobertura: personas sin cobertura*

- **Gasto** **no cubierto exclusivo** : uso bajo demanda que solo un compromiso de gasto habría podido cubrir.
- **Recurso exclusivo** **no cubierto** : uso bajo demanda que solo un compromiso de recursos habría podido cubrir.
- **U** so **no exclusivo no cubierto** : uso bajo demanda que podría haber sido cubierto por un recurso o un compromiso de gasto.
- **Importe total no cubierto** : el importe total que podría haberse cubierto, pero que no lo fue.

*Desglose de los indicadores de cobertura: importe total*

- **Importe total** : el importe total cubierto más el importe total no cubierto. Otra interpretación es que este valor representa la ODE de lo que podría haber estado o estuvo cubierto por los compromisos.

*Resumen de la cobertura de proveedores*

- **Importe cubierto** : El importe que cubren los compromisos. Ten en cuenta que este valor no tiene en cuenta el coste de compromiso que quedó sin utilizar.
- **Importe no cubierto** : El importe que no quedó cubierto por los compromisos. Dado que se facturó bajo demanda, esto puede considerarse tanto como ODE como como coste real.
- **No admisible para compromisos** : Gastos que no pueden cubrirse mediante compromisos debido a las normas relativas al tipo de servicio o de uso.
- **Importe total del servicio** : el ODE total (coste en caso de que no se hubieran adquirido compromisos para el proveedor en cuestión) de los servicios cubiertos por los compromisos de « Cloudability ». (Véase el resumen de tipos de compromiso)
- **Créditos de descuento por uso continuado (SUD)** : Un descuento mensual específico de GCP por el uso continuado de GCE cuando no se aplican otros descuentos. Es un detalle menor, pero lo incluyo aquí para que se tenga en cuenta.

## Uso cubierto frente a uso no cubierto: cómo interpretarlo

La cobertura te ayuda a responder a dos preguntas:

1. ¿Qué porcentaje de mi demanda admisible se ha optimizado mediante tarifas con descuento? (cubierto)
2. ¿En qué casos podrían haberse aplicado los compromisos, pero no se aplicaron? (sin cubrir)

*Posibles interpretaciones de los datos*

- Un elevado porcentaje de «Spend Covered» con un gran solapamiento con «Resource Eligible» puede indicar que existe margen para convertir parte de la demanda en más compromisos de recursos, que suelen conllevar una tasa de descuento por compromiso (CDR) más elevada.
- El nivel «Alto, no exclusivo, sin cobertura» sugiere que existen amplias oportunidades: tanto los compromisos en materia de recursos como los de gasto podrían colmar esa brecha. Utiliza las recomendaciones para determinar qué combinación de categorías se adapta mejor a tu tolerancia al riesgo.
- El indicador «High Resource Exclusive Uncovered» suele señalar familias de instancias o regiones concretas que carecen de compromisos de recursos. En este caso no se aplicarían los compromisos de gasto, por lo que es necesario crear una estrategia de compromiso específica para los recursos con el fin de optimizar este gasto.
- El programa «High Spend Exclusive Uncovered» puede indicar patrones de uso poco frecuentes, mixtos o entre distintos servicios, más adecuados para los compromisos de gasto. Consuélate pensando que este gasto no se puede optimizar más con una asignación de recursos.

Recordatorio: Si tu organización utiliza tarifas personalizadas, la referencia de ODE reflejará dichas tarifas; las tasas de ahorro derivadas de ODE diferirán de las referencias minoristas.

## Integración de enlaces de informes

Con el lanzamiento de « GCP », hemos incorporado enlaces directos a los valores que se muestran en la ventana modal de cobertura. Estos enlaces se abren en una nueva pestaña y generan un informe mediante la función de generación de informes nativa de « Cloudability ». Esta función amplía aún más la finalidad original de «modal» al:

- Dar a conocer los costes subyacentes, de modo que exista una total transparencia sobre cómo se ha calculado el indicador clave de rendimiento (KPI) de la cobertura.
- Revelación de los costes subyacentes cubiertos para los casos de uso de devoluciones y reembolsos.
- Analizar los costes subyacentes cubiertos para comprender qué es lo que se cubría, con el fin de determinar si procede renovar el compromiso.
- Poner de manifiesto los costes subyacentes no cubiertos para determinar si dicho coste es lo suficientemente estable como para que su cobertura mediante un compromiso se traduzca en un ahorro. Gracias a la función de recomendaciones, los usuarios pueden estar seguros de que sus planes futuros tendrán un resultado positivo y de que merece la pena asumir el riesgo.

## Puntos de partida clave

- La cobertura se presenta en ODE para unificar la interpretación entre los distintos proveedores.
- El modal distingue entre lo que se ha cubierto y lo que se podría haber cubierto, y clasifica la parte no cubierta según los criterios de elegibilidad (solo recursos, solo gastos o cualquiera de los dos).
- Utiliza los enlaces de generación de informes para pasar de la señal a la causa raíz y, a continuación, prueba las estrategias que se proponen en las «Recomendaciones de compromiso».

**Tema principal:** [Guía sobre las funciones avanzadas de compromiso](../product/guide_to_advanced_commitment_functionality.html)
