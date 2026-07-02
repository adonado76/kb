---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de bala"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/bullet.html"
images:
  - "resources/images/studio_images/studioimages/studio_bullet_max.png"
  - "resources/images/studio_images/studioimages/studio_bullet_secondsplit.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de bala

aplica-se a: TBM Studio v12.3.4 e posterior

A função Bullet permite que você gere um gráfico de marcadores em uma tabela.

## Onde usar

A função Bullet pode ser usada em colunas Formula em tabelas de relatórios.

## Sintaxe

- **Sintaxe básica** - Se você não tiver certeza, comece com esta sintaxe: `=Bullet(performance_measure)`
- **Sintaxe completa** - Essa sintaxe permite que você substitua muitos padrões e comportamentos que afetam a forma como o gráfico de marcadores é renderizado: `=Bullet(performance_measure,[target|min|max|firstSplit|secondSplit=Expression()]*)`

## Argumentos

`performance_measure`

Esse argumento obrigatório deve ser o nome de uma coluna numérica. Esse será o valor principal apresentado pelo gráfico de marcadores.

Guia visual:

![Argumentos](../../../resources/images/studio_images/studioimages/studio_bullet%20function_performance%20measure.png)

## Argumentos opcionais

Um ou mais argumentos opcionais podem ser passados como pares argumento=valor. Isso permite que você substitua as configurações desejadas, deixando outras configurações com o comportamento padrão.

| Argumento | Valor Padrão | Significado | Guia visual |
| --- | --- | --- | --- |
| **destino** | Somente renderizado se especificado. | Qual é o valor da medida comparativa que o bullet chart deve exibir, se houver. A medida comparativa é exibida como uma linha vermelha vertical. | destino |
| **Min** | O menor valor na coluna para performanceMeasure, ou para o alvo especificado. Isso usa apenas os valores da própria tabela exibida, não as linhas que foram filtradas. | Qual é o valor mínimo na escala dos gráficos. | valor mínimo |
| **Máx.** | O maior valor no site performanceMeasure, ou no destino especificado. Isso usa apenas os valores da própria tabela exibida, não as linhas que foram filtradas. | Qual é o valor máximo na escala dos gráficos. | valor máximo |
| **firstSplit** | (máx.-mín.) \* 0.6 | Qual é o valor no qual a caixa de fundo mais à esquerda deve ser desenhada. | primeira divisão |
| **secondSplit** | (máx.-mín.) \* 0.8 | Qual é o valor no qual a caixa de fundo do meio deve ser desenhada. | segunda divisão |

## Sinais

Os gráficos de marcadores permitem um valor mínimo negativo e um valor máximo positivo. O gráfico de marcadores será renderizado da mesma forma que se você pegasse todos os números e adicionasse um valor a eles que os tornasse todos com o mesmo sinal.

## Exemplos

Esta seção fornece exemplos de uso da função Bullet.

**Exibir custo** - Essa função de marcador cria um gráfico de marcadores simples mostrando o custo. O mínimo e o máximo serão definidos com base no intervalo de valores dentro da coluna exibida.

`=bullet(Cost)`

![exemplo de gráfico de marcadores](../../../resources/images/studio_images/studioimages/studio_bullet%20function_example%20bullet%20chart.png)

**Comparar custo com orçamento** - Este é um exemplo que exibe o custo como a medida de desempenho e a métrica de orçamento como a meta:

`=Bullet(Cost,target=Budget)`

![Compare o custo com o orçamento](../../../resources/images/studio_images/studioimages/studio_bullet_compare%20cost%20to%20budget.png)

**Desabilitar a divisão em segundo plano** - Esse exemplo desabilitará as divisões em segundo plano, desde que os gráficos com marcadores contenham apenas números positivos.

`=Bullet(Cost,firstSplit=0,secondSplit=0)`

![Desativar a divisão do plano de fundo](../../../resources/images/studio_images/studioimages/studio_bullet%20func_table.png)

**Compare um valor gráfico com 0** - Quando as pessoas calculam uma variação orçamentária, seu sinal significa se a pessoa está acima ou abaixo do orçamento. Um gráfico Bullet pode ser configurado para renderizar o valor assinado em relação a 0.

`=Bullet(Variance,Target=0)`

![Comparar um valor gráfico](../../../resources/images/studio_images/studioimages/studio_bullet%20function_simple%20bullet.png)

**Sobrepor informações estatísticas** - Este exemplo combina a função Bullet com a função Percentile. Ele renderiza um gráfico de marcadores que mostra que um terço dos valores está à esquerda da primeira divisão e um terço dos valores está à direita da segunda divisão.

`=Bullet(Cost,Target=0,firstSplit=Percentile(Cost,33),secondSplit=Percentile(Cost,66))`

![Sobreposição de informações estatísticas](../../../resources/images/studio_images/studioimages/studio_bullet%20function_table.png)
