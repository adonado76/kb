---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Opções de exibição de dados"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas"
source_path: "studio/new-uc/reference/report-studio-reference/data-display-options.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Opções de exibição de dados

**Formatação de números**

A formatação de números controla a forma como os valores numéricos são exibidos na tabela. A formatação pode ser definida no nível da métrica (para métricas de modelo), no nível da coluna (para colunas de fórmula) ou usando a função ` NumberFormat `.

|  |  |  |  |
| --- | --- | --- | --- |
| **Tipo de formato** | **Exemplo de padrão** | **Exemplo de saída** | **Notas** |
| Número padrão | #,### | 5.000.000 | Inclui separador de agrupamento |
| Moeda (USD) | $#,###,00 | US$ 5, 000.00 | Use ¤ para a moeda local |
| Percentual | #,###% | 75% | Valor multiplicado por 100 |
| Precisão decimal | #,###,00 | 1, 234.56 | Número de casas decimais fixas |
| Milhões | $#,###M | $5M | Sufixo de abreviação |
| Sem formatação | # | 5000000 | Número bruto |

**NumberFormat sintaxe da função:**

`=NumberFormat(Table.Column, "$#,###.00")`

**Dica:** Para formatar como moeda usando as configurações regionais do projeto, use o símbolo universal de moeda (¤) em vez de um símbolo específico de moeda.

**Exibição de números negativos**

Os números negativos podem ser exibidos em vários formatos, especificando-se um padrão para números negativos na função ` NumberFormat `.

|  |  |  |
| --- | --- | --- |
| **Estilo** | **Padrão** | **Exemplo de saída** |
| Sinal de menos (padrão) | #,###;-#,### | -1.000 |
| Parênteses | #,###;(#,###) | (1.000) |
| Moeda entre parênteses | $#,###;($#,###) | (US$ 1.000) |

**Exibição de valores nulos e vazios**

Por padrão, os valores vazios ou nulos nas tabelas são exibidos como espaços em branco. Use a função IF para exibir uma alternativa:

`=IF(IsNumeric(Value), Currency(Value), "$0")`

**Filtro de zeros**

Você pode remover linhas com valores nulos das tabelas para se concentrar nos dados relevantes.

**Para aplicar o filtro de zeros:**

1. Selecione a tabela e clique na guia Dados.
2. Clique em "Zeros".
3. Selecione os relatórios dos quais os zeros devem ser removidos.
4. Clique em OK. Para reverter, selecione os relatórios e clique em “Reverter tudo”.

**Tópico principal:** [Componentes do relatório: Tabelas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
