---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Informes de sostenibilidad en la nube"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
source_path: "product/cld-sustainability-reporting.html"
images:
  - "images/Sustainability-Metrics.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Informes de sostenibilidad en la nube

**Visión general**

Mediante esta función, los usuarios de Cloudability podrán ver su huella de carbono en la nube pública (operativa + incorporada) para los servicios compatibles.

Requisitos previos

Para acceder a las métricas de sostenibilidad de la nube, los clientes deben cumplir los siguientes requisitos previos:

- Para acceder a las métricas de carbono en la nube, los clientes deben tener datos de Costes durante 1 mes.
- Los clientes deben tener habilitadas las credenciales avanzadas para los cálculos de los niveles de utilización reales, de lo contrario, utilizaremos por defecto niveles de utilización del 50%
- Los clientes de « GCP » deben tener activada la facturación detallada.
- Aplicable a los clientes de Cloudability Standard y Cloudability Premium.

Introducción

Cloudability los usuarios pueden ver rápida y fácilmente las métricas de sostenibilidad de la nube para obtener información sobre las emisiones de carbono de su nube pública. Las métricas de sostenibilidad de la nube están disponibles en los informes y cuadros de mando de Cloudability utilizando las siguientes métricas:

- **Emisión operativa de carbono** **( MTCO2e** ) - Esta métrica representa las emisiones de carbono generadas durante el funcionamiento diario de los servicios en nube. Procede principalmente de la electricidad utilizada para alimentar y refrigerar los centros de datos mientras se ejecutan las cargas de trabajo.
- **Emisiones de carbono incorporadas** **( MTCO2e )** : esta métrica representa la proporción de emisiones de carbono vinculadas a la producción y el ciclo de vida de la infraestructura en la nube. En el contexto de la nube, se calcula asignando una parte del total de emisiones incorporadas de los servidores y equipos físicos en función de su uso específico.
- **Emisiones estimadas de carbono ( MTCO2e** ) - Esta métrica representa el total de emisiones estimadas de carbono, suma de las emisiones de carbono **operativas** e **incorporadas**. Esto proporciona una visión completa de su huella de carbono en la nube en toneladas métricas de CO₂ equivalente.
- **Potencia consumida ( kWh** ) - Potencia consumida en kilovatios hora. Cloudability calcula la huella de carbono de la nube de los principales proveedores de servicios en la nube ( AWS, Azure, GCP y OCI) y ofrece una metodología uniforme para comparar las emisiones de carbono de la nube entre los distintos proveedores.

Estas métricas están disponibles a nivel de recursos para los siguientes servicios subvencionados.

| AWS | Azure | GCP | OCI |
| --- | --- | --- | --- |
| EC2 | Cálculo | CME | Cálculo |
| EBS | Disco gestionado | Disco persistente |  |
| RDS | Azure Base de datos   - SQL Server   - PostgresSQL | Cloud SQL |  |

Dónde encontrar las métricas

Cloudability > Nuevos informes o Añadir widget > Categoría Sostenibilidad

![](../../../../03-media/cloudability-premium/images/Sustainability-Metrics.png)

También hay un **panel de control de ejemplo —Sostenibilidad en la nube—** ya configurado, que se puede encontrar en «Todos los paneles de control» en Cloudability

**Metodología**

Para calcular las emisiones de carbono, nuestra metodología es un enfoque ascendente en el que las emisiones de cada recurso se calculan por separado. Estas emisiones calculadas se agregan para representar colectivamente las emisiones totales de una organización derivadas del uso de su infraestructura en la nube.

Para más detalles, véase [Metodología](cloud_sustainability_methodology.html)

**Preguntas más frecuentes**

**1. ¿Cómo puedo empezar a consultar las métricas de sostenibilidad?**

Compruebe el cuadro de mandos predeterminado configurado para la sostenibilidad en todos los cuadros de mandos en Cloudability.

**2.What ¿diferencia la solución de Cloudability de cualquier otra solución disponible?**

- La metodología es independiente de la nube y aplica la misma lógica a todos los ISP, lo que facilita las comparaciones y las hace más coherentes.
- La metodología proporciona los resultados a una **granularidad de cada Id. de recurso.**
- Las métricas pueden ampliarse a cualquier dimensión compatible, como región, servicio, proveedor, etc., así como a dimensiones temporales, como año, mes, semana, etc., lo que permite realizar comparaciones interanuales, intermedias o entre YoY y MoM.
- Las métricas **utilizan** **la utilización real.**
- Una vez disponibles, los datos honran a las vistas, mapeos de negocio creados que permiten a los usuarios de cloudability ver las emisiones basadas en sus derechos de datos.
- Las emisiones pueden utilizarse junto con las métricas de coste y uso para comparar las tendencias de los costes frente a las de las emisiones.
- La solución utiliza datos de emisiones de la red procedentes de los últimos datos disponibles por organismos gubernamentales locales como la AEMA y la EPA para disponer de datos auténticos para calcular las emisiones de carbono.

**3. ¿Proporciona Cloudability emisiones de Alcance 1, Alcance 2 y Alcance 3 como parte de esta función?**

Cloudability proporciona datos sobre las emisiones de carbono de alcance 3, tanto operativas como incorporadas.

- La combustión de cualquier combustible para generar energía en las instalaciones de una organización se atribuye al Alcance 1, el uso de la energía generada en otro lugar para hacer funcionar el equipo contribuye al Alcance 2, mientras que la cadena de suministro contribuye a las emisiones de Alcance 3.
- Como consumidores de nube pública, utilizamos los servicios en la nube ofrecidos por los CSP sin tener ningún control sobre la electricidad, el mantenimiento de los equipos en la nube o la refrigeración del centro de datos. Por lo tanto, el alcance de las emisiones es **sólo de Alcance 3** para un cliente.

**4. ¿Con qué frecuencia se actualizan las métricas del carbono?**

Las métricas de carbono se actualizarán el día 15 de cada mes para el mes anterior. por ejemplo, el 15 de abril rellenaremos las métricas de marzo

**5. ¿Es** **posible obtener datos históricos sobre las emisiones de las nubes**?

No se dispone de actualizaciones de datos históricos.

**6. ¿Cuál es la granularidad de las métricas de sostenibilidad?**

La granularidad es a nivel de recursos y Cloudability proporciona datos con una granularidad diaria.

**7. ¿Es posible realizar comparaciones anuales, mensuales o semanales?**

Sí, estas comparaciones son posibles utilizando los cuadros de mando e informes de Cloudability.

**8. ¿Es posible comparar la evolución de los costes con la de las emisiones?**

Sí, es posible comparar el coste con las tendencias de las emisiones en una dimensión elegida. A continuación compartimos algunas dimensiones de uso común

- Desde principios de año, en lo que va de mes
- Región
- Proveedor
- Día, Semana, Mes, Año

**9. ¿Estarán disponibles las emisiones de carbono en la API?**

Sí, las cuatro métricas estarán disponibles a través de la API. Consulte siempre la documentación de la API Cloudability

**10. ¿Apoyan vistas y Business Mappings con métricas de sostenibilidad?**

Sí, todas las vistas y asignaciones de negocio son compatibles con las métricas de sostenibilidad, de forma similar a los informes y cuadros de mando.

**11. Veo un aumento de las emisiones en los datos de octubre de 2025, ¿a qué se debe?**

Esto se debe a que, a partir de los datos de octubre de 2025, Cloudability tiene en cuenta tanto las emisiones operativas como las incorporadas. Antes de esta fecha, Cloudability sólo tenía en cuenta las emisiones operativas.

**12. ¿Es obligatorio adelantar credenciales para obtener métricas de sostenibilidad?**

Recomendamos tener activadas las credenciales anticipadas para realizar cálculos más precisos. Si están activadas, Cloudability tendrá en cuenta los niveles de utilización reales de los servicios soportados; de lo contrario, consideraremos una utilización por defecto del 50% para los cálculos.

**13. He comparado la métrica de emisiones de carbono de Cloudability con las emisiones de CSP y las cifras no coinciden, ¿qué debo hacer?**

No recomendamos comparar las emisiones, ya que las metodologías, la granularidad de los datos y los alcances de las emisiones pueden ser diferentes. Para más información sobre exclusiones e inclusiones, consulte [Cloudability 's Cloud Sustainability Methodology](cloud_sustainability_methodology.html).

**14. ¿Se necesitan permisos para acceder a los informes de sostenibilidad?**

No se requieren permisos adicionales para utilizar los informes de sostenibilidad. La función de generación de informes está disponible para todos los usuarios y clientes de Cloudability Standard y Premium.

- **[Metodología de sostenibilidad de la nube](../product/cloud_sustainability_methodology.html)**
