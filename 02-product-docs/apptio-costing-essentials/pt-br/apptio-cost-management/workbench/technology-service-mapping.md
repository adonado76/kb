---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "pt-br"
doc_type: "apptio-cost-management"
title: "Mapeamento de serviços de tecnologia"
breadcrumb:
  - "Costing Essentials"
  - "Ambiente de Trabalho"
source_path: "apptio-cost-management/workbench/technology-service-mapping.html"
images:
  - "resources/images/studio_images/tsm-1.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Mapeamento de serviços de tecnologia

Use o ET superior para selecionar o Método de estimativa

- Percentual
- Volume

Use o ET inferior para preencher os valores de acordo:

- Estimativa de uso de infraestrutura: %
- Calcular: Nb. contra o Total
- Armazenamento: Nb. contra o Total

![Mapeamento TS](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/tsm-1.png)

A ponderação em porcentagem deve ser inserida em decimais.

Esse mapeamento afetará o TCO das soluções, pois redistribuirá o custo dos serviços de tecnologia entre diferentes IDs de oferta.

O custo dos serviços de tecnologia é determinado a partir de todos os custos em que os recursos (fornecedor/trabalhador/outros) foram mapeados para os tipos de solução Infraestrutura ou Plataforma

O custo dos serviços de tecnologia pode ser alocado para IDs de oferta em qualquer tipo de solução (infraestrutura, plataforma e outros): Business, Delivery, Shared & Corporate, Workplace)

No exemplo acima, o custo dos serviços de tecnologia será alocado em 40% para o Vmware (em Infra), 10% para o servidor FTP (em Plataforma) e 50% para SAP Order Management v4 (em Negócios)
