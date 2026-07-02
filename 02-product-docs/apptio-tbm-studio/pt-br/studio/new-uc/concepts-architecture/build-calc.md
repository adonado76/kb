---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Processo de construção e cálculo"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Ciclo de vida de compilação e implantação"
source_path: "studio/new-uc/concepts-architecture/build-calc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Processo de construção e cálculo

No TBM Studio, uma “compilação” refere-se ao processo de calcular todas as transformações, métricas, análises detalhadas e relatórios para um determinado ambiente. Entender o que desencadeia as compilações e como elas são enfileiradas ajuda você a planejar seu trabalho de forma eficaz.

**O que desencadeia uma compilação**

As compilações são acionadas por diferentes ações, dependendo do ambiente:

|  |  |  |
| --- | --- | --- |
| **Meio ambiente** | **Ativador** | **O que conta** |
| Desenvolvimento | Salvar (com a opção "Cálculo automático" ativada) | Transformações e métricas |
| Preparação | Registro de qualquer documento | Transformações, métricas, análises detalhadas, relatórios |
| Produção | Promoção a partir do estágio | Recebe a compilação calculada (sem recálculo) |

**Fluxo de dados de cálculo**

Compreender o fluxo de dados de cálculo ajuda a diagnosticar problemas quando as compilações falham ou produzem resultados inesperados. O fluxo geral é o seguinte:

1. **Tabelas de dados:** os dados brutos são carregados ou importados.
2. **Etapas da transformação:** os dados são limpos, mapeados, combinados e enriquecidos.
3. **Conjuntos de dados mestre:** Tabelas unificadas (por exemplo, Mestre de fontes de custo) combinam dados do Razão, do Orçamento e da Previsão.
4. **Objetos de modelo:** O modelo faz referência a essas tabelas de transformação unificadas.
5. **Alocações:** As métricas são propagadas ao longo da cadeia de alocação.
6. **Relatórios:** Os valores calculados são apresentados nos relatórios.

Nota:

**Comportamento principal:** O modelo não pode realizar cálculos a menos que as tabelas de transformação sejam validadas. Erros nas transformações anteriores bloquearão a lógica da camada do modelo. Sempre resolva os erros de transformação antes de esperar que os cálculos do modelo sejam concluídos.

**Monitoramento da fila de cálculos**

A fila de cálculos mostra o que já foi calculado (com a duração), o que está sendo calculado no momento e o que está em espera. Para visualizá-lo:

1. No TBM Studio, selecione a guia "Build".
2. Clique em "Fila de cálculos".

Quando ocorrem vários check-ins em um curto período, eles podem ser agrupados em um único cálculo. Se um cálculo já estiver em execução, os check-ins subsequentes são colocados na fila para o próximo cálculo. Para cálculos de etapa de longa duração, considere usar o recurso “Cancelar compilação” ( v.12.3.1+ ) para cancelar a compilação em andamento, de modo que as alterações pendentes possam ser incluídas na próxima compilação.

Dica:

Coordene as reuniões com sua equipe. Se todos fizerem o check-in ao mesmo tempo (por exemplo, no final do dia), o sistema processa tudo em um único cálculo, em vez de enfileirar vários cálculos sequenciais.
