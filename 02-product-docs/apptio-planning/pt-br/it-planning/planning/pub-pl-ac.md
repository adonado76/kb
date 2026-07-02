---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Publicar lista de projetos em Apptio Cálculo de custos"
breadcrumb:
  - "Planning"
  - "Integrações"
  - "Conecte-se ao site Apptio Costing"
source_path: "it-planning/planning/pub-pl-ac.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Publicar lista de projetos em Apptio Cálculo de custos

Observação: essas tarefas exigem a função de administrador com a permissão DataOrchestrationServiceFeatureFullAccess.

**Pré-requisito:** ADM ( Data Management ) automatizado habilitado

A Lista de Projetos no nível do plano pode ser publicada em um Cálculo de Custos d Apptio e usando o ADM ( Data Management, ou Gerenciamento de Despesas Automatizado), garantindo que os dados do projeto permaneçam alinhados entre os aplicativos.

## Antes de começar

Certifique-se de que os seguintes pré-requisitos sejam atendidos:

- **O ADM ( Data Management ) automatizado** é provisionado em seu ambiente
- O ADM está habilitado no planejamento de Apptio :
- Vá para **Configurações (⚙) → Perfil da empresa**
- Selecione **Ativar integração automatizada com o Data Management**
- **Os conjuntos de dados de integração de planejamento** necessários estão instalados em Cálculo de custos d Apptio
- Você tem a função de administrador com a permissão **DataOrchestrationServiceFeatureFullAccess**.

## Gestão de Entidades

Certifique-se de que **o mapeamento automatizado de entidades ( Data Management ) → mapeamento de entidades (Entity Mapping)** inclua os mapeamentos corretos para os conjuntos de dados de custos de produtos ( Apptio ).

1. Vá para **Configurações (⚙) → Automatizado Data Management**
2. Navegue até **Gerenciamento de Entidades**.
3. Localize a entidade **Lista de projetos publicados** na tabela Entidade.
4. Mapeie o **conjunto de dados de custos** Apptio correspondente para a entidade.
5. Selecione **Atualizar** para salvar suas alterações.

Saiba mais: [Gestão de entidades](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-entity-management "(Abre em uma nova guia ou janela)")

## Publicar lista de projetos em Apptio Cálculo de custos

Para publicar a Lista de Projetos do Plano para o Cálculo de Custos do Apptio :

1. Navegue até **Plano > Lista de projetos**.
2. Selecione o **menu de overflow (⋯)**.
3. Selecione **Publicar em Cálculo de custos de Apptio**.
4. Selecione o botão **Status** para visualizar o status da tarefa de publicação.

Para saber mais sobre como gerenciar projetos, consulte [Gerenciar projetos](iip/project-list-document.html).

**Tópico principal:** [Conecte-se ao Cálculo de Custos d Apptio](../../it-planning/planning/adm/adm_capabilities.html "Apptio O planejamento se integra ao cálculo de custos do “ Apptio ” (Cálculo de Custos de Produção) usando o “ Data Management ” (Módulo de Cálculo de Custos) automatizado. O ADM é um serviço de plataforma compartilhada projetado para fornecer uma experiência de troca de dados unificada, segura e escalável entre aplicativos d Apptio.")
