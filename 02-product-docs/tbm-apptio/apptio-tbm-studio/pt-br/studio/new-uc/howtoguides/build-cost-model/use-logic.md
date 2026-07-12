---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Utilizar a lógica de correspondência para alocações"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Modelagem avançada"
source_path: "studio/new-uc/howtoguides/build-cost-model/use-logic.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Utilizar a lógica de correspondência para alocações

## Objetivo

Configure relações entre dados para mapear dinamicamente as linhas de origem às linhas de destino durante a alocação, eliminando a necessidade de múltiplas linhas de alocação quando os dados forem alterados.

## Quando utilizar este procedimento

Utilize a lógica de correspondência (relações entre dados) quando:

- Você precisa alocar custos de uma fonte a linhas correspondentes específicas em uma tabela de destino (por exemplo, custos do data center aos servidores desse mesmo data center)
- As tabelas de origem e de destino compartilham uma dimensão comum (por exemplo, Data Center, Região, ID do fornecedor, Categoria de aplicativo)
- Você deve evitar criar linhas de alocação separadas para cada valor único
- Novos recursos (por exemplo, novos data centers) devem ser gerenciados automaticamente, sem necessidade de reconfiguração

**Pré-requisitos**

- As tabelas de origem e de destino foram adicionadas ao modelo por meio das etapas do modelo
- Ambas as tabelas contêm uma coluna com valores correspondentes (a coluna de relacionamento)
- Tabelas selecionadas para edição

## Tempo estimado

15 a 20 minutos

## Compreendendo o conceito

Sem uma lógica de correspondência, seria necessário criar uma linha de alocação separada para cada valor único. Por exemplo, para alocar os custos do data center apenas aos servidores desse mesmo data center, você pode criar:

- Alocação 1: De filtro = "SEA", Para filtro = "SEA"
- Alocação 2: De filtro = "NYC", Para filtro = "NYC"
- E assim por diante para cada data center...

Essa abordagem não é recomendada, pois gera sobrecarga de manutenção e exige a adição de novas linhas de alocação sempre que os dados forem alterados.

A opção **“Relação de dados”** resolve isso criando uma única linha de alocação que divide automaticamente a alocação em grupos com base na correspondência dos valores das colunas. Cada valor único na coluna de relação de dados resulta em um valor de ORIGEM distinto e em um conjunto correspondente de linhas de destino.

## Cenário de exemplo

**Antes** : Você tem uma tabela “Data Centers” com os custos (US$ 100.000 para SEA, US$ 80.000 para NYC) e uma tabela “Servers” com servidores em vários data centers. Sem uma lógica de distribuição, os $180.000 seriam alocados proporcionalmente entre todos os servidores.

**Depois** : Com uma relação de dados na coluna “Data Center”, os custos de SEA (US$ 100.000) são alocados apenas aos servidores de SEA, e os custos de NYC (US$ 80.000) são alocados apenas aos servidores de NYC.

**Passos**

1. No Project Explorer, clique na tabela de origem e clique na etapa Modelo no pipeline de transformação.
2. No diagrama de Sankey, clique em “Adicionar alocação” sob o título “Alocações” (ou clique em uma alocação existente para editá-la).
3. Na seção “Alocar”, selecione as métricas às quais a alocação se aplicará (por exemplo, Custo, Orçamento).
4. Em “Usar”, selecione o tipo de alocação (Valor Ponderado, Igualitário ou outro método de distribuição).
5. Em "Para", selecione a tabela de destino.
6. Localize a seção “Relação de dados” no painel de configuração de alocação.
7. Se a opção “Relação automática” estiver ativada, desmarque a caixa de seleção para configurar relações explícitas.
8. Na coluna "Fonte", selecione a coluna da tabela de origem que contém os valores correspondentes (por exemplo, "Data Center").
9. Na coluna "Destino", selecione a coluna correspondente na tabela de destino.
10. (Opcional) Para adicionar critérios de correspondência adicionais, repita as etapas 8 e 9 para cada par de colunas adicional. Todas as relações devem corresponder para que o valor seja atribuído.
11. Clique em “Visualizar” para verificar se os resultados da alocação mostram os custos atribuídos às linhas correspondentes corretas.
12. Clique em Salvar para aplicar as alterações.

## Resultados esperados

A pré-visualização da alocação mostra:

- Custos de origem agrupados por sua(s) coluna(s) de relacionamento
- Cada valor único recebe seu próprio conjunto de custos
- Linhas de destino que recebem custos apenas das linhas de origem correspondentes

## Utilização de múltiplas relações de dados

Você pode especificar mais de uma relação quando precisar realizar uma correspondência em várias dimensões. Por exemplo, para alocar custos de fornecedores às aplicações tanto por ID do fornecedor quanto por região:

- Coluna de origem 1: ID do fornecedor → Coluna de destino 1: ID do fornecedor
- Coluna de origem 2: Região → Coluna de destino 2: Região

Observação: Ao especificar várias relações, ***todas*** elas devem corresponder para que o valor seja atribuído. Uma linha deve corresponder tanto ao ID do fornecedor quanto à região para receber os custos.

## Armadilhas comuns

- Valores incompatíveis: certifique-se de que os valores nas colunas de origem e destino correspondam exatamente (incluindo maiúsculas e minúsculas e espaços em branco). Valores incompatíveis resultam em custos não alocados.
- Valores NULL: as linhas com NULL na coluna de relação não serão correspondidas e os custos permanecerão sem alocação.
- Relações automáticas herdadas: Se aparecerem erros relacionados à "Operação de junção do modelo herdado", desmarque a caixa de seleção "Relação automática" e configure explicitamente as colunas de origem e destino.
- Muitas relações: adicionar critérios de correspondência em excesso pode resultar na ausência de correspondências. Comece com um ou dois relacionamentos importantes.

## Tarefas relacionadas

- [Configurar colunas de ponderação](config-wc.html)
- [Tratar custos não alocados](handle-unallocated-costs.html)
- [Acompanhar os fluxos de custos ao longo do modelo](trace-cost-flow.html)

**Tópico principal:** [Modelagem avançada](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
