---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Etiquetas e formatação de eixos"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/axis-labels.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Etiquetas e formatação de eixos

**Truncamento de rótulos**

Os rótulos exibidos nos eixos X e Y têm um comprimento máximo de 20 caracteres. Se um rótulo exceder esse comprimento, os caracteres do meio serão removidos e substituídos por reticências. Isso garante que as etiquetas permaneçam legíveis e, ao mesmo tempo, se encaixem no espaço disponível.

**Exemplo:** "aaaa bbbb cccc dddd eeee ffff 0001" seria truncado e exibido como "aaaa bb...fff 0001"

**Formatação de números**

Use a propriedade “Formato numérico do gráfico” para controlar a forma como os números aparecem nos eixos do gráfico. O formato utiliza padrões padrão de formatação numérica:

|  |  |  |
| --- | --- | --- |
| **Padrão** | **Exemplo de entrada** | **Exemplo de saída** |
| #,### | 5000000 | 5.000.000 |
| # | 5000000 | 5.000.000 (sem formatação) |
| ¤#,### | 5000000 | $5.000.000 (moeda local) |

Dica: Use o símbolo universal de moeda (¤) no campo de prefixo ou formato para exibir o símbolo de moeda adequado à localidade. Para inserir este símbolo, copie-o da documentação ou da caixa de diálogo de propriedades.

**Tópico principal:** [Componentes do relatório: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
