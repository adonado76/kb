---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de depuração"
breadcrumb: []
source_path: "studio/apptioscript/debug_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de depuração

Use Debug() para exibir uma caixa de diálogo que contenha texto ou dados em um local específico do script.

Essa função pode ser anexada a um botão ou a uma tabela editável onCellValueChange.

## Sintaxe

`Debug(expression)`

## expressão

A expressão pode ser uma das seguintes:

- Uma cadeia de texto entre aspas duplas.
- Uma linha e uma coluna de uma tabela editável.

## Exemplo

Exibir as palavras I'm here quando o script for executado:

`Debug("I'm here")`
