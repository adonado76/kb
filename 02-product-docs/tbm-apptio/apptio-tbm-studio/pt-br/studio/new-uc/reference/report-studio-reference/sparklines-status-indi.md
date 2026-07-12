---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gráficos de tendência e indicadores de status"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas"
source_path: "studio/new-uc/reference/report-studio-reference/sparklines-status-indi.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de tendência e indicadores de status

**Colunas de minigráficos**

As minigráficos exibem pequenas linhas de tendência que mostram dados históricos e futuros em uma única célula.

**Sintaxe da função Sparkline:**

`=SPARKLINE(past, future, column)`

|  |  |
| --- | --- |
| **Parâmetro** | **Descrição** |
| passado | Número de períodos a serem analisados para a tendência retrospectiva. Deve ser um número positivo. |
| futuro | Número de períodos para a projeção. Deve ser um número positivo. |
| coluna | Nome da coluna que contém os dados a serem analisados. |

**Exemplo:** =SPARKLINE( 4,4,Cost ) exibe uma linha de tendência que abrange os últimos 4 meses e os próximos 4 meses para a coluna Custo.

**Colunas de indicador de status**

Os indicadores de status utilizam ícones coloridos para comunicar os estados dos valores de forma imediata.

**Sintaxe da função Icon:**

`=Icon(["icon_type"], condition1, condition2, ...)`

|  |  |
| --- | --- |
| **Tipo de ícone** | **Descrição** |
| círculos vermelhos | 2 estados: Círculo vermelho (expressão 1 verdadeira), círculo rosa (expressão 2 verdadeira) |
| 3colorcircles | 3 níveis: círculos verdes, amarelos e vermelhos, de acordo com as condições |
| (padrão) | Se nenhum tipo de ícone for especificado, o padrão será “redcircles” |

Os valores que não correspondem a nenhuma expressão recebem o último ícone do conjunto. Para ver todos os tipos de ícones disponíveis, passe o mouse sobre o nome do cálculo na caixa de diálogo “Configurações do campo de valor”.

**Indicadores de cálculo rápido**

Acesse essas opções em “Configurações do campo de valor” (clique com o botão direito do mouse em um valor na “Configuração do componente”):

|  |  |
| --- | --- |
| **Indicador** | **Descrição** |
| Ícones de limiar | Ícone vermelho abaixo do limite, ícone verde acima do limite. |
| Zero Flechas | Seta para cima (>0), seta lateral (=0), seta para baixo (<0). |
| Tendência do gráfico mini | Pequeno gráfico de tendências dos últimos seis meses. |

**Tópico principal:** [Componentes do relatório: Tabelas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
