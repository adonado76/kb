---
concept: "Concepts: TBM Fundamentals — la disciplina TBM, su taxonomía de cuatro capas, casos de uso estándar, metodologías de asignación, y el modelo de madurez de cuatro niveles"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/fundementals-introduction-technology-business-management.md
  - kb/02-product-docs/apptio-tbm-studio/en/fundementals-tbm-taxonomy.md
  - kb/02-product-docs/apptio-tbm-studio/en/fundementals-common-tbm-use-cases.md
  - kb/02-product-docs/apptio-tbm-studio/en/fundementals-cost-allocation-methodologies.md
  - kb/02-product-docs/apptio-tbm-studio/en/fundementals-tbm-maturity-model.md
last_updated: "2026-07-07"
---
# Concepts: TBM Fundamentals — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

Este capítulo es, de las 21 categorías de este proyecto, la única que documenta la **disciplina TBM en sí misma** — no una capacidad del producto, sino el marco metodológico que TBM Studio implementa. Es el material fundacional correcto para cualquier conversación de discovery con un cliente que aún no domina el vocabulario TBM.

## Cómo lo resuelve Apptio TBM Studio

**Qué es TBM, en la definición del propio documento**: una disciplina que da a los líderes de TI un marco estandarizado para entender, comunicar y optimizar el costo y valor de los servicios de TI — un "idioma común" entre tecnología y negocio. Cuatro problemas de negocio que resuelve, documentados explícitamente: falta de transparencia (miles de líneas de costo sin estructura), incentivos desalineados (infraestructura compartida tratada como "gratis" por quien la consume), decisiones de trade-off difíciles (balancear "correr el negocio" vs. innovación sin datos), y brechas de responsabilidad (nadie es dueño del costo end-to-end de un servicio).

**TBM la disciplina vs. TBM Studio la herramienta** — una distinción explícita que el propio producto hace, y que vale la pena preservar en cualquier conversación de cliente: TBM es la metodología (agnóstica de herramienta); TBM Studio es una implementación tecnológica de esa metodología.

**La taxonomía TBM de cuatro capas, con un ejemplo numérico completo documentado:**

1. **Cost Pools** — dónde se origina el costo (Hardware, Software, Labor), correspondiente típicamente a cuentas del libro mayor.
2. **IT Towers** — cómo se organiza el costo en categorías tecnológicas funcionales (Compute, Storage, Network, End-User Computing, Application Development, IT Management, Security) — los "bloques de construcción" de la entrega de TI.
3. **IT Services and Applications** — qué entrega TI en términos que un stakeholder no técnico entiende (CRM, ERP, Email) — donde el costo se vuelve significativo para el negocio.
4. **Business Units and Consumers** — quién consume esos servicios — la capa que habilita showback y chargeback.

**Ejemplo de flujo de datos a través de las capas**: $10M de costo de hardware de servidor entra desde el libro mayor → se asigna a la torre Compute según propósito del servidor (producción/desarrollo/pruebas) → se asigna a servicios (CRM recibe $3M, ERP $4M, Email $1.5M, Otro $1.5M) según métricas de uso de servidor → el $3M de CRM se asigna a Sales ($1.8M), Marketing ($0.9M) y Support ($0.3M) según conteo de usuarios. El modelo es flexible: organizaciones pueden agregar capas (sub-torres), personalizar categorías, simplificar (combinar u omitir capas), o usar rutas de asignación distintas según el tipo de costo.

**Cinco casos de uso estándar de TBM:**
- **Showback** — comunicar costo sin facturar; informativo, sin consecuencia financiera. Apropiado para organizaciones nuevas en TBM o modelos aún no validados.
- **Chargeback** — facturar realmente, transfiriendo presupuesto vía journals o cargos inter-compañía. Requiere modelos de costo maduros y validados, y que las unidades de negocio ya hayan aceptado responsabilidad.
- **Cost Optimization** — usar los datos TBM para identificar redundancia, right-sizing, y consolidación de proveedores.
- **Benchmarking** — comparar contra líneas base internas, pares de industria, o estándares — responde "¿estamos gastando la cantidad correcta?"
- **Budgeting and Forecasting** — presupuesto de abajo hacia arriba a nivel de servicio individual, en lugar de "el gasto del año pasado más un porcentaje".

**Metodologías de asignación de costo, en orden de complejidad creciente:**
- **Direct Allocation** — costo atribuible exclusivamente a un solo destino, relación uno a uno, sin necesidad de repartir.
- **Indirect Allocation** — costo compartido entre múltiples destinos, requiere un método para determinar la porción justa de cada uno.
- **Driver-Based Allocation** — un *driver* es la métrica medible que determina cómo se distribuye el costo compartido, respondiendo "¿por qué este consumidor recibe esta porción?"
- **Activity-Based Costing (ABC)** — el método de mayor precisión: identifica las actividades discretas involucradas en la entrega del servicio y asigna costo según el volumen de cada actividad consumida — apropiado para servicios de alto costo o críticos, dado su esfuerzo de mantenimiento significativamente mayor.

**El trade-off complejidad vs. precisión está resuelto con una recomendación explícita**: empezar con métodos más simples (headcount, incluso ingresos) y progresar hacia drivers basados en consumo más precisos a medida que madura la práctica TBM — con la ventaja técnica de que TBM Studio soporta ese cambio de driver **sin reestructurar el modelo**.

**El Modelo de Madurez TBM — cuatro niveles, con la pregunta clave y el área de producto asociada a cada uno:**

| Nivel | Enfoque | Pregunta clave | Áreas de TBM Studio |
|---|---|---|---|
| 1. Visibility | Saber cuánto se gasta | ¿Cuánto cuesta TI? | Data Studio, reportes básicos |
| 2. Transparency | Entender hacia dónde fluye el costo | ¿En qué estamos gastando? | Model Studio, vistas Sankey |
| 3. Optimization | Reducir y optimizar costo | ¿Dónde podemos ahorrar? | Métricas calculadas, chargeback, drill-through |
| 4. Value | Alinear TI con valor de negocio | ¿Qué valor entrega TI? | Plataforma completa + integraciones API |

## Por qué importa en una conversación con el cliente

Este capítulo es el material correcto para la primera reunión con un cliente que necesita entender TBM antes de evaluar cualquier herramienta — la tabla del Modelo de Madurez es especialmente útil como herramienta de diagnóstico: preguntarle al cliente en qué nivel se ubica hoy determina directamente qué capacidades de TBM Studio priorizar primero.

La progresión Showback → Chargeback es un argumento de secuenciación de adopción ya visto repetidamente en otros productos del portafolio (Costing Standard, Billing) — confirma que esta filosofía de madurez incremental no es específica de un producto, sino un principio central de toda la práctica TBM que IBM promueve.

El trade-off explícito complejidad/precisión en metodologías de asignación (con la recomendación de empezar simple y progresar) es un argumento de gestión de expectativas importante para cualquier cliente que inicialmente pida el máximo de precisión (ABC) para todo su modelo — vale la pena mostrar el ejemplo de $10M para ilustrar cómo funciona la cascada de asignación de forma concreta, antes de discutir qué nivel de sofisticación necesita cada servicio específico.

## Documentos fuente

- Introduction to Technology Business Management — `kb/02-product-docs/apptio-tbm-studio/en/fundementals-introduction-technology-business-management.md`
- The TBM Taxonomy — `kb/02-product-docs/apptio-tbm-studio/en/fundementals-tbm-taxonomy.md`
- Common TBM Use Cases — `kb/02-product-docs/apptio-tbm-studio/en/fundementals-common-tbm-use-cases.md`
- Cost Allocation Methodologies — `kb/02-product-docs/apptio-tbm-studio/en/fundementals-cost-allocation-methodologies.md`
- TBM Maturity Model — `kb/02-product-docs/apptio-tbm-studio/en/fundementals-tbm-maturity-model.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
