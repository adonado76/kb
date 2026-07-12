---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Oficina de Trabalho"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/laborworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Oficina de Trabalho

## Preparação de seus dados trabalhistas

Você pode começar e preparar seu trabalho analisando os pontos de verificação abaixo:

1. Se ainda não tiver feito isso, carregue seus dados do Labor, incluindo:
   - Número real de funcionários
   - Número de funcionários planejados
2. Seguindo as Apptio práticas padrão, categorize cada conjunto de dados brutos na categoria de Trabalho.
3. Se for o caso, aplique um filtro de data aos seus dados de trabalho.

## Sobre o identificador de trabalho

Anteriormente, o identificador do conjunto de dados mestre da mão de obra era preenchido automaticamente. Isso mudou em R12 e agora você deve mapear um campo para essa coluna no conjunto de dados mestre de mão de obra. Considere o grau de granularidade que você precisa que os dados tenham e defina seu identificador de acordo. Por exemplo, se você estiver calculando os custos no nível do funcionário, mapeie o ID do funcionário para o ID do trabalho.

Talvez você queira definir o identificador como o número de identificação do funcionário, como no exemplo acima. No entanto, não há relatórios prontos para uso que exibam esse nível de detalhe. Os relatórios dinamizam os dados em atributos como centro de custo, função ou outras informações, portanto, considere mapear essas combinações na chave para clientes maiores ou se o ID for muito sensível para ser exibido no modelo.

## Sobre as Chaves Trabalhistas

As chaves do conjunto de dados mestre de mão de obra são todas geradas pelo sistema e não devem ser alteradas.

| Chave | A chave de campo é baseada em | Lógica |
| --- | --- | --- |
| **Fonte de custo\_Trabalho** | Custo CenterCost PoolCost Sub Pool  Metacampo-chave da fonte de custos | Anexar o texto Chave de mão de obra ao metacampo Centro de custos, Pool de custos, Subpolo de custos e Chave de origem de custos |
| **Chave do projeto\_trabalho** | Definido pelo usuário durante o mapeamento | Considere a possibilidade de usar o código do projeto, pois ele precisa vincular o objeto Trabalho e o objeto Projetos no modelo |
| **Chave Labor\_Resource** | Torre de recursos de TI  Subtracção de recursos de TI | Anexar o texto Labor\_Resource à torre de recursos de TI e à subnave de recursos de TI |
| **Chave de controle de tempo de trabalho** | Identificação do trabalho | Anexar o texto Labor\_Time Tracking à ID do trabalho |

## Mapear dados para os dados mestre do trabalho

Mapeie seus dados de mão de obra para o conjunto de dados mestre de mão de obra. A maior parte do mapeamento deve ser autoexplicativa neste ponto.

Se você definir seu identificador como o ID do funcionário, mapeie **=1** para o campo Headcount da mão de obra. Se você usou outra coisa como identificador (como centro de custo), mapeie o campo de headcount em seu conjunto de dados para o campo Labor Headcount.

Ao mapear o número de funcionários planejados, certifique-se de mapear o valor do número de funcionários para o campo Número de funcionários planejados (em vez do campo Número de funcionários). Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre de mão de obra ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

Pontos que devem ser levados em conta:

- Mapeie seu conjunto de dados de mão de obra para o conjunto de dados mestre de mão de obra.

## Analise o objeto de trabalho nos modelos

| Modelo | Ações |
| --- | --- |
| **Custo** | Assegure-se de que os valores estejam fluindo para o objeto Labor.  As chaves que unem os dois conjuntos de dados incluem o centro de custo, o pool de custos, o subconjunto de custos e o metacampo da chave da fonte de custos.  Talvez seja necessário ajustar a alocação para ponderar por outro valor se o identificador exclusivo não for o ID individual do funcionário. |
| **Orçamento** | Assegure-se de que os valores estejam fluindo para o objeto Labor.  As chaves que unem os dois conjuntos de dados incluem o centro de custo, o pool de custos, o subconjunto de custos e o metacampo da chave da fonte de custos.  Talvez seja necessário ajustar a alocação para ponderar por outro valor se o identificador exclusivo não for o ID individual do funcionário. |
| **Previsão** | Assegure-se de que os valores estejam fluindo para o objeto Labor.  As chaves que unem os dois conjuntos de dados incluem o centro de custo, o pool de custos, o subconjunto de custos e o metacampo da chave da fonte de custos.  Talvez seja necessário ajustar a alocação para ponderar por outro valor se o identificador exclusivo não for o ID individual do funcionário. |
| **CapEx** | Assegure-se de que os valores estejam fluindo para o objeto Labor.  As chaves que unem os dois conjuntos de dados incluem o centro de custo, o pool de custos, o subconjunto de custos e o metacampo da chave da fonte de custos.  Talvez seja necessário ajustar a alocação para ponderar por outro valor se o identificador exclusivo não for o ID individual do funcionário. |
| **Orçamento CapEx** | Assegure-se de que os valores estejam fluindo para o objeto Labor.  As chaves que unem os dois conjuntos de dados incluem o centro de custo, o pool de custos, o subconjunto de custos e o metacampo da chave da fonte de custos.  Talvez seja necessário ajustar a alocação para ponderar por outro valor se o identificador exclusivo não for o ID individual do funcionário. |
| **Previsão de Capex** | Assegure-se de que os valores estejam fluindo para o objeto Labor.  As chaves que unem os dois conjuntos de dados incluem o centro de custo, o pool de custos, o subconjunto de custos e o metacampo da chave da fonte de custos.  Talvez seja necessário ajustar a alocação para ponderar por outro valor se o identificador exclusivo não for o ID individual do funcionário. |

As torres de TI ainda não foram mapeadas, portanto, nenhum valor fluirá para o objeto Torres de recursos de TI.

## Revisar relatórios trabalhistas

Os relatórios a seguir são atualizados após a configuração do objeto Labor:

- Revisão do trabalho
- Revisão Trabalhista - Detalhes
- Análise trabalhista
- Dimensões dos dados - Trabalho
- Validade do trabalho

Para ver os detalhes desses relatórios (incluindo navegação, funções, objetivos e perguntas respondidas para cada relatório), consulte o Guia do Usuário do Costing Standard disponível na Ajuda on-line.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
