---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "RowCount_EditableTable( ) função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/rowcount-editabletable.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# RowCount_EditableTable( ) função

**Aplica-se a** : TBM Studio 12.11.3 e posterior

Retorna uma contagem do número total de linhas em uma tabela editável.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Métricas calculadas e relatórios com colunas de métricas
- Colunas de fórmula em tabelas de relatórios

## Sintaxe

`RowCount([editabletable])`

## Argumentos

*tabela*

Indica qual tabela editável deve ser contada. Se você não especificar uma tabela editável, ele retornará a contagem da tabela editável atual. Não é possível inserir o nome da tabela editável atual como argumento.

## Tipo de retorno

Número

## Exemplo

No exemplo a seguir, se a tabela editável Servers tiver 180 linhas, a função retornará 180.

`=RowCount(Servers)`

**Veja também** : [UniqueCount](uniquecount.htm "(Abre em uma nova guia ou janela)")
