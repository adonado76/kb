---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Âmbito e pré-requisitos"
breadcrumb:
  - "Billing"
  - "Configurando o padrão de faturamento (implementação)"
source_path: "boit/billing/config-bs/bs-overview.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Âmbito e pré-requisitos

Esta seção descreve como o Padrão de Faturamento é configurado em um projeto Padrão de Custeio, desde a instalação dos componentes até as primeiras faturas ricas em domínios utilizáveis. Presume-se que o Padrão de Custeio já esteja implantado e estável.

Observação: aplica-se apenas ao padrão de faturamento.

A configuração no TBM Studio é normalmente feita por um administrador ou função equivalente com acesso ao Studio.

## Âmbito e pré-requisitos

Antes de fazer alterações, confirme:

- A organização está usando **o Padrão de Faturamento** (Modelo de Componente versão 120 ou anterior).
- Existe um projeto **de Norma de Custos** com:
  - Em ambientes de desenvolvimento, teste e produção.
  - Um modelo de custos operacionais que já suporta torres tecnológicas, aplicações, serviços e consumidores.
- Existe um projeto claro para:
  - Ofertas faturáveis (serviços/produtos).
  - Consumidores (unidades de negócios, centros de custo, projetos, produtos, etc.).
  - Modelagem de domínio:
    - Aplicativos
    - Servidores e armazenamento
    - Contas e serviços na nuvem
    - Dispositivos do usuário final
    - Projetos
    - Pessoas jurídicas, se os preços de transferência estiverem dentro do escopo
    - Estratégia de taxas e abordagem de variação (custo vs. plano vs. preço).

Pré-requisitos técnicos:

- Acesso do TBM Studio ao projeto Padrão de Custeio.
- Acordo sobre quais domínios serão usados ativamente no lançamento e quais serão implementados posteriormente.
