---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "ObjectName função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/objectname.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ObjectName função

**Aplica-se a** : TBM Studio 12.0 e posterior

A função retorna o nome do objeto que está conduzindo o relatório atual.

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

Essa função é usada com mais frequência em caixas de texto HTML em relatórios como parte do texto dinâmico.

## Sintaxe

`ObjectName()`

## Argumentos

Nenhum

## Tipo de retorno

Sequência

## Exemplos

O texto dinâmico a seguir em uma caixa de texto HTML em um relatório retorna o nome do objeto de relatório atual.

`<%=ObjectName()%>`
