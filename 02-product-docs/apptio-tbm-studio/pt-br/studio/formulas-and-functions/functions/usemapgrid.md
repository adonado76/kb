---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função Use_Map_Grid"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/usemapgrid.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função Use_Map_Grid

**Aplica-se a** : TBM Studio 12.0 e posterior

Para alocações baseadas em tabelas, especifica mapeamentos de unidades um a um e uma porcentagem do valor da unidade de origem. Essa função substitui a [Use\_Map\_Table](usemaptable.htm "(Abre em uma nova guia ou janela)").

## Onde usar

Em uma fórmula de alocação **avançada** em um modelo.

Observação: Não é necessário nem aconselhável usar essa função diretamente. A interface do usuário para alocação baseada em tabela permite especificar um quadro de alocação graficamente e cria a função automaticamente.

## Sintaxe

`Use_Map_Grid(table:source_column[,notation])`

## Argumentos

*tabela*

Faz referência a uma tabela de mapeamento.

*coluna\_fonte*

Especifica o nome da coluna da unidade de origem.

*notação*

Uma das duas cadeias de caracteres literais que indicam como a alocação é expressa:

- percent = Um número inteiro que especifica uma ponderação percentual (pode ser *n* ou *n%* ).
- proporção = Um número inteiro, dividido pelo total para obter um valor decimal.

Se *a notação* não for especificada, presume-se que os números já sejam um valor decimal (por exemplo, 0.25 = 25%).

## Tipo de retorno

O tipo das colunas na tabela de correspondência.

## Comentários

A tabela terá uma única coluna (que é especificada na função). Todas as demais colunas são colunas de unidades de destino.
