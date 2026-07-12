---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "GetLastFilterColumn função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/getlastfiltercolumn.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetLastFilterColumn função

**Aplica-se a** : TBM Studio 12.0 e posterior

Retorna o nome da última coluna à qual foi aplicado um filtro.

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Texto dinâmico

## Sintaxe

`GetLastFilterColumn()`

## Tipo de retorno

Texto

## Exemplo

O seguinte retornaria o valor "Business Unit" (Unidade de negócios)

`!Filter[Business Unit=Sales]`

**Veja também** : [GetLastFilterValue](getlastfiltervalue.htm "(Abre em uma nova guia ou janela)")
