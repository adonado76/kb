---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gráficos de colunas + linhas (sobreposição)"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Visualizações"
source_path: "studio/report-studio/visualizations/col-line.html"
images:
  - "resources/images/studio_images/col-line.png"
  - "resources/images/studio_images/soverlay.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de colunas + linhas (sobreposição)

O gráfico Coluna + Linha (Sobreposição) combina visualizações de coluna e linha em um único gráfico. Permite comparar valores absolutos (colunas) com uma tendência ou métrica relacionada (linha) nas mesmas categorias.

Esta visualização é especialmente útil quando você deseja analisar as relações entre duas medidas diferentes sem alternar entre gráficos.

**Quando usar um gráfico de colunas + linhas**

Use um gráfico de colunas + linhas (sobreposição) quando desejar:

- Compare valores reais com uma tendência ou meta
- Visualize o volume e o desempenho juntos (por exemplo: custo versus utilização)
- Acompanhe as alterações ao longo do tempo enquanto continua a ver a distribuição por categoria
- Destaque como uma métrica se comporta em relação a outra

**Adicionar um gráfico de colunas + linhas a um relatório**

- Adicione um gráfico de colunas + linhas no painel Visualizações da barra de ferramentas
- Clique no gráfico para ativar os painéis Dados e Formato.
- Painel de dados
  - Selecione o objeto modelo no menu suspenso
  - Categorias – Define o eixo X do gráfico. Clique aqui ou arraste para adicionar dimensões a partir do Dimension Explorer
  - Valores das colunas – Métricas exibidas como colunas
  - Valores da linha – Métricas exibidas como uma sobreposição de linha
  - Legenda – Diferencia várias séries de colunas ou linhas
  - Filtros de coluna – Aplique filtros que afetam apenas os valores da coluna
  - Filtros de linha – Aplique filtros que afetam apenas os valores da linha.
- Painel de formatação
  - Propriedades gerais – Veja [Propriedades do componente](../components/components.html#abt-comp__comprop)
  - Propriedades específicas do gráfico de colunas + linhas
    - Categorias
      - Mostrar título da categoria
      - Mostrar rótulos de categoria
      - Escolha o tamanho da fonte, o estilo (negrito, itálico, sublinhado) e a cor
      - Mostrar linhas da grade
    - Valores
      - Mostrar título dos valores
      - Mostrar rótulos de valores
      - Escolha o tamanho da fonte, o estilo (negrito, itálico, sublinhado) e a cor
      - Mostrar linhas da grade
    - Legenda
      - Alterne para mostrar a legenda
      - Título da legenda, tamanho e estilo da fonte da legenda (negrito, itálico, sublinhado)
      - Cor do texto da legenda (com opção para redefinir a cor)
      - Rótulos de legenda – tamanho, estilo e cor da fonte
      - Localização da legenda – escolha entre centro, esquerda e direita
    - Linhas
      - Escolha o tipo de linha, cor e estilo
    - Colunas
      - Resultados a exibir – Permite escolher o número de colunas a exibir
      - Espaçamento entre colunas – Controla o espaçamento entre colunas adjacentes no gráfico, ajudando a melhorar a legibilidade e a clareza visual.
      - Cor da série – Aplique cor a diferentes séries
    - Etiquetas de dados
      - Alterne para mostrar as etiquetas de dados
      - Posição da etiqueta – escolha entre as diferentes posições

Exemplo: Gráfico de colunas + linhas

![imagem de gráficos de colunas e linhas sobrepostas](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/col-line.png)

O gráfico de colunas + linhas suporta fórmulas personalizadas e dimensões de fórmulas. Para obter mais detalhes, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "As fórmulas personalizadas (também conhecidas como dimensões de fórmula) permitem definir novas dimensões calculadas utilizando campos existentes no seu modelo de dados. Isso permite uma análise mais profunda e insights mais ricos, sem a necessidade de alterações no conjunto de dados ou esquema subjacente.")

**Gráficos de colunas empilhadas + linhas** : amplia o gráfico de colunas + linhas ao empilhar vários valores de coluna dentro de cada categoria, permitindo comparar distribuições de partes em relação ao todo juntamente com uma tendência ou métrica sobreposta.

**Eixo de proporção em gráficos sobrepostos:** Os gráficos sobrepostos agora oferecem suporte a um eixo de proporção, permitindo que várias séries de dados sejam alinhadas em uma escala comum para facilitar a comparação e melhorar a legibilidade.

![opção de sobreposição do eixo](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/soverlay.png)
