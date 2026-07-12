---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "GetGroupbyColumn função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/getgroupbycolumn.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug126.png"
  - "resources/images/studio_images/studioimages/studio/aug128.png"
  - "resources/images/studio_images/studioimages/studio/aug358.png"
  - "resources/images/studio_images/studioimages/studio/aug359.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetGroupbyColumn função

**Aplica-se a** : TBM Studio 12.0 e posterior

A função GetGroupbyColumn é usada com tabelas com uma ou mais colunas filtradas e uma coluna agrupada. Retorna o nome da coluna usada para agrupamento. Se você tiver agrupado a tabela por mais de uma coluna, a função retornará os nomes de todas as colunas agrupadas.

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Texto dinâmico

## Sintaxe

`GetGroupbyColumn()`

## Argumentos

Não há argumentos para essa função.

## Tipo de retorno

Sequência

## Exemplo

Suponha que você tenha a tabela mostrada na imagem a seguir:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug126.png)

Você filtra a tabela para "Seattle" na coluna **Data Center**. O resultado é mostrado na imagem a seguir:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug128.png)

Em seguida, você agrupa a tabela pela coluna **Service**. O resultado é mostrado na imagem a seguir:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug358.png)

Agora, você adiciona uma coluna com a fórmula: =GetGroupbyColumn( ). O resultado é mostrado na imagem a seguir:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug359.png)
