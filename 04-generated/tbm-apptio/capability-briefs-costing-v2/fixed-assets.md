---
concept: "Fixed Assets (depreciación, ciclo de vida de activos capitalizados, tracking de valor remanente)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/fa-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/fa-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/fa-getstart.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-fa-component.md
last_updated: "2026-07-05"
---
# Fixed Assets — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

Los activos fijos de TI — servidores, equipos, infraestructura — representan típicamente una porción significativa de la inversión tecnológica, pero a diferencia del gasto operativo, su costo no se reconoce de una sola vez sino a lo largo de su vida útil vía depreciación. Sin un tracking consistente de capitalización, depreciación y utilización, una organización corre el riesgo de un retorno de inversión pobre, costos de mantenimiento más altos de lo necesario, y oportunidades de optimización que pasan desapercibidas — por ejemplo, activos completamente depreciados que siguen en uso sin que nadie lo note, o activos subutilizados que podrían retirarse antes.

## Cómo lo resuelve Apptio Costing Standard

**Un solo caso de uso estándar, muy concreto: Depreciation Management.** Rastrea el costo de capital, la depreciación mensual y la depreciación remanente de los activos de TI, dando soporte a reporte financiero preciso y asignación de costo. Un segundo caso de uso — **Asset Lifecycle Management** (rastrear activos a través de adquisición, uso, envejecimiento y fin de vida) — está documentado explícitamente como personalizado, no estándar.

**Un reporte central: Fixed Assets.** Da visibilidad detallada a activos depreciados y en proceso de depreciación, con información de clase, edad, ubicación, torre de recursos TI, proveedor, tipo y categoría de activo, junto con métricas de depreciación. Dirigido a IT Finance y Service Owners, permite identificar activos completamente depreciados y cerca del fin de su vida útil, entender la depreciación remanente de activos activos por rango de edad, y monitorear tendencias de depreciación OpEx año a la fecha.

**Un componente, con una lista de campos requeridos inusualmente extensa y específica.** El componente CTF-Fixed Assets requiere, como prerrequisito, CTF-Cost Source. La lista de campos **requeridos** para que los reportes estándar funcionen es larga y precisa: Acquisition Date, Age, Asset Count, Asset Number, Class, Cost Center (recomendado), Depreciation Amount, Description, Fixed Asset Depreciation LIM, Fixed Asset Initial Cost, Fixed Asset Ledger ID, In Service, In Service Date, IT Resource Sub-Tower, IT Resource Tower, Location, Object Identifier, y Vendor. Este nivel de detalle en campos requeridos (vs. recomendados) es más granular que lo visto en otros módulos hasta ahora, y vale la pena tenerlo a mano durante el discovery de datos.

**Fuentes de datos típicas.** Sistemas de gestión de activos empresariales o CMDBs: SAP Enterprise Asset Management, Oracle, PeopleSoft, BMC Asset Management/Atrium CMDB, ServiceNow Asset Management, Workday Financial Management — además de opciones adicionales documentadas en la guía de configuración del componente (HP Univ Config Mgmt, Sage, AssetWorks, CA Unicenter, Lawson). Normalmente se carga un único dataset de activos fijos, anexado y mapeado a la tabla Fixed Asset Master Data.

## Por qué importa en una conversación con el cliente

La lista extensa de campos requeridos es un dato concreto y útil para calibrar expectativas de esfuerzo de implementación desde el discovery inicial: si el cliente no tiene un registro de activos fijos con ese nivel de detalle (fecha de puesta en servicio, torre de recursos IT, ID de ledger), hay trabajo de preparación de datos antes de poder activar los reportes estándar — vale la pena preguntarlo temprano, no descubrirlo a mitad de la implementación.

La distinción entre el caso de uso estándar (Depreciation Management) y el personalizado (Asset Lifecycle Management completo, incluyendo fin de vida) es útil para conversaciones de alcance: la version out-of-the-box responde "cuánto vale este activo hoy y cuánto se deprecia cada mes", pero no necesariamente "cuándo deberíamos retirarlo" — esa pregunta más estratégica requiere trabajo de personalización adicional.

Esta capacidad conecta directamente con el principio ya documentado en la base de conocimiento de Apptio Planning: la transición de CapEx a OpEx vía depreciación es el mismo concepto en ambos productos — Fixed Assets en Costing Standard consume y reporta sobre los actuals de esa depreciación, mientras Asset Planning en Planning la proyecta hacia adelante. Es un buen puente narrativo en conversaciones donde el cliente tiene o está considerando ambos productos.

## Documentos fuente

- Fixed Assets Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/fa-overview.md`
- Fixed Assets Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/fa-reports.md`
  - Fixed Assets: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-fixed-assets
- Fixed Asset Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/fa-getstart.md`
- CTF - Fixed Asset component: install and configure — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-fa-component.md`

*Nota: la URL de Fixed Assets es un link real embebido en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*