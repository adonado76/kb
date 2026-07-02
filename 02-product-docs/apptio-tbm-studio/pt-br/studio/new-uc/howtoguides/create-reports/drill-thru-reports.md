---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar relatórios detalhados"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Relatórios avançados"
source_path: "studio/new-uc/howtoguides/create-reports/drill-thru-reports.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar relatórios detalhados

**Objetivo:** Permitir que os usuários cliquem nos dados resumidos e acessem relatórios detalhados, proporcionando uma exploração progressiva dos dados, desde visões gerais até detalhes específicos.

**Quando usar:** Quando os usuários precisam explorar hierarquias de dados de forma interativa, como clicar em uma unidade de negócios para ver suas aplicações ou clicar em uma categoria de custos para ver itens individuais.

**Tempo estimado:** 20 a 30 minutos por configuração de drill-through

## Entendendo a navegação detalhada

Os relatórios com funcionalidade de drill-through permitem que os usuários cliquem em valores nas tabelas ou em elementos nos gráficos para acessar relatórios mais detalhados. Quando configurados, os valores vinculados aparecem em azul nas tabelas. Os gráficos também podem conter links para relatórios quando os usuários clicam nas fatias do gráfico circular ou nos segmentos da barra.

O TBM Studio oferece vários padrões de detalhamento:

- **Exploração de dados agrupados:** quando você usa a função GROUPBY em uma tabela, as entradas agrupadas se transformam automaticamente em links clicáveis que revelam os detalhes subjacentes.
- **Links de navegação configurados:** é possível configurar explicitamente colunas de tabelas ou elementos de gráficos para navegar até relatórios específicos com filtragem opcional.
- **Navegação por botões:** use componentes de botão para facilitar a navegação entre relatórios.
- **Links codificados:** use sintaxe no estilo Wiki nas caixas de texto HTML para criar uma navegação personalizada com texto dinâmico.

**Pré-requisitos**

- Relatório de origem com dados resumidos (ponto de partida para os usuários do relatório)
- Relatório de metas com dados detalhados (para o qual os usuários do relatório serão direcionados)
- Relações de dados estabelecidas por meio do Mecanismo de Inferência do Apptio
- Tabelas ou gráficos ad hoc (a navegação funciona apenas com componentes ad hoc, não com componentes legados)

## Método 1: Configurar links de navegação nas colunas da tabela

Este método cria links clicáveis nas colunas da tabela que levam a um relatório de destino, passando, opcionalmente, o contexto do filtro.

1. Abra o relatório de código-fonte e dê uma olhada.
2. Selecione a coluna da tabela que você deseja tornar clicável (por exemplo, Unidade de Negócios).
3. Na guia Ad Hoc, clique em Drill na seção Navegação. O painel de propriedades de navegação é exibido.
4. Marque a opção “Ativar navegação” para ativar os links desta coluna.
5. No campo “Navegar para”, selecione o relatório de destino na lista suspensa. Você também pode clicar em “Novo relatório” para criar o relatório desejado.
6. Configure as opções de contexto para controlar quais informações são passadas para o relatório de destino:
   - **Filtrar na linha selecionada:** filtra o relatório de destino com base no valor em que o usuário clicou
   - **Filtrar com base nas seleções do segmentador aplicado:** transfere todos os filtros ativos do segmentador para o relatório de destino
   - **Incluir os filtros do relatório atual:** aplica os filtros definidos na caixa de diálogo Configuração do componente
   - **Adicionar coluna selecionada:** adiciona a coluna clicada ao relatório de destino, caso ainda não esteja presente
7. (Opcional) Marque a opção “Abrir como modal” para exibir o relatório de destino em uma janela pop-up, em vez de abrir uma nova página no navegador.
8. Salve e verifique o relatório.

Dica: Para relatórios de detalhamento em janelas modais (pop-ups), mantenha o relatório de destino simples. Evite filtros complexos ou seletores de colunas que possam não ser exibidos corretamente na janela pop-up.

## Método 2: Configurar a navegação no gráfico

Permita que os usuários cliquem nos elementos do gráfico (fatias do gráfico circular, segmentos da barra) para acessar relatórios detalhados.

1. Selecione seu gráfico e vá para a guia de configuração do gráfico.
2. Na seção Navegar (Explorar), marque a opção Ativar navegação. Isso torna os elementos do gráfico clicáveis.
3. (Opcional) Marque a opção “Usar detalhamento por métrica” para permitir clicar nos valores numéricos exibidos nas barras ou fatias do gráfico circular, e não apenas nos próprios segmentos.
4. No campo Navegar, digite o nome do relatório de destino. O relatório deve ser um subrelatório do relatório atual.
5. Salve e verifique o relatório.

Observação: os links do relatório se aplicam apenas a tabelas baseadas em objetos e gráficos ad hoc. Não é possível configurar a navegação detalhada a partir de tabelas de transformação ou gráficos legados.

## Método 3: Navegação por botões

Adicione botões de navegação explícitos que levem os usuários a relatórios específicos.

1. Na guia Relatório, clique no botão. Um componente de botão é adicionado ao relatório.
2. Clique no pequeno triângulo no canto superior esquerdo do botão e selecione Propriedades.
3. Na guia Botão, insira um texto descritivo no campo Texto do botão (por exemplo, “Ver detalhes do aplicativo”).
4. Na guia Ações, configure a navegação:
   - **Navegar:** insira um link no estilo wiki para o relatório de destino
   - **Alterar data:** opcionalmente, altere o período ao navegar
   - **Botão Voltar:** marque esta opção para criar um botão "Voltar" que retorna ao relatório anterior
5. Clique em OK para salvar a configuração do botão.

## Sintaxe de links no estilo wiki

Use esta sintaxe em caixas de texto HTML ou campos de navegação por botões:

`[[report|display-text|tooltip]]`

|  |  |
| --- | --- |
| **Sintaxe** | **Descrição** |
| [[ReportName]] | Link para um relatório filho, com o nome do relatório como texto do link |
| [[ ReportName|Click Aqui]] | Link com texto personalizado |
| [[..]] | Subir um nível na hierarquia do relatório |
| [[/]] | Acesse o relatório padrão do projeto |
| [[//ProjectName/Report]] | Link para um relatório de outro projeto |
| [[dialog:report:ReportName]] | Abrir o relatório em uma janela pop-up modal |
| [[tab:TabName/ReportName]] | Link para um relatório em uma guia específica |

## Padrões comuns de detalhamento

**Padrão 1: Unidade de Negócios para Aplicações**

Um relatório resumido de custos apresenta os custos por unidade de negócios. Os usuários clicam em uma unidade de negócios para ver todos os aplicativos pertencentes a essa unidade. Configure a coluna “Unidade de Negócios” com a opção “Ativar navegação” marcada e a opção “Filtrar na linha selecionada” ativada. Isso passa a unidade de negócios selecionada como filtro para o relatório de Aplicações.

**Padrão 2: Da categoria às partidas individuais**

Um gráfico mostra os custos por categoria (gráfico circular). Os usuários clicam em uma fatia do gráfico circular para ver os itens individuais que compõem essa categoria. Ative a navegação no gráfico e selecione o relatório “Itens de linha” como destino.

**Padrão 3: Hierarquia multinível**

O Relatório A apresenta as Unidades de Negócio. Ao clicar em uma unidade, o usuário é direcionado ao Relatório B, que mostra os centros de custo dessa unidade. Ao clicar em um centro de custo, você é direcionado ao Relatório C, que mostra os aplicativos desse centro de custo. Configure a navegação de cada nível para filtrar com base na linha selecionada e inclua as seleções dos filtros aplicadas, a fim de manter o contexto ao longo do caminho de detalhamento.

## Resultados esperados

- Os valores vinculados nas tabelas aparecem como texto sublinhado em azul
- Ao clicar em um link, você é direcionado ao relatório de destino
- O contexto do filtro é passado com base na sua configuração
- A trilha de navegação é exibida

## Armadilhas comuns

- **A navegação não está funcionando:** verifique se você está usando tabelas/gráficos ad hoc, e não componentes legados. A navegação funciona apenas com componentes da Configuração Ad Hoc de Componentes.
- **O relatório de destino não exibe dados:** certifique-se de que as relações entre os dados estejam definidas por meio do Mecanismo de Inferência do Apptio. Os dados de origem e de destino devem estar vinculados.
- **Problemas de desempenho:** tenha cuidado ao criar links para relatórios que exijam um tempo de cálculo significativo. Isso pode afetar o desempenho do sistema.

## Tarefas relacionadas

- [Criar coleções de relatórios](build-rc.html)
- [Adicionar segmentadores e filtros](use-slicers.html)
- [Configurar a visibilidade dos componentes](add-et-rep.html)

**Tópico principal:** [Relatórios avançados](../../../../studio/new-uc/howtoguides/create-reports/adv-rep.html)
