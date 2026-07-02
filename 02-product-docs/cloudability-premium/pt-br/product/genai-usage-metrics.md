---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Entenda as métricas de uso dos serviços GenAI em Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
source_path: "product/genai-usage-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Entenda as métricas de uso dos serviços GenAI em Cloudability

Os serviços de IA generativa ( GenAI ), como **AWS Bedrock**, **Azure OpenAI** e **Google Vertex AI**, usam modelos de faturamento que diferem da computação ou do armazenamento tradicionais. Cada provedor mede o uso de maneiras diferentes: tokens, caracteres ou horas de computação. Cloudability permite que você interprete esses custos de forma consistente usando métricas e dimensões existentes.

## Principais tipos de carga de trabalho

GenAI o uso geralmente se enquadra em duas categorias:

- Cargas de trabalho de inferência
  - Uso de modelos treinados para gerar texto, código ou imagens.
  - Unidades de faturamento: tokens (≈ 4 caracteres) ou caracteres processados
  - Cloudability métrica: Aparece em Quantidade de uso
- Cargas de trabalho de treinamento ou ajuste fino (trabalhos com uso intensivo de computação que treinam ou adaptam modelos)
  - Unidades de faturamento: GPU, TPU ou horas de instância
  - Cloudability métrica: Aparece em Horas de uso (ou métricas de computação semelhantes)

Observação: entender a que categoria sua carga de trabalho pertence ajuda a interpretar o que a métrica Quantidade de uso representa em seus relatórios.

## Como analisar o uso do GenAI em Cloudability

Use os relatórios do Cloudability para explorar como os serviços do GenAI estão sendo cobrados.

Exemplo de configuração:

| Passo | O que adicionar | Propósito |
| --- | --- | --- |
| 1. | Métricas: Quantidade de uso, custo não combinado | Veja quanto foi consumido e quanto custou |
| 2. | Dimensões: Descrição do item, operação, nome do serviço aprimorado | Identifique como o provedor de nuvem mediu o uso |
| 3. | Filtros: gpt, bedrock, vertex, openai, claude, mistral (observação: esses são exemplos e os filtros podem variar de acordo com o nome do serviço ou do produto) | Limite seu relatório ao consumo relacionado à IA |

**Exemplo:** Criar uma filtragem de relatório para Enhanced Service Name = AWS Bedrock. Adicione Item Description e Operation como dimensões e, em seguida, filtre por gpt ou claude. Se você vir "Usage Quantity = 2000" (Quantidade de uso = 2000) e "Unit = Tokens" (Unidade = Tokens), isso equivale a 2.000 tokens (≈ 8.000 caracteres).

## Exemplos por provedor de nuvem

| Nome do provedor/serviço | Unidade de faturamento típica | Como aparece em Cloudability |
| --- | --- | --- |
| AWS Bedrock | Tokens | Quantidade de uso = 2000 → 2.000 tokens (≈ 8.000 caracteres). *Descrição do item* : Bedrock:Claude:InputTokens |
| AzureOpenAI / Fundição de IA | 1K Fichas | Quantidade de uso = 100 → 100 × 1.000 = 100.000 tokens. A coluna Unit mostra “1K Tokens". |
| Google Vértice / Gêmeos | Caracteres | Quantidade de uso = 4.000 → ≈ 1.000 tokens. *Descrição do item* : VertexAI:TextInputCharacters |
| AWS Sagemaker | Horas da instância | Endpoints de treinamento e inferência cobrados por instância-hora. |
| OCI GenAI | Unidade Horas, caracteres | Baseado em caracteres para inferência; horas de unidade de IA para clusters dedicados. |
| IBM Watsonx | Unidades de subscrição | Rastreados como instâncias ou usuários ativos (por exemplo, MAUs, unidades agênticas). |

## Práticas recomendadas de Fin Ops

- **Normalizar o uso:** Aproximadamente 4 caracteres = 1 token. Use isso para fazer comparações entre CSPs.
- **Separe a computação da inferência:** Os custos de treinamento (horas de uso) diferem da inferência baseada em solicitações (quantidade de uso).
- **Correlacionar custo e descrição:** Combine o custo não combinado, a quantidade de uso e a descrição do item para identificar o uso e os custos
- **Agrupe de forma lógica:** Use Enhanced Service Name ou Usage Family para comparar as despesas do GenAI entre os provedores.

Observação: Crie uma coluna calculada para converter caracteres em tokens - isso o ajuda a comparar Azure OpenAI, Vertex AI e Bedrock em termos iguais.
