---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de período"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/period.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de período

**Aplica-se a** : TBM Studio 12.0 e posterior

Retorna uma cadeia de caracteres que representa um período de tempo selecionado com base em um formato de exemplo especificado.

Essa função pode ser útil em uma região HTML, onde o script de texto dinâmico é usado. Você pode especificar uma cadeia de formato de exemplo, como **mensal**, para ser usada como sufixo com um valor de dados dependente do tempo. Então, quando você visualizar esse valor de dados para diferentes períodos de tempo, o sufixo refletirá o período de tempo apropriado. Neste exemplo, se você visualizar os dados de um ano, o sufixo será **anual**, para um trimestre, será **trimestral**, e assim por diante.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`Period(["time_period"][1])`

## Argumentos

Insira um dos dois argumentos, mas não ambos.

`time_period`

Uma cadeia de caracteres que fornece um exemplo do formato, como **mês**, **mensal**, **GB/mês**, **$ por mês** ou **$/m**. A cadeia de caracteres deve conter um elemento que represente o mês. Os formatos incluem:

- "month" (não diferencia maiúsculas de minúsculas)
- "mensal" (não diferencia maiúsculas de minúsculas)
- terminando em "month "terminando em "Month"
- terminado em "/m"
- terminando em "/M"
- "period" (diferencia maiúsculas de minúsculas)
- terminando em "período"
- terminando em "Período"
- terminando em "/p"
- terminando em "/P"

`1`

Retorna um número que representa o período de tempo atual: 1 para período ou mês, 3 para trimestre e 12 ou 13 para ano, dependendo do tipo de calendário (gregoriano, variante 445 ou período 13). Esse argumento pode ser usado se você quiser usar o valor de retorno nos cálculos.

Por exemplo, =Cost/Period(1) resultaria no custo médio por período ou mês.

## Tipo de retorno

Sequência

## Exemplo

No exemplo a seguir, o uso da função Period permite que o custo seja exibido com um sufixo que muda dinamicamente com o período de tempo selecionado. Se estiver analisando os dados de um ano e Cost=$503,122, o resultado será de **US$ 503.122 por ano**, mas se estiver analisando os dados de um trimestre, o resultado será de **US$ 503.122 por trimestre**.

```
Total Cost: <%=Cost%> <%=Period("per
      month")%>
```
