---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Produtos Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso da solução"
  - "Produtos"
source_path: "cost-transparency/solution-uc/product-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Produtos Introdução

O componente TCO do produto permite que as organizações modelem, calculem e analisem o custo total de propriedade (TCO) dos produtos ao longo de todo o seu ciclo de vida. Ele oferece transparência total dos custos dos produtos, conectando dados financeiros e operacionais, permitindo que as equipes de Produto, Finanças e Tecnologia compreendam os fatores que influenciam os custos, acompanhem os gastos ao longo do ciclo de vida e alinhem as decisões de investimento com os resultados estratégicos. Este componente faz parte do Product Content Suite e oferece suporte a uma governança financeira consistente e centrada no produto em todo o portfólio.

## Instalação de componentes

A solução TCO do produto é ativada por meio de dois novos componentes criados para a solução. São eles:

- Custo total de propriedade do produto
- Relatórios de TCO do produto

**Observação:** esses componentes estão disponíveis nos modelos **v120 e posteriores**.

## Pré-requisito

Você deve instalar os seguintes componentes antes de instalar o componente TCO do produto:

- CTF - Fonte de custos
- CTF - Trabalho
- CTF - Torres de TI
- Aplicativos CT - Aplicações
- Aplicativos CT - Serviços
- CT - Unidades de Negócios

## Fontes comuns de dados

O TCO do produto aproveita os dados financeiros e operacionais de vários sistemas empresariais. Os dados de custos são normalmente obtidos do livro razão, incluindo OpEx e CapEx em todos os centros de custos e contas. Os dados de apoio geralmente provêm de portfólios de aplicações, sistemas de gestão de projetos e investimentos, ferramentas de controle de mão de obra e tempo, e plataformas de gestão de fornecedores ou contratos. Essas fontes permitem a atribuição precisa dos custos aos produtos e apoiam a análise do ciclo de vida e do portfólio.

**Conjuntos de dados**

Pode ser necessário carregar a tabela do feed do catálogo de produtos e mapeá-la para o conjunto de dados mestre de todos os serviços comerciais fornecido no componente.

Além disso, para classificar as ofertas como produtos, selecione **Todos os serviços comerciais** como destino e defina **Tipo de oferta de serviço = Produto** no campo Oferta de serviço.
