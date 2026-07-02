---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tabelas publicadas"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura de dados"
  - "Tabelas e tipos de tabelas"
source_path: "studio/new-uc/concepts-architecture/data-architecture/published-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tabelas publicadas

**Objetivo:** Compartilhar dados modelados com sistemas externos em um formato controlado e com esquema estável.

As tabelas publicadas são o principal mecanismo de saída de dados no TBM Studio. Eles fornecem um conjunto de dados estável e alinhado ao modelo, que sistemas externos (como Power BI, Snowflake ou lagos de dados corporativos) podem recuperar programaticamente por meio de uma API URL.

Principais características das tabelas publicadas:

- São entidades distintas dos relatórios e das tabelas de transformação, concebidas especificamente para a exportação de dados.
- Eles refletem valores calculados do modelo — e não valores preliminares das ramificações de desenvolvimento.
- Eles são atualizados automaticamente após cálculos bem-sucedidos no ambiente de teste ou de produção.
- Por padrão, as tabelas publicadas são pré-calculadas para que estejam prontas imediatamente quando solicitadas via API.
- Somente administradores podem criar ou modificar tabelas publicadas.

As tabelas publicadas foram criadas para substituir a prática anterior de gerar relatórios bloqueados exclusivamente para exportação de dados, o que acarretava uma carga desnecessária no sistema durante os cálculos.

Nota:

**Quando usar tabelas publicadas**

Utilize tabelas publicadas quando precisar importar resultados de modelos de custo para plataformas de análise externas, data warehouses ou sistemas de planejamento. Eles oferecem um esquema estável que não se altera à medida que os relatórios evoluem, tornando-os ideais para pipelines de integração automatizados

**Tópico principal:** [Tabelas e tipos de tabelas](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
