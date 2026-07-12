---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Seletor de coluna"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Componentes"
source_path: "studio/report-studio/components/rs-column-picker.html"
images:
  - "resources/images/studio_images/column-picker.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Seletor de coluna

Um Seletor de Colunas permite que os usuários controlem quais colunas são exibidas em uma tabela normal, tabela editável ou gráfico. Permite a exploração flexível de dados tabulares sem exigir alterações na configuração do relatório.

## Quando usar um Seletor de Colunas

Use um seletor de colunas quando desejar que os usuários:

- Mostrar ou ocultar colunas da tabela de acordo com suas necessidades
- Concentre-se em métricas ou dimensões específicas
- Reduzir a desorganização visual em tabelas largas

## Adicionar um Seletor de Coluna ao Relatório

1. Adicione um Seletor de Colunas a partir do painel Componentes na barra de ferramentas
2. Clique no Seletor de Colunas para ativar os painéis Dados e Formato.
3. Painel de dados
   1. Selecione o objeto modelo na lista suspensa
   2. Arraste as dimensões do Dimension Explorer para a seção de campos no painel de dados
4. Painel de formatação
   1. Propriedades gerais – Veja [Propriedades do componente](components.html#abt-comp__comprop)
   2. Propriedades específicas do Seletor de colunas
      1. Seleção
         1. Seleção múltipla - As colunas aparecem como um conjunto de caixas de seleção.
         2. Seleção única com - Os campos do seletor aparecem como botões de rádio.
      2. Habilitar Selecionar tudo
         1. Alterne para ver a opção **Selecionar tudo** no componente seletor de coluna.
      3. Orientação
         1. Vertical
         2. Horizontal

Exemplo: Seletor de colunas

![selecionador de colunas](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/column-picker.png)

O Column Picker suporta fórmulas personalizadas e dimensões de fórmulas. Para obter mais detalhes, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "As fórmulas personalizadas (também conhecidas como dimensões de fórmula) permitem definir novas dimensões calculadas utilizando campos existentes no seu modelo de dados. Isso permite uma análise mais profunda e insights mais ricos, sem a necessidade de alterações no conjunto de dados ou esquema subjacente.")
