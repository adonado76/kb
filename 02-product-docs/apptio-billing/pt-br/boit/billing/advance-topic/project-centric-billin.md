---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Faturamento e visualizações centrados no projeto"
breadcrumb:
  - "Billing"
  - "Tópicos avançados"
source_path: "boit/billing/advance-topic/project-centric-billin.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Faturamento e visualizações centrados no projeto

Os projetos geralmente representam investimentos em produtos, serviços ou iniciativas de mudança. Os componentes do projeto Padrão de Faturamento permitem o faturamento e o showback centrados no projeto.

Observação: aplica-se apenas ao padrão de faturamento.

## Projeto como consumidor vs projeto como dimensão

Dois padrões comuns:

- **Projeto como consumidor**
  - O projeto é cobrado pelos serviços que consome (por exemplo, plataformas, ambientes, ferramentas compartilhadas).
  - Útil para acompanhar o uso de infraestruturas ou plataformas compartilhadas pelo projeto.
- **Projeto como dimensão**
  - As cobranças às unidades de negócios são marcadas com atributos do projeto.
  - Útil para compreender quanto uma unidade de negócios gasta em iniciativas específicas.

Escolhas de design:

- Decida se os projetos irão:
  - Receba diretamente as cobranças.
  - Marque apenas o consumo subjacente de mão de obra ou serviços.
- Garanta que os IDs e nomes dos projetos sejam estáveis e consistentes em todos os sistemas (PPM, RH, Finanças).

## Dados necessários para visualizações do projeto

Requisitos mínimos:

- Mestre do projeto:
  - ID do projeto, nome, proprietário, tipo e status do ciclo de vida.
- Mapeamentos de projeto para serviço:
  - Vincule projetos a serviços, aplicativos ou plataformas utilizados.
- Mão de obra e outros fatores de custo:
  - Tempo, custo ou pontos por projeto, quando os projetos determinam a alocação.

Com isso em vigor, o Padrão de Faturamento pode:

- Mostrar despesas por projeto e consumidor.
- Mostrar taxas unitárias específicas do projeto para serviços compartilhados.
- Relatórios de suporte, como “os 10 principais projetos por consumo de tecnologia”
