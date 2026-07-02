---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Importar planos de referência do Apptio Cálculo de custos"
breadcrumb:
  - "Planning"
  - "Integrações"
  - "Conecte-se ao site Apptio Costing"
source_path: "it-planning/planning/adm/adm-import-baseline-data.html"
images:
  - "resources/images/it_planning_images/impbaseline.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Importar planos de referência do Apptio Cálculo de custos

Esse recurso permite importar dados do plano de referência do Apptio Cálculo de custos para Apptio o Planejamento. Isso é útil quando você deseja trazer um conjunto de dados existente do Apptio Cálculo de custos como ponto de partida para o orçamento ou a previsão.

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

Quando o Automated Data Management (ADM) está ativado, a página Mapeamento de Entidades no ADM é automaticamente atualizada com as seguintes novas entidades:

- **Importar Plano de Mão de Obra** – Representa os itens de mão de obra em **Despesas > Mão de Obra**
- **Importar Contrato de Plano** – Representa os itens do contrato em **Despesas > Contratos**
- **Importar ativo do plano** – Representa itens de ativo em **Despesas > Ativos**
- **Importar dados financeiros do plano** – Representa itens financeiros em **Despesas > Outros**
- **Importar atividade de mão de obra do plano** – Representa os itens de atividade de mão de obra em **Despesas > Atividade de mão de obra**

Essas entidades permitem o mapeamento para os conjuntos de dados correspondentes em Apptio Cálculo de custos. Depois de mapeados, os dados do Apptio Cálculo de custos podem ser importados diretamente para as guias Despesas apropriadas do plano selecionado no Apptio Planejamento.

## Como importar um plano de linha de base

1. Em Apptio Planejamento, navegue até **Plano → Despesas**.
2. Habilite a **Nova Visualização** (a importação de planos de linha de base do Apptio Cálculo de Custos é suportada apenas na Nova Visualização).
3. Selecione a **guia Despesas** para a qual deseja importar (Mão de obra, Atividade de mão de obra, Contratos, Ativos ou Outros).
4. Abra o **menu de ações da tabela de reticências** e selecione **Importar de Apptio Cálculo de custos...**
5. Escolha como os dados devem ser aplicados:
   1. **Substitua todos os dados** para sobrescrever os dados existentes ou
   2. **Atualizar dados** para mesclar atualizações no plano existente usando o código do item de linha.
6. Selecione o **período de Apptio cálculo de custos** do qual deseja importar os dados.
7. Clique em **Importar**. Os dados de referência são importados para o plano usando o conjunto de dados da entidade mapeada do Apptio Cálculo de custos.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/impbaseline.png)

Observação: A *Importar com* ***Atualizar dados*** opção está disponível apenas quando o **Código externo** recurso estiver ativado. Essa opção atualiza as linhas existentes do Plano, identificando-as por meio de um identificador exclusivo nos dados importados. Como os dados do Planejamento se originam do Cálculo de Custos, é necessário um identificador único definido pelo usuário para garantir o alinhamento preciso entre os registros do Cálculo de Custos e do Planejamento.

Para saber mais sobre o Código Externo, acesse [Códigos Externos](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-external-codes "(Abre em uma nova guia ou janela)")

**Tópico principal:** [Conectar-se ao cálculo de custos d Apptio](../../../it-planning/planning/adm/adm_capabilities.html "Apptio O planejamento integra-se ao Apptio cálculo de custos usando o ADM ( Data Management Automated Design Management). O ADM é um serviço de plataforma compartilhada projetado para fornecer uma experiência de troca de dados unificada, segura e escalável entre Apptio aplicativos.")
