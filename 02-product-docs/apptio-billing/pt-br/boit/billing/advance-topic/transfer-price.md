---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Preços de transferência e pontos de vista das entidades jurídicas"
breadcrumb:
  - "Billing"
  - "Tópicos avançados"
source_path: "boit/billing/advance-topic/transfer-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Preços de transferência e pontos de vista das entidades jurídicas

Os preços de transferência e as visões ao nível da entidade jurídica tornam-se importantes quando os encargos tecnológicos ultrapassam as fronteiras jurídicas ou fiscais.

Observação: aplica-se apenas ao padrão de faturamento.

## Modelagem de pessoas jurídicas

Elementos mínimos:

- Mestre de entidade jurídica:
  - ID da entidade, nome, país, atributos fiscais.
- Mapeamentos de:
  - De consumidores a pessoas jurídicas.
  - Serviços ou infraestrutura para pessoas jurídicas, quando necessário.

## Fluxos entre empresas

Requisitos comuns:

- Identifique os encargos que representam fluxos entre empresas:
  - De uma pessoa jurídica para outra.
- Represente os fluxos de uma forma que as equipes financeiras e tributárias possam usar:
  - Separe as linhas de receitas internas e despesas internas.
  - Utilize contas e marcadores fiscais adequados.

Elementos típicos de configuração:

- Tabelas de mapeamento para definir relações de origem e destino entre entidades.
- Regras nos modelos de faturamento para:
  - Divida ou reclassifique os encargos em linhas entre empresas.
  - Marque-os com os atributos apropriados.

O objetivo é tornar os preços de transferência transparentes e rastreáveis para as mesmas definições de taxa unitária e serviço utilizadas em outros lugares, e não manter um processo separado e opaco.
