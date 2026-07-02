---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "UniqueCount função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/uniquecount.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# UniqueCount função

**Aplica-se a** : TBM Studio 12.0 e posterior

Retorna uma contagem de valores distintos em uma coluna.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Colunas de fórmula em tabelas de relatórios

Observação: Essa função não pode ser usada na mesa em que será aplicada. Por exemplo, você não pode criar uma fórmula como =UniqueCount(Servers:Location ) na tabela Servers (Servidores).

## Sintaxe

UniqueCount(table nome:coluna)

## Argumentos

*nome da tabela*

A tabela a ser examinada em busca de valores distintos.

*coluna*

A coluna a ser examinada em busca de valores distintos. Observe que são usados dois pontos entre o nome da tabela e o nome da coluna. Por exemplo: Servidores:Localização.

## Tipo de retorno

Número

## Exemplo

Suponha que você tenha a seguinte tabela:

| Servidor | Local |
| --- | --- |
| EXCH006 | Seattle |
| EXCH010 | Boston |
| NET207 | Boston |
| STOR124 | Seattle |
| STOR250 | Boston |
| STOR350 | Denver |

A função a seguir, se executada na tabela Servers (Servidores) acima, retorna 3, porque a tabela contém 3 locais distintos.

=UniqueCount(Servers:Location)

**Veja também** : [RowCount](rowcount.htm "(Abre em uma nova guia ou janela)")
