---
concept: "Quickstart (acceso, prerequisitos, primeros 60 minutos, y criterio para pasar a configuración detallada)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-benchmarking
status: draft
generated_from:
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-audience-purpose.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-prerequisites.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-accessing-benchmarking.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-navigating.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-first-60-minutes-benchmarking.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-when-move-detailed-configuration.md
last_updated: "2026-07-12"
---
# Quickstart — Cómo IBM Apptio Benchmarking Aborda Esta Capacidad

## El concepto

Entre "tenemos la licencia de Benchmarking" y "tenemos una comparación creíble que mostrarle a un stakeholder" hay una distancia que, sin una ruta clara, puede convertirse en semanas de indecisión sobre por dónde empezar. El Quickstart resuelve exactamente ese problema: define el camino más corto y repetible desde el primer login hasta una vista de benchmark defendible, dejando la configuración fina y la gobernanza para después.

## Cómo lo resuelve IBM Apptio Benchmarking

**Objetivo explícito y acotado.** El documento es deliberadamente modesto en su ambición: el objetivo es ir de "puedo iniciar sesión" a "puedo mostrar una vista de benchmark que tiene sentido" en un camino corto y repetible — no llegar a una configuración perfecta el primer día. Esto es un punto de expectativas importante para fijar con el cliente al inicio de cualquier engagement de implementación.

**Tres prerrequisitos mínimos, con una salida honesta para datos incompletos:**

- **Acceso al producto** — Interactive Benchmarking debe estar aprovisionado en Frontdoor; si no aparece el botón correspondiente, hay que contactar al punto de contacto de IBM Apptio (nada que un TBMA pueda resolver por su cuenta).
- **Datos organizacionales mínimos** — revenue anual y headcount/FTE para el alcance de la organización de TI, más industria y región.
- **Datos de costo de TI** — gasto anual por Cost Pool y por Resource Tower como mínimo; el nivel de Sub-Tower es opcional pero recomendado.

El documento es explícito y repetido en un punto clave: **se puede arrancar con benchmarks de Industria y OpEx sin datos de volumen de infraestructura**, y agregar infraestructura después. Esto reduce la barrera de entrada para clientes con madurez de datos limitada — un argumento útil cuando alguien objeta "no tenemos inventario de infraestructura completo todavía".

**Acceso vía dos rutas equivalentes** — directo a `itbmx.apptio.com`, o vía Access Administration (`frontdoor.apptio.com`) haciendo clic en el botón de Interactive Benchmarking. El nivel de permiso mínimo requerido es `ViewInteractiveBenchmarksAndCostData`; para completar toda la configuración inicial se necesitan además `ConfigureInteractiveBenchmarking` y `RetrieveInteractiveBenchmarkingCostData` — un detalle operativo concreto para anticipar en la solicitud de accesos antes de la sesión de kickoff.

**Navegación estructurada en cuatro colecciones de reporte principales**, cada una con sus propios tabs:

- **Industry Benchmarks** — IT Spend as % of Revenue, IT Spend as % of OpEx, % OpEx Spend, IT Spend per Employee, IT FTEs as % of Employees.
- **IT OpEx Benchmarks** — By Cost Pool, y By Resource Tower/Sub-Tower (con un selector que permite enfocarse en "Overall" o en un Resource Tower específico como Application).
- **Infrastructure Benchmarks** — Unit Costs y FTE Efficiency, filtrables por Resource Sub-Tower.
- **Configuration** — seis tabs: Organization Profile (revenue/OpEx/FTEs), Apptio Source (proyecto de Costing y validación de conexión), Cost Data, Volumes, FTEs, y Advanced (versión ATUM/TBM y moneda).

**Un walkthrough de "primeros 60 minutos", concreto y secuencial, pensado para el Admin/TBMA responsable de la configuración inicial:**

1. **Ubicar Settings > Configuration** — el punto de partida para todo lo que sigue.
2. **Cargar el perfil organizacional** — revenue anual, OpEx anual, y FTEs, **siempre de forma manual** (no se jala de Costing). La guía es explícita: usar el año fiscal más reciente completado (no un forecast), alinear el alcance de revenue con el alcance real de costo de TI (no usar revenue global si TI solo soporta Norteamérica), y aceptar que el primer objetivo es ser "direccionalmente correcto" — las estimaciones aproximadas son aceptables en esta etapa.
3. **Cargar costo de TI, volúmenes y FTEs, por una de dos rutas** — **Ruta 1 (recomendada): conectar con Costing**, seleccionando el proyecto primario y el período fiscal base, tras lo cual Benchmarking jala automáticamente el costo anual por Cost Pool y Resource Tower/Sub-Tower desde el ambiente de producción. **Ruta 2: carga manual**, si Costing no está listo o no se usa. Independientemente de la ruta, el documento insiste en dos validaciones cruzadas antes de continuar: que el costo total cargado concilie con Finanzas para el año seleccionado, y que todas las torres mayores esperadas tengan valores no-cero.
4. **Correr una comparación de benchmark básica** — elegir hasta tres peer groups (industria similar, banda de revenue similar, región apropiada), abrir la vista de Industry Benchmarks y verificar que la métrica propia aparezca en el gráfico (marcada con líneas punteadas), revisar distribuciones de OpEx por Cost Pool/Tower, y si hay datos de infraestructura, revisar costos unitarios y eficiencia de FTE. La instrucción explícita es no estar "afinando" en este punto, solo buscando problemas obvios: gráficos en blanco, números fuera de magnitud, o filtros de peer group que no coinciden con la historia que se quiere contar.
5. **Guardar y compartir las vistas iniciales** — un paquete mínimo de arranque de tres gráficos: una vista de Industria (IT spend vs. revenue), una distribución de OpEx (por Cost Pool o Resource Tower), y una vista de Infraestructura si está disponible (idealmente una torre donde se sospechen brechas interesantes). El mensaje explícito es que el objetivo no es la perfección, sino tener un conjunto pequeño y consistente de vistas para iterar.

**Criterio explícito para saber cuándo "graduarse" del quickstart hacia configuración detallada** — cuando se puede abrir Interactive Benchmarking de forma confiable, mostrar al menos una vista de Industria y una de OpEx con valores sensatos, explicar el peer group y período usado, y defender a un nivel básico qué está incluido en las métricas mostradas. En ese punto se recomienda pasar a Configuration Guide (para refinar versión TBM/ATUM, alineación de volúmenes de infraestructura, y selecciones de peer group) y a Using Benchmarking Reports (para construir mejores narrativas). El documento cierra con una advertencia de disciplina de proyecto: **no sobre-diseñar esta etapa** — llegar a una línea base usable y luego iterar con mejor mapeo y gobernanza, en vez de intentar que todo sea perfecto el primer día.

## Por qué importa en una conversación de cliente

Este Quickstart es, literalmente, el guion de la primera sesión de trabajo con el cliente en cualquier implementación de Benchmarking — se puede usar casi verbatim como agenda de un taller de medio día. El punto sobre "las estimaciones aproximadas son aceptables al inicio" es valioso para desbloquear clientes perfeccionistas que retrasan el arranque esperando datos perfectos. Y el criterio explícito de "cuándo graduarse" da una forma concreta y objetiva de medir el éxito de la primera fase de un engagement, en vez de dejarlo a un juicio subjetivo de "ya quedó bien configurado".

## Documentos fuente

- Audience and purpose — `02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-audience-purpose.md`
- Prerequisites — `02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-prerequisites.md`
- Accessing Benchmarking — `02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-accessing-benchmarking.md`
- Navigating — `02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-navigating.md`
- "First 60 minutes" with Benchmarking — `02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-first-60-minutes-benchmarking.md`
- When to move on to detailed configuration — `02-product-docs/tbm-apptio/apptio-benchmarking/en/quickstart-when-move-detailed-configuration.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
