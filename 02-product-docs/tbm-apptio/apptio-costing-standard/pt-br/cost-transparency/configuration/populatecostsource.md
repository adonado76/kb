---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Preencher a tabela de dados mestre da fonte de custos"
breadcrumb: []
source_path: "cost-transparency/configuration/populatecostsource.html"
images:
  - "resources/images/ct_images/6843_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Preencher a tabela de dados mestre da fonte de custos

A tabela Dados mestre de origem de custos define os dados necessários para os relatórios relacionados a custos e orçamento. Para preencher a tabela, você deve carregar os valores de custo e de orçamento. Para preencher a tabela de dados mestre da fonte de custos, carregue dois conjuntos de dados: Cost Actuals (Custo real) e Cost Budget (Custo orçamentário). Mapeie os conjuntos de dados para a tabela de dados mestre da fonte de custos.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

## Fontes de dados típicas

Os valores de custo e orçamento geralmente são extraídos de fontes como o registro geral e o plano de contas. Esses dados geralmente são fornecidos por aplicativos como Oracle, SAP, Lawson e Cognos Financial Statement Reporting. Os dados que você usar determinarão o nível de detalhe disponível e as colunas que você mapeará para a tabela de dados mestre de origem de custos.

## Várias tabelas

Talvez você precise carregar várias tabelas. As tabelas típicas estão descritas abaixo.

- Razão geral (GL) - O razão geral é a fonte financeira da verdade na maioria das empresas. É um registro contábil sensível ao tempo usado para acompanhar as transações financeiras. As transações são categorizadas em várias contas e, muitas vezes, categorizadas por proprietários regionais ou centros de custo.
- Plano de contas - Um plano de contas fornece uma listagem completa de todas as contas em um sistema contábil. Uma conta é um registro exclusivo para cada tipo de ativo, passivo, patrimônio líquido, receita e despesa.
- Hierarquia organizacional - Uma hierarquia organizacional identifica cada cargo, sua função e a quem ele se reporta dentro da organização
- Orçamento - O orçamento é o gasto esperado em vários níveis de granularidade com base em como o cliente acompanha suas finanças. No aplicativo Costing Standard , o orçamento é monitorado por centro de custo e por conta.

Você anexa as tabelas à tabela Dados mestre de origem de custos. As tabelas devem conter campos que possam ser mapeados para os campos apropriados na tabela Dados mestre da origem de custos.

## Dados principais

Para obter uma descrição dos campos na tabela de dados mestre, consulte as informações na página do componente CTF - Fonte de custos no produto. Para exibir a página:

1. Clique na guia Project (Projeto) na faixa de opções.
2. Clique em Components (Componentes) na faixa de opções.
3. Clique no componente CTF - Fonte de custos.

## Campos obrigatórios e recomendados

Os campos obrigatórios e recomendados necessários para iluminar os relatórios padrão do site Costing Standard estão listados abaixo.

- Conta (obrigatório)
- Descrição da conta (recomendado)
- Grupo de contas (recomendado)
- Subgrupo de contas (recomendado)
- Valor (obrigatório)
- Benchmark % Alocação (obrigatório)
- Benchmark Sub-Tower (obrigatório)
- Centro de custos (obrigatório)
- Nome do centro de custos (recomendado)
- Proprietário do centro de custo (recomendado)
- Pool de custos (obrigatório)
- Subgrupo de custos (recomendado)
- Tipo de despesa (obrigatório)
- Fixo Variável (obrigatório)
- Is Depr (obrigatório)
- É trabalhista (obrigatório)
- ID do periódico (obrigatório)
- Descrição da linha do diário (recomendado)
- ID da linha do jornal (obrigatório)
- Proprietário (obrigatório)
- ID do projeto (recomendado)
- Nome do projeto (recomendado)

## Campos de alocação de chaves

A tabela Dados mestre de origem de custos tem vários campos-chave que são usados para alocar valores da tabela Origem de custos para as tabelas Trabalho, Ledger de ativos fixos, Fornecedores, Outros pools de custos e Projetos. A tabela abaixo mostra como os campos-chave são mapeados. Os metacampos são opcionais, mas se for inserido um valor em um metacampo no conjunto de dados mestre de origem de custos, será necessário inserir o mesmo valor no conjunto de dados de destino.

| Esse campo na tabela Cost SourceMaster Data: | Deve corresponder a esse campo: | Nessa tabela de destino: |
| --- | --- | --- |
| Fonte de custo\_Trabalho | Fonte de custo\_Trabalho | Dados mestre de mão de obra |
| Metacampo da chave de trabalho | Metacampo-chave da fonte de custos |
| Fonte de custos\_Chave do ativo fixo | Fonte de custos\_Chave do ativo fixo | Dados mestre do ativo fixo |
| Metacampo da chave do ativo fixo | Metacampo-chave da fonte de custos |
| Chave da fonte de custo\_fornecedor | Chave da fonte de custo\_fornecedor | Dados mestre do fornecedor |
| Metacampo da chave do fornecedor | Metacampo-chave da fonte de custos |
| Fonte de custos\_Outra chave do pool de custos | Fonte de custos\_Outra chave do pool de custos | Fonte de custos para os dados mestre do ITResource |
| Metacampo-chave do pool de outros custos | Metacampo-chave da fonte de custos |
| Fonte de custos Chave do projeto | Fonte de custos Chave do projeto | Dados mestre de projetos |

## Mapear os dados do plano de contas

Há cinco campos na tabela de dados mestre de origem de custos que devem ser mapeados para que o valor flua corretamente da tabela de origem de custos para o restante do modelo. Os campos são:

- **Pool de** custos - Um dos pools de custos padrão do site ATUM.
- **Subgrupo** de custos - Um dos subgrupos de custos padrão do site ATUM.
- **Is Depr** - Identifica uma entrada como depreciada ou não depreciada.
- **Fixo variável** - Identifica uma entrada como fixa ou variável.
- **Discricionário/não discricionário** - Identifica a entrada como discricionária ou não discricionária.

Se os dados que você trouxer para o aplicativo não incluírem campos que possam ser mapeados para os campos acima, será necessário criar uma tabela de mapeamento para fornecer as informações. Normalmente, a tabela de mapeamento atribui valores a cada uma das contas em seu plano de contas. Um exemplo de tabela é mostrado abaixo. Observe as três últimas colunas.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6843_1.png)

Com essa tabela, você pode usar a função Lookup para determinar os valores de cada conta. Por exemplo, você poderia usar a seguinte fórmula para o campo Fixed Variable (variável fixa):

```
=Lookup(Account,Chart of Accounts
        Mapping,Account,{Fixed/Variable})
```

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
