---
tbm_concept: "How to Use This Guide (audiencias, mapa de secciones, ruta por persona, checklist de implementación)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-benchmarking
status: draft
generated_from:
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-who-this-is.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-what-each-section-covers.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-where-start-by-persona.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-conventions-used-in-this.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-implementation-checklist.md
last_updated: "2026-07-12"
---
# How to Use This Guide — Cómo IBM Apptio Benchmarking Aborda Esta Capacidad

## El concepto

La documentación completa de Benchmarking cubre desde conceptos de negocio hasta troubleshooting técnico detallado — un volumen que ningún stakeholder necesita leer de principio a fin. Esta sección resuelve un problema práctico de adopción: decirle a cada tipo de usuario (TBMA, ejecutivo patrocinador, dueño de Resource Tower) exactamente qué leer primero, y darle al equipo de implementación un checklist accionable que convierte "tenemos la licencia" en "tenemos una comparación creíble en producción".

## Cómo lo resuelve IBM Apptio Benchmarking

**Dos audiencias claramente diferenciadas.** La audiencia primaria — quienes configuran y operan la herramienta día a día — son TBM Analysts, IT Finance/ITFM Analysts y Admins. La audiencia secundaria — quienes consumen los resultados — son CIO, CTO, CFO, VPs de Finanzas/Infraestructura, y los dueños de Producto/Servicio/Resource Tower. Esta distinción importa en una conversación de habilitación con el cliente: el entrenamiento operativo va dirigido a un grupo pequeño y técnico, mientras que el resto de la organización solo necesita saber interpretar lo que ve en pantalla.

**Diez secciones con propósito específico, resumidas como mapa de navegación:** Overview & Key Concepts (qué es y cómo encaja con Costing/TBM), Implementation Checklist (pasos prácticos), Quickstart (primer acceso), Configuration Guide (cableado detallado), Using Benchmarking Reports (cómo leer y aplicar las vistas), Data & Methodology Reference (de dónde vienen los benchmarks y cómo se calculan), Operations & Governance (cómo correrlo como parte del programa TBM), Troubleshooting & FAQ, y los dos apéndices (Glosario, Versión/Compatibilidad). Este mapa es útil tal cual para estructurar el índice de cualquier entregable de habilitación al cliente.

**Ruta de lectura diferenciada por persona — un atajo de valor inmediato para consultoría:**

- **TBMAs / ITFMAs / Admins** — empiezan por Overview & Key Concepts y Quickstart; usan como referencia continua el Implementation Checklist, Data & Methodology Reference y Troubleshooting & FAQ; consultan Operations & Governance para contexto de programa y stakeholders.
- **Ejecutivo o patrocinador (CIO/CTO/CFO/VP)** — empieza por Overview & Key Concepts y Using Benchmarking Reports; va a Operations & Governance para entender cómo se mide su Resource Tower y cómo se fijan metas; va a Data & Methodology Reference solo si tiene preguntas puntuales sobre definiciones de métricas.
- **Dueño de Resource Tower / Domain Lead** (Infra, End User, Network, etc.) — misma ruta que el ejecutivo, ya que su interés principal es entender cómo se mide su torre específica.
- **Cuando algo se ve mal** — cualquier persona empieza directo en Troubleshooting & FAQ, y de ahí navega a Configuration Guide o Data & Methodology Reference según el tipo de problema.

**Convenciones de nomenclatura explícitas, útiles para evitar ambigüedad en documentos de cliente:** "Costing" siempre se refiere al producto anteriormente conocido como Cost Transparency; "IBM Apptio Benchmarking" e "Interactive Benchmarking" se usan como sinónimos del producto en general; "reportes benchmark-enabled" se refiere específicamente a los reportes dentro de Costing que incluyen valores de benchmark junto a los datos reales; y "TBM" y "ATUM" se usan intercambiablemente al hablar de Cost Pools, Resource Towers y Sub-Towers, ya que ATUM es la implementación de Apptio del modelo TBM estándar.

**Un checklist de implementación de cuatro fases, diseñado para llevar a un cliente de cero a un piloto gobernado:**

1. **Antes de empezar** — confirmar visibilidad de producto en Frontdoor, identificar el proyecto de Costing que actuará como sistema de registro (si aplica integración), y asignar roles clave: TBM/ITFM Program Lead, TBMA propietario de Benchmarking, admin de plataforma, y dueños de Resource Tower relevantes.
2. **Preparación de datos** — perfil organizacional completo (revenue anual, FTE, industria, región/tamaño), gasto de TI de al menos un año completo mapeado a Cost Pools y Resource Towers, y — si se van a usar benchmarks de infraestructura — volúmenes por Sub-Tower (servidores, TB de storage, puertos de red, FTEs de funciones de infra). El documento aclara explícitamente que si no se puede completar el ítem de infraestructura, aun así se puede arrancar con benchmarks de Industria y OpEx y agregar infraestructura después — un punto útil para no bloquear un piloto por falta de datos de volumen.
3. **Entorno y configuración** — acceso verificado, versión TBM alineada con el proyecto de Costing, perfil organizacional configurado, datos de costo conectados o cargados, datos de infraestructura configurados si aplica, y peer group por defecto definido y documentado para reutilización en reportes ejecutivos.
4. **Validación y primer uso** — pruebas de humo en las vistas core (Industria, OpEx, al menos una métrica de infraestructura), chequeos de sanidad (que el gasto total concilie con Finanzas, que no haya outliers de 10x por errores de unidad), un paquete inicial de 3-5 gráficos para stakeholders con narrativa de "dónde estamos en línea / dónde diferimos / dónde vamos a investigar más", y una sesión introductoria formal con el patrocinador donde se documenten decisiones sobre métricas a rastrear y cadencia de revisión.

El checklist cierra con gobierno y operación continua: cadencia acordada (anual para refresh completo, trimestral para revisión en QBR, ad hoc para casos de negocio), políticas de cambio que requieren aprobación del TBM Lead (cambiar versión TBM, cambiar el proyecto de Costing primario, cambiar el peer group por defecto), y un documento de una página que resume la configuración vigente (proyecto de Costing usado, versión TBM, peer group por defecto, cadencia de refresh, notas de mapeo para decisiones de alcance no obvias).

## Por qué importa en una conversación de cliente

El checklist de implementación es, en sí mismo, un artefacto de entregable de consultoría casi listo para usar — se puede convertir directamente en un plan de proyecto o en una lista de verificación de go-live para un engagement de implementación de Benchmarking. La ruta de lectura por persona también resuelve un problema común en proyectos de habilitación: evita que se le entregue documentación técnica completa a un ejecutivo que solo necesita entender los reportes, y viceversa, evita que el TBMA reciba solo el resumen ejecutivo cuando necesita el detalle de configuración. Finalmente, la nota de que "se puede empezar con Industria y OpEx sin datos de infraestructura" es un argumento útil de reducción de fricción cuando un cliente potencial duda de tener la madurez de datos suficiente para arrancar.

## Documentos fuente

- Who this guide is for — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-who-this-is.md`
- What each section covers — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-what-each-section-covers.md`
- Where to start by Persona — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-where-start-by-persona.md`
- Conventions used in this guide — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-conventions-used-in-this.md`
- Implementation Checklist — `02-product-docs/tbm-apptio/apptio-benchmarking/en/guide-implementation-checklist.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
