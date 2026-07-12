---
tbm_concept: "Optimize — Turbonomic (visibilidad de acciones de Application Resource Management directamente dentro de Cloudability, con inversiones necesarias vs. ahorros potenciales)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/optimize-turbonomic.md
last_updated: "2026-07-09"
---
# Optimize — Turbonomic — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

**Aclaracion de empaquetamiento importante, a comunicar explicitamente en cualquier conversacion de alcance**: IBM Turbonomic NO es una capacidad incluida en el empaquetamiento o licencia de IBM Cloudability Standard. Es un producto separado del portafolio IBM, con su propia licencia, instalacion e infraestructura. Lo que Cloudability Standard ofrece es una **integracion** -- la capacidad de conectar una instancia de Turbonomic ya desplegada (adquirida por separado) y visualizar sus acciones de optimizacion directamente dentro de la interfaz de Cloudability, sin necesitar que el usuario cambie de herramienta para verlas. Un cliente que no tenga ya IBM Turbonomic licenciado no obtiene esta funcionalidad simplemente por tener Cloudability Standard.


Rightsizing (Capítulo 10) genera sus propias recomendaciones basadas en datos históricos de utilización. Turbonomic aporta un enfoque complementario y en tiempo real: un modelo de **Application Resource Management (ARM)** que corre continuamente, representando el entorno completo como una cadena de suministro de compradores y vendedores de recursos, anticipando riesgos antes de que ocurran, no solo reaccionando a patrones ya observados.

## Cómo lo resuelve IBM Cloudability Standard

**El modelo conceptual de Turbonomic, con su propia metáfora económica.** Representa el entorno como un mercado: los **compradores** (ej. VMs) tienen un presupuesto para buscar los recursos que sus aplicaciones necesitan; los **vendedores** (ej. hosts) fijan precio a su CPU, memoria, almacenamiento y otros recursos disponibles según utilización en tiempo real. Este equilibrio de mercado mantiene las aplicaciones en estado óptimo, corriendo 24/7/365, escalando con entornos complejos de nube y Kubernetes.

**La combinación Cloudability + Turbonomic da la solución FinOps más completa documentada explícitamente**: permite a los equipos de infraestructura y de aplicación maximizar resultados de negocio a través de nube y Kubernetes, con las recomendaciones de Turbonomic surgiendo directamente dentro de la interfaz de Cloudability — sin necesidad de que el usuario cambie de herramienta para verlas.

**Dos gráficos centrales en el dashboard de Turbonomic dentro de Cloudability:**

- **Necessary Investments** — el costo total acumulado de todas las acciones pendientes que Turbonomic identifica como necesarias para evitar riesgo de performance (ej. escalar una VM que corre riesgo de degradación). Muestra cómo esas acciones se traducen en un incremento de gasto proyectado (costos on-demand incluidos), desglosable por tipo de acción/entidad y por entidad individual, ordenado de mayor a menor costo.
- **Potential Savings** — el ahorro total acumulado si se ejecutan todas las acciones pendientes identificadas por el análisis de Turbonomic, incluyendo un tipo de acción documentado con detalle: **discount optimization actions** — cuando una acción de escalado libera capacidad en una instancia con descuento, esa capacidad puede reasignarse a otra VM; estas acciones específicas **no las ejecuta el usuario de Turbonomic**, reflejan una reasignación de capacidad que realiza directamente el proveedor de nube.

Ambos gráficos permiten filtrar haciendo clic en un tipo de acción específico (ej. "Scale Volumes") y navegar con "View in Turbonomic" — que abre la instancia real de Turbonomic en una pestaña separada del navegador.

**Dos limitaciones documentadas explícitamente en el FAQ**: las **Views de Cloudability no están soportadas** en esta página específica, y **"View in Turbonomic" no tiene single sign-on** — el usuario debe autenticarse por separado con sus credenciales de Turbonomic al navegar hacia esa instancia.

## Por qué importa en una conversación con el cliente

La distinción entre Necessary Investments (costo de evitar riesgo de performance) y Potential Savings (ahorro de ejecutar optimizaciones) es un marco de comunicación ejecutiva poderoso — permite presentarle a liderazgo una vista balanceada de "cuánto necesitamos invertir para no tener problemas" junto con "cuánto podemos ahorrar", en lugar de solo un número de ahorro aislado sin contexto de riesgo.

Las discount optimization actions son un detalle técnico sutil que vale la pena explicar a cualquier cliente que vea esta categoría de ahorro y se pregunte por qué Turbonomic no le muestra un botón para "ejecutarla" — es una reasignación que hace el proveedor de nube automáticamente, no una acción manual del usuario.

La ausencia de single sign-on hacia Turbonomic es un detalle operativo a anticipar en cualquier despliegue conjunto — vale la pena confirmar en el discovery si el cliente tiene o planea tener credenciales separadas gestionadas para ambos sistemas, o si esto genera fricción de adopción que valga la pena resolver de otra forma.

## Documentos fuente

- Turbonomic — `kb/02-product-docs/apptio-cloudability-standard/en/optimize-turbonomic.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
