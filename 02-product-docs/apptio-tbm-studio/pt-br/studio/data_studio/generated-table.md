---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gerar uma tabela"
breadcrumb: []
source_path: "studio/data_studio/generated-table.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu604.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gerar uma tabela

**Aplica-se a** : TBM Studio 12.0 e posterior

Para criar uma nova tabela a partir de uma tabela existente no projeto atual, use a opção Tabela gerada. A nova tabela será vinculada à tabela de origem.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu604.png)

## Conjunto de dados de origem

Selecione um conjunto de dados na lista.

## Coluna de chave primária

Selecione a coluna que servirá como chave primária. O aplicativo filtrará automaticamente as entradas dessa coluna para entradas exclusivas. Por exemplo, se houver duas linhas para Smith na tabela de origem, haverá apenas uma linha na tabela gerada. Para manter a integridade entre a tabela de origem e a tabela gerada, selecione uma coluna cujos valores não serão alterados.

Se quiser preservar entradas duplicadas, crie uma nova coluna na tabela de origem que combine a coluna de chave primária com uma segunda coluna. Use a nova coluna como a chave primária na tabela gerada.

## Colunas a serem incluídas

Verifique as colunas que você deseja incluir na tabela gerada.

## Permitir edição de colunas incluídas

Em geral, as colunas incluídas na tabela de origem são estáticas na tabela gerada. Se quiser que os usuários possam editar as colunas incluídas na tabela de origem, selecione essa opção. As colunas que serão editáveis geralmente são adicionadas à tabela gerada após a geração da tabela.
