---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Bases de dados compartilhadas"
breadcrumb:
  - "Billing"
  - "Requisitos e integração de dados"
source_path: "boit/billing/datareq-integrate/shared-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Bases de dados compartilhadas

O faturamento está acima do cálculo de custos. Se os dados fornecidos ao Cálculo de Custos e Faturamento forem fracos, as contas serão fracas. Esta seção explica quais dados o faturamento precisa, como eles são normalmente estruturados e onde a integração geralmente ocorre.

Tanto o Billing Essentials quanto o Billing Standard se baseiam em alguns fundamentos comuns:

- **Consumidores**
  - Unidades de negócios, centros de custos, departamentos, projetos ou outras entidades que recebem cobranças.
  - Deve ter identificadores estáveis e exclusivos e uma hierarquia (por exemplo, BU → Departamento → Centro de Custos).
- **Ofertas (serviços/produtos)**
  - O catálogo do que está sendo cobrado.
  - Cada oferta deve conter:
    - Um identificador único.
    - Um nome reconhecível para as partes interessadas do mundo dos negócios.
    - Uma unidade de medida (por exemplo, usuário por mês, GB por mês).
    - Um status (ativo, aposentado, apenas interno).
- **Consumo**
  - Registros que mostram “quanto de quê” um consumidor usou em um determinado período.
  - Requer, no mínimo:
    - Identificação do consumidor.
    - Oferecendo ID (ou algo explicitamente mapeado para ele).
    - Ponto final.
    - Unidades consumidas.
- **Taxas**
  - Preço ou recuperação por unidade.
  - Deve estar vinculado a ofertas e períodos e ser recuperável de forma determinística (por exemplo, taxa efetiva para esse período).

- **Resultados do cálculo de custos**
  - Resultados de custos que representam o lado dos custos (por exemplo, custo por unidade, custo por serviço, custo por consumidor) que o Faturamento pode usar para:
    - Validação das taxas.
    - Análise de variância.
    - Ajustes ou preços baseados nos custos.

Se essas bases forem instáveis ou incompletas, espere problemas mais tarde: cobranças ausentes, taxas inexplicáveis ou contas que não podem ser reconciliadas com o Cálculo de Custos.
