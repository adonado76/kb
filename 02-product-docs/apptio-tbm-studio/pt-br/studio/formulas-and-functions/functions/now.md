---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função atual"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/now.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função atual

A função Now( ) retorna a data e a hora atuais como um registro de data e hora do UNIX com base na hora do servidor. O tempo é baseado no tempo em que a função é executada. O resultado é armazenado em cache no disco, durante as reinicializações, etc. Ele é atualizado somente quando um recálculo completo é realizado.

## Sintaxe

`Now()`

## Comportamento

- Retorna a data e a hora atuais do servidor como um registro de data e hora do UNIX quando a função é avaliada.
- Usado em fórmulas que exigem a data atual do sistema, como o cálculo do tempo decorrido ou a filtragem por atividade recente.

## Parâmetros

Nenhum

## Tipo de retorno

Data

## Exemplo

- Retorna o carimbo de data/hora atual do sistema, por exemplo, para comparações com outro campo de data:

  ```
  Now()
  ```
- Calcula o número de períodos decorridos desde o valor no site {Start Date} column.: `Months(Now()) - Months({Start Date})`

**Observações** :

- Essa função não aceita nenhum argumento.
- A função Now não pode ser usada em tabelas de transformação porque ela não será atualizada. Se uma função Now tiver sido adicionada a uma tabela de transformação da versão 8, ela deverá ser removida.
