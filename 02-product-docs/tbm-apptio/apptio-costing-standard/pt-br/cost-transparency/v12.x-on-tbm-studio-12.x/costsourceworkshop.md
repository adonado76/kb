---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workshop de fontes de custo"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/costsourceworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workshop de fontes de custo

Os custos são trazidos para o Objeto de origem de custos na parte inferior do modelo, geralmente do livro-razão da sua organização. Em seguida, os custos são alocados aos objetos no modelo usando estratégias baseadas nas práticas recomendadas do Technology Business Management.

## Preparação de seus dados de origem de custos

Você pode começar e preparar seus dados de origem de custos revisando os pontos de verificação abaixo:

1. Se ainda não tiver feito isso, carregue seus dados de Cost Source Actuals, incluindo:
   - GL Actuals ( OpEx e ( CapEx )
   - Orçamento GL (se aplicável)
   - GL Forecast (se aplicável)
   - Plano de contas
   - Lista de centros de custo

   Precisamos de pelo menos o primeiro mês de dados GL carregados em Apptio antes de prosseguir.
2. Seguindo as práticas padrão do site Apptio, categorize cada conjunto de dados brutos na categoria de Fonte de Custos.
3. Se apropriado, aplique um filtro de data aos dados reais do GL.

## Sobre o identificador da fonte de custos

O identificador do objeto Fonte de custos é predefinido e não deve ser alterado. Ele inclui:

- Pool de custos
- Subgrupo de custos
- Conta
- Centro de custo
- ID de Projeto
- ID do Fornecedor
- Metacampo UID
- Fixo Variável
- Tipo de Despesas
- Identificador de benchmark

Se precisar de granularidade adicional (como até os itens de linha GL individuais), você poderá preencher o metacampo UID com o nível apropriado de detalhes.

## Sobre as chaves de origem de custos

As chaves do conjunto de dados mestre da origem de custos são todas predefinidas e não devem ser alteradas.

| Chave | A chave de campo é baseada em | Lógica |
| --- | --- | --- |
| Fonte de **custos\_Chave do ativo** fixo | É Depr Metacampo da chave do ativo fixo | SE Se Depr for "yes" (sim)  THEN  Anexar o texto do prefixo de FA\_Key ao metacampo Fixed Asset Key  ELSE  Definir o texto como CS\_FA\_null |
| **Fonte de custo\_Trabalho** | É trabalho Centro de custo  Pool de custos  Subgrupo de custos  Metacampo da chave de trabalho | SE O trabalho é "sim"  THEN  Anexar o texto do prefixo de Labor\_Key ao metacampo Centro de custos, Pool de custos, Subpolo de custos e Chave de mão de obra  ELSE  Definir o texto como CS\_Labor\_null |
| **Chave da fonte de custo\_fornecedor** | É fornecedor É trabalho  É Depr  ID do Fornecedor  Metacampo da chave do fornecedor | SE Is Vendor é "sim" e Is Labor é "não" e Is Depr é "não"  THEN  Anexar o texto do prefixo de CS\_Vendor ao metacampo de ID do fornecedor e chave do fornecedor  ELSE  Defina o texto como CS\_Vendor\_null |
| **Fonte de custos Chave do projeto** | É projeto ID de Projeto | SE Is Project = "yes"  THEN  Anexar o texto do prefixo de Project\_Key ao ID do projeto  ELSE  Definir o texto como CS\_Project\_null |
| **Fonte de custos\_Outra chave do pool de custos** | Fonte de custos\_Chave do ativo fixo Fonte de custo\_Trabalho  Chave da fonte de custo\_fornecedor  Fonte de custos Chave do projeto  Centro de custo  Metacampo-chave do pool de outros custos | SE Fonte de custos/Chave do ativo fixo = CS\_FA\_null AND  Chave da fonte de custos\_trabalho = CS\_Labor\_null AND  Chave do fornecedor da fonte de custos = CS\_Vendor\_null AND  Chave do projeto de origem de custos = CS\_Project\_null  THEN  Anexar o texto do prefixo de CC.Map ao metacampo da chave do centro de custos e de outro pool de custos  ELSE  Definir o texto como CC\_ITRT\_null |
| **Chave da fonte de custo\_Benchmark** | Sub-Tower de referência | Anexar o texto do prefixo "Benchmark" com a subestrutura Benchmark |

As chaves acima são predefinidas e não devem ser alteradas. Se você precisar de granularidade adicional, preencha o metacampo apropriado com o nível de granularidade necessário. Algumas sugestões incluem:

- Metacampo da chave do ativo fixo - Código do centro de custo
- Metacampo da chave do fornecedor - Código do centro de custo

## Fatores determinantes da fonte de custos

O objeto Fonte de custos tem drivers de unidade que determinam quais valores são alimentados no objeto Fonte de custos. Para o modelo de custo, há dois drivers. A tabela abaixo descreve a lógica em cada um dos drivers. Em 12.6, atualizamos os drivers para incluir o Plane e não ter a complexidade que temos com os drivers atuais: ( [R12.6 Change - Expense Type Change](https://community.apptio.com/docs/DOC-10629 "(Abre em uma nova guia ou janela)") )

| Motorista da unidade | O driver é baseado em | Lógica |
| --- | --- | --- |
| **OpEx fixo** | Tipo de Despesas Fixo Variável  Quantia | SE O tipo de despesa é "OpEx" E a variável fixa é "Fixed"  THEN  Alimentação na quantidade  ELSE  Alimentação em 0 |
| **Variável OpEx** | Tipo de Despesas Fixo Variável  Quantia | SE O tipo de despesa é "OpEx" E  Fixo variável é "variável"  THEN  Alimentação na quantidade  ELSE  Alimentação em 0 |

Os outros modelos que contêm o objeto Cost Source (Budget, Forecast, CapEx, CapEx Budget, CapEx Forecast) contêm uma lógica semelhante ainda baseada nos campos Expense Type, Fixed Variable e Amount. Isso significa que você deve preencher esses campos para direcionar os valores para o objeto Fonte de custos.

Normalmente, os dados do tipo de despesa e da variável fixa são mapeados como parte do plano de contas e, em seguida, convertidos (por meio de uma coluna LOOKUP) para o GL.

## Colunas computadas comuns necessárias para a origem de custos

Abaixo está uma lista de colunas computadas que você pode precisar criar. Na maioria dos casos, as colunas estão convertendo dados do plano de contas e da lista de centros de custo para o conjunto de dados do GL. Em 12.7, temos dois novos recursos com relação à configuração da fonte de custos, o que pode ajudar a criar as colunas abaixo:

- Os dados mestre do plano de contas agora serão aproveitados pelo site Machine Learning para ajudar a atribuir contas a pools de custos, em vez de ter que passar uma planilha de um lado para o outro com um cliente. ( [Machine Learning para pools de custos](https://community.apptio.com/docs/DOC-11548 "(Abre em uma nova guia ou janela)") ).
- Além de aproveitar o plano de contas, agora você pode aproveitar a etapa de união ([unir dados](https://community.apptio.com/docs/DOC-5078 "(Abre em uma nova guia ou janela)") ) no Razão, no orçamento e na previsão dos clientes para extrair as colunas normalmente encontradas no plano de contas. ([Atribuir pools de custos e mapear colunas](https://community.apptio.com/docs/DOC-11359 "(Abre em uma nova guia ou janela)") )

Observação: o uso da etapa Join para isso eliminará a necessidade de todas as pesquisas que contêm o plano de contas abaixo

- Pesquisa da descrição da conta do plano de contas no conjunto de dados GL
- Pesquisa do pool de custos do plano de contas no conjunto de dados GL
- Pesquisa do subgrupo de custos do plano de contas no conjunto de dados GL
- Pesquisa de fixo/variável do plano de contas no conjunto de dados GL
- Pesquisa de discricionário/não discricionário do plano de contas no conjunto de dados GL
- Pesquisa de grupo de contas do plano de contas no conjunto de dados GL
- Pesquisa de subgrupo de contas do plano de contas no conjunto de dados GL
- Pesquisa do proprietário do centro de custo da lista de unidades funcionais no conjunto de dados GL
- Pesquisa do proprietário de TI da lista de unidades funcionais no conjunto de dados GL
- A marcação Sim/Não da depreciação é baseada no subgrupo de custos no conjunto de dados GL?
- O sinalizador Sim/Não do trabalho é baseado no subgrupo de custos no conjunto de dados GL?
- O sinalizador Sim/Não do projeto é baseado no código do projeto no conjunto de dados GL?

Para todas essas colunas computadas, talvez seja necessário criá-las também nos conjuntos de dados de previsão e orçamento relevantes.

## Mapear dados para os dados mestre da fonte de custos

Mapeie seus dados de origem de custos para o conjunto de dados mestre de origem de custos. A maior parte do mapeamento é autoexplicativa. Não há requisitos incomuns de mapeamento. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre da fonte de custos ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

Pontos que devem ser levados em conta:

- Mapeie o conjunto de dados reais do GL para o conjunto de dados mestre da origem de custos.

## Revise o objeto Fonte de custos nos modelos

Depois de mapear seus dados para os dados mestre da fonte de custos, você pode ir em frente e revisar os objetos da fonte de custos nos modelos. Analise os modelos a seguir e verifique se os valores estão fluindo para o objeto Fonte de custos adequadamente.

- Custo
- Orçamento
- Previsão
- CapEx
- Orçamento CapEx
- CapEx Previsão

## Revisar relatórios de origem de custos

Os relatórios a seguir são atualizados após a configuração do objeto Fonte de custos:

- Análise do pool de custos
- Detalhes da análise do pool de custos
- Validade da fonte de custos
- Costing Standard Carregar conjunto de dados
- Dimensões de dados - Fonte de custos
- Painel de dimensões de dados
- Painel de dimensões de dados - Página inicial
- Análise financeira
- Análise financeira - CapEx Transação
- Análise financeira - CapEx Tendência
- Análise financeira - OpEx Transação
- Análise financeira - OpEx Tendência
- Revisão financeira
- Análise de variação financeira
- Ajuda - Tabela de alocação
- IT Finance - Transação de conta - CapEx Detalhe
- Finanças de TI
- Painel de controle da TBM
- Detalhes da transação
- Transações
- Detalhe do desvio

Para ver os detalhes desses relatórios (incluindo navegação, funções, objetivos e perguntas respondidas para cada relatório), consulte o Guia do Usuário Costing Standard na Ajuda on-line.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
