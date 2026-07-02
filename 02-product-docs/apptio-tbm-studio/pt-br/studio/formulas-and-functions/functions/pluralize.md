---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Pluralizar a função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/pluralize.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug063.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Pluralizar a função

**Aplica-se a** : TBM Studio 12.0, 12.1

Converte substantivos singulares em suas formas plurais e coloca a primeira letra de cada palavra em maiúscula.

Se quiser converter substantivos singulares em suas formas plurais, mas não colocar a primeira letra de cada trabalho em maiúscula, use a [função Plural](plural.htm "(Abre em uma nova guia ou janela)").

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Métricas calculadas e relatórios com colunas de métricas
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`Pluralize(noun[,count])`

## Argumentos

*substantivo*

Uma forma singular de um substantivo, como "servidor" e "rede" A função lida com substantivos compostos, como "data center" e "sistema operacional"

*contagem*

O substantivo será colocado no plural somente se o valor desse argumento for maior que um. O argumento pode ser extraído de qualquer coluna numérica.

## Tipo de retorno

Sequência

## Exemplo

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug063.png)
