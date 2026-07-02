---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de moeda"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/currency.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de moeda

Formata valores numéricos como cadeias de moeda, adicionando o símbolo de moeda apropriado com base na localidade. Por padrão, os valores negativos são exibidos em vermelho.

## Sintaxe

`Currency(sourceColumn, [pattern], [options])`

## Argumentos

*coluna de origem* : Uma coluna ou expressão numérica que contém os valores a serem formatados como moeda. Coloque os nomes das colunas entre colchetes { }. Necessário

*padrão* : Uma cadeia de caracteres opcional que especifica um padrão de formatação personalizado. Opcional

*opções* : Argumentos nomeados opcionais que controlam o comportamento de formatação adicional. Opcional

Opções compatíveis:

- `compact`: Aplicar formatação abreviada (consulte a seção Referência de notação compacta abaixo para ver os valores suportados)
- `negSymbol`: Use `dash`, `parens`, `none`, ou `default` para saber como os números negativos são exibidos
- `minFractPrecision`: Número mínimo de dígitos após o ponto decimal (número inteiro >= 0)
- `maxFractPrecision`: Número máximo de dígitos após o ponto decimal (número inteiro >= 0)
- `localeprecisionoverride`: Substituir os padrões de localidade para precisão decimal (`true`, `false`)
- `minIntPrecision`: Número mínimo de dígitos antes do ponto decimal (número inteiro >= 0)
- `maxIntPrecision`: Número máximo de dígitos antes do ponto decimal (número inteiro >= 0)
- `thousandSep`: Mostrar separador de milhares (`true`, `false`, `default`)
- `posColor`: Defina a cor da fonte para números positivos usando códigos hexadecimais HTML (por exemplo, `#FF0000`)
- `negColor`: Defina a cor da fonte para números negativos usando códigos hexadecimais HTML (por exemplo, `#FF0000`)
- `posBold`: Aplique o estilo negrito a números positivos (`true`, `false`, `default`)
- `negBold`: Aplicar estilo em negrito a números negativos (`true`, `false`, `default`)
- `posItalic`: Aplique o estilo itálico a números positivos (`true`, `false`, `default`)
- `negItalic`: Aplique o estilo itálico a números negativos (`true`, `false`, `default`)
- `posUnderline`: Aplique o estilo de sublinhado a números positivos (`true`, `false`, `default`)
- `negUnderline`: Aplicar estilo de sublinhado a números negativos (`true`, `false`, `default`)
- `posPrefix`: Adicionar HTML/texto antes de números positivos
- `negPrefix`: Adicionar HTML/texto antes de números negativos
- `posSuffix`: Adicionar HTML/texto após números positivos
- `negSuffix`: Adicionar HTML/texto após números negativos

## Comportamento

- Adiciona um símbolo de moeda apropriado à localidade atual ao valor numérico.
- Formata o número de acordo com o padrão especificado, se fornecido.
- Aplica opções de estilo opcionais, como cor, negrito, itálico e formatos de números compactos.
- Exibe valores negativos em vermelho por padrão, a menos que sejam substituídos por opções.

## Exemplos

Currency( {Cost} ): Formata os valores na coluna {Cost} como moeda com base na localidade, mostrando números negativos em vermelho.

Currency( {Revenue}, "#,## 0.00 ¤"): Formata {Revenue} com um padrão personalizado, garantindo duas casas decimais e um símbolo de moeda.

Currency( {Profit}, "#,##0", compact="K", posColor="green", negColor="red" ): Formata {Profit} usando notação compacta (por exemplo, 1.000 → 1K ), com números positivos mostrados em verde e números negativos em vermelho.

Nota:

- As práticas recomendadas recomendam a conversão de todos os valores financeiros em uma moeda comum antes de usá-los em drivers ou relatórios.
- Os parâmetros "pattern" e "options" permitem o ajuste fino da saída para diferentes estilos e necessidades de relatórios.
- O uso de 'compact=A' seleciona automaticamente a melhor unidade para números grandes (por exemplo, K, M, B, T).
- As opções de cor e estilo de fonte ajudam a personalizar a aparência dos números positivos e negativos de forma independente.

## Referência de notação compacta

Há suporte para as seguintes notações abreviadas padrão. Nessa tabela, a coluna Código é composta pelos valores que você pode colocar após o parâmetro opcional compact=. A coluna Pattern for Charts (Padrão para gráficos) mostra os acréscimos que você pode colocar no final do padrão de formatação para formatar um gráfico:

**Notações de taquigrafia padrão**

| Código | Padrão para gráficos | Descrição | Exemplo |
| --- | --- | --- | --- |
| K | {@K} | Isso sempre resumirá os números em termos de "milhares" | 100.000 é exibido como 100K |
| M | {@M} | Isso sempre resumirá os números em termos de "milhões" | 10.000.000 é exibido como 10M |
| B | {@B} | Isso sempre resumirá os números em termos de "bilhões" | 10.000.000.000 é exibido como 10B |
| T | {@T} | Isso sempre resumirá os números em termos de "trilhões" | 10.000.000.000.000 é exibido como 10T |
| A | {@A} | Isso resumirá os números usando todas as notações padrão. Para um determinado número, será usada a notação de ordem de magnitude mais alta possível, de modo que o número exibido seja maior ou igual a 1.0. Ou seja, {@A} exibirá 964.999 como 9.65K e não como 0.96M, pois 0.96 é menor que 1.0. Em caso de dúvida, esse costuma ser o melhor formato abreviado a ser usado. | Todos os exemplos acima são verdadeiros. |
