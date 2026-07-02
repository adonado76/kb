---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Compartilhamento de custos - Alocações baseadas em telemetria e consumo"
breadcrumb:
  - "Cloudability Premium"
  - "Configuração"
  - "Compartilhamento de custos em Cloudability"
source_path: "product/cost-sharing-telemetry.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Compartilhamento de custos - Alocações baseadas em telemetria e consumo

Visão geral

As alocações baseadas em telemetria permitem que você distribua custos compartilhados em seu ambiente de nuvem usando métricas de uso real de seus sistemas. Ao fazer o upload dos dados de telemetria, você pode criar regras de alocação mais precisas e baseadas em dados no Cost Sharing.

Benefícios

O uso de dados de telemetria para alocação de custos oferece várias vantagens importantes, como

- Distribuição de custos com base no uso : alocar custos com base no uso real do sistema, em vez de porcentagens estáticas ou métricas estimadas
- Maior precisão de custos : crie uma correlação direta entre o consumo de recursos e a distribuição de custos
- Modelo de alocação defensável : suporte a alocações de custos com dados de uso concretos, facilitando a justificativa de modelos de charge-back
- Suporte flexível a métricas : use qualquer métrica mensurável (chamadas de API, uso de computação, operações de armazenamento) para orientar as decisões de alocação

Antes de começar

O arquivo utilizado para o envio dos seus dados de telemetria deve ser um arquivo do tipo “ CSV ” com os seguintes campos obrigatórios:

- Data: O registro de data e hora da medição métrica
- Categoria: Mapas para sua categoria de dimensão de negócios
- Valor: A medida da métrica (por exemplo, number\_of\_api\_requests, compute\_hours)

O exemplo a seguir mostra um arquivo no formato “ CSV ”.

| Data | Categoria | Número de solicitações de API |
| --- | --- | --- |
| 01/01/2025 | Equipe A | 15000 |
| 01/01/2025 | Equipe B | 8.5 |
| 01/01/2025 | Equipe C | 12000 |

Uso da telemetria no compartilhamento de custos

Siga as etapas abaixo para usar a Telemetria e as alocações baseadas em consumo:

1. Selecione Organize/Cost Sharing (Organizar/Compartilhamento de custos ) no painel de navegação à esquerda
2. Selecione o botão New Allocation (Nova alocação )
3. Selecione uma Dimensão na caixa de diálogo modal Nova alocação e, em seguida, selecione o botão Criar
4. Selecione a guia Telemetry Data (Dados de telemetria )
5. Selecione o botão “Carregar arquivo de telemetria” e carregue o arquivo CSV
6. O arquivo “ CSV ” aparecerá na tabela “Telemetria”, na guia “Dados de telemetria”
7. Selecione a guia Regras
8. Selecione o botão Nova regra
9. Selecione Telemetry / Consumption (Telemetria / Consumo) no menu suspenso Allocation Method (Método de alocação )
10. Selecione pelo menos uma opção na lista Source (from)
11. Os valores de destino aparecem desativados porque foram definidos no arquivo “ CSV ” que foi enviado
12. Salvar sua regra de alocação

O sistema calculará automaticamente as taxas de alocação com base em seus dados de telemetria e as aplicará aos seus custos compartilhados.

Práticas recomendadas

Siga as práticas recomendadas em Telemetria conforme abaixo:

- Certifique-se de que seus dados de telemetria abranjam o mesmo período de tempo que os períodos de alocação de custos.
- Valide se os valores do campo Categoria estão alinhados com as categorias de dimensão de negócios existentes.
- As atualizações regulares dos dados de telemetria fornecerão a distribuição de custos mais precisa.
- Considere a sazonalidade e os padrões de uso ao selecionar as métricas apropriadas para alocação.

**Tópico dos pais:** [Compartilhamento de custos em Cloudability](../product/cost-sharing.html)
