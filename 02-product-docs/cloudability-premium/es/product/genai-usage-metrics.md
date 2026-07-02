---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Comprender las métricas de uso de los servicios de GenAI en Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
source_path: "product/genai-usage-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Comprender las métricas de uso de los servicios de GenAI en Cloudability

Los servicios de IA generativa ( GenAI ), como **AWS Bedrock**, **Azure OpenAI** y **Google Vertex AI**, utilizan modelos de facturación distintos de los tradicionales de computación o almacenamiento. Cada proveedor mide el uso de formas distintas: tokens, caracteres u horas de cálculo. Cloudability le permite interpretar estos costes de forma coherente utilizando las métricas y dimensiones existentes.

## Principales tipos de cargas de trabajo

GenAI el uso se divide generalmente en dos categorías:

- Cargas de trabajo de inferencia
  - Utilización de modelos entrenados para generar texto, código o imágenes.
  - Unidades de facturación: fichas (≈ 4 caracteres) o caracteres procesados
  - Cloudability métrica: Aparece en Cantidad de uso
- Cargas de trabajo de formación o ajuste (trabajos informáticos intensivos que forman o adaptan modelos)
  - Unidades de facturación: GPU, TPU u horas de instancia
  - Cloudability métrica: Aparece bajo Horas de uso (o métricas de cómputo similares)

Nota: Comprender a qué categoría pertenece su carga de trabajo ayuda a interpretar lo que representa la métrica Cantidad de uso en sus informes.

## Cómo analizar el uso de GenAI en Cloudability

Utilice los informes de Cloudability para explorar cómo se están facturando sus servicios de GenAI.

Ejemplo de configuración:

| Paso | Qué añadir | Finalidad |
| --- | --- | --- |
| 1. | Métricas: Cantidad de uso, Coste no mezclado | Vea cuánto se consumió y cuánto costó |
| 2. | Dimensiones: Descripción del artículo, funcionamiento, nombre del servicio mejorado | Identifique cómo midió el uso el proveedor de la nube |
| 3. | Filtros: gpt, bedrock, vertex, openai, claude, mistral (nota: se trata de ejemplos y los filtros pueden variar en función del nombre del servicio o del producto) | Limite su informe al consumo relacionado con la IA |

**Ejemplo:** Crear un informe filtrando por Enhanced Service Name = AWS Bedrock. Añada Descripción del artículo y Operación como dimensiones y, a continuación, filtre por gpt o claude. Si ve "Cantidad de uso = 2000" y "Unidad = Tokens", eso equivale a 2.000 tokens (≈ 8.000 caracteres).

## Ejemplos por proveedor de nube

| Nombre del proveedor/servicio | Unidad de facturación típica | Cómo aparece en Cloudability |
| --- | --- | --- |
| AWS Bedrock | Señales | Cantidad de uso = 2000 → 2.000 tokens (≈ 8.000 caracteres). *Descripción del artículo* : Bedrock:Claude:InputTokens |
| AzureOpenAI / Fábrica de IA | 1K Fichas | Cantidad de uso = 100 → 100 × 1.000 = 100.000 fichas. La columna de unidades muestra “1K Tokens". |
| Google Vértice / Géminis | Caracteres | Cantidad de uso = 4.000 → ≈ 1.000 fichas. *Descripción del artículo* : VertexAI:TextInputCharacters |
| AWS Sagemaker | Horas de instancia | Puntos finales de formación e inferencia facturados por instancia-hora. |
| OCI GenAI | Unidad Horas, caracteres | Basado en caracteres para la inferencia; horas-unidad de IA para grupos dedicados. |
| IBM Watsonx | Unidades de suscripción | Rastreados como instancias o usuarios activos (por ejemplo, MAU, unidades agénticas). |

## Mejores prácticas de Fin Ops

- **Normalizar el uso:** Aproximadamente 4 caracteres = 1 ficha. Utilícelo para comparar distintos CSP.
- **Separar el cálculo de la inferencia:** Los costes de formación (horas de uso) difieren de la inferencia basada en la consulta (cantidad de uso).
- **Correlacionar coste y descripción:** Combine el coste no mezclado, la cantidad de uso y la descripción del artículo para identificar el uso y los costes
- **Agrupe lógicamente:** Utilice Nombre de servicio mejorado o Familia de uso para comparar los gastos de GenAI entre proveedores.

Nota: Construye una columna calculada para convertir caracteres a tokens - esto te ayuda a comparar Azure OpenAI, Vertex AI, y Bedrock en igualdad de condiciones.
