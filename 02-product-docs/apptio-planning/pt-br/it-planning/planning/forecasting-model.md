---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Modelos de previsão"
breadcrumb:
  - "Planning"
  - "Previsão inteligente"
source_path: "it-planning/planning/forecasting-model.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Modelos de previsão

A Previsão Inteligente avalia automaticamente um conjunto diversificado de modelos estatísticos para identificar o mais adequado para seus dados. Esses modelos variam de **métodos de suavização adaptativa** a abordagens **baseadas em** **linha de base** e regressão. O objetivo é capturar diferentes comportamentos de dados — como tendências de crescimento, padrões sazonais repetitivos, volatilidade e relações lineares — para que o sistema possa gerar previsões precisas e explicáveis de forma consistente em vários cenários de negócios.

A precisão das previsões geralmente melhora quando há mais dados históricos disponíveis, pois os modelos podem identificar melhor os padrões sazonais recorrentes, as tendências de longo prazo e a variabilidade subjacente. Fornecer um contexto histórico mais rico permite que o mecanismo de previsão faça previsões mais estáveis e confiáveis.

Modelos de previsão suportados:

- **Os modelos Holt-Winters** são altamente flexíveis e adaptam-se às tendências em constante mudança e aos padrões sazonais.
- **Modelos ingênuos** atuam como linhas de base simples, mas robustas, ideais para séries voláteis ou sem padrões.
- **Os modelos de regressão linear** fornecem estrutura ao aprender relações lineares entre o tempo (ou fatores determinantes) e a métrica alvo.

## Modelos Holt-Winters

Esses modelos descrevem séries temporais usando três componentes adaptativos:

- **Erro (E)** – Como novas observações ajustam o modelo (geralmente aditivo)
- **Tendência (T)** – Direção do movimento: Nenhuma (N), Aditiva (A) ou Aditiva Amortecida (Ad)
- **Sazonalidade (S)** – Ciclos repetitivos: Nenhum (N), Aditivo (A) ou Multiplicativo (M)

Esses modelos são eficazes para planejamento financeiro e previsão operacional porque são atualizados automaticamente à medida que novos dados chegam e podem representar com flexibilidade uma variedade de padrões do mundo real

## Variantes do modelo Holt–Winters

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Nome do modelo** | **Notação ETS** | **Tipo de tendência** | **Tipo de sazonalidade** | **Quando usar** |
| Modelo de suavização exponencial simples | ANN | Nenhum | Nenhum | Para dados estáveis, sem tendência ou sazonalidade. |
| Modelo de sazonalidade aditiva | ANA | Nenhum | Aditivo | Quando os efeitos sazonais são constantes em tamanho. |
| Modelo de Sazonalidade Multiplicativa | ANM | Nenhum | Multiplicativo | Quando os efeitos sazonais variam de acordo com o nível dos dados. |
| Modelo de Tendência Linear de Holt | AAN | Aditivo | Nenhum | Quando os dados apresentam uma tendência linear constante de alta ou baixa. |
| Modelo de tendência amortecida de Holt | AAdN | Amortecimento aditivo | Nenhum | Quando a tendência existe, mas se espera que se estabilize com o tempo. |
| Modelo Aditivo Holt-Winters | AAA | Aditivo | Aditivo | Para tendência + sazonalidade de magnitude constante. |
| Modelo multiplicativo de Holt-Winters | AAM | Aditivo | Multiplicativo | Para tendências + variações sazonais proporcionais. |
| Modelo Holt-Winters Aditivo Amortecido | AAdA | Amortecimento aditivo | Aditivo | Quando as tendências estão se estabilizando e a sazonalidade é constante. |
| Modelo Holt-Winters multiplicativo amortecido | AAdM | Amortecimento aditivo | Multiplicativo | Quando a tendência se estabiliza e a sazonalidade se ajusta aos dados. |

## Modelo de previsão ingênuo

O modelo ingênuo é a abordagem de previsão mais direta: ele simplesmente transporta o valor histórico mais recente para períodos futuros.

Para planejadores financeiros, esse método é especialmente útil quando:

- Os dados são voláteis, erráticos ou difíceis de prever
- Os resultados recentes são o melhor indicador do desempenho futuro a curto prazo
- Você precisa de uma previsão de base clara para comparar com modelos mais avançados.

Não requer configuração e reage imediatamente a mudanças repentinas, tornando-o um modelo confiável de “estimativa rápida”.

## Modelo de regressão linear

O modelo de regressão linear identifica uma **tendência linear** nos seus dados históricos e a extrapola para o futuro.

Para cenários de planejamento financeiro, este modelo é valioso quando:

- Seus dados mostram uma tendência consistente de alta ou baixa ao longo do tempo,
- Você deseja previsões que reflitam os fatores planejados (por exemplo, fatores de crescimento, eventos comerciais, premissas orçamentárias),
- Você precisa de previsões explicáveis, já que a regressão mostra claramente como o tempo ou os fatores determinantes afetam os resultados.

É um modelo prático para ciclos de orçamento e planejamento em que fatores de crescimento, declínio ou operacionais influenciam valores futuros.

## Detalhes estatísticos

Os detalhes estatísticos fornecem informações técnicas sobre como a previsão foi gerada e qual é o seu nível de confiabilidade. Esses detalhes destinam-se a usuários que desejam compreender o comportamento do modelo por trás dos valores previstos.

## Detalhes sobre precisão

Essas métricas medem o grau de distância das previsões em relação à parte de teste dos seus dados históricos. Números mais baixos são melhores para todas as métricas de erro.

|  |  |  |  |
| --- | --- | --- | --- |
| **Métrica** | **Intervalo** | **Descrição** | **Como usar/Interpretar** |
| **MAE** (Erro Absoluto Médio) | 0 a qualquer número positivo | A diferença média entre os valores previstos pelo modelo e os valores reais históricos. | Um MAE mais baixo indica que o modelo se mantém mais próximo dos padrões históricos. Útil para compreender a consistência geral das previsões. |
| **MAPE** (Erro percentual absoluto médio) | 0.0 para qualquer número positivo (expresso em porcentagem) | O erro médio de previsão expresso como uma porcentagem dos valores históricos. | Ajuda a comparar a precisão entre itens com escalas diferentes. Intervalos típicos de interpretação:  • **0–10%:** Muito preciso  • **10–20%:** Bom  • **20–50%:** Aceitável  • **50%+:** Baixa precisão  Observação: Não é confiável quando os valores históricos são muito pequenos ou zero. |
| **MASE** (Erro absoluto médio escalonado) | 0.0 para qualquer número positivo ou **“Infinito”** | Compara o erro do seu modelo com uma previsão de linha de base simples que repete o último valor histórico. | Intervalos típicos de interpretação:  - **Menos que o 1.0** **e:** o modelo tem um desempenho melhor do que a linha de base - **Igual a 1.0** : tem o mesmo desempenho que a linha de base - **Maior que 1.0** **:** A linha de base tem um desempenho melhor - **Infinito:** todos os valores históricos são constantes; a linha de base é a mais adequada |
| **RMSE** (Erro Quadrático Médio) | 0 a qualquer número positivo | Semelhante ao MAE, mas dá mais peso a erros maiores (grandes falhas). | - RMSE próximo ao MAE → os erros de previsão são estáveis e consistentes - RMSE muito superior ao MAE → os dados apresentam picos ou erros ocasionais significativos |
| **Pontuação de precisão** | 0 a 100 (escala percentual) | Uma pontuação combinada que reflete a precisão geral do modelo com base em várias métricas de erro. Pontuações mais altas indicam melhor desempenho do modelo em relação às alternativas. | Intervalos típicos de interpretação:  - **90-100%:** Excelente - Previsão altamente confiável - **75-89%:** Bom - Previsão confiável - **60-74%:** Razoável - Use com cautela - **Abaixo de 60%:** Ruim - A previsão pode não ser confiável |

Use as diretrizes abaixo para identificar rapidamente qual modelo fornece os resultados mais confiáveis.

- **Pontuação de precisão:** valores mais altos indicam melhor precisão geral.
- **MAPE:** Valores mais baixos são melhores.
- **MASE:** Valores mais baixos são melhores (idealmente**, menos que 1.0** ).
- **MAE/RMSE:** Valores mais baixos indicam que o modelo está mais próximo dos seus dados históricos.

## Parâmetros

Os parâmetros determinam o quanto o modelo se baseia em valores recentes em comparação com tendências de longo prazo e padrões sazonais.

**Alfa (Suavização de Nível)**

Controla a importância atribuída ao valor mais recente ao estimar o nível geral dos dados.

- **Alfa mais baixo** → suavização mais intensa; o modelo se baseia mais no histórico de longo prazo.
- **Alfa mais alto** → suavização mais leve; o modelo reage mais fortemente às mudanças recentes.
- **Alfa = 1** → apenas o ponto de dados mais recente é utilizado para o nível.

**Beta (Suavização de Tendências)**

Controla a rapidez com que o modelo atualiza sua estimativa da tendência ao longo do tempo.

- Comporta-se de maneira semelhante ao Alpha, mas afeta especificamente o componente de tendência.
- Um beta mais alto torna o modelo mais sensível às mudanças recentes na tendência; um beta mais baixo estabiliza-o.

**Gamma (Suavização sazonal)**

Controla como o modelo atualiza os padrões sazonais (por exemplo, sazonalidade trimestral ou mensal).

- Comportamento semelhante ao Alpha, mas aplicado ao componente sazonal.
- O Gamma mais alto atualiza a sazonalidade com base em períodos recentes; o Gamma mais baixo suaviza os efeitos sazonais ao longo de um histórico mais longo.

## Tendência e sazonalidade

Esses indicadores mostram o quanto a tendência e a sazonalidade influenciam a precisão do modelo. Eles ajudam a identificar se os dados contêm movimentos significativos para cima ou para baixo, ou padrões repetitivos ao longo do tempo.

|  |  |  |  |
| --- | --- | --- | --- |
| **Métrica** | **Intervalo** | **Descrição** | **Como usar/Interpretar** |
| Força da tendência | 0.0 para 1.0 | Indica o quanto o componente de tendência melhora a precisão do modelo. Calculado comparando o modelo original com o mesmo modelo sem a tendência. | Intervalos típicos de interpretação: • **0.0:** Sem tendência significativa  • **0.0 — 0.3:** Tendência fraca  • **0.3 – 0.7:** Tendência moderada  • **0.7 – 1.0:** Tendência forte; |
| Força sazonal | 0.0 para 1.0 | Indica o quanto o componente sazonal melhora a precisão do modelo. Calculado comparando o modelo original com o mesmo modelo sem o componente sazonal. | Intervalos típicos de interpretação: • **0.0:** Sem padrão sazonal  • **0.0 – 0.3:** Sazonalidade fraca  • **0.3 – 0.7:** Sazonalidade moderada  • **0.7 – 1.0:** Padrões sazonais fortes e consistentes |
