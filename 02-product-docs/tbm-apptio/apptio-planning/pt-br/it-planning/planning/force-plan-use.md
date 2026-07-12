---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Forçar um plano para usar dados de referência atualizados"
breadcrumb: []
source_path: "it-planning/planning/force-plan-use.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Forçar um plano para usar dados de referência atualizados

Quando um administrador ou proprietário do processo orçamentário atualiza as dimensões nos dados de referência, os planos existentes não são atualizados simultaneamente. Para obter informações sobre a atualização de dimensões, consulte [Dimensões de dados de referência](manage-reference-data.html "(Abre em uma nova guia ou janela)") e selecione o link da categoria de dimensão apropriada. Os planos são associados a um instantâneo de dados de referência. O administrador ou o proprietário do processo orçamentário pode visualizar a atualização específica dos dados de referência que foi feita e, em seguida, prosseguir com a atualização do plano para usar os dados de referência mais atuais.

Observação: É possível desativar as restrições de atualização de dados em um plano aberto. No entanto, essas atualizações acarretam o risco de perda de dados. Para obter mais informações, consulte [Atualizar dados de referência em um plano aberto](update-data-open-plan.htm "(Abre em uma nova guia ou janela)").

## Visualizar e atualizar dados de referência

1. Navegue até Planning > Plans e selecione o plano.
2. No canto superior direito da página, selecione Update Reference Data (Atualizar dados de referência ).
3. Revise os detalhes dos dados de referência. Se os dados estiverem atualizados, selecione Cancel (Cancelar ). Caso contrário, selecione Update (Atualizar ) para atualizar as novas informações.

## Visualizar e atualizar dados de referência para um plano aberto

Você pode atualizar os dados de referência de um plano no estado Novo ou Aberto. Um plano no estado Novo pode aplicar todas as atualizações de dados de referência. Um plano no estado Aberto pode aplicar as seguintes atualizações a partir de dados de referência:

- Criar objetos de custo de folha
- Criar dimensões personalizadas
- Adicionar ou modificar atributos de dimensão
- Adicionar valores a uma dimensão

Se o seu plano estiver no estado Aberto e precisar de atualizações adicionais, você poderá fazer isso com a seguinte solução alternativa. Observe que talvez você queira desativar as notificações no Company Profile para que, quando fizer alterações, os e-mails de notificação não sejam enviados aos proprietários do processo orçamentário. Consulte [Editar o perfil da empresa](edit-company-profile.htm "(Abre em uma nova guia ou janela)").

1. Arquive o plano, dando-lhe um novo nome (consulte [Arquivar, restaurar ou excluir planos](manage-plans.htm "(Abre em uma nova guia ou janela)") )
2. Crie um plano e nomeie-o com o nome do plano original (consulte [Criar um plano ou previsão](create-budget-plan.htm "(Abre em uma nova guia ou janela)") ). Os novos dados de referência são usados automaticamente no novo plano. Um lembrete: se você desativou as notificações, volte a ativá-las.
3. Abra o novo plano (consulte [Abrir um plano ou uma previsão](open-plan-forecast.htm "(Abre em uma nova guia ou janela)") ).

Atualmente, não é possível atualizar uma parte da referência em um plano. Ao selecionar a opção **Update Reference Data (Atualizar dados de referência)** no Plan (Plano), o administrador recebe detalhes sobre as dimensões que serão atualizadas, quantas linhas serão modificadas e excluídas se o usuário prosseguir com a aplicação das atualizações. O administrador pode então decidir prosseguir com a atualização dos dados de referência ou não.
