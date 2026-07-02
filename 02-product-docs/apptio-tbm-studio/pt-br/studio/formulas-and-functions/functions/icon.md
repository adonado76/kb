---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de ícone"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/icon.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-right.png"
  - "resources/images/studio_images/studioimages/icons/arrow-up-right.png"
  - "resources/images/studio_images/studioimages/icons/circle-green.png"
  - "resources/images/studio_images/studioimages/icons/circle-pink.png"
  - "resources/images/studio_images/studioimages/icons/circle-red.png"
  - "resources/images/studio_images/studioimages/icons/circle-yellow.png"
  - "resources/images/studio_images/studioimages/icons/down-arrow-green.png"
  - "resources/images/studio_images/studioimages/icons/down-arrow.png"
  - "resources/images/studio_images/studioimages/icons/right-arrow.png"
  - "resources/images/studio_images/studioimages/icons/up-arrow-red.png"
  - "resources/images/studio_images/studioimages/icons/up-arrow.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de ícone

**Aplica-se a** : TBM Studio 12.0 e posterior

Avalia duas ou mais expressões e retorna uma de até cinco tags HTML <img> para ícones coloridos com base nos resultados.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Métricas calculadas e relatórios com colunas de métricas
- Colunas de fórmula em tabelas de relatórios
- Texto dinâmico

## Sintaxe

`Icon(["icon-type"], expression, expression+)`

## Argumentos

*[tipo de ícone]*

Há vários tipos de ícones disponíveis. A tabela abaixo lista os tipos, as expressões e os resultados de cada expressão.

Esse argumento é opcional. Se você omitir o argumento, a função terá como padrão o tipo de ícone "redcircles".

| Tipo de ícone | Expressões e resultados |
| --- | --- |
| "círculos vermelhos" | Expressão 1: círculo vermelho círculo vermelhoExpressão 2: círculo rosa círculo rosa |
| "3colorcircles" | Expressão 1: círculo verde círculo verdeExpressão 2: círculo amarelo círculo amareloExpressão 3: círculo vermelho círculo vermelho |
| "3arrows" | Expressão 1: seta para cima seta verde para cimaExpressão 2: seta para a direita seta amarela para a direitaExpressão 3: seta para baixo seta vermelha para baixo |
| "3arrowsinv" | Expressão 1: seta para cima Expressão 2: seta para a direita seta amarela para a direitaExpressão 3: seta para baixo seta verde para baixo |
| "4arrows" | Expressão 1: seta para cima seta verde para cimaExpressão 2: seta para cima à direita seta amarela para cima e para a direitaExpressão 3: seta para baixo à direita Expressão 4: seta para baixo seta vermelha para baixo |
| "4arrowsinv" | Expressão 1: seta para cima Expressão 2: seta para cima à direita seta amarela para cima e para a direitaExpressão 3: seta para baixo à direita seta amarela para baixo e para a direitaExpressão 4: seta para baixo seta verde para baixo |
| "5arrows" | Expressão 1: seta para cima seta verde para cimaExpressão 2: seta para cima à direita seta amarela para cima e para a direitaExpressão 3: seta para a direita seta amarela para a direitaExpressão 4: seta para baixo à direita seta amarela para baixo e para a direitaExpressão 5: seta para baixo seta vermelha para baixo |
| "5arrowsinv" | Expressão 1: seta para cima Expressão 2: seta para cima à direita seta amarela para cima e para a direitaExpressão 3: seta para a direita seta amarela para a direitaExpressão 4: seta para baixo à direita seta amarela para baixo e para a direitaExpressão 5: seta para baixo seta verde para baixo |
| "círculos vermelhos" | Expressão 1: círculo vermelho círculo vermelhoExpressão 2: círculo rosa |
| "3colorcircles" | Expressão 1: círculo verde círculo verdeExpressão 2: círculo amarelo círculo amareloExpressão 3: círculo vermelho círculo vermelho |
| "3arrows" | Expressão 1: seta para cima seta verde para cimaExpressão 2: seta para a direita seta amarela para a direitaExpressão 3: seta para baixo seta vermelha para baixo |
| "3arrowsinv" | Expressão 1: seta para cima Expressão 2: seta para a direita seta amarela para a direitaExpressão 3: seta para baixo |
| "4arrows" | Expressão 1: seta para cima seta verde para cimaExpressão 2: seta para cima à direita seta amarela para cima e para a direitaExpressão 3: seta para baixo à direita seta amarela para baixo e para a direitaExpressão 4: seta para baixo seta vermelha para baixo |
| "4arrowsinv" | Expressão 1: seta para cima Expressão 2: seta para cima à direita seta amarela para cima e para a direitaExpressão 3: seta para baixo à direita seta amarela para baixo e para a direitaExpressão 4: seta para baixo |
| "5arrows" | Expressão 1: seta para cima seta verde para cimaExpressão 2: seta para cima à direita seta amarela para cima e para a direitaExpressão 3: seta para a direita seta amarela para a direitaExpressão 4: seta para baixo à direita seta amarela para baixo e para a direitaExpressão 5: seta para baixo seta vermelha para baixo |
| "5arrowsinv" | Expressão 1: seta para cima  Expressão 2: seta para cima à direita seta amarela para cima e para a direita  Expressão 3: seta para a direita seta amarela para a direita  Expressão 4: seta para baixo à direita seta amarela para baixo e para a direita  Expressão 5: seta para baixo seta verde para baixo |

Há várias regras que regem a avaliação das expressões:

- As expressões são avaliadas na ordem em que estão listadas na função.
- Se uma expressão for verdadeira, o resultado dessa expressão será exibido na tabela e as demais expressões serão ignoradas.
- Se um conjunto completo de expressões for inserido para um tipo de ícone e nenhuma das expressões for verdadeira, a célula será deixada em branco.
- Se um conjunto de expressões menor que o total for inserido para um tipo de ícone, os valores que estiverem fora das expressões especificadas receberão o ícone associado à primeira expressão não specified.For exemplo, supondo que você esteja usando o tipo de ícone 3colorcircles. Você insere expressões para os ícones do círculo verde e do círculo amarelo, mas não para o ícone vermelho. Os valores que estiverem fora das expressões dos ícones verde e amarelo receberão automaticamente o ícone de círculo vermelho.

O argumento icon-type é opcional. Se você omitir o argumento, a função terá como padrão o tipo de ícone "redcircles".

*expressão*

O número de expressões depende do tipo de ícone selecionado. As expressões suportam os operadores AND e OR.

Por exemplo:

Ícone(" 3arrows ",Avg CPU Util<40,Avg CPU Util<50,Avg CPU Util<70 AND Disk Image GB=500 )

Há várias regras que regem a avaliação das expressões:

- As expressões são avaliadas na ordem em que estão listadas na função.
- Se uma expressão for verdadeira, o resultado dessa expressão será exibido na tabela e as demais expressões serão ignoradas.
- Se um conjunto completo de expressões for inserido para um tipo de ícone e nenhuma das expressões for verdadeira, a célula será deixada em branco.
- Se um conjunto de expressões menor que o total for inserido para um tipo de ícone, os valores que estiverem fora das expressões especificadas receberão o ícone associado à primeira expressão não especificada.
- Por exemplo, suponha que você esteja usando o tipo de ícone 3colorcircles. Você insere expressões para os ícones do círculo verde e do círculo amarelo, mas não para o ícone vermelho. Os valores que estiverem fora das expressões dos ícones verde e amarelo receberão automaticamente o ícone de círculo vermelho.
- A ordem de avaliação é AND e depois OR. As operações entre parênteses são avaliadas primeiro.

## Tipo de retorno

Sequência

## Comentários

Somente expressões simples, iguais às usadas no [IF](if.htm "(Abre em uma nova guia ou janela)"), podem ser usadas.

## Exemplo

O exemplo a seguir retorna:

- Uma seta verde para cima se a utilização média da CPU for maior que 65.
- Uma seta amarela para a direita se a utilização média da CPU for maior que 50.
- Uma seta vermelha para baixo se a utilização média da CPU for maior que 0.

Se CostPerGB não existir, a função retornará cinza.

`Icon("3arrows",Avg CPU Util>65,Avg CPU Util>50,Avg CPU Util>0)`

**Veja também** : [StatusIcon](statusicon.htm "(Abre em uma nova guia ou janela)")
