---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de publicação recorrente"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/ApptioScript-function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de publicação recorrente

**Aplicável a** : TBM Studio 12.11.22 e versões posteriores

O recurso **de publicação recorrente** permite automatizar a publicação de dados de tabelas editáveis por meio de uma função do ApptioScript. Ao clicar no botão, o sistema permite que você crie um Apptioscript para programar execuções recorrentes de publicação. Após a execução, o script publica os dados da tabela editável na tabela de transformação associada.

## Onde usar

Use a sintaxe no campo **“Ação do servidor”** de um botão em um relatório.

## Sintaxe

`PublishNow("schedule2", "schedule4",autoPromoteToProd="true")`

## Parâmetros

O Anexo 2 é um parâmetro obrigatório, enquanto os demais parâmetros são opcionais

*Anexo 2* : Defina quando a publicação recorrente deve ser executada.

*autoPromoteToProd="true"* Quando definido como `true`, as alterações publicadas são transferidas para **o ambiente de produção.** Se definido como `false`, as alterações permanecem no ambiente **de teste**.

## Exemplo

`PublishNow("Weekday Evening Publish", autoPromoteToProd="true")`

Isso será publicado todas as noites dos dias úteis e os dados serão transferidos para a tabela de transformação associada.
