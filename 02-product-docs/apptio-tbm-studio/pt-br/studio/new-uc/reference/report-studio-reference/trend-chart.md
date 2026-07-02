---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gráficos de tendências"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/trend-chart.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de tendências

Os gráficos de tendências são gráficos de linhas especializados, concebidos especificamente para mostrar a evolução dos valores ao longo do tempo. Incluem suporte integrado para intervalos de tempo e podem incluir projeções estatísticas para prever valores futuros.

**Criando um gráfico de tendências**

1. Na guia Relatório, clique em Gráfico.
2. No painel Configuração de Componentes, arraste os campos para as áreas apropriadas.
3. Arraste um campo de tempo (Meses, Trimestres, Anos) para a área do eixo. É isso que transforma o gráfico em um gráfico de tendências.
4. Clique com o botão direito do mouse no campo de tempo na área do eixo para definir o intervalo de tempo.

**Opções de intervalo de tempo**

Ao clicar com o botão direito do mouse em um campo de tempo na área do Eixo, você pode selecionar um destes intervalos predefinidos:

- Neste trimestre: Exibe os três meses do trimestre fiscal atual.
- Este semestre: Exibe os seis meses do semestre fiscal atual.
- Este ano: exibe os 12 meses do ano fiscal atual.
- Intervalo: Abre uma caixa de diálogo onde você pode definir meses personalizados para trás e para frente a partir do período atual.

**Fixar o período**

Por padrão, os gráficos de tendências exibem dados relativos ao período selecionado no momento. Para fixar o gráfico a um período específico, independentemente da seleção de data do relatório, use o campo “Período de dados” na guia “Avançado” da caixa de diálogo “Propriedades”. Por exemplo, defina o período de data e hora como “Início do ano fiscal atual” para que seja sempre exibido o ano fiscal completo.

**Adicionando projeções**

Os gráficos de tendências podem incluir projeções que estimam valores futuros com base em dados históricos. O TBM Studio oferece vários algoritmos de regressão:

|  |  |
| --- | --- |
| **Algoritmo** | **Descrição** |
| Regressão | Regressão linear padrão para linhas de tendência simples. |
| Regressão linear múltipla | Regressão utilizando múltiplas variáveis independentes. |
| Regressão polinomial | Ajusta uma curva polinomial para capturar tendências não lineares. |
| Suavização exponencial simples | Suaviza os dados para reduzir o ruído e destacar tendências. |
| Suavização exponencial dupla | Leva em conta tanto o nível quanto a tendência dos dados. |
| Média móvel | Calcula médias em intervalos de tempo móveis. |

Observação: Para adicionar uma projeção a um gráfico de tendências antigo, clique com o botão direito do mouse no gráfico e selecione “Projetar tendência” no menu pop-up.

**Tópico principal:** [Componentes do relatório: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
