---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tratar custos não alocados"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Criar alocações"
source_path: "studio/new-uc/howtoguides/build-cost-model/handle-unallocated-costs.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tratar custos não alocados

**Objetivo:** Gerenciar os custos que não se enquadram nos critérios de alocação para garantir que 100% dos custos sejam contabilizados no seu modelo.

**Quando usar:** Após executar as alocações, restam custos que não foram distribuídos às tabelas de destino. Isso geralmente ocorre quando os critérios de correspondência de drivers não abrangem todas as linhas de origem.

**Tempo estimado:** 15 a 30 minutos, dependendo da estratégia escolhida

## Entendendo os custos não alocados

Os custos não alocados ocorrem quando:

- As linhas de origem não correspondem a nenhuma linha de destino (não há valores de chave correspondentes)
- Os filtros excluem determinadas linhas de origem de todas as alocações
- Os valores de ponderação são zero para algumas linhas de destino
- Chegam novos dados que não estavam previstos no projeto original de alocação

## Estratégia 1: Criar um fundo de reserva

Um pool residual é um destino genérico que recebe os custos que não se enquadram em nenhum critério específico de alocação.

**Quando usar:** quando se deseja acompanhar separadamente os custos não alocados para análise, garantindo ao mesmo tempo que o modelo esteja equilibrado.

**Passos**

1. **Criar uma mesa de sinuca residual**
   - No ` Data Studio `, crie uma nova tabela chamada "Custos não alocados" ou "Reserva residual".
   - Adicione a tabela ao modelo usando a etapa "Modelo".
2. **Criar uma alocação genérica**
   - Na tabela de origem, crie uma nova alocação após todas as alocações específicas.
   - Não adicione nenhum filtro (isso captura tudo o que restar).
   - Definir peso por = Par.
3. **Monitorar o saldo residual**
   - Verifique regularmente os valores residuais do fundo comum.
   - Valores elevados indicam problemas de correspondência ou de qualidade dos dados.

## Estratégia 2: Distribuição equitativa dos custos restantes

Distribua os custos não alocados de maneira uniforme entre as metas existentes, em vez de acompanhá-los separadamente.

**Quando usar: quando** os custos não alocados são pequenos ou quando é aceitável distribuí-los proporcionalmente entre todos os alvos.

- Crie uma alocação em duas etapas: primeiro com correspondência específica e, em seguida, com distribuição uniforme para o restante.
- Adicione um filtro "De" na segunda alocação para selecionar apenas as linhas sem correspondência.

## Estratégia 3: Distribuição proporcional com ponderação métrica

Distribuir os custos não alocados proporcionalmente, com base na forma como os demais custos já foram alocados.

**Quando usar: quando** se deseja que os custos não alocados sigam o mesmo padrão de distribuição dos custos alocados.

- Crie uma alocação secundária com Ponderar por = Métrica.
- Selecione a métrica da sua alocação principal.
- Isso distribui os custos restantes utilizando as mesmas proporções.

## Estratégia 4: Resolver a causa raiz

Elimine os custos não atribuídos resolvendo os problemas subjacentes relacionados aos dados ou à configuração.

1. **Identificar por que os custos não estão alocados**
   - Exporte as linhas não atribuídas da visualização.
   - Analise os valores das chaves correspondentes.
2. **Corrigir problemas de qualidade dos dados**
   - Se os campos-chave estiverem com erros ortográficos ou forem inconsistentes, corrija-os nos dados de origem ou nas transformações.
   - Se surgirem novas categorias, adicione-as à tabela de destino.
3. **Atualizar a lógica de correspondência**
   - Se os critérios de correspondência forem muito restritivos, amplie-os.
   - Adicione relações de dados adicionais, se necessário.

## Matriz de decisão para custos não alocados

|  |  |
| --- | --- |
| **Cenário** | **Estratégia recomendada** |
| Montante significativo não alocado (>5% do total) | Corrigir a causa principal |
| Pequeno montante não alocado (<5% do total) | Distribuição proporcional ou fundo residual |
| É necessário um registro de auditoria para os recursos não alocados | Reserva residual |
| Problema pontual com os dados | Distribuição uniforme pelos alvos existentes |
| Créditos ou estornos que resultam em valores negativos | Separar e tratar separadamente |

**Tópico principal:** [Criar alocações](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
