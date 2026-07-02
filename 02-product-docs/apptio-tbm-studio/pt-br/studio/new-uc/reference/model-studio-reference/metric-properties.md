---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Propriedades métricas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Métricas de modelo"
source_path: "studio/new-uc/reference/model-studio-reference/metric-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Propriedades métricas

Cada métrica possui propriedades configuráveis que controlam seu comportamento. As propriedades marcadas com (\*) aplicam-se apenas a métricas calculadas.

**Referência completa do imóvel**

|  |  |  |
| --- | --- | --- |
| **Propriedade** | **Valores** | **Descrição** |
| Visualização padrão | Nome do relatório | Relatório exibido ao clicar no link da métrica |
| Tipo de modelo | Modelo, calculado | Se o valor é derivado de alocações (Modelo) ou utiliza uma fórmula (Calculado) |
| Tipo de métrica | Cálculo de custos, precificação, dados numéricos | Cálculo de custos = monetário; Precificação = preço × quantidade; Numérico = outros |
| Oculto(a) | Booleano | Oculta a unidade métrica nas tabelas de unidades do objeto modelo |
| Formato de tabela | Fórmula | Formato de exibição em tabelas (por exemplo, =Currency($\_)) |
| Formato do gráfico | Padrão | Formato numérico no eixo do gráfico (por exemplo, $#,###) |
| Prefixo do gráfico | Texto | Prefixo adicionado à métrica nos gráficos (por exemplo, $) |
| Sufixo do gráfico | Texto | Sufixo adicionado à métrica nos gráficos |
| Comportamento temporal | Soma, Média, Recalcular | Como os agregados métricos se comportam ao longo dos períodos |
| Cálculo do valor\* | Fórmula | Fórmula que define o valor da métrica calculada |
| Pode somar\* | Booleano | Se os valores podem ser somados ou recalculados |
| Incluir nos modelos virtuais\* | Booleano | Incluir em modelos filtrados e recursivos |
| Ignorar para filtragem interna\* | Booleano | Excluir da avaliação da filtragem de linhas com zero |
| Intervalo de tempo\* | Nenhuma, Trimestral, Anual | Obter o valor do primeiro período do intervalo |

**Opções de comportamento temporal**

|  |  |
| --- | --- |
| **Opção** | **Comportamento** |
| Soma | Calcula cada período separadamente e, em seguida, soma os períodos. Utilizar para métricas aditivas, como Custo. |
| Média | Calcula cada período, soma os valores e divide pelo número de períodos. Utilizar para métricas de taxa. |
| Recalcular | Calcula os valores agregados em todas as colunas e, em seguida, executa novamente a fórmula. Use para índices. |

**Tópico principal:** [Métricas do modelo](../../../../studio/new-uc/reference/model-studio-reference/model-metrics.html)
