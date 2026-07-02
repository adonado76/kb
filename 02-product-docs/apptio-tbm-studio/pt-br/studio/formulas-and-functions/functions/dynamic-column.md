---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "DynamicColumn( ) função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/dynamic-column.html"
images:
  - "resources/images/studio_images/dynamic-columns.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DynamicColumn( ) função

**Aplica-se a** : TBM Studio 12.10.9 e posterior

Uma nova função DynamicColumn( ) foi introduzida para substituir a função Eval(). Queremos eliminar o uso de Eval() para habilitar os aprimoramentos de desempenho do Precision Calc que virão no Server 12.10.10 em julho de 2023.

A função DynamicColumn( ) permite que você passe um nome de coluna e retorne dinamicamente os valores em outras colunas em que esse nome corresponda. Usando a coluna dinâmica, você pode tornar sua configuração mais programática e reduzir a dependência do aninhamento de funções if para retornar dados na mesma tabela.

Para substituir a flexibilidade total da função Eval(), a nova fórmula pode precisar ser dividida em chamadas de função DynamicColumn( ) separadas para retornar os resultados concatenados desejados. Veja na captura de tela um exemplo básico de fórmula usando DynamicColumn( ).

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/dynamic-columns.png)

Para maximizar as melhorias de desempenho de cálculo do novo recurso "cálculos de precisão", a funcionalidade da função Eval() é substituída por DynamicColumn( ) ou outras alterações de código. Os clientes que ainda têm Eval() na configuração do projeto podem fazer as alterações necessárias usando o documento [de código de substituição OOTB Eval()](../updated-eval-formulas.htm "(Abre em uma nova guia ou janela)"), que contém informações sobre todos os relatórios e alterações de métricas.

**AVISO** : Se você tiver modificado os relatórios OOTB, o Eval() não será removido dos relatórios em modelos anteriores (por exemplo, v104, v105, v106. v107 ).

## Onde usar

Essa função pode ser usada em:

- Tabelas

## Sintaxe

`DynamicColumn()`

## Argumentos

*Coluna*

O nome de uma coluna da qual se obtém o valor

*defaultValue*

O valor que existe na coluna com base no valor Column (name)

## Tipo de retorno

Sequência

## Exemplo

Para ver um exemplo dessa função, consulte [Colunas dinâmicas](https://community.apptio.com/viewdocument/apptio-quick-tips-dynamic-columns?CommunityKey=3ff74a27-8291-48d0-ba5a-403be94d07b8&tab=librarydocuments "(Abre em uma nova guia ou janela)")
