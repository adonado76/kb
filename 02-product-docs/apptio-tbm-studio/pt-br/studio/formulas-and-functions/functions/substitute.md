---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de substituição"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/substitute.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de substituição

Procura em uma cadeia de caracteres de destino especificada a presença de uma cadeia de caracteres de pesquisa especificada. Se a string de pesquisa for encontrada, ela será substituída por uma string de substituição especificada.

## Sintaxe

`Substitute(target_string, search_string, replacement_string)`

## Parâmetros

*target\_string* : A cadeia de caracteres na qual pesquisar e realizar a substituição. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*search\_string* : A substring a ser pesquisada na string de destino. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*replacement\_string* : A cadeia de caracteres a ser usada como substituição para cada ocorrência da cadeia de caracteres de pesquisa. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Substitui todas as ocorrências da string de pesquisa na string de destino pela string de substituição.
- A correspondência faz distinção entre maiúsculas e minúsculas.
- Se a string de pesquisa não for encontrada, a string original será retornada inalterada.

## Tipo de retorno

Sequência

## Exemplo

O exemplo a seguir pesquisa todas as ocorrências de **servidor virtual** e substitui **virtual** por **físico**.

`=Substitute("virtual server", "virtual", "physical")`

O exemplo a seguir procura por aspas simples e as substitui por nada, basicamente removendo as aspas simples da cadeia de caracteres. Isso pode ser útil se você estiver importando dados do Excel e algumas entradas, mas não todas, tiverem uma aspa simples à esquerda.

`=Substitute(Billing
ID,"'","")`

`Substitute({Server Type}, "legacy", "modern")`: Substitui "legacy" por "modern" em todos os valores da coluna {Server Type}.

Observação: use Substitute (Substituto) para padronizar o texto ou substituir substrings indesejadas em tarefas de preparação ou formatação de dados. A substituição afeta todas as correspondências, não apenas a primeira ocorrência.
