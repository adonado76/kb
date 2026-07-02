---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Fatiador"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Componentes"
source_path: "studio/report-studio/components/rs-compact-slicer.html"
images:
  - "resources/images/studio_images/slicer.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Fatiador

Um Slicer permite que os usuários filtrem dados de forma interativa em um relatório, selecionando um ou mais valores de uma dimensão. Os segmentadores aplicam suas seleções em todos os componentes e visualizações suportados no relatório, permitindo uma análise focada sem modificar a estrutura do relatório. Os cortadores também são aplicáveis em tabelas editáveis.

## Quando usar um cortador

Use um Slicer quando desejar:

- Filtre um relatório por uma única dimensão (por exemplo, família de aplicativos, região, centro de custos ou tempo)
- Altere rapidamente o contexto dos dados

## Adicionar um Slicer ao Relatório

1. Adicione um Slicer a partir do painel Componentes na barra de ferramentas
2. Clique no Slicer para ativar os painéis Dados e Formato.
3. Painel de dados
   1. Selecione o objeto modelo na lista suspensa
   2. Arraste uma dimensão do Dimension Explorer para o campo Slice by. Isso define a dimensão que controla o segmentador.
   3. Adicione um ou mais filtros para restringir as opções do segmentador. Isso é útil quando você deseja expor um subconjunto controlado de valores aos usuários.
4. Painel de formatação
   1. Propriedades gerais – Veja [Propriedades do componente](components.html#abt-comp__comprop)
   2. Propriedades específicas do Slicer
      1. Pesquisar
         1. Contains (Contém) - Encontra todos os valores que incluem os caracteres inseridos.
         2. Starts With - Encontra todos os valores que começam com os caracteres inseridos.
      2. Tipo de cortador
         - Menu suspenso
           - Exibe os valores do filtro em uma lista suspensa compacta.
           - Adequado quando há muitos valores de divisão.
           - Expanda a lista para fazer uma seleção.
         - Lista vertical
           - Exibe os valores do filtro como uma lista visível.
           - Mostra todos os valores de uma só vez.
           - Permite uma seleção mais rápida sem expandir um menu.
      3. Classificar
         1. ABC/123
         2. Estado
      4. Opções rápidas de tamanho
         1. Grande, Médio, Pequeno

Exemplo: Cortador

![componente slicer](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/slicer.png)

O Slicer suporta fórmulas personalizadas e dimensões de fórmulas. Para obter mais detalhes, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "As fórmulas personalizadas (também conhecidas como dimensões de fórmula) permitem definir novas dimensões calculadas utilizando campos existentes no seu modelo de dados. Isso permite uma análise mais profunda e insights mais ricos, sem a necessidade de alterações no conjunto de dados ou esquema subjacente.")
