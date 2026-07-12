---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gráficos de linhas"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Visualizações"
source_path: "studio/report-studio/visualizations/rs-line.html"
images:
  - "resources/images/studio_images/rs-line.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de linhas

Um gráfico de linhas exibe pontos de dados conectados por linhas, tornando-o ideal para mostrar tendências, padrões e mudanças ao longo do tempo. É mais adequado para dados contínuos ou categorias sequenciais.

## Quando usar um gráfico de linhas

Use um gráfico de linhas quando desejar:

- Mostrar tendências ao longo do tempo ou categorias sequenciais
- Compare várias séries para análise de correlação ou padrões
- Destaque aumentos, diminuições ou flutuações nos dados

## Adicionar um gráfico de linhas a um relatório

1. Adicione um gráfico de linhas a partir do painel Visualizações na barra de ferramentas
2. Clique no Gráfico de Linhas para ativar os painéis Dados e Formato.
3. Painel de dados
   1. Selecione o objeto modelo no menu suspenso
   2. Categorias – Define o eixo X, geralmente uma dimensão baseada no tempo ou sequencial. Clique aqui ou arraste para adicionar dimensões a partir do Dimension Explorer
   3. Valores – Especifica a(s) métrica(s) exibida(s) como pontos de dados conectados por linhas
   4. Legenda – Divide os valores em várias séries com base em uma dimensão.
   5. Filtros – Limita os dados exibidos no gráfico com base nas condições selecionadas
   6. Resultados a exibir – Indique o número de linhas a exibir
   7. Configurar classificação – Controla a ordem das categorias no eixo X.
4. Painel de formatação
   1. Propriedades gerais – Veja [Propriedades do componente](../components/components.html#abt-comp__comprop)
   2. Propriedades específicas do gráfico de linhas
      1. Categorias
         1. Mostrar título da categoria
         2. Mostrar rótulos de categoria
         3. Escolha o tamanho da fonte, o estilo (negrito, itálico, sublinhado) e a cor
         4. Alternar para mudar a posição das categorias
         5. Mostrar linhas da grade
      2. Valores
         1. Mostrar título dos valores
         2. Mostrar rótulos de valores
         3. Escolha o tamanho da fonte, o estilo (negrito, itálico, sublinhado) e a cor
         4. Alternar para inverter a faixa
         5. Mostrar linhas da grade
      3. Legenda
         1. Alternar para mostrar a legenda
         2. Tamanho e estilo da fonte da legenda (negrito, itálico, sublinhado)
         3. Cor do texto da legenda (com opção para redefinir a cor)
      4. Linhas
         1. Escolha a cor e o estilo da linha
      5. Etiquetas de dados
         1. Alterne para mostrar as etiquetas de dados – centro, direita, esquerda
         2. Escolha o tamanho da fonte, o estilo (negrito, itálico, sublinhado) e a cor
         3. Definir cores automaticamente – atribui cores automaticamente às barras com base nos dados e no tema selecionados.
         4. Defina o contorno e a cor da etiqueta

Exemplo: Gráfico de linhas

![gráfico de linha](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-line.png)

Os gráficos de linha suportam fórmulas personalizadas e dimensões de fórmulas. Para obter mais detalhes, consulte [Fórmulas personalizadas](../create-first/custom-formula.html "As fórmulas personalizadas (também conhecidas como dimensões de fórmula) permitem definir novas dimensões calculadas utilizando campos existentes no seu modelo de dados. Isso permite uma análise mais profunda e insights mais ricos, sem a necessidade de alterações no conjunto de dados ou esquema subjacente.").

Os gráficos de linha também suportam visualizações compatíveis. Para obter mais detalhes, consulte [Visualizações compatíveis](visualizations.html#abt-visual__compvis).
