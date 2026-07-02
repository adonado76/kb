---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Compromisso Indicadores-chave de desempenho"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Noções básicas sobre gerenciamento de compromissos no Cloudability"
source_path: "product/commitments_key_performance_indicators.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Compromisso Indicadores-chave de desempenho

## Propósito

Estabelecer um entendimento básico dos KPIs comuns usados em todos os Cloudability Commitments. Em todo o gerente de compromisso, portfólio e recomendações, utilizamos KPIs comuns que quantificam a economia e o risco após a contabilização de todos os ajustes de custo e preço.

## Indicadores de desempenho de poupança

**Economia líquida** - Economia menos o desperdício. Reflete o valor real realizado/esperado por seu portfólio, compromisso ou recomendações. Usado tanto em nível de compromisso individual quanto em nível agregado.

Exemplo: se um conjunto de compromissos custasse $10k em um período de tempo específico, o que equivaleria a $15k em despesas equivalentes sob demanda. A economia bruta dos compromissos seria $15k - $10k = $5k. Se 5% desses compromissos não forem utilizados, o desperdício seria igual a $10k\*5% = $500. Portanto, a economia líquida = $5k - $500 = $4.5k.

**Taxa de poupança** - Temos várias taxas de poupança disponíveis em nosso aplicativo. Suas definições são as seguintes:

**Genericamente** - Taxa de poupança = Poupança / Gastos

**Taxa de economia efetiva (ESR** ) - As despesas comprometíveis são explicitamente em termos de preço sob demanda. Portanto, uma base de custo de *lista* significa que nem as taxas negociadas sob demanda nem os compromissos estão incluídos; o ESR baseia-se apenas no preço de lista. Para uma base de custo *ajustada*, a taxa de lista sob demanda é usada em conjunto com a taxa de compromisso negociada. Embora um pouco matizada, essa definição está alinhada com a FinOps Foundation e faz sentido quando o preço negociado é incluído como um componente da otimização de tarifas. Usamos esse termo apenas no Painel de Otimizações, pois é fundamental isolar o desempenho do compromisso do preço negociado no nível do recurso do compromisso.

ESR = (economia de compromisso + economia de taxa personalizada) / despesas comprometíveis.

**Negotiated Savings Rate (NSR)** **-** Embora não seja explicitamente usado em Cloudability, o NSR é um termo que pode ser usado para isolar suas taxas negociadas sob demanda. O numerador é simplesmente a economia atribuída a essa taxa negociada, enquanto o denominador, Despesas Compromissáveis, tem a mesma definição que a ESR.

NSR = Economia com taxa personalizada / Gastos comprometidos.

**Taxa de economia de portfólio (PSR)** - A PSR é a principal métrica que a Cloudability Commitments usa para comunicar o desempenho de um portfólio ou conjunto de recomendações. Notavelmente, as despesas comprometedoras aqui estão totalmente alinhadas com a base de custos. Uma base de *custo de lista*, portanto, implica que a economia e os gastos são gerados com base nas taxas de lista, enquanto a base *ajustada* implica que o KPI é calculado com base nas taxas negociadas.

PSR = Poupança de compromisso / Despesas comprometidas.

**Taxa de economia de compromisso (CSR)** - A taxa de economia realizada (portfólio) ou esperada (recomendações) de um compromisso. Pode ser comparado diretamente com o CDR para entender o impacto da utilização. Notavelmente, esse KPI aparece junto com o PSR no portfólio, quando aplicável. Outra maneira de descrever esse KPI, quando exibido no portfólio, é a média ponderada das taxas de economia de vários compromissos.

CSR = economia de compromisso / ODE do custo do compromisso

**Taxa de desconto do compromisso (CDR)** - A taxa de economia, considerando que o compromisso foi totalmente utilizado. Isso é apresentado juntamente com a CSR para demonstrar a taxa máxima de economia que pode ser alcançada por um determinado compromisso.

CDR = 𝑆𝑎𝑣𝑖𝑛𝑔𝑠 𝑅𝑎𝑡𝑒 @ 100% 𝑈𝑡𝑖𝑙𝑖𝑧𝑎𝑡𝑖𝑜𝑛.

Os documentos de ajuda subsequentes se aprofundarão mais nessa terminologia e explicarão onde ela é relevante para entender completamente o desempenho do compromisso e avaliar as oportunidades

## Estratégia e indicadores de risco

**Utilização** - A medida em que os compromissos adquiridos foram realmente consumidos; ponderada e agregada quando exibida como um KPI. Essa métrica é realizada para o portfólio, mas é esperada como resultado do intervalo de uso selecionado nas recomendações.

**Cobertura** - A parte do uso elegível coberta por compromissos (vs. sob demanda), mostrada como uma porcentagem e amplamente apoiada por um modal de cobertura.

Exemplo - 75% de cobertura significa que três quartos do uso elegível se beneficiaram do preço com desconto.

**Custo do compromisso restante** - O que você deve a partir de hoje até que todos os compromissos ativos expirem, independentemente do intervalo do relatório.

É importante ressaltar que os KPIs e metadados de compromisso geralmente não podem ser derivados de métricas de negócios e, portanto, as páginas de compromisso suportam apenas visualizações baseadas em contas e fornecedores. Nós nos esforçamos para continuar aprimorando essa parte do nosso aplicativo e incentivamos você a sinalizar as solicitações no [Portal de Ideias IBM](https://ideas.ibm.com/new-idea?product=7428699546216862860&category=7429430490210197213 "(Abre em uma nova guia ou janela)"). Aproveite a categoria "Otimização de taxas"

**Tópico dos pais:** [Entendendo os fundamentos do gerenciamento de compromissos em Cloudability](../product/commitment_management_basics.html)
