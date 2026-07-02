---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Informes de facturación en Billing Essentials"
breadcrumb:
  - "Billing"
  - "Trabajar con informes de facturación"
source_path: "boit/billing/work-bill-reports/billrep-be.html"
images:
  - "resources/images/boit_images/billcostmodel.png"
  - "resources/images/boit_images/billdetail.png"
  - "resources/images/boit_images/billinv.png"
  - "resources/images/boit_images/billjournal.png"
  - "resources/images/boit_images/billprocessasmin1.png"
  - "resources/images/boit_images/ratemgmt.png"
  - "resources/images/boit_images/solnlib.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Informes de facturación en Billing Essentials

Billing Essentials incluye un pequeño conjunto específico de informes que se instalan a través del componente «Informes de facturación y cargos»:

Nota: Se aplica únicamente a Billing Essentials.

## Informe detallado de la factura

- Objetivo: Inspeccionar los cargos, las unidades y las tarifas por solución ofrecida y organización receptora, a lo largo del tiempo (mes actual, trimestre, año hasta la fecha, anual), y comparar los datos reales con los previstos para explicar las variaciones.
- Preguntas respondidas:
  - ¿Cuál es el cargo total para el período seleccionado y cómo se compara con el plan?
  - ¿Cuáles son mis cargos acumulados hasta la fecha y los cargos anuales previstos (y estamos por encima o por debajo del plan)?
  - ¿Qué soluciones u ofertas están generando más ingresos para esta organización?
  - ¿Qué soluciones tienen la tarifa facturable más alta?
  - Para una oferta determinada, ¿cuáles fueron las unidades facturables, la unidad de medida y la tarifa utilizadas para calcular el cargo?
  - ¿A qué organizaciones se les cobra por una oferta determinada?
  - ¿Dónde tenemos variaciones en los cargos con respecto al plan, y están determinadas por la tarifa o por las unidades?
  - ¿Dónde tenemos variaciones en las unidades respecto al plan (aumento o disminución del consumo)?
  - ¿Hay cargos con unidades cero (o unidades con cargo cero), lo que indicaría un problema con los datos o los precios?
  - ¿Cómo cambian los cargos y las unidades cuando cambio entre las vistas Mes actual, Trimestre, Año, Anual o Tendencia?
- Usuarios objetivo: Consumidores, analistas, propietarios de servicios o productos.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/billdetail.png)

Fig. n.º: Informe detallado de facturas en Billing Essentials

## Informe de facturas

- Objetivo: Agrupa los cargos de la organización y el período seleccionados, destaca los factores que generan mayores costes y las tarifas unitarias más caras, muestra la tendencia y proporciona los conceptos de la factura (oferta, unidades, tarifa, cargo y diferencias de MoM ) para que la organización receptora pueda revisar y validar la factura rápidamente.
- Preguntas respondidas:
  - ¿Cuál es el gasto total de esta organización para el período actual y cómo se compara con lo previsto?
  - ¿Cuál es el gasto acumulado del año de la organización y estamos por encima o por debajo del plan acumulado del año?
  - ¿Cuál es el cargo anual previsto y cómo se compara con el cargo anual planificado?
  - ¿Qué soluciones u ofertas principales generan más ingresos para esta organización?
  - ¿Qué soluciones tienen las tarifas facturables más altas, aunque no sean las que más gastan?
  - ¿Cómo han evolucionado las tarifas de los servicios clave a lo largo del tiempo?
  - Para cada partida de la factura, ¿cuáles fueron las unidades facturables, la tarifa facturable y el cargo resultante?
  - ¿Qué partidas registraron el mayor cambio mensual en unidades o cargos?
  - ¿Existen anomalías, como unidades sin cargos o cargos sin unidades, que sugieran problemas con los datos o los precios?
- Usuarios objetivo: propietarios de servicios o productos, analistas, consumidores.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/billinv.png)

Fig. n.º: Informe de facturas en Billing Essentials

## Informe de la biblioteca de soluciones

- Objetivo: Enumera cada solución con los metadatos clave necesarios para facturarla y gestionarla, como el tipo y la categoría de la solución, el ID y el nombre de la oferta, el propietario, la capacidad empresarial, la fase del ciclo de vida, la unidad de medida y la tarifa facturable. En la práctica, es la referencia de «qué vendemos internamente, quién es el propietario y cuánto cobramos».
- Preguntas respondidas:
  - ¿Qué soluciones/ofertas existen actualmente en nuestro catálogo de facturación?
  - ¿Qué soluciones son facturables y cuáles no?
  - ¿Cuál es la tarifa facturable para cada solución y qué unidad de medida se utiliza?
  - ¿Qué soluciones se incluyen en un tipo o categoría de solución determinados?
  - ¿Quién es el propietario de la solución para cada oferta y qué «posee» cada propietario de principio a fin?
  - ¿Qué soluciones admiten una capacidad empresarial específica (y qué cobertura de catálogo tenemos por capacidad)?
  - ¿En qué fase del ciclo de vida se encuentran las soluciones (y cuáles podrían ser candidatas a retirarse o dejar de facturar)?
  - ¿Dónde tenemos patrones de precios inconsistentes, como ofertas similares con tarifas o unidades muy diferentes?
  - ¿Qué ofertas carecen de metadatos críticos para la gobernanza, como propietario, capacidad, etapa del ciclo de vida, unidad de medida o tarifa?
  - ¿Cuáles son los ID de oferta de las soluciones para que pueda conciliar las facturas, los feeds de uso o las partidas de las facturas con el catálogo?
- Usuarios objetivo: propietarios de servicios o productos, finanzas, liderazgo tecnológico.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/solnlib.png)

Fig. n.º: Informe de la biblioteca de soluciones en Billing Essentials

## Informe de gestión de tarifas

- Objetivo: Establecer, regular y ajustar las tarifas facturables de las soluciones y, a continuación, validar si dichas tarifas están recuperando los costes. Combina una tarjeta de tarifas editable (tarifa base más ajustes que se incorporan a la tarifa facturable) con un análisis de la variación entre costes y cargos, lo que le permite reducir la recuperación insuficiente o excesiva y mantener la justificación de las facturas.
- Preguntas respondidas:
  - ¿Cuál es la tarifa facturable actual para cada solución y cómo se calcula (tarifa base frente a ajuste de tarifa)?
  - ¿Qué soluciones son facturables y cuáles no, y quién es su propietario?
  - ¿En qué aspectos estamos recuperando menos o más de lo debido (varianza) este mes y en lo que va de año?
  - ¿Qué soluciones tienen los mayores factores de variación entre el coste y el cargo?
  - Para una oferta determinada, ¿el coste y el cargo coinciden cuando se analizan el volumen real, las unidades facturables, el precio unitario y la variación unitaria?
  - ¿Qué unidades de medida se facturan por cada solución (y son coherentes con la intención de la tarifa)?
  - ¿Quién actualizó por última vez una tarifa y cuándo (registro de auditoría)?
  - Si cambio una tasa, ¿qué impacto tiene en la recuperación esperada (variación a la baja o al alza)?
  - ¿Hay soluciones con tarifas establecidas pero sin volumen, o volumen con tarifas nulas o faltantes que deban limpiarse?
  - ¿En qué casos se facturan varias unidades de medida en la misma oferta y eso genera inconsistencias en los precios?
- Usuarios objetivo: propietarios de servicios y productos, altos directivos, finanzas, analistas.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/ratemgmt.png)

Fig. Informe de gestión de tarifas de facturación en Billing Essentials

## Proceso de facturación Informe administrativo

- Pestaña Archivo de facturas
  - Objetivo: Revisar y crear una copia archivada de los detalles de las facturas de un período fiscal específico que pueda consultarse con fines de auditoría u otras necesidades.
- Pestaña Archivo de diarios de facturas
  - Objetivo: Revisar y crear una copia archivada de los detalles del diario para un período fiscal específico que pueda consultarse con fines de auditoría u otras necesidades.
- Preguntas respondidas:
  - ¿Ya archivamos los detalles de las facturas del mes o rango de fechas seleccionado?
  - ¿Qué servicios se facturaron, a qué organizaciones y por qué importe?
  - ¿Cuáles fueron las unidades facturables y las tarifas facturables utilizadas para cada organización y oferta?
  - ¿Cuáles fueron las unidades facturables y los cargos del período anterior (para una comparación rápida entre períodos)?
  - ¿Cuál es el desglose histórico de las partidas de las facturas de una organización, oferta o ID de oferta determinados?
  - ¿Cuál es el registro histórico del diario de facturación para el mismo período (coste y dimensiones relacionadas)?
  - ¿Las salidas de facturas y las salidas de diarios coinciden para un período, y en qué se diferencian?
  - ¿Qué organizaciones u ofertas están generando los mayores cargos en la instantánea archivada?
  - Si alguien impugna una factura más adelante, ¿qué publicamos realmente en ese momento (la verdad archivada)?
  - Después de un cambio de modelo/tasa/configuración, ¿afectó a la vista actual pero no a la instantánea archivada (como era de esperar), y qué período se ve afectado?
- Usuarios objetivo: Finanzas, Analistas.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/billprocessasmin1.png)

Fig. n.º: Pestaña «Archivo de facturas» del informe «Proceso de facturación»

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/billjournal.png)

Fig. n.º: Pestaña Archivo del diario de facturación del informe de administración del proceso de facturación

## Informe sobre el modelo de costes de facturación

- Objetivo: Una forma rápida e interactiva de ver de dónde proceden los cargos facturados y dónde se ubican en las dimensiones fundamentales de la facturación. Le permite basar la vista en una métrica seleccionada (cargo, cargo del plan e impacto del ajuste de tarifa) por oferta de solución, organización y departamento, de modo que pueda validar los resultados del modelo de facturación, detectar la concentración y encontrar rápidamente la historia de «quién/qué impulsó esta factura».
- Preguntas respondidas:
  - ¿Qué soluciones están generando los mayores costes en este periodo?
  - ¿Qué organizaciones están recibiendo la mayor parte de los cargos?
  - ¿Qué departamentos son los mayores consumidores y cuánto se les cobra?
  - Si elijo una solución específica, ¿a qué organizaciones y departamentos afecta más?
  - ¿Los cargos se concentran en unas pocas ofertas o están ampliamente distribuidos?
  - ¿Cuáles son los principales factores que impulsan el aumento de los cargos, por oferta, organización o departamento?
  - ¿Los resultados parecen estructuralmente correctos (por ejemplo, se está cobrando a los departamentos correctos por las ofertas correctas), o hay algo claramente mal asignado?
  - ¿Qué combinaciones de oferta + organización + departamento son las que más contribuyen al cargo total?
  - Si un líder empresarial impugna su factura, ¿cuáles son los principales elementos que determinan sus cargos sin entrar en detalle en cada partida de la factura?
- Usuarios objetivo: propietarios de servicios y productos, finanzas, analistas.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/billcostmodel.png)

Fig. n.º: Informe del modelo de costes de facturación en Billing Essentials
