---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Alocações de valor ponderado"
breadcrumb: []
source_path: "studio/model_studio/weighted-value-allocations.html"
images:
  - "resources/images/studio_images/neg-wa.png"
  - "resources/images/studio_images/studioimages/studio/stu588.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Alocações de valor ponderado

**Aplica-se a** : TBM Studio 12.0 e posterior

Uma alocação de **valor ponderado** distribui o valor com base na proporção (tamanho relativo) dos valores em uma coluna que você seleciona na tabela de destino. Esse é um dos tipos mais comuns de alocações ([saiba mais](allocate-value-in-model.html "Aplica-se a: TBM Studio 12.0 e posterior") ). Por exemplo, você pode distribuir a alocação com base no número de funcionários em uma unidade de negócios, no número de usuários de um aplicativo, no número de servidores em um data center ou no número de metros quadrados em um data center.

A seguir, um exemplo de valor ponderado por alocação:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu588.png)

## Opções de distribuição

Há três opções de distribuição:

- Mesmo
- Peso por
- Relacionamento de dados

## Distribuição uniforme

A opção Distribuição **uniforme** é a opção padrão e entra em vigor quando as opções **Ponderação por** e **Relação de dados** não estão selecionadas.

![](../../resources/images/studio_images/studioimages/studio_weighted%20value_distributing.png)

Essa opção distribui a alocação uniformemente entre todas as unidades identificadas na tabela de metas pela propriedade **"Para"**. Por exemplo, se houver uma tabela de **destino de aplicativos** com cinco aplicativos e US$ 100.000 estiverem sendo alocados, US$ 20.000 serão alocados para cada aplicativo.

## Peso por distribuição

A adição de uma ponderação a uma alocação impõe uma distribuição desigual de moeda ao fazer referência a um campo ou métrica que captura a distribuição desejada entre os registros no objeto de destino da alocação. As ponderações de alocação são usadas em duas situações distintas:

- Quando há uma coluna em um conjunto de dados que captura com mais precisão como as unidades (geralmente dólares) devem ser distribuídas entre os registros de um conjunto de dados. Um exemplo disso é o uso de dólares de depreciação do registro de ativos fixos para ponderar as alocações em ativos fixos.
- Quando há falta de pontos de dados relevantes para alocar com precisão. Nesse caso, as ponderações são usadas para tornar as alocações mais precisas do que seriam de outra forma, usando relações de dados.

## Exemplo

Suponha que haja cinco aplicativos com vários números de usuários, conforme mostrado na tabela abaixo, e US$ 100.000 a serem alocados. Se nenhuma ponderação for usada e os dólares forem distribuídos igualmente, cada aplicativo receberá uma parte igual dos US$ 100.000.

![](../../resources/images/studio_images/studioimages/studio_diagram_weight%20by%20distribution.png)

No entanto, no próximo caso, você deseja ponderar a distribuição pelo número de usuários. Em seguida, os US$ 100.000 seriam distribuídos conforme mostrado abaixo na coluna **Alocação** :

![](../../resources/images/studio_images/studioimages/studio_diagram_weighted%20value%20allocation%20example.png)

Observação: Há dois problemas comuns ao ponderar as alocações:

- Ponderação **por não numérico** : Se você tentar ponderar uma alocação por uma coluna numérica que contenha pelo menos um valor não numérico, a ponderação será ignorada. Para corrigir o problema, remova os valores não numéricos da coluna.
- **Ponderação por negativo** : Se você tentar ponderar uma alocação por um valor negativo, a alocação falhará devido a uma barreira colocada em prática para evitar problemas de cálculo decorrentes da ponderação por valores negativos. Para obter mais informações, consulte [Sobre ponderação e números negativos](about-weighting-and-negative-numbers.html "aplica-se a: TBM Studio 11.8.3.1 e posterior; TBM Studio 12.0 e posterior. O objetivo de uma ponderação é alocar o número de origem onde a soma é a mesma no destino.").

Há três opções para ponderar as alocações:

| Opção de ponderação | Resumo | Exemplo |
| --- | --- | --- |
| Tabela | Distribui a alocação com base na proporção dos valores em uma coluna do conjunto de dados que faz o backup do objeto de destino na alocação. | Você poderia usar a coluna Depreciação do Ledger de ativos fixos para ponderar a alocação de custos da origem de custos para os ativos fixos. |
| Métrica | Distribui a alocação com base na proporção dos valores no mesmo objeto de destino, mas para uma métrica diferente.  **OBSERVAÇÃO** : isso está disponível somente em TBM Studio 12.5 e posterior. | Você poderia usar a distribuição de alocação de custos para ponderar uma alocação de orçamento. |
| Outro motorista | Distribui a alocação com base na proporção dos valores em um driver específico ou conjunto de drivers no objeto de destino.  **OBSERVAÇÃO** : isso está disponível somente em TBM Studio 12.5 e posterior. | Você poderia usar sua alocação de mão de obra em Torres de Recursos de TI para ponderar a alocação do projeto em Torres de Recursos de TI |

**Ignore pesos insignificantes**

![imagem da caixa de seleção “Ignorar pesos insignificantes”](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/neg-wa.png)

Para ponderar colunas em uma alocação, se pesos pequenos estiverem fora de um intervalo configurável, trate-os como zero.

para desativar: -Ddisable.allocation.weighing.range =true

para definir o intervalo: -Dallocation.weighing.range=1000000000

Isso pode ser interpretado como se os pesos que forem 1 bilhão de vezes menores do que o maior peso, por chave de alocação, fossem tratados como zero.

## Relacionamento de dados

A opção **Relacionamento de dados** distribui a alocação uniformemente entre as unidades que correspondem aos valores em uma coluna na tabela de origem com os valores em uma coluna na tabela de destino. Por exemplo, suponha que a tabela de origem inclua informações sobre aplicativos. As tabelas de origem e destino incluem uma coluna **Application Category (Categoria do aplicativo** ). Uma das categorias é identificada como **Bancos de dados**, mas há dois aplicativos de banco de dados: Oracle e SAP. O valor das entradas do banco de dados na tabela de origem seria agregado e alocado igualmente às entradas do banco de dados na tabela de destino. Se estivessem sendo alocados US$ 20.000, eles seriam divididos em US$ 10.000 para Oracle e US$ 10.000 para SAP.

Por fim, você pode especificar mais de um relacionamento. Se você especificar mais de uma relação, todas as relações deverão corresponder para que o valor seja alocado.
