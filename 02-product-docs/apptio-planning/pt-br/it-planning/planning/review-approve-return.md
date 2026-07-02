---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Revisar, aprovar ou devolver planos ou objetos de custo"
breadcrumb: []
source_path: "it-planning/planning/review-approve-return.html"
images:
  - "resources/planning_images/itp_diagram_department-hierarchy.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Revisar, aprovar ou devolver planos ou objetos de custo

Assista a este vídeo do site Apptio Education Services: [Verificação de status, aprovação ou devolução de planos](https://community.apptio.com/videos/1616 "(Abre em uma nova guia ou janela)")

Quando os proprietários de departamentos, proprietários de unidades de negócios e (se habilitados) proprietários de projetos ou proprietários de serviços enviam seus planos ou previsões para seus respectivos objetos de custo, os planos enviados ficam imediatamente visíveis nas páginas Todas as seções do plano. Consulte [Editar o perfil da empresa](edit-company-profile.html) e [Enviar um plano ou previsão](submit-plan-forecast.html "Depois de inserir as informações do plano ou da previsão, você pode enviá-las para aprovação. O proprietário do orçamento pode enviar seu plano a partir da página Status ou Despesas.") para obter mais informações. Os proprietários podem, então, revisar o plano do centro de custo e aprová-lo ou devolvê-lo ao proprietário do orçamento para que ele trabalhe mais.

## Processo de aprovação

A dimensão Permissões de objetos de custo determina quem pode executar ações com objetos de custo. Para obter mais informações, consulte [os dados de referência de Manage Cost Object Permissions](manage-cost-object.html). Os níveis de edição das permissões de objetos de custo incluem o seguinte:

| Nível de edição | Visualização | Editar | Enviar | Aprovar | Rejeitar |
| --- | --- | --- | --- | --- | --- |
| Proprietário | Sim | Sim | Sim | Sim, se o proprietário estiver em um objeto de custo de grupo | Sim, se o proprietário estiver em um objeto de custo de grupo |
| Editar e enviar | Sim | Sim | Sim | Não | Não |
| Somente visualizar | Sim | Não | Não | Não | Não |

Se as permissões forem concedidas em um nível de objeto de custo de grupo, todas as permissões se aplicarão a todos os objetos de custo filhos.

Observação: As funções Administrador e Proprietário do processo orçamentário têm o nível de edição "Proprietário" no nível mais alto da hierarquia, mesmo que não estejam listadas na hierarquia Permissões de objeto de custo. Os usuários devem ter pelo menos a função Proprietário do centro de custo para ter os níveis de edição Proprietário ou Editar e enviar.

Exemplo

Se a hierarquia do seu departamento incluir vários níveis, talvez você queira nivelar o fluxo de trabalho de aprovação. Você pode configurar a hierarquia de aprovação para ignorar determinados níveis, de modo que os departamentos dentro do nó que você ignora sejam transferidos para o proprietário do próximo nível. Na imagem a seguir, o Grupo E, o Grupo F e o Grupo H são nós de "salto". Os departamentos dentro desses grupos seriam aprovados pelo proprietário do próximo nível: o plano para o Departamento D e o Departamento E seria aprovado pelo proprietário do Grupo B.

![img](../../../../../03-media/apptio-planning/resources/planning_images/itp_diagram_department-hierarchy.png)

## Visualizar e gerenciar planos enviados

Os proprietários de centros de custo podem aprovar ou rejeitar planos a qualquer momento. Se vários usuários forem atribuídos como proprietários, apenas um usuário precisará aprovar os planos. Se um proprietário de nível superior aprovar um plano, os níveis inferiores serão aprovados automaticamente.

1. Nos menus do plano no canto superior direito, selecione um plano, um tipo de objeto de custo e um objeto de custo ou grupo de objetos de custo.

   [Saiba mais sobre a navegação no Planejamento](navigate-apptio-planning.html)
2. Navegue até Planning > Status. Selecione Include View-Only Cost Objects (Incluir objetos de custo somente para visualização) para incluir objetos de custo com permissões somente para visualização.

   Observação: A opção Enforce View Permissions (Aplicar permissões de visualização) deve estar ativada. Consulte [Editar o perfil da empresa](edit-company-profile.html).

   Na visualização Status, os usuários podem enviar, aprovar e devolver os objetos de custo. Há duas maneiras de realizar essas ações:
   - Coluna Ações - Na visualização Status, na coluna Ações, em uma linha de um objeto de custo ou de um objeto de custo de grupo, selecione Aprovar, Devolver ou Enviar.

     Essas ações podem ser executadas no nível do objeto de custo folha e no nível do objeto de custo do grupo. Quando uma ação é executada no nível do objeto de custo do grupo, tanto o objeto de custo folha quanto o objeto de custo do grupo são atualizados.

     [Leia mais sobre como determinadas ações afetam os objetos de custo de folha e de grupo](#ReviewapproveorreturnplansorCostObjects__ApprovalHierarchyActions)
   - Ações em massa - Na exibição Status, na primeira coluna, selecione os objetos de custo usando as caixas de seleção. No menu suspenso Ações acima da tabela, selecione Aprovar selecionados, Retornar selecionados ou Enviar selecionados para executar uma ação em massa nos objetos de custo selecionados.

     Os objetos de custo em nível de grupo não são afetados pelas ações em massa.
   - Para enviar planos ao proprietário do orçamento ou ao proprietário do centro de custos, selecione os itens, selecione Ações e selecione Enviar selecionados. Você também pode selecionar Enviar na linha para cada item individual.
   - Para aprovar planos, selecione os itens, selecione Ações e selecione Aprovar selecionados.
   - Para solicitar que o proprietário do orçamento ou o proprietário do centro de custos modifique um plano ou planos enviados, selecione os itens, selecione Ações e selecione Retornar selecionados.

Quando todos os orçamentos forem enviados, selecione Finalize Plan (Finalizar plano ).

Nota:

- Se vários usuários compartilharem o mesmo nível de aprovação, apenas um precisará aprovar os planos.
- Se um proprietário de nível superior aprovar um plano, os níveis inferiores serão automaticamente aprovados.

## Ações de hierarquia de aprovação

Observação: O envio no nível do grupo resultará na aprovação automática de todos os objetos de custo filhos, mesmo que o remetente não tenha permissão explícita de aprovação.

A tabela a seguir descreve as Ações e o comportamento resultante no Status para objetos de custo:

| Ação | Comportamento no objeto de custo da folha | Comportamento no objeto de custo do grupo |
| --- | --- | --- |
| Enviar | Marca o objeto de custo como "Enviado"  Cria um novo instantâneo não editável do objeto de custo enviado  Impede que as linhas atuais do objeto de custo sejam editadas | Marca todos os objetos de custo folha filho como "Aprovado"  Cria um novo instantâneo não editável de todos os objetos de custo de lâmina filha  Qualquer objeto de custo folha filho que já esteja em status aprovado não será afetado |
| Aprovar | Marca o objeto de custo como "Aprovado" Observação: somente os objetos de custo de folha no status "Submitted" terão essa opção | Marca o objeto de custo do grupo como "Aprovado" Marca qualquer objeto de custo de lâmina filha no status "Submitted" (Enviado) como "Approved" (Aprovado) |
| Rejeitar | Marca o objeto de custo como "Rejeitado" ou "Devolvido" Observação: somente os objetos de custo de folha com status "Submitted" ou "Approved" terão essa opção | Marca o objeto de custo do grupo como "Rejeitado" ou "Devolvido"  Qualquer objeto de custo de folha secundária com status "Submitted" ou "Approved" não será afetado, a menos que o proprietário do objeto de custo decida o contrário. |

## Capturas instantâneas

Um instantâneo é uma cópia não editável de um item de linha em um plano aberto. Os usuários podem comparar um plano com um instantâneo.

Um instantâneo é tirado automaticamente quando ocorre uma das seguintes situações:

- Um plano é enviado.
- O status de um plano muda de Novo para Aberto.

Você pode usar snapshots ao comparar planos.

Ver [Comparar versões ou planos](compare-versions-plans.html)

Quando um instantâneo está sendo tirado no nível do objeto de custo, esse objeto de custo não pode ser editado.

## Tirar um instantâneo manualmente

1. Abra o painel de navegação à esquerda e selecione Planning > Plans.
2. Na lista Planos, selecione um plano.
3. No canto superior direito, no menu de seção, selecione um tipo de objeto de custo.

   ![img](../../resources/images/it%20planning_images/cost-object-category.png)
4. No canto superior direito, no menu da subseção, selecione um objeto de custo.

   ![img](../../resources/images/it%20planning_images/cost_object_sub-section.png)
5. Selecione uma exibição de tabela de itens de linha.

   ![img](../../resources/images/it%20planning_images/line-item_table_view.png)
6. No menu suspenso do instantâneo, selecione Save Snapshot (Salvar instantâneo).

   ![img](../../resources/images/it%20planning_images/snapshot_save.png)
7. Digite o nome do snapshot.
8. Selecione Criar.

## Acessar instantâneos

1. Abra o painel de navegação à esquerda e selecione Planning > Plans.
2. Na lista Planos, selecione um plano.
3. No canto superior direito, no menu de seção, selecione um tipo de objeto de custo.

   ![img](../../resources/images/it%20planning_images/cost-object-category.png)
4. No canto superior direito, no menu da subseção, selecione um objeto de custo.

   ![img](../../resources/images/it%20planning_images/cost_object_sub-section.png)
5. Selecione a lista suspensa de instantâneos.

   ![img](../../resources/images/it%20planning_images/snapshot_dropdown.png)
