---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Tabelas e relações do domínio principal"
breadcrumb:
  - "Billing"
  - "Configurando o padrão de faturamento (implementação)"
source_path: "boit/billing/config-bs/bs-core.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Tabelas e relações do domínio principal

A força do Billing Standard vem de seu modelo rico em domínios. No mínimo, espere trabalhar com as seguintes famílias de tabelas:

- **Catálogo de serviços/ofertas**
  - ID, nome, unidade de medida, status do ciclo de vida, sinalizador faturável.
- **Consumidores**
  - Compartilhado com o Cálculo de Custos ou alinhado a ele.
  - ID do consumidor, nome, hierarquia e atributos como região, função ou gerente.
- **Unidades e definições de unidades**
  - Unidades padrão (por exemplo, VM por mês, GB por mês, usuário nomeado por mês, ticket por mês).
  - Mapeamentos de medidas específicas do domínio para unidades padrão.
- **Aplicativos**
  - ID do aplicativo, nome, proprietário, status do ciclo de vida.
  - Links para serviços/ofertas e, eventualmente, para projetos e consumidores.
- **Servidores e armazenamento**
  - Servidores: ID, tipo, ambiente, plataforma, propriedade, capacidade.
  - Armazenamento: pool, camada, capacidade, alocação ou mapeamento para consumidores/serviços.
- **Dispositivos do usuário final**
  - ID ou grupo do dispositivo, tipo de dispositivo, proprietário, localização, regras de alocação.
- **NUVEM**
  - Provedor, ID da conta/assinatura, tipo de serviço.
  - Mapeamentos de tags para serviços, consumidores e domínios.
- **Projetos**
  - ID e nome do projeto, tipo ( CapEx/OpEx/other ), proprietário, serviços ou aplicativos vinculados.
- **Pessoas jurídicas / preços de transferência** (se aplicável)
  - Identificação da pessoa jurídica, nome, país, atributos fiscais, relações de emparelhamento entre empresas.
- **Tabelas de preços e variações**
  - Listas de preços, custo vs. plano vs. configuração de preços, categorias de variação.

Essas tabelas foram projetadas para funcionar em conjunto. Evite criar tabelas personalizadas isoladas que duplicam sua finalidade, a menos que haja uma razão clara para isso.
