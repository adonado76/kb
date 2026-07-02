---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Guía para la gestión de compromisos Preguntas frecuentes"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Guía para la gestión de compromisos"
source_path: "product/guide_to_commitment_management_faq.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Guía para la gestión de compromisos Preguntas frecuentes

## Gestor de compromisos

## Cartera de compromisos

**¿Cuál es la diferencia entre unidades y recuentos?**

**Los recuentos** se refieren al número de instancias en una reserva, mientras que **las unidades** se refieren a las horas de instancia normalizadas. Esto es relevante para las RI que se aplicaron a varios tamaños de instancia dentro de una familia. Esto también le ayuda a decidir el tamaño total de una RI, de modo que una reserva de 5 instancias de m4.large (Recuento de 5, Unidades de 20) no parezca mayor que una reserva de 4 instancias de m4.16xlarge (Recuento de 4, Unidades de 512).

**¿Por qué disminuyen mis ahorros cuando miro el coste ajustado?**

Los precios personalizados suelen desplazar los ahorros de un RI a los precios personalizados. Por poner un ejemplo sencillo, si una instancia cuesta $1/hour y la reserva cuesta $0.80/hour, una reserva de 10 instancias totalmente utilizada proporcionaría un ahorro de 48 $ al día (10 x 24 x 0.2 $).

Si tiene un acuerdo de precios personalizado que le ofrece un descuento del 10 % para instancias informáticas, su ahorro por este concepto se reduciría efectivamente a 43.20 s de dólares al día (10 x 24 x 0.18 dólares).

**¿Por qué cambia el ahorro/utilización cuando selecciono una vista?**

La cartera admite vistas basadas en grupos de cuentas. Sin embargo, cuando seleccione una vista, filtre tanto por el propietario de la reserva como por el lugar donde se aplica la reserva. Si su equipo compra RI dentro de una cuenta vinculada y desea ver cuánto del RI ha consumido su equipo, puede hacerlo con una vista.

Para ver los RI que se poseen en una cuenta concreta, utilice el filtro **Cuenta** de la página principal.

**En las instancias reservadas de Azure, ¿el porcentaje de ahorro y los KPI de ahorro a lo largo del plazo incorporan las tarifas personalizadas de Azure?**

Si tiene precios personalizados calibrados en la aplicación, también puede calcular sus ahorros netos de los descuentos de precios personalizados.

**En mi cartera de compromisos faltan algunos compromisos, ¿dónde están?**

Cloudability Los compromisos solo pueden ver los compromisos que la cuenta de usuario puede ver. Tomando como ejemplo AWS, una cuenta principal de facturación consolidada no puede ver la actividad de la cuenta secundaria que se produjo antes de que entrara en la relación de facturación consolidada. Esto significa que la cuenta principal no puede ver los compromisos pertenecientes al secundario que se adquirieron antes de que comenzara la relación de facturación consolidada.

La solución alternativa sugerida es añadir una credencial de IAM para la cuenta secundaria a Cloudability, además de la cuenta principal de facturación consolidada. Cloudability Los compromisos podrán ver los compromisos que fueron adquiridos por la cuenta secundaria. Cloudability eliminará automáticamente cualquier dato duplicado.

## Recomendaciones de compromiso

- **El valor comprometido en el plan de ahorro es superior al de RI en EC2. ¿Recomienda comprar ambos?**

  En Cloudability, es posible que el importe del compromiso en un plan de ahorro sea superior al de la instancia reservada para AWS EC2. Las instancias reservadas ofrecen un descuento al reservar una determinada cantidad de potencia informática (medida por hora) durante un plazo de uno o tres años, mientras que los planes de ahorro ofrecen un descuento al comprometerse a gastar una determinada cantidad (medida en dólares por hora) durante un plazo de uno o tres años. La decisión de adquirir un recurso o de asumir un compromiso de gasto corresponde al responsable de « FinOps » de la organización. El uso subvencionable puede estar cubierto por varios tipos de compromiso. Actualmente, proporcionamos estas recomendaciones de forma aislada. Por ejemplo, no se recomienda adquirir todas las instancias reservadas y todos los planes de ahorro de AWS EC2.
- **¿Cuál es la mejor estrategia para utilizar los compromisos? ¿Cuáles son las mejores prácticas? ¿Espera tener en cuenta todas las recomendaciones a la vez y actuar en consecuencia?**

  La estrategia elegida al utilizar descuentos basados en compromisos para ahorrar en gastos en la nube variará en función de la organización, el proveedor y el tipo de compromiso. No existe un enfoque universalmente óptimo. Dado que los compromisos suelen implicar contratos de uno o tres años, es crucial considerar cuidadosamente los planes de futuro. En general, es aconsejable realizar compras más pequeñas y frecuentes a lo largo del tiempo hasta alcanzar el porcentaje de cobertura deseado. Una vez alcanzado este umbral, podrán adquirirse compromisos adicionales a medida que aumente el uso o expiren los compromisos existentes. También es importante no renovar los compromisos si se prevé una disminución del uso.

  En Cloudability 's support for commitments, las recomendaciones de compromisos proporcionan qué compromisos deben adquirirse para maximizar el ahorro neto, dado el rango de uso seleccionado. Se ofrecen recomendaciones individuales para cada permutación de los criterios necesarios para cada tipo de compromiso en el que se detecte un uso de cobertura. En efecto, las Recomendaciones de Compromiso de Cloudability le proporcionan el compromiso óptimo. Las organizaciones deberían esforzarse por alcanzar este nivel de cobertura para lograr un ahorro óptimo; sin embargo, dado que las mejores prácticas abogan por pequeñas compras incrementales, rara vez debería actuarse directamente sobre la recomendación óptima.

## GCP Preguntas frecuentes específicas

**¿Hasta qué punto puedo remontarme en el uso histórico para realizar un análisis?**

Un máximo de 2 meses: todo el consumo de los meses anteriores, hasta el día anterior del mes actual.

**¿Qué dimensiones puedo utilizar para filtrar el uso para el análisis?**

Puede utilizar cualquier dimensión configurada en Cloudability : Etiquetas y etiquetas, Grupos de cuentas o Asignaciones comerciales. Algunas dimensiones pueden no estar disponibles si la variabilidad de los datos es alta, por ejemplo: «nombre del servidor». Solo estarán disponibles las dimensiones con un grado de variabilidad bajo-moderado, por ejemplo: «entorno: producción/preproducción», «centro de costes: abc123” ».

**¿Cuántas dimensiones puedo utilizar para filtrar mi uso para el análisis?**

Puede seleccionar hasta 10 dimensiones de Cloudability para aplicar a su uso.

**¿Cuándo se aplicarán las dimensiones seleccionadas a mi uso?**

Las dimensiones se aplican cuando se produce la siguiente ingesta de datos de facturación. Las dimensiones pueden tardar hasta un máximo de 24 horas en aplicarse a su uso y estar disponibles para utilizarlas como filtros. Cuando se inicie el procesamiento de « GCP », tomará las preferencias configuradas en ese momento y las aplicará.

**¿Puedo cambiar las dimensiones seleccionadas varias veces?**

Sí, puedes cambiar las dimensiones varias veces. Cuando se produce la ingesta de datos de facturación, se toman las dimensiones configuradas actualmente y se aplican a los datos.

**¿Pueden diferentes usuarios tener configuradas diferentes dimensiones para su uso?**

No, las dimensiones se configuran para toda la organización.

**¿Cómo se muestra el uso en los gráficos?**

Los gráficos muestran datos por hora, con varias horas promediadas en un solo punto si es necesario para ajustarse al gráfico.

**¿Cómo se calcula la recomendación predeterminada?**

Este es el algoritmo de propiedad Cloudability, que busca maximizar los ahorros y equilibrar el riesgo.

**¿Se han incorporado los SUD a la recomendación?**

Sí, si un recurso recibió anteriormente un SUD, el ahorro recomendado por el programa de ahorro de energía ( Cloudability ) mostrará el aumento con respecto a la tarifa SUD, no a la tarifa bajo demanda.

**El nivel de descuento SUD cambia a lo largo del mes, ¿qué nivel de descuento SUD se utiliza?**

Se utiliza el promedio del descuento de todos los meses anteriores y se aplica al uso modelado para cualquier recurso que haya recibido un descuento.

**¿En qué se** diferencian las recomendaciones de Cloudability **de las recomendaciones GCP?**

Hay cinco características que darán lugar a resultados distintos de las recomendaciones nativas de GCP :

1. **Datos incluidos:** Cloudability incluye cualquier recurso que se ejecute durante cualquier periodo de tiempo, no es necesario que se ejecute de forma continua durante 30 days/1 meses
2. **Período de uso:** selección de un período de uso específico
3. **Filtrado de datos:** Cloudability le permite eliminar el uso del análisis a un nivel muy detallado
4. **SUD:** Cloudability incorpora los descuentos SUD en los cálculos si se han recibido anteriormente
5. **Riesgo:** los usuarios de Cloudability pueden analizar diferentes niveles de compromiso en función del riesgo

**¿Cómo se redondean los valores en la consola**?

Los valores se redondean al número entero más cercano.

**Tema principal:** [Guía para la gestión de compromisos](../product/guide_to_commitment_management.html)
