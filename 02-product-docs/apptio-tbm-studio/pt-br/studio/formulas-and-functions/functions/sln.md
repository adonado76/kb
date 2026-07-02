---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função do SLN"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/sln.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função do SLN

**Aplica-se a** : TBM Studio 12.0 e posterior

Retorna a depreciação linear de um ativo por um ano.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico
- Métricas calculadas e relatórios com colunas de métricas

## Sintaxe

`SLN(original,salvage,lifespan)`

## Argumentos

*original*

O valor original do ativo que está sendo depreciado.

*recuperação*

O valor residual do ativo que está sendo depreciado.

*tempo de vida*

O número de anos a serem depreciados.

## Tipo de retorno

Número

## Exemplo

O exemplo a seguir calcula a depreciação linear ao longo de 5 anos para um ativo de US$ 4.000 com um valor residual de US$ 800. Essa função retorna um valor de depreciação anual de 640.

`=SLN(4000,800,5)`
