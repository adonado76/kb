---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gráficos de barras"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/bar-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de barras

Os gráficos de barras apresentam barras horizontais para comparar valores entre categorias. Esses são os tipos de gráfico padrão quando se adiciona um novo gráfico a um relatório e são ideais quando os rótulos das categorias são longos ou quando se compara muitos itens.

**Gráfico de barras horizontais**

O gráfico de barras horizontais padrão exibe uma única série de valores com barras que se estendem da esquerda para a direita. Cada barra representa um valor de categoria, facilitando a comparação de magnitudes entre diferentes itens, como centros de custo, aplicativos ou unidades de negócios.

**Quando usar: para** comparar valores entre categorias com nomes longos, classificar itens por valor ou exibir dados em que o eixo das categorias precisa de mais espaço do que o eixo dos valores.

**Gráfico de barras horizontais empilhadas**

Os gráficos de barras horizontais empilhadas dividem cada barra em segmentos que representam diferentes séries. Isso mostra tanto o valor total quanto a composição desse total. Use isso quando precisar mostrar como os diferentes componentes contribuem para um valor total.

**Quando usar: Para** mostrar relações entre custos parciais e totais, mantendo a possibilidade de comparar totais entre categorias, como, por exemplo, apresentar a composição dos custos por tipo de despesa para cada departamento.

**Configuração dos dados do gráfico de barras**

|  |  |
| --- | --- |
| **Área de configuração** | **Descrição** |
| Legenda | Arraste os campos de dimensão para definir as categorias exibidas como barras separadas ou segmentos de barra (para gráficos empilhados). A legenda determina como os dados são agrupados. |
| Valores | Arraste os campos métricos para definir os valores representados pelo comprimento das barras. Várias métricas geram barras agrupadas ou segmentos empilhados adicionais. |
| Axis | Arraste os campos de dimensão ou de tempo para definir os rótulos do eixo Y (para barras horizontais). Os campos de tempo permitem uma apresentação em forma de gráfico de tendências. |
| Filtros | Arraste os campos e configure os critérios de filtro para limitar os dados exibidos no gráfico. |

**Propriedades específicas do gráfico de barras**

- Número máximo de linhas: controla o número de barras exibidas. Os itens excedentes são agrupados na barra "Outros".
- Gráficos de série única multicoloridos: quando ativada, cada barra em um gráfico de série única é exibida em uma cor diferente.
- Ordem inversa: Inverte a ordem das barras no eixo.
- Ocultar eixo X / Ocultar eixo Y: Remove os rótulos dos eixos do gráfico.
- Ocultar linhas da grade: Remove as linhas horizontais e verticais da grade para proporcionar uma aparência mais limpa.

**Tópico principal:** [Componentes do relatório: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
