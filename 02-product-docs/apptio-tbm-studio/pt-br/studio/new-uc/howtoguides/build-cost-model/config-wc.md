---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar colunas de ponderação"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Modelagem avançada"
source_path: "studio/new-uc/howtoguides/build-cost-model/config-wc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar colunas de ponderação

## Objetivo

Configure alocações de valores ponderados que distribuam os custos proporcionalmente com base em uma coluna numérica, em vez de distribuí-los uniformemente por todas as linhas de destino.

## Quando utilizar este procedimento

Use colunas de ponderação quando:

- Nem todas as entidades-alvo são iguais (por exemplo, os servidores têm diferentes números de CPUs, os aplicativos têm diferentes números de usuários)
- Você dispõe de um indicador mensurável que reflete o consumo ou a capacidade relativa
- Você quer que os grandes consumidores paguem proporcionalmente mais do que os pequenos consumidores
- Uma distribuição uniforme não refletiria com precisão o consumo real nem os padrões de uso

**Pré-requisitos**

- As tabelas de origem e de destino foram adicionadas ao modelo
- A tabela de destino contém uma coluna numérica com valores de ponderação
- A coluna de ponderação contém valores numéricos não nulos e não negativos (ver notas sobre valores negativos abaixo)
- Tabelas selecionadas para edição

## Tempo estimado

10 a 15 minutos

## Compreendendo o conceito

Uma alocação de valores ponderada distribui os custos com base na proporção (tamanho relativo) dos valores de uma coluna selecionada na tabela de destino. A fórmula é:

Atribuição à linha = FONTE × (Peso da linha / Peso total de todas as linhas correspondentes)

Por exemplo, se você estiver distribuindo US$ 100.000 entre cinco servidores com base no número de CPUs:

|  |  |  |
| --- | --- | --- |
| **Servidor** | **Número de CPUs** | **Alocação** |
| Servidor A | 4 | $10.000 (4/40 = 10%) |
| Servidor B | 8 | $20.000 (8/40 = 20%) |
| Servidor C | 16 | $40.000 (16/40 = 40%) |
| Servidor D | 8 | $20.000 (8/40 = 20%) |
| Servidor E | 4 | $10.000 (4/40 = 10%) |
| Total | 40 | $100.000 |

## Passos

1. No Project Explorer, clique na tabela de origem e clique na etapa Modelo no pipeline de transformação.
2. No diagrama de Sankey, clique em “Adicionar alocação” (ou clique em uma alocação existente para editá-la).
3. Na seção “Alocar”, selecione as métricas às quais a alocação se aplicará.
4. Em “Usar”, selecione “Valor ponderado” como tipo de alocação.
5. Em "Para", selecione a tabela de destino.
6. Nas opções de distribuição, selecione “Ponderar por”.
7. Selecione a coluna numérica da tabela de destino que contém seus valores de ponderação (por exemplo, Número de CPUs, Número de usuários, Metros quadrados).
8. (Opcional) Configure as relações entre os dados caso seja necessário fazer a correspondência entre as linhas de origem e as de destino.
9. Clique em “Visualizar” para verificar se os custos estão distribuídos proporcionalmente com base na sua coluna de ponderação.
10. Clique em Salvar para aplicar as alterações.

## Resultados esperados

A pré-visualização da alocação mostra:

- O valor do peso de cada linha de destino e sua porcentagem do total
- Custo alocado proporcional à relação de peso
- Custo total alocado correspondente ao valor de origem

## Avançado: Utilização de outras ponderações de pilotos

No TBM Studio 12.5 e versões posteriores, você pode usar a opção “Outro driver” para ponderar uma alocação com base nos resultados de uma alocação diferente. Isso é útil quando se deseja uma ponderação consistente entre várias alocações.

Por exemplo, se você já alocou custos de mão de obra às torres de recursos de TI, poderia usar esse mesmo padrão de ponderação para alocar custos de projeto às torres de recursos de TI. Selecione “Outro driver” e escolha o driver “Labor” existente para manter a consistência.

## Armadilhas comuns

- Valores não numéricos: Se a coluna de ponderação contiver pelo menos um valor não numérico, a ponderação será ignorada e os custos serão distribuídos igualmente. Limpe seus dados para garantir que todos os valores sejam numéricos.
- Todos zeros: Se todos os valores de ponderação forem 0, os custos são distribuídos uniformemente pelas linhas de destino (comportamento padrão por meio da função Ratio).
- Valores NULL: as linhas com NULL na coluna de ponderação não receberão nenhuma alocação.
- Valores negativos: Por padrão, o TBM Studio não realiza a alocação quando há ponderações negativas, pois isso pode resultar em resultados inesperados. Se for necessário usar pesos negativos, consulte a documentação sobre o tratamento de números negativos.

Dica: Verifique sempre se a coluna de ponderação está corretamente definida como numérica na etapa de importação do seu pipeline de transformação. Códigos que parecem números, mas são armazenados como texto, farão com que a ponderação falhe sem aviso prévio.

## Tarefas relacionadas

- [Utilizar a lógica de correspondência para alocações](use-logic.html)
- Criar alocações de fórmula (Referência da Seção " 5.2 ")
- [Tratar custos não alocados](handle-unallocated-costs.html)

**Tópico principal:** [Modelagem avançada](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
