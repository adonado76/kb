---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Referência rápida de fórmulas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Data Studio Referência"
source_path: "studio/new-uc/reference/formulas-quick-reference.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referência rápida de fórmulas

Para obter a documentação completa sobre fórmulas e funções, consulte a Seção 5.4 Fórmulas e funções. Adicionando etapas de transformação

**Sintaxe da fórmula:**

- Comece com = (obrigatório)
- Referência a colunas usando chaves: {Column Name}
- Use os operadores padrão: +, -, \*, /

**Padrões comuns de fórmulas:**

|  |  |
| --- | --- |
| **Padrão** | **Exemplo de fórmula** |
| Concatenar | ="prefix-"& {Column} |
| Condicional | =Se( {Type} ="A", {Value} \*2, {Value} ) |
| Consulta | =Lookup( {Key}, Table, {SourceKey}, {ReturnColumn} ) |
| Formato numérico | =NumberFormat({Column},"#,###") |
| Conversão de tipo (Texto para Numérico) | =VALOR( {Column} ) |
| Conversão de tipo (numérico para rótulo) | =NumberFormat({Column},"#,###") |
| Formato de data | =DateFormat({Column },"aaaa-MM-dd") |

**Tópico principal:** [Referência do ` Data Studio `](../../../studio/new-uc/reference/data-studio-reference.html)
