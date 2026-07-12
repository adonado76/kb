---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função Untag"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/untag.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função Untag

**Aplica-se a** : TBM Studio 12.0 e posterior

A função Untag diz ao aplicativo para ignorar todas as tags atribuídas aos drivers no modelo atual.

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Fórmulas de fontes de alocação

Em uma fórmula de alocação **avançada** em um modelo.

## Sintaxe

`Untag(value)`

## Argumentos

*valor*

Uma métrica modelada ou calculada, ou uma fórmula.

## Tipo de retorno

O tipo de retorno é o mesmo da coluna de argumentos.

## Exemplo

`=SOURCE*Untag({Qualified CtB (Cost driver)})`
