---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "GetLastPublishTime função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/getlastpublishtime.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetLastPublishTime função

Aplica-se a: 12.11.10 e posterior

Retorna a hora em que a publicação recorrente foi executada para atualizar os dados da tabela editável na tabela de transformação associada. Ele também exibe a última publicação para todos os três métodos: programação recorrente, botão de publicação ou upload do administrador no Studio. Essas datas/horas são mantidas no nível da tabela de transformação individual.

Os dados da tabela editável são publicados das seguintes maneiras:

- Publicar a partir da superfície de relatório
- Programação recorrente
- "Atualizar para este período" no transform

A última publicação é atualizada quando os dados são publicados de qualquer uma das formas acima.

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`= GetLastPublishTime(“transform_table_name”)`

## Argumentos

TableName

Nome da transformação criada a partir da tabela editável

## Tipo de retorno

Data Hora

## Exemplo

`GetLastPublishTime(“Table_Demo”)`

Resultado: 12 de novembro de 2024 12:31:00 PM GMT+05:30
