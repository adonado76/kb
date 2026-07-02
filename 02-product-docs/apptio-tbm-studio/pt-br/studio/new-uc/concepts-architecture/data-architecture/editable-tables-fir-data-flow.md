---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Como as tabelas editáveis se encaixam no fluxo de dados"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura de dados"
  - "Tabelas e tipos de tabelas"
source_path: "studio/new-uc/concepts-architecture/data-architecture/editable-tables-fir-data-flow.html"
images:
  - "resources/images/studio_images/editable-data-flow.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Como as tabelas editáveis se encaixam no fluxo de dados

As tabelas editáveis participam do fluxo de dados por meio de um mecanismo de publicação:

![Fluxo de dados de tabela editável](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/editable-data-flow.png)

A publicação sobrescreve todo o conjunto de dados da tabela editável na tabela de transformação associada. Isso pode ser feito manualmente ou de acordo com uma programação recorrente (a cada hora, diariamente, semanalmente ou mensalmente). Opcionalmente, a publicação pode acionar uma promoção automática para o ambiente de produção.

Nota:

**Importante**

As tabelas editáveis são específicas de cada ramificação. Ao criar um ramo, é gerada uma cópia independente das tabelas editáveis, e as alterações feitas no tronco não aparecem no ramo (e vice-versa).

**Tópico principal:** [Tabelas e tipos de tabelas](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
