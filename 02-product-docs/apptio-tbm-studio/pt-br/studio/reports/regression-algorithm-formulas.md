---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Fórmulas de algoritmo de regressão"
breadcrumb: []
source_path: "studio/reports/regression-algorithm-formulas.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Fórmulas de algoritmo de regressão

**Aplica-se a** : TBM Studio 12.0 e posterior

Um recurso útil dos gráficos de tendência é a capacidade de adicionar projeções aos gráficos. O aplicativo oferece uma variedade de algoritmos de regressão que podem ser aplicados às projeções. Os algoritmos são:

- Regressão
- Regressão linear múltipla
- Regressão polinomial
- Suavização exponencial simples
- Suavização exponencial dupla
- Média móvel

Os algoritmos do aplicativo são baseados nos algoritmos de regressão padrão do Java OpenForecast. As descrições abaixo foram extraídas da documentação do Java: [OpenForecast](http://openforecast.sourceforge.net/docs/) "(Abre em uma nova guia ou janela)").

## Regressão

Implementa um modelo de regressão linear de variável única. Um modelo de regressão linear de variável única tenta essencialmente colocar uma linha reta através dos pontos de dados. Essa linha é definida por seu gradiente ou inclinação e pelo ponto em que ela intercepta o eixo x (ou seja, onde a variável independente tem, talvez apenas teoricamente, um valor zero). Matematicamente, supondo que a variável independente seja x e a variável dependente seja y, essa linha pode ser representada como:

> ```
> y = intercept +
>           slope * x
> ```

## Regressão linear múltipla

Implementa um modelo de regressão linear de múltiplas variáveis. Um modelo de regressão linear de múltiplas variáveis tenta essencialmente colocar um hiperplano nos pontos de dados. Matematicamente, supondo que as variáveis independentes sejam xi e a variável dependente seja y, esse hiperplano pode ser representado como:

> ```
> y = a0 + a1*x1 +
>           a2*x2 + a3*x3 +
> ```

...em que os ai são os coeficientes da regressão. O coeficiente a0 também é chamado de interceptação. Se todos os xi forem zero (teoricamente, pelo menos), esse é o valor previsto do dependentVariable, y.

## Regressão polinomial

Implementa um modelo de regressão polinomial de variável única. Um modelo de regressão polinomial de variável única tenta essencialmente colocar uma linha polinomial (uma curva, se preferir) nos pontos de dados. Matematicamente, supondo que a variável independente seja x e a variável dependente seja y, essa linha pode ser representada como:

> ```
> y = a0 + a1*x +
>           a2*x2 + a3*x3 + ... + am*xm
> ```

## Suavização exponencial simples

Um modelo de previsão de suavização exponencial simples é um modelo muito popular usado para produzir uma série temporal suavizada. Enquanto nos modelos de média móvel simples as observações passadas são ponderadas igualmente, a suavização exponencial atribui pesos exponencialmente decrescentes à medida que as observações ficam mais antigas.

Em outras palavras, as observações recentes têm um peso relativamente maior na previsão do que as observações mais antigas.

No caso das médias móveis, os pesos atribuídos às observações são os mesmos e são iguais a 1/N. Na suavização exponencial simples, entretanto, um parâmetro de suavização ou uma constante de suavização é usado para determinar os pesos atribuídos às observações.

Esse modelo simples de suavização exponencial começa definindo a previsão para o segundo período igual à observação do primeiro período.

## Suavização exponencial dupla

A suavização exponencial dupla (também conhecida como suavização exponencial Holt) é um refinamento do popular modelo de suavização exponencial simples, mas acrescenta outro componente que leva em conta qualquer tendência nos dados. Os modelos de suavização exponencial simples funcionam melhor com dados em que não há componentes de tendência ou sazonalidade nos dados. Quando os dados exibem uma tendência crescente ou decrescente ao longo do tempo, as previsões de suavização exponencial simples tendem a ficar atrasadas em relação às observações. A suavização exponencial dupla foi projetada para lidar com esse tipo de série de dados, levando em conta qualquer tendência nos dados.

Observe que a suavização exponencial dupla ainda não trata da sazonalidade. Para obter melhores previsões com suavização exponencial usando dados em que se espera ou se sabe que há variação sazonal nos dados, use a suavização exponencial tripla.

Assim como na suavização exponencial simples, nos modelos de suavização exponencial dupla, as observações passadas recebem pesos exponencialmente menores à medida que as observações ficam mais antigas. Em outras palavras, as observações recentes têm um peso relativamente maior na previsão do que as observações mais antigas.

Há duas equações associadas à suavização exponencial dupla:

> ```
> ft =
>           a.Yt+(1-a)(ft-1+bt-1)
> ```
>
> `bt = g.(ft-ft-1)+(1-g).bt-1`

em que:

- Yt é o valor observado no momento t.
- ft é a previsão no momento t.
- bt é a inclinação estimada no momento t.
- a, representando alfa, é a primeira constante de suavização, usada para suavizar as observações.
- g, representando gama, é a segunda constante de suavização, usada para suavizar a tendência.

Para inicializar o modelo de suavização exponencial dupla, f1 é definido como Y1, e a inclinação inicial b1 é definida como a diferença entre as duas primeiras observações, ou seja, Y2-Y1.

## Suavização exponencial tripla

A suavização exponencial tripla (também conhecida como método Winters) é um refinamento do popular modelo de suavização exponencial dupla, mas acrescenta outro componente que leva em conta qualquer sazonalidade (ou periodicidade) nos dados.

Os modelos de suavização exponencial simples funcionam melhor com dados em que não há componentes de tendência ou sazonalidade nos dados. Quando os dados exibem uma tendência crescente ou decrescente ao longo do tempo, as previsões de suavização exponencial simples tendem a ficar atrasadas em relação às observações. A suavização exponencial dupla foi projetada para lidar com esse tipo de série de dados, levando em conta qualquer tendência nos dados. No entanto, nenhum desses modelos de suavização exponencial aborda qualquer sazonalidade nos dados.

Para obter melhores previsões com suavização exponencial de dados em que se espera ou se sabe que há variação sazonal nos dados, use a suavização exponencial tripla.

Assim como na suavização exponencial simples, nos modelos de suavização exponencial tripla, as observações passadas recebem pesos exponencialmente menores à medida que as observações ficam mais antigas. Em outras palavras, as observações recentes têm um peso relativamente maior na previsão do que as observações mais antigas. Isso se aplica a todos os termos envolvidos. Ou seja, o nível básico Lt, a tendência Tt e o índice de sazonalidade st.

Há quatro equações associadas ao Triple Exponential Smoothing:

> ```
> Lt =
>           a.(xt/st-c)+(1-a).(Lt-1+Tt-1)
> ```
>
> ```
> Tt = b.(Lt-Lt-1)+(1-b).Tt-1
> st =
>           g.(xt/Lt)+(1-g).st-c
> ```
>
> `ft,k = (Lt+k.Tt).st+k-c`

em que:

- Lt é a estimativa do valor base no momento t. Ou seja, a estimativa para o tempo t após a eliminação dos efeitos da sazonalidade e da tendência.
- a, representando alfa, é a primeira constante de suavização, usada para suavizar Lt.
- xt é o valor observado no momento t.
- st é o índice sazonal no momento t.
- c é o número de períodos no padrão sazonal. Por exemplo, c=4 para dados trimestrais ou c=12 para dados mensais.
- Tt é a tendência estimada no momento t.
- b, representando o beta, é a segunda constante de suavização, usada para suavizar as estimativas de tendência.
- g, representando gama, é a terceira constante de suavização, usada para suavizar as estimativas de sazonalidade.
- ft,k é a previsão no final do período t para o período t+k.

Há várias maneiras de obter valores iniciais para o modelo de suavização exponencial tripla. A abordagem implementada aqui usa os dois primeiros anos (ou ciclos completos) de dados para chegar aos valores iniciais de Lt, Tt e st. Portanto, são necessários pelo menos dois ciclos completos de dados para inicializar o modelo. Para obter os melhores resultados, recomenda-se o uso de mais dados (idealmente, um mínimo de 4 ou 5 ciclos completos). Isso dá ao modelo a chance de se adaptar melhor aos dados, em vez de depender da obtenção (adivinhação) de boas estimativas para as condições iniciais.

## Média móvel

Um modelo de previsão de média móvel baseia-se em uma série temporal construída artificialmente, na qual o valor de um determinado período de tempo é substituído pela média desse valor e dos valores de alguns períodos de tempo anteriores e posteriores. Como você deve ter adivinhado pela descrição, esse modelo é mais adequado para dados de séries temporais, ou seja, dados que mudam com o tempo.

Como o valor da previsão para qualquer período específico é uma média dos períodos anteriores, a previsão sempre parecerá estar atrasada em relação aos aumentos ou reduções dos valores observados (dependentes). Por exemplo, se uma série de dados tiver uma tendência ascendente perceptível, uma previsão de média móvel geralmente fornecerá uma subestimação dos valores da variável dependente.

O método de média móvel tem uma vantagem sobre outros modelos de previsão, pois suaviza picos e depressões (ou vales) em um conjunto de observações. No entanto, ele também tem várias desvantagens. Em particular, esse modelo não produz uma equação real. Portanto, não é tão útil como uma ferramenta de previsão de médio e longo prazo. Ele só pode ser usado de forma confiável para prever um ou dois períodos no futuro.

O modelo de média móvel é um caso especial da média móvel ponderada mais geral. Na média móvel simples, todos os pesos são iguais.
