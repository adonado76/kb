---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Análise aprimorada de arquivos do Excel"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Data Studio Referência"
source_path: "studio/new-uc/reference/enhanced-excel-parsing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Análise aprimorada de arquivos do Excel

A análise aprimorada do Excel lê os valores brutos diretamente dos arquivos do Excel, ignorando a formatação do Excel para aumentar a precisão.

## Tratamento de formatos

|  |  |  |  |
| --- | --- | --- | --- |
| **Formato do Excel** | **Antigo analisador** | **Novo analisador** | **Fórmula de conversão** |
| Geral | Olá | Olá | Não é necessário |
| Número | 1 | 0.99999999 | =Round( {Column},0) |
| Moeda | $10.50 | 10.5 | =Currency( {Column}, "#,## 0.00 ") |
| Contabilidade | 34, 343.00 | 34343 | =NumberFormat({Column},"#,##0.00") |
| Data | 1-Jan-24 | 1704047400 (época) | =DateFormat({Column }, "d-MMM-aaaa") |
| Percentual | 10% | 0.1 | =NumberFormat({Column }, "#.00%") |

## Conversão de data e hora

**Sistema de datas do Excel:** números de série sequenciais que começam com 1 = 1º de janeiro de 1900

**Unix Época:** Início em 1º de janeiro de 1970, às 00:00:00 UTC

**Fórmula de conversão:** =DateFormat(({Column }-25569)\*86400,"M/d/aa")

**Explicação:**

- 25569 = número de dias entre a época do Excel (1900) e a época do Unix (1970)
- 86.400 = segundos por dia

**Tópico principal:** [Referência do ` Data Studio `](../../../studio/new-uc/reference/data-studio-reference.html)
