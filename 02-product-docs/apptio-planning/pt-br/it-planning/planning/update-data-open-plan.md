---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Atualizar dados de referência em um plano aberto"
breadcrumb: []
source_path: "it-planning/planning/update-data-open-plan.html"
images:
  - "resources/images/icons/3-dots.jpg"
  - "resources/images/it_planning_images/icon_gear.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Atualizar dados de referência em um plano aberto

Quando um plano é criado, ele herda as versões publicadas dos dados de referência atualmente carregados no módulo **Reference Data**. Se forem feitas alterações subsequentes nos dados de referência, os dados do plano precisarão ser atualizados. Como os dados de referência são usados para estruturar dados planejados e para marcar partidas individuais com atributos relatáveis, certas alterações nos dados de referência podem causar perda de dados. Por exemplo, a exclusão de um objeto de custo excluirá todas as partidas individuais planejadas associadas a esse objeto de custo. A exclusão de uma conta fará com que todos os itens de linha marcados nessa conta se tornem inválidos e, portanto, excluídos. Outras alterações, como a exclusão de um fornecedor, não farão com que as partidas individuais planejadas sejam excluídas, mas podem resultar na perda de fidelidade do relatório, pois as partidas individuais anteriormente marcadas com o fornecedor excluído agora serão marcadas com um fornecedor em branco.

## Sobre esta tarefa

É possível atualizar os dados de referência do plano, desde que as alterações não sejam destrutivas. Se a atualização apenas adicionar ou modificar elementos de dados de referência existentes, ela será permitida por padrão. No entanto, as atualizações dos dados de referência do plano que podem causar perda nos dados do plano geralmente não são permitidas. No entanto, os administradores podem desativar essa restrição em **Configurações**. Para obter mais informações, consulte [Remover restrições de atualização](update-data-open-plan.html#Remove). Mais detalhes podem ser encontrados em [Editar o perfil da empresa](edit-company-profile.html).

Um plano de backup é criado automaticamente para preservar a integridade dos dados sempre que você fizer uma atualização potencialmente destrutiva.

Quando a restrição for removida, as seguintes atualizações se tornarão possíveis:

- Você pode excluir itens (como objetos de custo ou contas).
- Você pode reorganizar sua estrutura de dados (por exemplo, pode atribuir um objeto de custo a um pai diferente).

Esses recursos permitem que você continue a usar seu plano atual se sua empresa passar por uma reorganização.

Primeiro, determine se é necessário remover essas restrições para fazer atualizações em seu plano. Se suas atualizações não resultarem em perda de dados, pule para [Update an open plan (Atualizar um plano aberto](update-data-open-plan.html#Update) ).

## Procedimento

- **Remover restrições de atualização**
  1. No menu Apptio Planning , clique no botão Settings (![ícone de engrenagem](../../../../../03-media/apptio-planning/resources/images/it_planning_images/icon_gear.jpg)) e, em seguida, clique em Company Profile.

     A página Company Profile é aberta.
  2. Na seção Settings (Configurações ), selecione Disable Update Reference Data Restrictions (Desativar restrições de atualização de dados de referência ).
  3. Selecione Salvar e sair.

     As restrições agora estão desativadas.
- **Atualizar um plano aberto**

  Depois de fazer as alterações nos dados de referência, você pode habilitar um plano aberto atualmente para que ele esteja em conformidade com essas alterações. Para obter mais informações sobre a atualização de dados de referência, consulte [Editar e publicar tabelas de dados de referência](edit-publish-reference.html).

  1. Navegue até Planning>Plans e selecione um plano.
  2. No [Menu de subseção do plano](navigate-apptio-planning.html#Plan_Sub-section_Menu) (após selecionar Departamentos no menu suspenso Seção ), selecione Todos os departamentos (no menu suspenso Departamento ).
  3. Selecione ![menu "three dots more](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.jpg) e, em seguida, selecione Update Reference Data (Atualizar dados de referência ).

     É exibida uma caixa de diálogo com informações sobre suas alterações, incluindo exclusões de itens de linha.
  4. Revise suas alterações e selecione Update (Atualizar ).

     Quando você faz a atualização, um plano de backup é criado automaticamente para espelhar seu plano antes das atualizações.
- **Sobre planos de backup**

  Observação: O histórico do plano não é capturado em um plano de backup.

  Se você tiver desativado as restrições de atualização dos dados de referência, um plano de backup será criado automaticamente sempre que você atualizar os dados de referência em um plano aberto. O plano de backup contém todos os dados do plano antes da atualização, com a notável exceção do histórico do plano. Além disso, se você fizer alterações subsequentes no mesmo plano, o plano de backup será sobrescrito a cada alteração. Em qualquer momento, você tem basicamente um backup que preserva seus dados (e os dados de referência de suporte) antes da atualização mais recente

## Informações relacionadas

- [update-data-open-plan.html #Atualizar dados referenciados em um plano aberto](update-data-open-plan.html#Updatereferencedatainanopenplan)
- [update-data-open-plan.html #Removeupdaterestrictions](update-data-open-plan.html#Removeupdaterestrictions)
- [update-data-open-plan.html #Updateanopenplan](update-data-open-plan.html#Updateanopenplan)
- [update-data-open-plan.html #Aboutbackupplans](update-data-open-plan.html#Aboutbackupplans)
