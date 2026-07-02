---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Visão geral dos fluxos de trabalho de aprovação"
breadcrumb:
  - "Planning"
  - "Fluxos de trabalho e colaboração"
source_path: "it-planning/planning/about-approval-workflows.html"
images:
  - "resources/images/it_planning_images/hier-approval.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Visão geral dos fluxos de trabalho de aprovação

Os fluxos de trabalho de aprovação no Apptio Planning controlam como os planos enviados passam pelos estágios de revisão e aprovação, garantindo que os planos sejam encaminhados às partes interessadas apropriadas para aprovação. Esses fluxos de trabalho oferecem flexibilidade para se alinharem à estrutura e ao processo de governança de sua organização.

Apptio O planejamento suporta dois tipos de workflows de aprovação:

- **Aprovações hierárquicas** - Encaminha os planos pela hierarquia do departamento para revisão e aprovação.
- **Aprovações em vários níveis** - Define uma cadeia de aprovação personalizada e sequencial (por exemplo, L1 → L2 → L3 ) para cada departamento, independentemente da hierarquia organizacional.

Os administradores podem escolher o tipo de fluxo de trabalho para um ciclo de planejamento com base na estrutura da organização e no processo de tomada de decisão.

## Aprovações hierárquicas

As aprovações hierárquicas encaminham os planos enviados de acordo com a hierarquia do departamento, exigindo que as aprovações avancem para cima em cada nível até que o plano geral seja finalizado. Essa abordagem é mais adequada quando as aprovações devem seguir a estrutura de relatórios da organização.

**Principais características:**

- **Roteamento baseado em hierarquia de departamentos:** As aprovações fluem dos departamentos folha para os departamentos pai.
- **Status do plano:** O status de um plano passa de **In Progress (Em andamento** ) para **Submitted (Enviado** ) e depois para **Approved (Aprovado** ) ou **Returned (Devolvido** ).
- **Vários proprietários por nível:** É possível atribuir vários proprietários em um nível de departamento ou grupo, sendo necessária apenas uma aprovação para que o plano avance.
- **Envios de departamentos de grupo:** Um Departamento de Grupo pode enviar todos os seus Departamentos filhos juntos para aprovação, e o envio de um Departamento de Grupo aprova automaticamente todos os Departamentos filhos dentro dele.
- **Comportamento de rejeição:** A rejeição de um plano faz com que ele volte um nível na hierarquia. O proprietário nesse nível precisaria rejeitá-lo novamente para continuar a levá-lo de volta ao Departamento de Folhas para revisões.
- **Suporte para ignorar nós:** Você pode configurar os nós da hierarquia para serem ignorados, deixando o proprietário não atribuído nesse nível, fazendo com que as aprovações sejam transferidas para o próximo proprietário de nível superior.

**Exemplo**

No exemplo abaixo, os grupos D e E podem ser configurados como nós de "salto". Os planos dos Departamentos A, B, C, D e E passarão pelos níveis intermediários e serão aprovados diretamente pelo proprietário do Grupo B.

![aprovação hierárquica](../../../../../03-media/apptio-planning/resources/images/it_planning_images/hier-approval.png)

**Aprovações hierárquicas - Permissões de nível de edição**

As aprovações hierárquicas usam o **nível de edição** para controlar quem pode visualizar, editar, enviar e aprovar em um fluxo de trabalho de aprovação. Você pode configurar o **nível de edição** de um usuário em **Permissões de objetos de custo**. Para obter mais informações, consulte [os dados de referência de Manage Cost Object Permissions](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=configuration-cost-object-permissions "(Abre em uma nova guia ou janela)").

Observação: Ative a opção **Send Email Notifications for Planning Process Events (Enviar notificações por e-mail para eventos do processo de planejamento** ) no Company Profile (Perfil da empresa) para acionar alertas por e-mail quando os planos forem abertos, enviados, aprovados ou devolvidos. Consulte [Notificações por e-mail](manage-email-notifications.html) para obter mais informações.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Nível de edição** | **Visualização** | **Editar** | **Enviar/Desbloquear planos** | **Aprovar** | **Voltar** | **Alertas de e-mail** |
| Proprietário | Sim | Sim | Sim | Sim | Sim | Sim |
| Editar e enviar | Sim | Sim | Sim | Não | Não | Sim |
| Editar | Sim | Sim | Não | Não | Não | Sim |
| Somente visualizar | Sim | Não | Não | Não | Não | Não |

Observação: a aprovação do orçamento é hierárquica. Os usuários com permissão **de “Proprietário”** no nível de um departamento de nível inferior não podem aprovar nem devolver orçamentos desse departamento; essas ações devem ser realizadas por um **“Proprietário”** do departamento superior.

## Aprovações em vários níveis

As aprovações em vários níveis permitem que os administradores configurem uma cadeia de aprovação personalizada e sequencial (por exemplo, L1 → L2 → L3 ) para cada departamento, independentemente da hierarquia organizacional. Isso é útil quando:

- As aprovações devem vir de funções específicas ou de aprovadores nomeados em todos os departamentos.
- O processo de aprovação não está estritamente alinhado à estrutura organizacional.

**Principais características:**

- **Aprovações sequenciais:** Configure até 10 níveis de aprovação por departamento, com as aprovações progredindo em ordem do Nível 1 para o Nível 2, Nível 3 e assim por diante.
- **Status do plano:** O status de um plano passa de In Progress (Em andamento) para Submitted (Enviado), depois para **L1 Approved (Aprovado** ), **L2 Approved (Aprovado** ) e assim por diante, até que todas as aprovações necessárias sejam concluídas e o aprovador final altere o status para **Approved (Aprovado** ).
- **Vários proprietários por nível:** Você pode atribuir vários aprovadores por nível, sendo necessária apenas uma aprovação para que o plano avance.
- **Comportamento de rejeição:** Se um departamento for rejeitado em qualquer nível, o plano retornará ao início da cadeia de aprovação, exigindo que o proprietário do departamento o reenvie a partir do nível 1.
- **Planejamento assíncrono:** Os departamentos podem enviar e avançar de forma independente pela cadeia de aprovação.

**Aprovações em vários níveis - Permissões de edição e aprovação**

Nos fluxos de trabalho de vários níveis, o **nível de edição** e **o nível de aprovação** são permissões separadas, permitindo que os administradores definam os direitos de edição independentemente da autoridade de aprovação.

- **Edit Level (Nível de edição):** Controla se um usuário pode visualizar, editar ou enviar dados do plano.
- **Nível de aprovação:** Determina se o usuário faz parte da cadeia de aprovação ( L1–L10 ). Um usuário pode ter acesso de edição sem ser um aprovador, ou ser um aprovador sem direitos de edição.

É possível configurar o **nível de edição** e o **nível de aprovação** de um usuário em **Permissões de objetos de custo**. Consulte [os dados de referência sobre “Gerenciar permissões de objeto de custo”](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=configuration-cost-object-permissions "(Abre em uma nova guia ou janela)") para obter mais informações.

Observação: Ative a opção **Send Email Notifications for Planning Process Events (Enviar notificações por e-mail para eventos do processo de planejamento** ) no Company Profile (Perfil da empresa) para acionar alertas por e-mail quando os planos forem abertos, enviados, aprovados ou devolvidos. Consulte [Notificações por e-mail](manage-email-notifications.html) para obter mais informações.

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Nível de edição** | **Visualização** | **Editar** | **Enviar/Desbloquear planos** | **Alertas de e-mail** |
| Proprietário | Sim | Sim | Sim | Sim |
| Editar e enviar | Sim | Sim | Sim | Sim |
| Editar | Sim | Sim | Não | Sim |
| Somente visualizar | Sim | Não | Não | Não |

|  |  |  |  |
| --- | --- | --- | --- |
| **Nível de aprovação** | **Aprovar** | **Voltar** | **Alertas de e-mail** |
| Nível 1 - Nível 10 | Sim | Sim | Sim |
| Nenhum | Não | Não | Não |

## Comparação do fluxo de trabalho

|  |  |  |
| --- | --- | --- |
|  | **Aprovações hierárquicas** | **Aprovações em vários níveis** |
| **Caminho de aprovação** | Segue a hierarquia do departamento, progredindo nível a nível pelos departamentos principais. | Definido de forma personalizada por departamento, com aprovações sequenciais que fluem em ordem ( L1 → L2 → L3, etc.). |
| **Níveis de aprovação** | Vários proprietários podem ser atribuídos por departamento ou grupo de departamentos, sendo necessária apenas uma aprovação para avançar. | Suporta até 10 níveis de aprovação por departamento. Vários aprovadores podem ser atribuídos por nível, sendo que apenas um é necessário para aprovar. |
| **Envio de grupo** | Oferece suporte a envios de departamentos de grupo, em que o envio de um grupo envia e aprova automaticamente todos os departamentos filhos juntos. | Não aplicável. |
| **Fluxo de planejamento** | Requer planejamento e envio síncronos (os Departamentos filhos devem enviar antes que o Grupo pai possa avançar). | Oferece suporte ao planejamento e à revisão assíncronos. Os departamentos podem enviar e avançar de forma independente pela cadeia de aprovação. |
| **Comportamento de rejeição** | A rejeição faz com que o plano volte um nível na hierarquia. O Proprietário em cada nível deve continuar rejeitando para empurrá-lo para o Departamento de Folhas. | A rejeição de um departamento faz com que ele retorne ao início do fluxo de trabalho, exigindo que o departamento seja reenviado ao Nível 1. |
| **Ignorar nós** | Com o suporte de deixar o proprietário não atribuído em um nível, as aprovações são transferidas para o próximo proprietário de nível superior. | Não aplicável. |
| **Permissões de usuário** | Permissão de nível de edição:  - **Proprietário:** pode editar, enviar e aprovar ou devolver planos. Recebe notificações por e-mail quando os planos são aprovados ou devolvidos. - **Edit & Submit** - Pode editar e enviar planos. - **Editar** - Pode editar planos, mas não pode enviar. - **View Only (Somente visualização** ) - Pode visualizar planos, mas não pode editar ou enviar. | Permissões de nível de edição:  - **Proprietário:** pode editar e enviar planos. Recebe notificações por e-mail quando os planos são aprovados ou devolvidos. - **Edit & Submit** - Pode editar e enviar planos. - **Editar** - Pode editar planos, mas não pode enviar. - **View Only (Somente visualização** ) - Pode visualizar planos, mas não pode editar ou enviar.  Permissão de nível de aprovação:  - Nível de aprovação: Defina um nível de aprovação (1-10) para definir a posição do usuário no fluxo de trabalho de aprovação. |

## Etapas de configuração

1. **Navegue até:** Perfil da empresa > **Fluxos de trabalho de aprovação**.
2. **Selecione o tipo de fluxo de trabalho:** Escolha **Aprovação hierárquica** ou **Aprovação multinível**.
3. **Opção de envio de grupo (somente hierárquico):** Você pode desativar o envio de grupo selecionando **Disable Group Cost Object Plan Submit**. A seleção dessa opção remove a capacidade dos Departamentos de Grupo de enviar em nível de grupo. Se precisar de um controle mais granular sobre os envios e as aprovações, considere usar o Multi-Level Approvals.
4. **Notificações por e-mail:** Para notificar os usuários sobre eventos importantes durante o processo de planejamento, selecione **Send Email Notifications for Planning Process Events (Enviar notificações por e-mail para eventos do processo de planejamento** ).
5. **Salvar e sair do** perfil da empresa.
6. **Atribuir aprovadores:** Navegue até Configuration > **Cost Object Permissions** e atribua usuários com base no tipo de fluxo de trabalho escolhido:
   - **Aprovação hierárquica:** Atribua aprovadores a cada departamento ou grupo de departamentos de acordo com sua estrutura organizacional. Defina Edit Level = Owner (Nível de edição = Proprietário) para usuários que podem aprovar ou rejeitar envios.
   - **Aprovação em vários níveis:** Atribua aos usuários um nível de edição para definir sua capacidade de visualizar, editar ou enviar planos, e um nível de aprovação ( L1–L10 ) para incluí-los na cadeia de aprovação.
