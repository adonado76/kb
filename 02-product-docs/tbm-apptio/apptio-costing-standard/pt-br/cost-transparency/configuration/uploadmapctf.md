---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Carregar e mapear os dados da Costing Standard Foundation"
breadcrumb: []
source_path: "cost-transparency/configuration/uploadmapctf.html"
images:
  - "resources/images/ct_images/6832_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Carregar e mapear os dados da Costing Standard Foundation

Depois de instalar os componentes e configurar o tempo para o projeto, a próxima etapa é fazer o upload dos dados do Costing Standard Foundation para o aplicativo e mapeá-los para as tabelas de dados mestre.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

Quando você criou o projeto Costing Standard , o aplicativo criou as tabelas de dados de suporte e as tabelas de dados mestre. Várias tabelas são preenchidas com entradas padrão. A maioria das tabelas está em branco e deve ser preenchida com seus dados.

## Conjuntos de dados populacionais

Os conjuntos de dados a seguir contêm entradas padrão:

- Lista de referência do pool de custos
- Lista de referência da torre de recursos de TI

Não é necessário fazer upload de dados para esses conjuntos de dados.

## Conjuntos de dados em branco

As tabelas de dados mestre a seguir estão em branco e você deve preenchê-las com seus dados:

- Dados mestre da fonte de custos
- Dados mestre do ativo fixo
- Dados mestre de mão de obra
- Dados mestre de projetos
- Fonte de custos para os dados mestre de recursos de TI

## Carregar dados em uma tabela de dados mestre

Há várias etapas para carregar dados em uma tabela de dados mestre:

1. Carregue os dados no aplicativo como uma tabela separada.
2. Se você precisar modificar a tabela (por exemplo, g.: adicionar colunas), adicione etapas ao pipeline de transformação da tabela. O objetivo é garantir que a tabela inclua todos os dados de que você precisará ao mapear os dados para a tabela de dados mestre. Não deve ser necessário usar instruções IF ou pesquisas ao mapear o conjunto de dados para o conjunto de dados mestre.
3. Mapear o conjunto de dados carregado para o conjunto de dados mestre.

Para obter detalhes sobre como executar essas etapas, consulte [Carregar dados no aplicativo Costing Standard](loaddata.html "As tabelas de dados mestre fornecem uma maneira de mapear seus dados para os dados exigidos pelo aplicativo CT. As informações abaixo descrevem como carregar dados no aplicativo.")  e [Mapear dados para uma tabela de dados mestre](maptomaster.html "Depois de fazer o upload de uma tabela de dados de origem e transformá-la, se necessário, você pode mapeá-la para uma tabela de dados mestre. Use as instruções a seguir para mapear dados para uma tabela de dados mestre.").

As instruções passo a passo para carregar seus dados em cada uma das tabelas de dados mestres estão descritas a seguir:

- [Preencha a tabela de dados mestre da fonte de custos.](populatecostsource.html)
- [Preencha a tabela Dados mestre do ativo fixo](populatefixedasset.html "A tabela Dados mestre do ativo fixo define os dados necessários para \"iluminar\" os relatórios relacionados a custos e orçamento. Para preencher o conjunto de dados, você deve carregar os valores de custo do ativo fixo e mapeá-los para a tabela Dados mestre do ativo fixo")
- [Preencha a tabela Dados-mestre de mão de obra](populatelabor.html "A tabela de dados mestre de mão de obra define os dados necessários para \"iluminar\" os relatórios relacionados a custos e orçamento. Os dados fornecem uma análise detalhada dos custos de mão de obra para funcionários FTE e contratados, incluindo comparações de custos reais e número de funcionários em relação ao plano. Para preencher a tabela de dados mestre de mão de obra, carregue uma tabela de dados de mão de obra e mapeie-a para a tabela de dados mestre de mão de obra.")
- [Preencha a tabela Origem dos custos para dados mestre de recursos de TI.](populatecostsource2.html "Para preencher a tabela Fonte de custos para dados mestre de recursos de TI, carregue uma tabela de dados que defina a porcentagem dos outros custos a serem alocados a cada centro de custo. Depois de criar a tabela, mapeie-a para a tabela Fonte de custo para dados mestre de recursos de TI.")

## Devo transformar os dados antes ou depois de importá-los?

Quanto mais seus dados estiverem em conformidade com as tabelas de dados mestre, mais fácil será mapear os dados. Quando possível, gere os dados necessários a partir de seus aplicativos externos antes de importá-los para o aplicativo CTF. Se isso não for possível, você poderá transformar os dados depois de importá-los. Ambas as abordagens são satisfatórias.

## Usar tabelas de mapeamento

Se os dados que você trouxer para o aplicativo não incluírem os dados necessários para mapear os campos para a tabela de dados mestre de destino, será necessário criar uma tabela de mapeamento para fornecer as informações. Normalmente, a tabela de dados de mapeamento atribui valores a cada uma das unidades em uma tabela de dados mestre. Por exemplo, talvez seja necessário adicionar informações de depreciação, fixo /var iable e discricionário/não discricionário a uma tabela do razão geral com base no número da conta. As três últimas colunas da tabela de mapeamento mostrada abaixo podem ser usadas para fornecer essas informações usando a função Lookup.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6832_1.png)

Usando a tabela acima, você pode usar a função Lookup para determinar os valores de cada conta. Por exemplo, você poderia usar a seguinte fórmula para o campo Fixed Variable (variável fixa):

=Lookup(Account,Chart of Accounts Mapping,Account, {Fixed/Variable} )

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Envie comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
