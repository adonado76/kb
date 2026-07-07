---
tbm_concept: "Products (TCO de producto, gobernanza de ciclo de vida producto, jerarquías de portafolio personalizables)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/product-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/product-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/product-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/product-tco-overview.md
last_updated: "2026-07-05"
---
# Products — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Hallazgo arquitectónico: Products no es un objeto nuevo, es una clasificación

A diferencia de todos los módulos anteriores, **Product no introduce un objeto de costo propio en el modelo** — se implementa marcando registros existentes en la misma tabla **All Business Services** (la que ya vimos en Services) con **Service Offering Type = Product**. Es decir, Products y Services comparten la misma estructura de datos subyacente; la diferencia es puramente de clasificación y de cómo se agrupan y reportan esos registros. Esto explica por qué el Model Review Report de Products específicamente filtra por la condición **"Is Product = Yes"** para trazar el flujo de costo.

**Los prerrequisitos de Product TCO son los más extensos vistos en todo el proyecto hasta ahora**: CTF-Cost Source, CTF-Labor, CTF-IT Towers, CT Apps-Applications, CT Apps-Services, **y CT-Business Units**. Esto sitúa a Products en la cima de la cadena de dependencias del módulo Applications and Services — necesita que Applications, Services y Business Units ya estén configurados antes de poder activarse con sentido completo.

## El concepto

A medida que las organizaciones migran de modelos de entrega basados en servicio hacia modelos operativos centrados en producto, los modelos de costeo tradicionales (enfocados en servicios) dejan una brecha de visibilidad real: no hay una forma consistente y defendible de ver el costo total de un producto tecnológico específico, alineado a cómo lo gestionan realmente los equipos de producto modernos (con roadmap, financiamiento e iteración continua).

## Cómo lo resuelve Apptio Costing Standard

**Tres casos de uso**, con énfasis en flexibilidad organizacional: Product Cost and Driver Visibility (costo continuo y sus drivers a través de labor, vendors, herramientas e iniciativas), Product Lifecycle and Investment Management (gestionar recursos a través de ideación → desarrollo → mantenimiento → retiro, para rebalancear inversión hacia crecimiento), y **Customizable Product and Portfolio Hierarchies** — jerarquías flexibles y específicas por rol que muestran información relevante para distintos stakeholders manteniendo gobernanza y consistencia.

**Cinco reportes**, con una progresión clara de gobierno de datos a análisis de negocio:
- **Products Review** — resumen de costos de producto con desglose jerárquico OpEx/CapEx en múltiples niveles de agregación.
- **Products Portfolio** — comparte los mismos KPIs de alto nivel que Review, pero permite segmentar por jerarquía de producto específica y ver drivers de costo por unidad de negocio, aplicación, torre y proyecto.
- **Launched & Retired** — spend de productos recién lanzados y en proceso de retiro, identificando productos que se acercan o pasaron su fecha planeada de retiro — el equivalente para producto del reporte "New & Retired Apps" ya visto.
- **Product List** — vista centralizada de todos los productos con sus atributos, ubicación jerárquica y contexto financiero; sirve como fundación de gobernanza antes de cualquier análisis más profundo, e incluyó recientemente métricas de presupuesto.
- **Model Review Report** — trazabilidad de flujo de costo específica para Product TCO, filtrando por la condición "Is Product = Yes" del dataset All Business Services.

**Jerarquía de portafolio de cuatro niveles, personalizable, coexistiendo con la taxonomía estándar TBM.** Los productos se organizan en una jerarquía de hasta cuatro niveles definida por la organización, además de la taxonomía de Solución estandarizada de TBM — permitiendo comparar "cómo mi organización agrupa este producto" vs. "cómo lo agruparía la taxonomía TBM estándar", útil para detectar productos duplicados o mal clasificados.

**Instalación de dos componentes nuevos, disponibles solo en templates v120+**: Product TCO y Product TCO Reporting. La activación real es un paso de clasificación de datos, no de modelado: en la tabla All Business Services, se selecciona **Service Offering Type = Product** para los registros que deben tratarse como productos (en lugar de servicios genéricos).

**Preguntas de negocio que el propio producto documenta como las que este módulo responde** — un nivel de honestidad orientada a valor poco común en la documentación técnica: "¿cuál es el costo totalmente cargado del Producto X este período?", "¿dónde tenemos variación presupuestal?", "¿qué proyectos soportan directamente qué productos?", "¿qué vendor impacta más el costo de mi producto?", "¿qué productos se acercan a su fecha de retiro objetivo?", "¿tengo costos remanentes asociados a un producto ya retirado?".

## Por qué importa en una conversación con el cliente

La revelación de que Products es una clasificación sobre la misma estructura de Services (no un objeto nuevo) es información valiosa de discovery: si un cliente ya tiene Services funcionando bien, activar Products es relativamente rápido — es principalmente un ejercicio de reclasificación y configuración de jerarquía, no de reconstrucción del modelo de costo.

La cadena de prerrequisitos (Applications → Services → Business Units → Products) es la más larga documentada en todo el proyecto — vale la pena presentarla explícitamente como una hoja de ruta de madurez en cualquier conversación donde el cliente exprese interés en TCO de producto: hay un camino claro de qué activar primero, no es un salto directo.

La pregunta "¿tengo costos remanentes asociados a un producto ya retirado?" es un gancho de conversación extremadamente concreto para clientes en transformación de portafolio — descubrir que se sigue pagando por algo formalmente retirado es exactamente el tipo de hallazgo que justifica el proyecto completo de TBM ante un CFO escéptico.

## Documentos fuente

- Products Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/product-overview.md`
- Products Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/product-reports.md`
- Products Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/product-gs.md`
- IBM Apptio Product TCO Solution — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/product-tco-overview.md`

*Nota: no se encontraron links públicos de ibm.com/docs embebidos en esta categoría. Hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*