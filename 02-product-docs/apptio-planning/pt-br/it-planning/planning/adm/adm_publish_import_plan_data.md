---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Publicar dados do plano para Apptio cálculo de custos"
breadcrumb:
  - "Planning"
  - "Integrações"
  - "Conecte-se ao site Apptio Costing"
source_path: "it-planning/planning/adm/adm_publish_import_plan_data.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Publicar dados do plano para Apptio cálculo de custos

A publicação dos dados do plano do Apptio Planejamento para Apptio o Cálculo de custos permite compartilhar os dados finalizados do orçamento e da previsão com o ambiente de alocação e transparência de custos. Por meio dos recursos integrados de integração e programação do Automated Data Management (ADM), você pode exportar itens financeiros (finanças, mão de obra, atividade de mão de obra, contratos, ativos) do Planejamento e enviá-los diretamente para Apptio o Cálculo de Custos.

Observação: essas tarefas exigem a função de administrador com a DataOrchestrationServiceFeatureFullAccess permissão.

Lembre-se: o modo automatizado Data Management (ADM) está ativado

## Antes de começar

Certifique-se de que os seguintes pré-requisitos sejam atendidos:

- **O Automated Data Management (ADM)** é provisionado no seu ambiente
- O ADM está habilitado em Apptio Planejamento:
  - Vá para **Configurações (⚙) → Perfil da empresa**
  - Selecione **Ativar integração Data Management automatizada**
- **Os conjuntos de dados de integração de planejamento** necessários são instalados em Apptio Cálculo de custos
- Você tem a função de administrador com a **DataOrchestrationServiceFeatureFullAccess** permissão.

## Gestão de Entidades

Antes de publicar os dados do plano, confirme se **o Mapeamento automatizado Data Management → Entidade** está configurado corretamente para mapear as entidades Apptio de planejamento para os conjuntos de dados de cálculo de custos Apptio apropriados.

1. Vá para **Configurações (⚙) → Automatizado Data Management**.
2. Navegue até **Gerenciamento de Entidades**.
3. Na tabela **Entidade**, localize as entidades de planejamento que deseja publicar, tais como:
   - Orçamento financeiro
   - Previsão financeira
   - Orçamento de ativos
   - Previsão de ativos
   - Orçamento do contrato
   - Previsão do contrato
   - Orçamento de mão de obra
   - Previsão de mão de obra
   - Orçamento de Atividades Trabalhistas
   - Previsão da atividade laboral
4. Para cada entidade, mapeie o **conjunto de dados de custos Apptio** correspondente que receberá os dados do plano publicado.
5. Selecione **Atualizar** para salvar suas alterações.

Saiba mais: [Gestão de entidades](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-entity-management "(Abre em uma nova guia ou janela)")

## Publicação manual

Para publicar manualmente os dados de um plano:

1. Abra o plano em Apptio Planejamento.
2. Selecione o plano desejado na lista suspensa.
3. Selecione a guia Despesas que deseja publicar (por exemplo: Mão de obra, Atividade de mão de obra, Contratos, Ativos, Resumo/Outros).
4. Clique no **menu Ações → Publicar para Apptio Cálculo de custos...**
5. A solicitação de publicação é enfileirada e processada em segundo plano
6. Monitore o status da tarefa de publicação através da página **Configurações (⚙) → Apptio** **Integração** **de custos → Status.**

## Publicação programada

Para automatizar exportações regulares de dados do plano para Apptio o Cálculo de custos (por exemplo, diariamente, semanalmente ou mensalmente):

1. Vá para **Configurações (⚙) → Automatizado** **→ Agenda Data Management de Entidades** para navegar até a interface Data Management Automatizado.
2. Clique em **Adicionar programação**. Conjunto:
   1. **Produtor** : Apptio Planejamento
   2. **Plano** : Selecione o plano a ser publicado
   3. **Entidades (tipos de itens de linha)** : escolha quais itens de linha incluir (orçamento financeiro, orçamento de mão de obra, previsão de contrato, orçamento de ativos, etc.)
3. Defina o período de publicação (por exemplo, mês atual, mês anterior, início do período fiscal ou uma data personalizada) e a frequência da programação (diária, semanal, mensal).
4. Defina a data/hora de início e a data de término opcional. Em seguida**, crie uma programação**.
5. Depois de configurado, o ADM exportará e publicará automaticamente os dados do plano selecionado para o Costing em cada intervalo programado.

As programações podem ser editadas ou removidas a qualquer momento através da mesma página Programação de Entidades no ADM. Saiba mais: [Publicações do Plano de Programação](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-schedule-plan-publishes "(Abre em uma nova guia ou janela)").

**Tópico principal:** [Conectar-se ao Apptio Cálculo de custos](../../../it-planning/planning/adm/adm_capabilities.html "Apptio O planejamento integra-se ao Apptio cálculo de custos usando o ADM ( Data Management Automated Design Management). O ADM é um serviço de plataforma compartilhada projetado para fornecer uma experiência de troca de dados unificada, segura e escalável entre Apptio aplicativos.")
