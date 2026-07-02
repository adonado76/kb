---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Métodos de depreciação"
breadcrumb:
  - "Planning"
  - "Planejamento de ativos"
source_path: "it-planning/planning/depreciation-method.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Métodos de depreciação

Apptio O Planning oferece suporte a vários métodos de depreciação para ajudá-lo a modelar com precisão como os custos de ativos fixos são gastos ao longo do tempo. A depreciação converte uma despesa de capital ( CapEx ) em despesa operacional ( OpEx ) ao longo da vida útil do ativo.

Você pode selecionar entre os seguintes métodos compatíveis:

- [linear](#deprecationmethod__SL)
- [Linha reta usando dias do calendário](#deprecationmethod__slcud)
- [Declínio duplo](#deprecationmethod__dd)
- [Saldo decrescente Períodos pares](#deprecationmethod__dbep)
- [Saldo decrescente usando dias de calendário](#deprecationmethod__dbucd)
- [Depreciação manual](#deprecationmethod__md)

## linear

Distribui uniformemente o custo do ativo ao longo de sua vida útil.

**Fórmula:**

**Valor da depreciação** = (preço de compra × (1 - valor residual)) ÷ vida útil do ativo

**Vida útil do ativo** = duração em meses

**Valor residual %** = A taxa do custo original do ativo que se espera que permaneça ao final de sua vida útil.

**Exemplo:**

Preço do ativo = US$ 40.000

Vida útil do ativo = 12 meses

Valor residual %: 0

**Depreciação mensal** = 40.000 × (1 - 0) ÷ 12 = **$3.333**

## Linha reta usando dias do calendário

Aplica a depreciação linear, mas aloca a despesa proporcionalmente com base no número de dias corridos em cada mês.

Se a depreciação começar no meio do mês ou abranger meses com contagens de dias diferentes (por exemplo, janeiro vs. fevereiro), cada mês receberá um valor proporcional com base nos dias reais decorridos, em vez de uma divisão mensal uniforme.

Esse método é normalmente usado quando a política contábil exige maior precisão para períodos parciais.

## Declínio duplo

O método do saldo decrescente duplo é uma técnica de depreciação acelerada que registra despesas de depreciação mais altas durante os primeiros anos da vida útil de um ativo. Ele calcula a depreciação multiplicando o valor contábil inicial do ativo pelo dobro da taxa de depreciação linear. Esse método é frequentemente usado para ativos que se depreciam rapidamente ou para reduzir a obrigação fiscal nos primeiros anos.

**Fórmula:**

**Valor da depreciação** = 2 × (1 ÷ vida útil do ativo) × valor contábil do período inicial

**Vida útil do ativo** = duração em meses

**Valor residual %** = A taxa do custo original do ativo que se espera que permaneça ao final de sua vida útil. O cálculo do saldo decrescente duplo não considera o valor residual na depreciação de cada período; no entanto, se o valor contábil cair abaixo do valor residual, o último período será ajustado para que termine no valor residual.

**Valor contábil do período inicial** (calculado mensalmente) = Valor da compra - Depreciação acumulada até a data

**Exemplo:**

Preço do ativo = US$ 40.000

Vida útil do ativo = 12 meses

Valor residual % = 0

- **P1** = 2 × (1 ÷ 12) × (40,000 - 0) = **$6,667**

- **P2** = 2 × (1 ÷ 12) × (40,000 - 6,667) = **$5,556**

- **P3** = 2 × (1 ÷ 12) × (40,000 - 6,667 - 5,556) = **$4,955**

- **Etc.**

**Importante:** O método Double Declining recalcula o valor contábil inicial **no início de cada período**, não anualmente. Se você quiser modelar um método tradicional de Declínio Duplo, use **o Saldo Declínio com uma Taxa de Saldo de 200%.**

## Saldo decrescente Períodos pares

Método de depreciação acelerada flexível que usa uma **taxa de saldo** definida por você (por exemplo, 150%, 200%).

**Fórmula:**

**Valor da depreciação** = Valor contábil do período inicial × [Taxa de saldo × ( 1 ÷ Vida útil do ativo)]

**Valor contábil do período inicial** (calculado anualmente) = Preço de compra - Depreciação acumulada até a data

**Vida útil do ativo** = duração em meses

**Valor residual %** = A taxa do custo original do ativo que se espera que permaneça ao final de sua vida útil. O cálculo do saldo decrescente duplo não considera o valor residual na depreciação de cada período; no entanto, se o valor contábil cair abaixo do valor residual, o último período será ajustado para que termine no valor residual.

**Taxa de saldo %** = A taxa para depreciar o ativo.

Se estiver usando Saldo Decrescente com **Taxa de Saldo = 200%**, isso equivale ao método de Declínio Duplo. Essa é a maneira recomendada para modelar o Double Declining padrão em Apptio.

**Exemplo:**

**Preço do ativo:** US$ 40.000

**Vida útil do ativo:** 36 meses

**Taxa de saldo %:** 200%

**Valor residual %:** 0

- **P1 - P12** = 40.000 × 200% × (1 ÷ 36) = **$ 2.220 por mês**

- **Ano 1 = US$ 26.667**

- **P13 - P24** = (40.000 – 26.667) × 200% × (1 ÷ 36) = **$ 741 por mês**

- **Ano 2 = US$ 8.889**

- **P25 - P36** = (40.000 – 26.667 – 8.889) × 200% × (1 ÷ 36) = **$ 247 por mês**

- **Ano 3 = US$ 2.963**

## Saldo decrescente usando dias de calendário

Esse método aplica a fórmula de depreciação de saldo decrescente para calcular a depreciação total do ano, mas aloca essa depreciação entre os períodos proporcionalmente com base no número de dias corridos em cada mês.

Ele mantém o padrão de depreciação acelerada (despesas mais altas no início da vida útil do ativo) e, ao mesmo tempo, melhora a precisão do período ao ponderar cada mês de acordo com seu número real de dias.

## Depreciação manual

Permite que os usuários insiram diretamente os valores de depreciação para cada período, em vez de depender de métodos calculados pelo sistema. Isso proporciona total flexibilidade para definir exatamente como os custos devem ser distribuídos entre os períodos.
