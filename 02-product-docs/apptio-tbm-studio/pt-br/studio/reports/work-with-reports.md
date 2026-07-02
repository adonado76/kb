---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Trabalhar com relatórios"
breadcrumb: []
source_path: "studio/reports/work-with-reports.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep054.png"
  - "resources/images/studio_images/studioimages/reports/rep055.png"
  - "resources/images/studio_images/studioimages/reports/rep057.png"
  - "resources/images/studio_images/studioimages/reports/rep058.png"
  - "resources/images/studio_images/studioimages/reports/studio_report_tab.png"
  - "resources/images/studio_images/studioimages/reports/studio_reports_auto_search.png"
  - "resources/images/studio_images/studioimages/reports/studio_reports_slicers_sui.png"
  - "resources/images/studio_images/studioimages/reports/studio_view_a_report.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Trabalhar com relatórios

**Aplica-se a** : TBM Studio 12.0 e posterior

Muito provavelmente, vários relatórios foram criados para apresentar os dados gerados pelo site Apptio. Geralmente, são dados de custo, mas também podem ser outros tipos de dados.

Os administradores podem configurar as permissões no nível de Report Collections e no nível de relatório individual. Para saber mais, consulte [Criar e gerenciar coleções de relatórios](creating-report-collections.html "Aplica-se a: TBM Studio 12.0 e posterior") e [Trabalhar com permissões de relatórios](control-access-reports-11755.html "Aplica-se a: Apptio TBM Studio 12.7 e posterior.").

## Exibir um relatório

Para visualizar um relatório, selecione Relatórios no Project Explorer.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_view_a_report.png)

Também é possível selecionar relatórios na guia Relatório, que é exibida após o check-out de um relatório.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_report_tab.png)

## Filtrar um relatório

Se houver um ou mais slicers em um relatório, use-os para filtrar o relatório. Clique em qualquer combinação das entradas em uma ou mais das segmentações.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_reports_slicers_sui.png)

Para limpar todos os filtros, clique no ícone de limpeza de redefinição de filtro ![imagem](../../resources/images/studio_images/studioimages/icons/filter%20reset.png).

Para pesquisar as entradas do filtro, digite o texto no campo Pesquisar.

## Busca automática

Nas tabelas dos relatórios, você pode ver campos de pesquisa abaixo dos cabeçalhos das colunas. Você pode inserir texto nesses campos para filtrar a tabela por esse termo de pesquisa.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_reports_auto_search.png)

Se você inserir um texto no campo Pesquisar, somente as linhas que contêm o texto serão exibidas. O filtro não diferencia maiúsculas de minúsculas e aceita texto e números, inclusive decimais. Você pode prefaciar o texto com o! para pesquisar entradas que não contenham texto. Para colunas numéricas, você pode usar os operadores padrão: =,<, <=, >, >=,!=. Para pesquisar uma célula vazia, digite a palavra BLANK na caixa de filtro. Para pesquisar células que não estejam vazias, digite!BLANK na caixa do filtro. Não há suporte para caracteres curinga, como asterisco (\*) e sinal de número #. Se você pesquisar valores = 0, serão incluídos números menores que 1 x 10-7.

As opções de pesquisa estão resumidas na tabela a seguir:

| Opção | Coluna de números | Coluna de texto | Descrição |
| --- | --- | --- | --- |
| !BRANCO | Sim | Sim | Digite essa palavra para pesquisar células que não estejam vazias. |
| !texto | Não | Sim | Pesquisar linhas que não contenham o texto. |
| && | Sim | Sim | Função AND. Por exemplo, Save && Master retorna todas as entradas que contêm a palavra Save e Master. É possível inserir mais de um && em uma pesquisa. Você pode usar a função && ou a || em uma pesquisa, mas não ambas. |
| = | Sim | Sim | Ao usar com texto, a correspondência diferencia maiúsculas de minúsculas. |
| >, <, >=, <=, != | Sim | Não | Use esses operadores com colunas de números. |
| BRANCO | Sim | Sim | Digite essa palavra para pesquisar células vazias. |
| Texto | Não | Sim | Pesquise as linhas que contêm o texto. |
| || | Sim | Sim | Função OR. Por exemplo, Save || Master retorna todas as entradas que contêm a palavra Save ou Master. É possível inserir mais de um || em uma pesquisa. Você pode usar a função || ou a função && em uma pesquisa, mas não ambas. |

## Ocultar elementos em gráficos

Nos gráficos, você pode ocultar elementos na legenda.

Em todos os tipos de gráficos com legendas, você pode ocultar elementos selecionados na legenda para se concentrar em dados específicos nos gráficos. Para ocultar um elemento, clique no elemento na legenda. O elemento está acinzentado. Por exemplo, suponha que você tenha o gráfico Servidores mostrado na imagem a seguir:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep054.png)

Você deseja se concentrar apenas em servidores Windows. Você clica nos outros quatro elementos da legenda para produzir o gráfico mostrado na imagem a seguir:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep055.png)

Quando você move o ponteiro do mouse sobre uma barra em um gráfico de barras, a dica de ferramenta exibe o valor da barra. Em um gráfico de barras empilhadas, a dica de ferramenta mostra o valor e a porcentagem do elemento na barra. Se você tiver elementos ocultos no gráfico, a porcentagem refletirá os elementos exibidos no momento.

## Ampliar os gráficos

Nos gráficos de linhas, é possível ampliar períodos de tempo específicos mantendo o botão do mouse pressionado e arrastando o ponteiro do mouse horizontalmente pelo gráfico. Por exemplo, suponha que você tenha o gráfico de linhas mostrado na imagem a seguir. Você deseja aumentar o zoom para ver os números do segundo trimestre, portanto, arraste o ponteiro do mouse de abril a junho.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep057.png)

O resultado é mostrado na imagem a seguir. Para redefinir o gráfico, selecione Reset Zoom no canto superior direito do gráfico. Quando você navega para fora de um relatório, todos os zooms são redefinidos.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep058.png)
