---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Analisar um plano"
breadcrumb:
  - "Planning"
  - "Análises e relatórios"
source_path: "it-planning/planning/analyze-plan-forecast.html"
images:
  - "resources/images/it_planning_images/filters.png"
  - "resources/images/it_planning_images/spnd-trnd.png"
  - "resources/images/it_planning_images/spnd-wf.png"
  - "resources/images/it_planning_images/tree-map.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Analisar um plano

A página Summary (Resumo) fornece visualizações interativas do seu plano, exibindo despesas diretas e indiretas e, se ativado, encargos trabalhistas do projeto vinculados aos dados do número de funcionários. Use esta página para explorar o desempenho financeiro, identificar tendências e descobrir variações.

## Abrir a página de resumo

1. Selecione um **plano** no menu de planos
2. Navegue até **Planejamento** **→ Resumo**
3. Escolha a visualização apropriada:
   1. Guia **Financeiro** - para visualizar resumos financeiros
   2. Guia **Headcount** - para visualizar resumos de mão de obra e FTE

## Filtrar e configurar sua visualização

Use os menus suspensos **Department (Departamento** ), **Project (Projeto** ) e **Date Range (Intervalo de datas** ) para controlar o escopo do que é exibido.

Você pode refinar ainda mais a visualização usando as seguintes opções:

1. **Group By (Agrupar por** ) - Dinamiza as análises por uma dimensão ou atributo específico (por exemplo, Departamento, Categoria de conta, Fornecedor).
2. **Comparar com** - Selecione **Metas**, **Dados reais** ou outro **Plano** para permitir comparações de variações nos gráficos Detalhamento de despesas (mapa em árvore) e Cascata de despesas. A opção Comparar com metas só está disponível quando a opção Agrupar por está definida como Código de departamento ou Nome do departamento.
3. **Filtros** - Aplique filtros adicionais para restringir os dados que estão sendo analisados.
4. **Todos / OpEx / CapEx** - Filtre os resultados por tipo de despesa.
5. **Layout** - Altere o layout dos gráficos para se adequar à sua visualização de análise preferida.

Observação: Os filtros afetam os gráficos e as tabelas, mas não ajustam os KPIs.

![imagem dos filtros](../../../../../03-media/apptio-planning/resources/images/it_planning_images/filters.png)

## Compreensão dos principais recursos visuais

*Detalhamento das despesas - Gráfico de mapa em árvore*

Exibe a representação proporcional das despesas por sua dimensão **Group By** selecionada.

- Os blocos são codificados por cores de acordo com o status da variação (abaixo da meta = azul, acima da meta = laranja).
- Clique em um bloco para carregar percepções mais detalhadas no gráfico Spend Trend.
- Clique em **Flip Comparison** (ícone de seta) para inverter a direção da variação.

![imagem do gráfico de mapa de árvore de despesas](../../../../../03-media/apptio-planning/resources/images/it_planning_images/tree-map.png)

*Gráfico de tendências de despesas*

Mostra tendências ao longo do tempo para o grupo selecionado ou para o plano geral.

- Use o **seletor de dimensão** para detalhar ainda mais as despesas no período selecionado por outra dimensão.
- Use o **seletor de período de tempo** para alternar entre pontos de análise (meses, trimestres, anos).
- Inclui uma sobreposição de dados reais, se importados e disponíveis (somente visualização de meses).
- Clique no **botão de download** para exportar os detalhes do gráfico para csv.

![imagem do gráfico de tendências de despesas](../../../../../03-media/apptio-planning/resources/images/it_planning_images/spnd-trnd.png)

*Gráfico de cascata de despesas*

Se você selecionou um plano de comparação, uma meta ou dados reais, a cascata mostra as "entradas e saídas" da variação.

- A barra da esquerda é o seu plano atual; a barra da direita é o comparador (plano, meta, real).
- As barras são codificadas por cores de acordo com o status da variação (abaixo da meta = azul, acima da meta = laranja).
- Clique em **Flip Comparison** (ícone de seta) para inverter a direção da variação.
- Clique no **botão de download** para exportar os detalhes do gráfico para csv.

![imagem do gráfico de cascata de despesas](../../../../../03-media/apptio-planning/resources/images/it_planning_images/spnd-wf.png)
