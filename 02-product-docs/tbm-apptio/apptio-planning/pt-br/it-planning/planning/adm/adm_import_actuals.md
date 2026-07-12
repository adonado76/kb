---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Importar dados reais do Apptio cálculo de custos"
breadcrumb:
  - "Planning"
  - "Integrações"
  - "Conecte-se ao site Apptio Costing"
source_path: "it-planning/planning/adm/adm_import_actuals.html"
images:
  - "resources/images/it_planning_images/imprefdata.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Importar dados reais do Apptio cálculo de custos

A importação de dados reais traz dados históricos de gastos do Apptio Cálculo de custos para Apptio o Planejamento, onde podem ser usados para previsões, análises de variação e comparações de planos.

Os dados reais são importados usando o Automated Data Management Data Management (ADM), garantindo que os dados de gastos reais permaneçam alinhados entre os aplicativos.

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

Certifique-se de que **o Mapeamento automatizado Data Management → Entidade** inclua os mapeamentos corretos para os conjuntos Apptio de dados de Cálculo de custos. Quando uma nova dimensão personalizada é adicionada no Apptio Planning, o ADM cria automaticamente uma entrada correspondente na tabela Mapeamento de Entidades — sem necessidade de configuração manual.

1. Vá para **Configurações (⚙) → Automatizado Data Management**
2. Navegue até **Gerenciamento de Entidades**.
3. Localize a entidade **Actuals** na tabela Entity.
4. Mapeie o **conjunto de dados de custos Apptio** correspondente para a entidade. Por exemplo, Mestre de dados reais de planejamento.
5. Selecione **Atualizar** para salvar suas alterações.

Saiba mais: [Gestão de entidades](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-entity-management "(Abre em uma nova guia ou janela)")

## Importar dados reais para Apptio o planejamento

Com a opção Automatizado Data Management ativada, as atualizações dos dados de referência feitas no Apptio Cálculo de custos são importadas automaticamente para Apptio o Planejamento. O processo completo funciona da seguinte maneira:

1. Um usuário atualiza conjuntos de dados mapeados para a entidade Real e realiza um check-in em Apptio Cálculo de custos ( Data Studio ).
2. As alterações são enviadas para a fila de cálculo de custos e processadas.
3. Assim que os cálculos forem concluídos, Apptio o Cálculo de Custos notifica o serviço Data Management Automatizado de que os dados atualizados estão disponíveis.
4. A ADM recupera os dados reais atualizados do Ambiente de Preparação de Custos e os importa para uso no Apptio Planejamento.
5. As atualizações dos dados de referência são aplicadas primeiro.
6. Os dados reais são importados para Apptio o Planejamento dos períodos fiscais relevantes.

Observação: se os períodos estiverem marcados como **Fechados** no Gerenciamento de Gastos, o Automated Data Data Management Management (ADM) não atualizará os dados desses períodos.

Se **a opção Publicar automaticamente dados de referência importados do Apptio Cálculo de custos** estiver ativada no **Perfil da empresa** :

- Os conflitos de dados de referência são resolvidos automaticamente
- Importação dos dados reais concluída sem necessidade de publicação manual

Se esta opção estiver desativada:

- Os dados são importados, mas ficam em estado pendente
- Quaisquer conflitos de dados de referência devem ser resolvidos manualmente
- Os dados devem ser publicados antes de ficarem disponíveis nos planos

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/imprefdata.png)

**Tópico principal:** [Conectar-se ao Apptio Cálculo de custos](../../../it-planning/planning/adm/adm_capabilities.html "Apptio O planejamento se integra ao Apptio cálculo de custos usando o ADM ( Data Management Automated Decision Making). O ADM é um serviço de plataforma compartilhada projetado para fornecer uma experiência de troca de dados unificada, segura e escalável entre Apptio aplicativos.")
