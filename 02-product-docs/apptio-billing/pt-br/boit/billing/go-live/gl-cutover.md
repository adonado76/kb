---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Abordagem de transição"
breadcrumb:
  - "Billing"
  - "Manual de lançamento"
source_path: "boit/billing/go-live/gl-cutover.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Abordagem de transição

Cutover é a transição controlada de “estamos testando” para “estamos usando o Faturamento como fonte de verdade”

## Decisões comuns sobre migração

Decida e documente:

- Primeiro **período oficial de faturamento** em produção.
- Se você é:
  - Iniciar o faturamento do zero ou
  - Substituir um processo manual ou antigo no meio do ano.
- Se você vai:
  - Republicar períodos anteriores para histórico ou
  - Comece do zero a partir do período de entrada em operação.

## Notas específicas sobre o Essentials

Observação: **aplica-se apenas ao Billing Essentials.**

Para o essencial sobre faturamento:

- A transição está diretamente ligada à promoção do projeto Costing Essentials.
- Quando você promove a compilação de Staging para Produção:
  - Você está promovendo o conteúdo do Costing e do Billing Essentials juntos.
- As ações de entrada em operação geralmente incluem:
  - Promovendo a compilação validada para produção.
  - Executando modelos do Billing Essentials em produção para o primeiro período oficial.
  - Tornar **a coleção de relatórios de faturamento** visível para o público-alvo.

## Notas específicas da norma

Aviso: Aplica-se apenas ao padrão de faturamento.

Para o padrão de faturamento:

- A transição envolve ambos:
  - Promover a criação do projeto de Padrão de Custos que contém a configuração do Padrão de Faturamento.
  - Habilitando e expondo o **endpoint de faturamento** com as coleções de relatórios corretas.

Etapas típicas:

1. Bloqueie o Staging e promova a compilação testada para Produção.
2. Confirme se o **endpoint de faturamento** exibe as coleções de relatórios acordadas (serviços, nuvem, aplicativos, projetos, variação, diários, etc.).
3. Peça a um ou dois usuários piloto (por exemplo, um proprietário de serviço e um representante financeiro) para fazer login no endpoint de faturamento e confirmar:
   - A navegação funciona.
   - Os filtros e as pesquisas detalhadas funcionam conforme o esperado.
