---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Design centrado no catálogo de serviços"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
source_path: "boit/billing/admin-ops/ao-service-catalog.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Design centrado no catálogo de serviços

**Quando usar**

- A organização de tecnologia possui um catálogo de serviços ou portfólio de produtos que deseja faturar.
- As principais conversas são no nível do serviço ou produto, não por servidor ou aplicativo.

**Orientar**

- O catálogo de serviços ou produtos é o principal objeto de faturamento.
- Os domínios (infraestrutura, nuvem, aplicativos) alimentam o custo e os volumes nos serviços dentro do Costing.
- O faturamento concentra-se em unidades de nível de serviço, taxas e encargos.

**Elementos-chave**

- Catálogo de serviços estável com propriedade clara.
- Tabelas de mapeamento:
  - Objetos de infraestrutura → serviços.
  - Aplicativos → serviços.
  - Contas/tags na nuvem → serviços.
- Faturamento:
  - Consumo no nível do serviço.
  - Taxas no nível de serviço.
  - O domínio opcional retorna através de relatórios.

**Relatórios típicos**

- Visualizações de contas centradas nos serviços: uma linha por serviço por consumidor.
- Visão da rentabilidade ou margem do serviço, onde o preço versus custo é relevante.
- Detalhes opcionais do domínio (por exemplo, “o que compõe o custo deste serviço”).

**Notas de implementação**

- Concentre os esforços de design em definir corretamente os serviços. O faturamento será muito mais fácil.
- Trate os serviços como a “linguagem” utilizada com as partes interessadas da empresa e utilize domínios para apoiar a análise interna.
