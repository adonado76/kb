---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Inventario de recursos"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
source_path: "product/resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Inventario de recursos

El Inventario de recursos permite crear una lista de recursos en la nube procedentes de varias cuentas, con diversas dimensiones y métricas. Al unificar los datos de facturación, utilización y metadatos descriptivos, podrás obtener una visión más completa del inventario de tus recursos.

## Casos de uso clave del inventario de recursos

1. **Correspondencia entre datos de costes y de utilización**

   **Solución:** Al combinar el inventario de recursos con las etiquetas sintéticas de Cloudability (dimensiones de etiquetas, grupos de cuentas y asignaciones empresariales), se pueden asignar con precisión los costes de los recursos. Por ejemplo, puedes consultar el uso exacto de la CPU y la memoria de una instancia concreta de Compute Engine perteneciente al «Equipo Alfa» y asignar su coste en consecuencia. Esto permite elaborar informes de rendición de cuentas sólidos para que los equipos puedan conocer su consumo, así como modelos de repercutición de costes bien fundamentados para la facturación interna.
2. **Reducción de residuos**

   **Reto:** Los recursos sobredimensionados generan gastos innecesarios en la nube. Identificar manualmente las instancias de Compute Engine o los discos gestionados que están infrautilizados lleva mucho tiempo y es propenso a errores.

   **Solución:** Aprovecha las métricas «Utilización de la CPU (media)», «Utilización de la memoria (media)» y «Memoria utilizada» del inventario. Identifica las instancias con un uso medio de la CPU o de la memoria que sea sistemáticamente bajo. En el caso de los discos gestionados, supervisa su tamaño en relación con los datos realmente almacenados para identificar oportunidades de reducir su tamaño.
3. **Optimización del rendimiento e identificación de cuellos de botella**

   **Reto:** Los recursos con una dotación insuficiente pueden provocar cuellos de botella en el rendimiento, lo que afecta a la capacidad de respuesta de las aplicaciones y a la experiencia del usuario. Para identificar la causa raíz se necesitan datos detallados sobre la utilización.

   **Solución:** Analiza la utilización de la CPU (máxima), la utilización de la memoria (máxima) y la utilización de la red (máxima). Los picos en estos indicadores podrían indicar la necesidad de aumentar los recursos. Estos datos te ayudan a optimizar de forma proactiva la asignación de recursos para garantizar un rendimiento óptimo de las aplicaciones.
4. **Resolución proactiva de problemas**

   **Reto:** Sin datos detallados a nivel de recursos, puede resultar difícil identificar los picos inesperados de costes o la disminución del rendimiento.

   **Solución:** Supervisa periódicamente las métricas de utilización que proporciona el Inventario de recursos. Los aumentos repentinos e inexplicables en la utilización de la CPU (mín.) o en la memoria utilizada en una instancia que, por lo demás, es estable, podrían indicar un proceso fuera de control, una configuración incorrecta o incluso un incidente de seguridad. Al configurar alertas basadas en estos indicadores, podrás detectar anomalías de forma temprana y tomar medidas correctivas antes de que afecten de manera significativa a los costes o a las operaciones.
5. **Gestión del ciclo de vida y gobernanza de los recursos**

   **Reto:** El seguimiento del ciclo de vida de los recursos en la nube, desde su puesta en marcha hasta su desactivación, puede resultar complejo, lo que da lugar a recursos «zombis» que generan costes sin aportar ningún valor.

   **Solución:** La «fecha de puesta en marcha de los recursos», junto con los indicadores de utilización, resulta de un valor incalculable. Identifica los recursos que llevan un tiempo prolongado en funcionamiento y que presentan una utilización persistentemente baja. Por ejemplo, una instancia de Compute Engine con una fecha de creación muy antigua y unos índices de utilización de CPU (media) y de memoria (media) constantemente bajos podría ser un recurso olvidado que se puede cerrar sin ningún problema. Este enfoque proactivo garantiza una mejor gestión de los recursos y evita gastos innecesarios.

Al ofrecer una visión unificada de tu inventario, que incluye métricas detalladas de utilización y metadatos esenciales, Cloudability te permite tomar decisiones basadas en datos, optimizar tu gasto en la nube y mejorar la eficiencia de tus operaciones en la nube.

- **[AWS Inventario de recursos](../product/aws-resource-inventory.html)**
- **[Azure Inventario de recursos](../product/azure-resource-inventory.html)**
- **[GCP Inventario de recursos](../product/gcp-resource-inventory.html)**
- **[Inventario de recursos de la OCI](../product/oci-resource-inventory.html)**
- **[Preguntas frecuentes sobre el inventario de recursos](../product/resource-inventory-faqs.html)**
