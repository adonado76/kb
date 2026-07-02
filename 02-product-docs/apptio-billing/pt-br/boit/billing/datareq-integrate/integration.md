---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Mecanismos de integração e opções fora do Studio"
breadcrumb:
  - "Billing"
  - "Requisitos e integração de dados"
source_path: "boit/billing/datareq-integrate/integration.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Mecanismos de integração e opções fora do Studio

Os dados podem chegar ao departamento de faturamento por meio de vários mecanismos. Quais são usados depende de quem gerencia a implementação e quais ferramentas estão disponíveis.

Opções comuns:

- **ETL estruturado no TBM Studio**
  - Usado quando a organização de TI, o parceiro ou a equipe IBM tem acesso total ao Studio e à integração.
  - Adequado para feeds recorrentes de CMDB, PPM, provedores de nuvem, RH e Finanças.
- **Datalink ou plataformas de integração**
  - Usado para automatizar a ingestão de vários sistemas sem o manuseio manual de arquivos.
  - Útil quando os sistemas de origem são baseados na nuvem ou quando são necessárias atualizações quase em tempo real.
- **Carregamento de tabelas e manutenção do front-end**
  - Utilizado quando o acesso ao Studio é limitado ou quando determinados dados de referência são mantidos por equipes voltadas para os negócios.
  - Exemplos:
    - Carregando tabelas de taxas atualizadas.
    - Atualização de pequenas listas de referência para ofertas ou tabelas de mapeamento.

Diretrizes:

- Use a integração automatizada para dados de alto volume ou que mudam com frequência (por exemplo, consumo, uso da nuvem, custo do projeto).
- Reserve os uploads manuais para:
  - Tabelas pequenas que mudam com pouca frequência (por exemplo, um catálogo de produtos ou uma lista de preços).
  - Ajustes controlados ou correções pontuais.

As seções posteriores deste guia pressupõem que esses requisitos de dados e padrões de integração estão em vigor ao descrever as etapas de configuração, o ciclo de faturamento e como interpretar os resultados do faturamento.
