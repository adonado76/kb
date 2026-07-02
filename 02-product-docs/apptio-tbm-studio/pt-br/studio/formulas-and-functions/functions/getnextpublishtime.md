---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "GetNextPublishTime função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/getnextpublishtime.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetNextPublishTime função

Aplica-se a: 12.11.10 e posterior

Retorna o tempo de execução planejado quando ocorrerá a próxima publicação recorrente. Essas datas/horas são mantidas no nível da tabela de transformação individual.

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`= GetNextPublishTime(“Table_name”)`

## Argumentos

TableName

Nome da transformação criada a partir da tabela editável

## Tipo de retorno

Data Hora

## Exemplo

`GetNextPublishTime(“Table_Demo”)`

Resultado: 12 de novembro de 2024 12:31:00 PM GMT+05:30
