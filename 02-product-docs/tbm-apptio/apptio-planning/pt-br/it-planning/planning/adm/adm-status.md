---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Status de integração"
breadcrumb:
  - "Planning"
  - "Integrações"
  - "Conecte-se ao site Apptio Costing"
source_path: "it-planning/planning/adm/adm-status.html"
images:
  - "resources/images/it_planning_images/int-adm.png"
  - "resources/images/it_planning_images/int-plan.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Status de integração

A página Status da integração fornece visibilidade do progresso das trocas de dados entre Apptio o Planejamento e Apptio o Custeio usando o ADM ( Data Management Automated Data Management). Essa visualização ajuda os administradores a monitorar importações, publicações e solucionar problemas de integração.

Observação: essas tarefas exigem a função de administrador com a DataOrchestrationServiceFeatureFullAccess permissão.

Lembre-se: o modo automatizado Data Management (ADM) está ativado

## O que você pode monitorar

A página Status Apptio da integração de custos mostra o status das atividades ADM relacionadas ao planejamento, incluindo:

- Importação de dados de referência do Apptio Cálculo de custos
- Importações reais
- Importações do plano de referência
- Os dados do plano são publicados em Apptio Cálculo de custos
- Tarefas de integração programadas e manuais
- Execuções bem-sucedidas, em andamento e com falha

Cada registro inclui carimbos de data/hora, status de execução e detalhes de erros (quando aplicável).

## Onde acessar o status da integração

Você pode visualizar o status da integração em qualquer um dos seguintes locais:

**Do Apptio Planejamento**

1. Vá para **Configurações (⚙)**
2. Selecione **Apptio Integração de custos**
3. Abra a guia **Status**

Esta visualização mostra apenas as atividades de integração Apptio ADM relacionadas ao planejamento.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/int-plan.png)

**Da Automated Data Management (ADM)**

1. Vá para **Configurações (⚙)**
2. Selecionar **automatizado Data Management**
3. Navegue até **Status**

Esta visualização exibe todas as atividades de integração ADM entre aplicativos. Saiba mais: [Status ADM](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-status "(Abre em uma nova guia ou janela)")

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/int-adm.png)

**Tópico principal:** [Conectar-se ao Apptio Cálculo de custos](../../../it-planning/planning/adm/adm_capabilities.html "Apptio O planejamento integra-se ao Apptio cálculo de custos usando o ADM ( Data Management Automated Design Management). O ADM é um serviço de plataforma compartilhada projetado para fornecer uma experiência de troca de dados unificada, segura e escalável entre Apptio aplicativos.")
