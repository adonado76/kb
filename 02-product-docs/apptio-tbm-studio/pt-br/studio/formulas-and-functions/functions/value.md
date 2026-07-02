---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de valor"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/value.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de valor

Converte uma cadeia de caracteres de aparência numérica em um número usando um padrão de formatação opcional. Útil para extrair valores numéricos de cadeias de caracteres que incluem texto ou símbolos.

## Sintaxe

`Value(value, pattern)`

## Parâmetros

*valor* : A expressão de cadeia de caracteres a ser convertida em um número. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*padrão* : Opcional. Um padrão usado para fazer a correspondência e analisar o valor numérico. Pode ser um padrão de sufixo (por exemplo, "#GB") ou um padrão numérico completo, conforme usado em NumberFormat. Se omitido, a função tentará inferir o formato correto. Opcional

Um padrão usado para correspondência. O padrão pode ser qualquer um:

- Um sufixo que indica que a análise deve levar o número até o primeiro caractere não numérico.
- Um padrão numérico completo reconhecível por [NumberFormat](numberformat.html "Formata um valor numérico em um rótulo (string) usando padrões personalizados para números positivos e negativos, durações ou formatação de tamanho de dados. Essa função foi projetada para uso em colunas do tipo Label.").

Se *o padrão* não for especificado, a função fará a melhor estimativa e tentará analisar o *valor* usando um dos formatos de número padrão.

## Tipo de retorno

Número

## Exemplo

O exemplo a seguir avalia a string na coluna Storage e retorna a parte numérica da string até os caracteres GB. Se Storage contiver a string 57GB, este exemplo retornará 57. : `=Value(Storage,"#GB")`

`Value("$1,234.56")`: Analisa a cadeia de caracteres e retorna o valor numérico 1234.56.

Observação: Se a análise falhar, a função retornará null.
