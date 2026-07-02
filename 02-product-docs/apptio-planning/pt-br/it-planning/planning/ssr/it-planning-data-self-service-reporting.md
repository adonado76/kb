---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Apptio BI visão geral"
breadcrumb: []
source_path: "it-planning/planning/ssr/it-planning-data-self-service-reporting.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Apptio BI visão geral

Apptio BI permite que os usuários criem e compartilhem seus próprios relatórios personalizados usando dados de uma variedade de aplicativos, incluindo Planning. Com os dados do Planning disponíveis no Apptio BI, os usuários agora podem criar um relatório personalizado que resume os dados de mão de obra, ativos, contratos e financeiros do departamento do Planning .

Para saber mais sobre Apptio BI, consulte [Apptio BI](../../../apptio_bi/home.html).

Nota:

Embora haja suporte para a funcionalidade de várias moedas, o site Apptio BI está disponível atualmente apenas em inglês.

## Pré-requisitos

Um administrador deve conceder a você permissão para acessar Apptio BI. Se você não tiver acesso, consulte [Apptio BI](../../../apptio_bi/home.html). As seguintes funções Enhanced Access Administration receberam acesso de visualização para Apptio BI :

- Admin
- Proprietário do centro de custo
- Proprietário do processo orçamentário

Os dados mostrados em Apptio BI seguem as mesmas permissões de visualização configuradas em Planning.

Se as fontes de dados Planning não aparecerem em Apptio BI, trabalhe com o gerente de atendimento ao cliente para registrar Planning como uma fonte de dados para Apptio BI. Veja aqui: Como registrar Planning como uma fonte de dados para Apptio BI.

## Dados disponíveis

Os dados de despesas de todos os planos ativos em Planning estão disponíveis para uso em Apptio BI. Para visualizar uma lista de planos ativos, selecione Plans (Planos) no menu Planning (consulte [Como se orientar no planejamento](../navigate-apptio-planning.html) ). Para revisar os dados que estarão disponíveis para um determinado plano, selecione um departamento e, em seguida, selecione Expenses (Despesas) no menu View (Exibir). Os dados das guias Resumo, Trabalho, Contratos e Ativos estarão disponíveis para relatórios. Os dados da guia Resumo estão disponíveis ao selecionar ITP Financials como fonte de dados.

Ao criar uma visualização em Apptio BI, você é solicitado a selecionar dimensões e métricas específicas dos dados a serem incluídos. Observe que as dimensões em Apptio BI são diferentes das " [dimensões de dados de referência](../navigate-apptio-planning.html) " em Planning. As dimensões disponíveis para relatório correspondem às colunas de despesas em Planning. As métricas correspondem aos valores listados para cada período.

Para visualizar uma lista de dimensões para relatórios, conclua as etapas a seguir:

1. No menu Plan (Plano), selecione um plano.

   Consulte [Encontre seu caminho no planejamento](../navigate-apptio-planning.html).
2. No menu de navegação esquerdo, selecione Planning > Expenses (Despesas).
3. No menu da seção Plano, selecione um departamento.
4. Navegue até qualquer uma das guias a seguir: Resumo, Trabalho, Contratos e Ativos.
5. Clique na seta suspensa em um nome de coluna e, em seguida, clique em Mostrar/Ocultar colunas.
6. As dimensões disponíveis correspondem a essa lista de colunas, independentemente de a coluna estar exibida ou oculta.

Em Apptio BI, um relatório é uma coleção de visualizações. Quando você criar um novo relatório, ele estará vazio. Você pode adicionar visualizações ao relatório para exibir dados.

Há suporte para colunas personalizadas para uso em relatórios.

Lembre-se:

- Apptio BI será reportado em seu ambiente de produção Planning .
- Apptio BI requer Planning 2.76 ou posterior.
- Há suporte para várias moedas.

Nota:

- Dados trabalhistas confidenciais (como Remuneração Base) não são expostos ao site Apptio BI.
- O ITP DataSources em Apptio BI mostra apenas os dados do tipo de objeto de custo Departamento. No momento, não há suporte para dados de projeto.
- Os dados relacionados ao PFP, como as dimensões de custo delegadas, não são expostos ao site Apptio BI até que o PFP seja compatível.
- Dados de despesas reais do Spend Management.

## Faça o download da lista de dados

Para obter a lista de dimensões e métricas disponíveis em Planning em Apptio BI : [faça o download como um arquivo.xslx](../../../resources/multimedia/itp%20-%20ssr%20integration/it%20planning%20data%20exposed%20to%20self%20service%20reporting_2020_12_08.xlsx).
