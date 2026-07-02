---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Análise e otimização da taxa unitária"
breadcrumb:
  - "Billing"
  - "Tópicos avançados"
source_path: "boit/billing/advance-topic/unit-rate-analysis.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Análise e otimização da taxa unitária

As taxas unitárias são frequentemente o tema central das conversas sobre faturamento. Esta subseção enfoca como analisá-los e ajustá-los ao longo do tempo.

## Análise da taxa unitária básica

Perguntas principais:

- Qual é a taxa unitária para cada oferta neste período?
- Como essa taxa unitária mudou ao longo do tempo?
- As mudanças são motivadas por decisões relacionadas a custos, volume ou preços?

Entradas típicas:

- **Unidades**
  - Das tabelas de consumo de faturamento.
- **Encargos**
  - Das tabelas de saída de faturamento.
- **Custo por unidade**
  - A partir dos resultados de custos, quando disponíveis.

Padrões básicos de análise:

- Calcule a taxa unitária como Encargo/Unidades para cada oferta e período.
- Compare a taxa unitária do período atual com:
  - Período anterior.
  - Mesmo período do ano passado.
- Compare a taxa unitária com o custo por unidade (se o custo estiver disponível).

Use esta visualização para identificar:

- Ofertas com taxas unitárias em alta e volumes estáveis ou em queda.
- Ofertas com quedas repentinas na taxa unitária que podem indicar problemas de configuração de dados ou taxas.

## Compreender os movimentos das taxas unitárias

Fatores comuns que influenciam as alterações nas taxas unitárias:

- **Mudanças de custo**
  - Aumentos nos custos a montante nas torres ou fornecedores de tecnologia.
  - Alterações na lógica de alocação no Cálculo de custos.
- **Alterações de volume**
  - Custos fixos distribuídos por um número significativamente maior ou menor de unidades.
  - Migrações ou aposentadorias únicas.
- **Alterações de preço**
  - Decisões explícitas para alterar taxas, ajustar a recuperação ou introduzir descontos.

Modelos de relatórios úteis:

- Para cada oferta e período:
  - Colunas de unidades, custo por unidade, preço por unidade e variação.
- Gráficos de tendências:
  - Taxa unitária ao longo do tempo juntamente com a tendência de volume.

Use esses padrões para separar questões estruturais (mudanças nos dados ou no modelo) de decisões comerciais conscientes (nova estratégia de taxas).

## Alavancas de otimização

Quando as taxas unitárias parecem erradas, as alavancas típicas são:

- Melhore os fatores de custo e as alocações no Cálculo de custos.
- Ajuste o design do serviço ou a estrutura do catálogo.
- Alterar taxas ou metas de recuperação.
- Reduzir os custos subjacentes (por exemplo, renegociação com fornecedores, otimização da nuvem).

O faturamento revela o comportamento da taxa unitária. O trabalho de implementação para otimizá-lo é geralmente feito em modelos de custos, projetos de domínio e decisões de sourcing.
