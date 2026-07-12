---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de desfazer perfurações"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/undrill.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de desfazer perfurações

**Aplica-se a** : TBM Studio 12.0 e posterior

Retorna o valor de uma métrica no nível superior de um modelo.

O valor retornado para uma métrica se baseia no nível em que você perfurou em um modelo. Se você estiver em vários níveis abaixo em um modelo, mas quiser o valor da métrica no nível superior do modelo, poderá usar a função Undrill.

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`Undrill(metric)`

## Argumentos

*métrica*

Uma métrica modelada ou calculada.

## Tipo de retorno

Número

## Exemplos

Suponha que você tenha um modelo que inclua várias unidades de negócios e que os custos do servidor tenham sido alocados para cada unidade de negócios. Se você detalhar vários níveis de relatórios em uma das unidades de negócios, por exemplo, Varejo, verá os custos de servidor para o Varejo. Mas, e se você quisesse mostrar a porcentagem dos custos do servidor alocados para o varejo?

Você pode usar a função Undrill para retornar os custos totais do servidor para todas as unidades de negócios e dividi-los pelos custos do servidor de varejo. Você poderia adicionar uma coluna à tabela do relatório para manter o custo não perfurado usando o seguinte:

`=Undrill(Cost)`
