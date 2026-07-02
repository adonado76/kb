---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "StatusIcon função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/statusicon.html"
images:
  - "resources/images/studio_images/studioimages/icons/small_blueicon.png"
  - "resources/images/studio_images/studioimages/icons/small_grayicon.png"
  - "resources/images/studio_images/studioimages/icons/small_greenicon.png"
  - "resources/images/studio_images/studioimages/icons/small_redicon.png"
  - "resources/images/studio_images/studioimages/icons/small_yellowicon.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# StatusIcon função

**Aplica-se a** : TBM Studio 12.0 e posterior

\* **\*\*Depreciada\*\*\*** Essa função foi substituída pela função [Icon](icon.htm "(Abre em uma nova guia ou janela)").

Avalia duas expressões e retorna uma das cinco tags HTML <img> para ícones coloridos com base nos resultados.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico
- Métricas calculadas e relatórios com colunas de métricas

## Sintaxe

`StatusIcon(green_expression,red_expression)`

## Argumentos

*expressão\_verde*

Uma expressão que é avaliada como verdadeira ou falsa. Se for verdadeira, a função retornará um

ícone verde ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_greenicon.png).

*expressão\_vermelha*

Uma expressão que é avaliada como verdadeira ou falsa. Se for verdadeira, a função retornará um

ícone vermelho ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_redicon.png).

Se ambas as expressões forem avaliadas como verdadeiras, a função retornará um ícone azul ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_blueicon.png).

Se nenhuma das expressões for avaliada como verdadeira, a função retornará um ícone amarelo ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_yellowicon.png).

Se houver um erro nas regras (por exemplo, se for especificada uma variável que não existe), a função retornará um ícone cinza ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_grayicon.png).

**Observações** :

As expressões suportam os operadores AND e OR.

Por exemplo:

```
StatusIcon(green_expression AND
          green_expression,red_expression AND (red_expression OR
      red_expression))
```

A ordem de avaliação é AND e depois OR. As operações entre parênteses são avaliadas primeiro.

## Tipo de retorno

Sequência

## Comentários

Somente expressões simples, iguais às usadas em [IF](if.htm "(Abre em uma nova guia ou janela)"), podem ser usadas.

## Exemplo

Suponha o seguinte exemplo:

`StatusIcon(CostPerGB<2,CostPerGB>3)`

Ele retorna:

- Verde se CostPerGB for menor que 2.
- Vermelho se CostPerGB for maior que 3.
- Amarelo se CostPerGB estiver entre 2 e 3.

Como ambas as expressões não podem ser verdadeiras, essa função nunca pode retornar azul.

Se CostPerGB não existir, a função retornará cinza.

**Veja também** : [Ícone](icon.htm "(Abre em uma nova guia ou janela)")
