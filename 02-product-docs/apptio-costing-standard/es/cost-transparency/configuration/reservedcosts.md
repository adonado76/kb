---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Costes de instancias reservadas - Asignaciones dentro de Apptio"
breadcrumb: []
source_path: "cost-transparency/configuration/reservedcosts.html"
images:
  - "resources/images/ct_images/8454_1.png"
  - "resources/images/ct_images/8454_2.png"
  - "resources/images/ct_images/8454_3.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Costes de instancias reservadas - Asignaciones dentro de Apptio

Las instancias reservadas (IR) incluyen opciones de precios por las que todos o algunos de los costes se pagan por adelantado en el momento de la compra. Para estas opciones (todo por adelantado o parcialmente por adelantado), Apptio repartirá el coste inicial uniformemente cada mes a lo largo del plazo de la compra de RI. Ese coste mensual efectivo se sumará a cualquier cuota periódica asociada a la RI (0 en el caso de All Upfront) para formar el coste mensual efectivo devengado.

## Determinar un coste mensual efectivo para las compras de RI

Es este coste mensual efectivo devengado para una RI el que se utilizará a la hora de asignar los costes a las partidas de facturación de AWS para aquellos recursos que se beneficien de las compras de RI. El siguiente diagrama ilustra cómo se repartiría el coste de una RI simple, "Todo por adelantado", entre todos los meses de la RI.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8454_1.png)

## Nota importante sobre las fuentes de datos de facturación: Informe de imputación de costes frente al informe de costes y utilización

Apptio aprovecha actualmente AWS ' Cost Allocation report for monthly billing data. AWS tiene previsto dejar obsoleto el informe de imputación de costes y recomienda utilizar el informe de costes y utilización. Por ello, Apptio está desarrollando actualmente la integración con el informe de Costes y Utilización. Por el momento, sin embargo, el informe de Asignación de Costes es la fuente principal para la facturación mensual y las asignaciones descritas a continuación se basan en las Tarifas Combinadas incluidas en el informe de Asignación de Costes.

## ¿Cómo se asignan los costes fijos de RI a las partidas de facturación de AWS?

Los costes de las instancias reservadas no se reflejan en las partidas de facturación de los recursos de AWS que se benefician de esas compras de RI. Para resolver este problema, Apptio asigna los costes fijos (tras amortizar dichos costes a lo largo de todos los meses del plazo de RI, como se muestra más arriba) a cada partida de la factura. Apptio consiste en distribuir las partidas en función de la familia/tipo de instancia, el sistema operativo y la región/zona de disponibilidad, y ponderarlas por la cantidad de uso de cada partida aplicable. El siguiente diagrama ilustra cómo se repartirán los costes desde la compra hasta una factura mensual.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8454_2.png)

## Nota importante sobre los costes combinados en el informe de imputación de costes

AWS el cálculo de los costes en el Informe de Asignación de Costes es un factor importante a tener en cuenta en el contexto de la asignación de los costes fijos de RI a las partidas de uso. El siguiente diagrama ilustra conceptualmente cómo AWS determina los costes combinados, en particular cuando intervienen RI. La clave es que los costes en el informe de asignación de costes se basan en una tasa combinada que es efectivamente el coste agregado dividido por la cantidad de uso agregada para una cohorte de instancias, independientemente de la cuenta y las etiquetas asociadas.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8454_3.png)

## ¿Cómo modifican las nuevas IR flexibles la asignación de costes fijos a las IR?

Con las nuevas IR regionales y de tamaño de instancia flexibles EC2, las asignaciones de costes se basarán en la familia de instancias y la región en lugar del tipo de instancia y la zona de disponibilidad. Los costes mensuales de RI se ponderarán por la cantidad de uso de la partida multiplicada por un factor de normalización que tiene en cuenta el tamaño relativo de la instancia. Este cambio sólo es aplicable a las IR de EC2, no a las IR de otros servicios de AWS como RDS o Elasticache.

## ¿Cómo afectan las modificaciones de RI a mis asignaciones de costes de RI?

Aunque las modificaciones de las IR son cada vez menos frecuentes como resultado de la nueva flexibilidad de las IR introducida por AWS, es posible que su organización siga teniendo instancias reservadas que hayan sido modificadas y será necesario introducir los datos de modificación de las IR en Apptio. ¿Por qué es necesario este paso? Cuando se produce una modificación, AWS crea una nueva entrada de compra de RI para las nuevas RI que se crean como resultado de la modificación y actualiza la fecha de finalización de la entrada de compra de RI original de modo que caduque en la fecha de la modificación. AWS no actualiza el coste inicial en la entrada de compra de la RI original ni AWS incluye un importe prorrateado en el coste inicial de la nueva entrada de compra de la RI (o entradas si la modificación crea varias RI). Por lo tanto, en los casos en que se hayan modificado las IR, las nuevas IR parecerán artificialmente más baratas que las originales, ya que no se aplica ninguno de los costes iniciales. Los siguientes pasos le ayudarán a resolver la situación ingiriendo y configurando las modificaciones de RI en su entorno Apptio.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
