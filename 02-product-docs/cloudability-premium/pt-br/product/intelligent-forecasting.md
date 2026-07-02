---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Previsão inteligente"
breadcrumb:
  - "Cloudability Premium"
  - "Planejar"
  - "Previsão aprimorada"
source_path: "product/intelligent-forecasting.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Previsão inteligente

## Visão geral

Recursos como a Página de Previsão Aprimorada e o " Cloudability Financial Planning " utilizam o Mecanismo de Previsão Inteligente para gerar previsões a partir de dados históricos de séries temporais. O Intelligent Forecast Engine avalia vários modelos de previsão para identificar aquele que melhor se ajusta a cada série temporal histórica. Esses modelos foram concebidos para capturar diferentes tipos de comportamento em dados de séries temporais, tais como valores estáveis, crescimento ou declínio linear, padrões sazonais recorrentes e mudanças na variabilidade ao longo do tempo. Ao oferecer suporte a vários tipos de modelos, o mecanismo pode gerar previsões mais precisas, explicáveis e adaptáveis a diferentes cenários.

A precisão das previsões geralmente melhora quando há mais dados históricos disponíveis, pois os modelos conseguem identificar melhor os padrões sazonais recorrentes, as tendências de longo prazo e a variabilidade subjacente. Um conjunto de dados históricos mais abrangente fornece ao mecanismo mais contexto para selecionar o modelo mais adequado e produzir uma previsão mais estável.

O Intelligent Forecast Engine suporta vários tipos de modelos de previsão, incluindo o modelo de referência, a tendência linear, a média móvel e determinados modelos ETS. Esses modelos foram concebidos para se adequarem a diferentes padrões históricos nos dados e utilizam diferentes configurações ou parâmetros, dependendo de como funcionam.

O Intelligent Forecast Engine aplica todos os tipos de modelos compatíveis a cada item de previsão e seleciona o modelo com melhor desempenho para o padrão histórico desse item.

[Saiba mais sobre como funciona a Previsão Inteligente](#topic__operation)

## Tipos de modelos de previsão

| Tipo de modelo | Descrição |
| --- | --- |
| **Linha de base** | O modelo de referência, por vezes chamado de **“ingênuo”**, utiliza o valor histórico mais recente como uma previsão simples, sem modelar explicitamente a tendência ou a sazonalidade. É mais adequado para padrões relativamente estáveis, nos quais o histórico recente serve como um indicador razoável dos valores futuros no curto prazo. Como não reproduz padrões mais complexos, pode ser menos preciso quando os valores estão em constante ascensão, em constante queda ou seguem ciclos sazonais recorrentes. |
| **Tendência linear** | O modelo de tendência linear ajusta uma linha reta aos valores históricos e projeta essa tendência para o futuro. É mais adequado para dados que aumentam ou diminuem de forma constante ao longo do tempo. Como não leva em conta padrões sazonais recorrentes, pode ser menos preciso quando os valores variam de acordo com padrões cíclicos mensais, trimestrais, diários ou de outra natureza. |
| **Média móvel** | O modelo de média móvel prevê valores futuros calculando a média de um número definido dos períodos históricos mais recentes. Por exemplo, uma média móvel de três períodos utiliza a média dos três períodos mais recentes para gerar a previsão. Este modelo é útil quando os dados apresentam ruído e é necessário suavizar as flutuações de curto prazo. Como suaviza os dados históricos recentes, tende a reagir mais lentamente às mudanças e pode subestimar os valores em alta ou superestimar os valores em queda. |
| **Modelos ETS** | ETS significa **Erro, Tendência e Sazonalidade**. Os modelos ETS constituem uma família de modelos de suavização exponencial em que cada modelo é definido pela forma de seus componentes de erro, tendência e sazonalidade. Na notação padrão, um modelo ETS é escrito como **ETS (Erro, Tendência, Sazonalidade)**. Por exemplo, o ETS(A,A,N) representa um modelo com erro aditivo, tendência aditiva e sem sazonalidade.  Na terminologia utilizada aqui:   - **A** = aditivo - **Ad** = tendência aditiva amortecida - **N** = nenhum - **M** = multiplicativo |

Os modelos baseados em ETS compatíveis incluem os seguintes:

| sigla ETS | Nome descritivo | Descrição técnica |
| --- | --- | --- |
| ANN | Suavização exponencial simples | Modela o erro aditivo sem tendência e sem sazonalidade |
| AAN | Tendência linear de Holt | Modela o erro aditivo com tendência aditiva e sem sazonalidade |
| ANA | Suavização exponencial com sazonalidade aditiva | Modela o erro aditivo sem tendência e a sazonalidade aditiva |
| ANM | Suavização exponencial com sazonalidade multiplicativa | Modela um erro aditivo sem tendência e sazonalidade multiplicativa |
| AAdN | Tendência Amortecida de Holt | Modela um erro aditivo com tendência aditiva amortecida e sem sazonalidade |
| AAA | Aditivo Holt-Winters | Modela o erro aditivo com tendência aditiva e sazonalidade aditiva |
| AAM | Método multiplicativo de Holt-Winters | Modela o erro aditivo com tendência aditiva e sazonalidade multiplicativa |
| AAdA | Curva aditiva de Holt-Winters com tendência amortecida | Modela o erro aditivo com tendência aditiva amortecida e sazonalidade aditiva |
| AAdM | Modelo multiplicativo de Holt-Winters com tendência amortecida | Modela o erro aditivo com tendência aditiva amortecida e sazonalidade multiplicativa |

Os modelos ETS são úteis quando os padrões nos dados são mais complexos e podem incluir mudanças direcionais sustentadas, comportamentos sazonais repetitivos ou ambos. Como os modelos ETS incluem parâmetros adicionais, muitas vezes conseguem ajustar padrões complexos de séries temporais com maior precisão do que modelos mais simples, desde que haja dados históricos suficientes para estimar esses parâmetros de forma confiável. Cada variante do ETS representa um pressuposto estrutural diferente sobre o comportamento da série temporal, e o Intelligent Forecast Engine avalia essas variantes para determinar qual estrutura se ajusta melhor ao padrão histórico observado.

## Comparação de modelos de previsão

| Família de modelos | Nome do modelo | Parâmetros do modelo | Ideal para | Principal limitação |
| --- | --- | --- | --- | --- |
| Modelos de referência | Ingenuo | Nenhum | Dados estáveis, nos quais o histórico recente serve como um indicador razoável dos valores futuros no curto prazo | Menos preciso quando os valores apresentam uma tendência constante ou padrões sazonais recorrentes |
| Modelos da moda | Tendência linear | Inclinação e interceptação | Dados que aumentam ou diminuem de forma constante ao longo do tempo | Menos preciso quando os valores apresentam padrões sazonais recorrentes |
| Modelos de média | Média móvel | Comprimento da janela | Dados ruidosos em que a suavização de curto prazo é útil | Tende a apresentar atrasos quando os valores sobem ou descem rapidamente |
| Modelos ETS | Suavização exponencial simples (ANN) | α | Dados estáveis, com tendência ou variação sazonal limitadas | Menos preciso quando os valores apresentam uma tendência constante ou padrões sazonais recorrentes |
| Modelos ETS | Tendência Linear de Holt (AAN) | α, β | Dados com uma tendência constante de alta ou de baixa, mas sem um padrão sazonal recorrente | Menos preciso quando os valores apresentam padrões sazonais recorrentes |
| Modelos ETS | Suavização exponencial com sazonalidade aditiva (ANA) | α, γ | Dados com padrões sazonais recorrentes, mas com um nível geral relativamente estável | Menos preciso quando os valores apresentam uma tendência sustentada de alta ou de baixa |
| Modelos ETS | Suavização exponencial com sazonalidade multiplicativa (ANM) | α, γ | Dados com padrões sazonais recorrentes cuja magnitude aumenta ou diminui com o nível geral | Menos preciso quando os valores apresentam uma tendência sustentada de alta ou de baixa |
| Modelos ETS | Tendência Amortecida de Holt ( AAdN ) | α, β, φ | Dados cuja tendência deverá se moderar com o tempo | Menos preciso quando os valores apresentam padrões sazonais recorrentes |
| Modelos ETS | Aditivo Holt-Winters (AAA) | α, β, γ | Dados com tendências e padrões sazonais cuja magnitude permanece relativamente constante ao longo do tempo | Menos adequado quando os efeitos sazonais aumentam ou diminuem em função do nível geral |
| Modelos ETS | Modelo Multiplicativo de Holt-Winters (AAM) | α, β, γ | Dados com tendências e padrões sazonais cuja magnitude aumenta ou diminui com o nível geral | Menos preciso quando os valores são baixos ou variam significativamente de um período para outro |
| Modelos ETS | Aditivo de Holt-Winters com tendência amortecida ( AAdA ) | α, β, γ, φ | Dados com padrões sazonais e uma tendência que se espera que se modere com o tempo | Requer dados históricos suficientes para estimar esses parâmetros com confiabilidade |
| Modelos ETS | Modelo multiplicativo de Holt-Winters com tendência amortecida ( AAdM ) | α, β, γ, φ | Dados com padrões sazonais cuja magnitude aumenta ou diminui em função do nível geral e cuja tendência deverá moderar-se ao longo do tempo | Menos preciso quando os valores são baixos ou variam significativamente de um período para outro |

## Parâmetros do modelo de previsão

Diferentes tipos de modelos de previsão utilizam diferentes configurações ou parâmetros.

| **Parâmetro** | **Usado em** | **Significado** |
| --- | --- | --- |
| Nenhum | Linha de base | O modelo de referência não utiliza parâmetros de previsão configuráveis |
| Inclinação | Tendência linear | Define a taxa de aumento ou diminuição da linha de tendência ajustada |
| Intercepto | Tendência linear | Define o ponto inicial da linha de tendência ajustada |
| Comprimento da janela | Média móvel | Define quantos períodos históricos são incluídos na média móvel |
| α (alfa) | Todos os modelos ETS | **Suavização de nível** – controla a rapidez com que o modelo atualiza o nível estimado, ou valor de referência, com base nos novos dados reais |
| β (beta) | Modelos ETS com tendência | **Suavização da tendência** – controla a rapidez com que o modelo atualiza a tendência estimada com base nos novos dados reais |
| γ (gama) | Modelos ETS com sazonalidade | **Suavização sazonal** – controla a rapidez com que o modelo atualiza o padrão sazonal estimado com base nos novos dados reais |
| φ (fi) | Modelos ETS com tendência amortecida | **Amortecimento da tendência** – controla o grau de amortecimento da tendência projetada ao longo do tempo |

Nos modelos ETS, a notação ETS descreve a forma estrutural do modelo, enquanto os parâmetros de suavização controlam a forma como o modelo atualiza seus **componentes de estado** internos ao longo do tempo. Esses componentes de estado incluem **nível**, **tendência** e **sazonalidade**. Esses componentes de estado diferem do componente **de erro** do ETS, que descreve a forma dos resíduos — as diferenças entre os valores observados e os valores produzidos pelo modelo durante o processo de ajuste.

Esses parâmetros influenciam a capacidade de resposta da previsão a novos valores observados e a precisão com que o modelo consegue representar o nível, a tendência e a sazonalidade dos dados históricos.

**Como interpretar os parâmetros de suavização do ETS**

**O parâmetro Alpha (suavização de nível)** controla o peso atribuído ao valor mais recente na estimativa do nível geral dos dados.

- Alfa mais baixo – suavização mais intensa; o modelo se baseia mais nos dados históricos de longo prazo
- Alfa mais alto – suavização mais leve; o modelo reage de forma mais acentuada às mudanças recentes
- Alpha = 1 – apenas o último valor é usado para atualizar o nível

**O parâmetro Beta (suavização da tendência)** controla a rapidez com que o modelo atualiza sua estimativa da tendência ao longo do tempo.

- Ele funciona de maneira semelhante ao alfa, mas se aplica especificamente ao componente de tendência
- Um beta mais alto torna o modelo mais sensível às mudanças recentes na tendência
- Um beta mais baixo torna a estimativa da tendência mais estável

**Gamma (suavização sazonal)** controla a forma como o modelo atualiza os padrões sazonais, tais como a sazonalidade mensal ou trimestral.

- Se comporta de maneira semelhante ao alfa, mas aplica-se à componente sazonal
- Um valor mais alto de gama reflete a sazonalidade de forma mais acentuada com base nos períodos recentes
- Um valor mais baixo de gama suaviza os efeitos sazonais ao longo de um período histórico mais extenso

**Phi (amortecimento de tendência)** controla a intensidade com que o modelo reduz o efeito da tendência ao longo do tempo.

- Um valor mais alto de phi mantém o efeito da tendência mais forte por mais tempo
- Um valor menor de phi reduz o efeito de tendência mais rapidamente
- Phi é utilizado apenas em modelos de tendência amortecida.

## Indicadores de tendência e sazonalidade

Os resultados do modelo ETS também podem incluir indicadores **de intensidade da tendência**, **intensidade da sazonalidade** e **período sazonal**. Esses valores ajudam a mostrar em que medida a tendência e os componentes sazonais contribuem para a precisão do modelo e com que frequência os padrões sazonais se repetem.

| **Indicador** | **Intervalo** | **Descrição** | **Interpretação típica** |
| --- | --- | --- | --- |
| Força da tendência | 0.0 para 1.0 | Indica em que medida a componente de tendência melhora a precisão do modelo. É calculado comparando-se o modelo original com o mesmo modelo sem a tendência. | - 0.0 = sem tendência significativa - 0.0-0.3 = tendência fraca - 0.0-0.3 = tendência fraca - 0.7-1.0 = tendência forte |
| Força da sazonalidade | 0.0 para 1.0 | Indica em que medida a componente sazonal melhora a precisão do modelo. É calculado comparando-se o modelo original com o mesmo modelo sem a componente sazonal. | - 0.0 = sem padrão sazonal - 0.0 = sem padrão sazonal - 0.3-0.7 = sazonalidade moderada - 0.7-1.0 = padrões sazonais marcantes e consistentes |
| Período sazonal | Número inteiro positivo | Indica o número de períodos em um ciclo sazonal completo utilizado pelo modelo. Por exemplo, um valor de 12 representa um ciclo anual em dados mensais, enquanto um valor de 7 representa um ciclo semanal em dados diários. | Valores mais altos indicam um ciclo de repetição mais longo. |

Esses indicadores podem ajudar a explicar por que foi escolhido um modelo que inclui tendência ou sazonalidade. Valores mais elevados de “Força da Tendência” e “Força da Sazonalidade” sugerem que o componente correspondente contribui de forma mais significativa para a precisão da previsão, enquanto o “Período Sazonal” indica a duração do ciclo repetitivo identificado nos dados.

## Como funciona a previsão inteligente

Quando o Intelligent Forecast Engine gera uma previsão, ele não se baseia em um único modelo nem em valores fixos de parâmetros. Em vez disso, ele ajusta cada modelo compatível ao padrão histórico do item de previsão, determinando os valores, as configurações ou os parâmetros do modelo necessários para melhor corresponder a esse padrão. Esse processo de ajuste ocorre antes de o mecanismo avaliar os resultados dos modelos e selecionar o modelo com melhor desempenho.

Alguns modelos utilizam estruturas relativamente simples. Por exemplo, um modelo de média móvel utiliza um comprimento de janela, enquanto um modelo de tendência linear utiliza a inclinação e a interceptação ajustadas da linha de tendência histórica. Os modelos ETS são mais adaptáveis e utilizam um ou mais parâmetros de suavização, tais como alfa (α), beta (β), gama (γ) e phi (φ), dependendo se o modelo inclui nível, tendência, sazonalidade ou tendência amortecida.

Para esses modelos ETS, o Intelligent Forecast Engine utiliza um processo iterativo para calcular os valores dos parâmetros que melhor se ajustam ao padrão observado nos dados históricos do item de previsão.

Valores mais altos ou mais baixos dos parâmetros alteram o grau de sensibilidade do modelo a novos valores observados. Por exemplo, um valor mais alto de alfa faz com que o nível estimado reaja mais rapidamente às mudanças recentes nos dados, enquanto um valor mais baixo de alfa faz com que o nível mude de forma mais gradual.

Depois que os valores ideais dos parâmetros forem selecionados para cada modelo, o Intelligent Forecast Engine avalia os modelos para determinar qual deles apresenta o melhor desempenho em relação aos dados históricos. Utilizando uma abordagem de aprendizado de máquina, o método aplica cada modelo a uma parte anterior dos dados históricos, compara os valores previstos resultantes para uma parte posterior da mesma série com os valores observados conhecidos e calcula o erro percentual absoluto médio simétrico (SMAPE). Em seguida, converte esse resultado em uma pontuação de precisão e seleciona o modelo com a pontuação de precisão mais alta.

Um modelo mais simples, como o Baseline ou a Média Móvel, pode apresentar melhores resultados para um padrão estável, enquanto um modelo ETS mais avançado pode apresentar melhores resultados para dados que incluam tendência, sazonalidade ou ambos. Ao testar os modelos candidatos com base em uma parte conhecida da série de dados de entrada e classificá-los de forma consistente, o mecanismo pode selecionar o modelo com maior probabilidade de produzir a previsão futura mais precisa para esse item.

**Por que isso é importante**

O Intelligent Forecast Engine gera previsões que se adaptam a diferentes tipos de comportamento de séries temporais. Um padrão estável pode ser melhor representado por um modelo mais simples, enquanto um padrão mais dinâmico ou sazonal pode exigir um modelo com parâmetros de tendência e sazonalidade ajustados a esse histórico específico. Um padrão também pode começar sendo estável e, com o tempo, evoluir para um que exija um modelo mais complexo.

Como o Intelligent Forecast Engine seleciona tanto o modelo com melhor desempenho quanto os valores de parâmetros que melhor se ajustam ao padrão histórico, ele é capaz de gerar previsões personalizadas para cada item de previsão, em vez de se basear em uma abordagem fixa para todos os dados.

**Tópico principal:** [Previsão aprimorada](../product/efp-forecast.html)
