---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Ativo fixo Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financeiro"
  - "Ativos fixos"
source_path: "cost-transparency/it-financials/fa-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Ativo fixo Introdução

**Introdução**

Use o recurso Ativos fixos para rastrear ativos de TI capitalizados, monitorar a depreciação e apoiar decisões informadas sobre gerenciamento de ativos. O **componente** CTF – Ativos Fixos permite a geração de relatórios sobre custos de depreciação e valor residual dos ativos, ajudando os responsáveis pelas finanças e serviços de TI a compreender o ciclo de vida dos ativos e o impacto financeiro.

Antes de utilizar os relatórios de Ativos Fixos, instale o componente necessário e carregue os dados dos ativos fixos na tabela de dados mestre.

## Instalação de componentes

**CTF - Ativos fixos**

O componente CTF - Ativos fixos fornece a estrutura necessária para analisar o custo, a depreciação e o valor residual dos ativos fixos ao longo do tempo.

**Pré-requisitos**

- CTF - Fonte de custos

Após instalar o componente, você deve carregar os dados de custo do ativo fixo e mapeá-los para a tabela **Dados mestre do ativo fixo** para preencher os relatórios de depreciação e relacionados ao ativo.

## Fontes comuns de dados

Os dados relativos aos ativos fixos são normalmente obtidos a partir de sistemas de gestão de ativos empresariais ou bases de dados de gestão de configurações (CMDBs) que mantêm um registo de ativos fixos. Esses sistemas rastreiam os ativos usados para fornecer bens ou serviços e geralmente incluem detalhes como data de compra, custo de compra, vida útil do ativo em meses e valores de depreciação.

As fontes mais utilizadas incluem **o Enterprise Asset Management** ( SAP ), **Oracle** **o PeopleSoft**, **o BMC Asset Management / BMC Atrium CMDB**, **o Asset Management** ( ServiceNow ) e **o Workday Financial Management**

**Conjuntos de dados mestres**

A tabela Dados mestre do imobilizado define os dados necessários para relatórios de custo e depreciação do imobilizado. Para preencher esta tabela, carregue um conjunto de dados de ativos fixos contendo informações sobre custos e depreciação e mapeie-o para os campos apropriados na tabela de dados mestre.

Normalmente, você carrega um **único conjunto de dados de ativos fixos**, que é anexado e mapeado na tabela Dados mestre de ativos fixos. O conjunto de dados deve incluir campos que estejam alinhados com a estrutura de dados mestre necessária para permitir relatórios precisos sobre depreciação e ciclo de vida.
