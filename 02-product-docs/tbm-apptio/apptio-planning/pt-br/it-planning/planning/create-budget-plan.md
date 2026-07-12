---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Criar um plano ou previsão orçamentária"
breadcrumb: []
source_path: "it-planning/planning/create-budget-plan.html"
images:
  - "resources/images/icons/icon-settings_20x20.png"
  - "resources/images/it_planning_images/async-plan-create-1.jpg"
  - "resources/images/it_planning_images/async-plan-create-2.jpg"
  - "resources/images/it_planning_images/new-plan-icon.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Criar um plano ou previsão orçamentária

## Sobre esta tarefa

Assista a este vídeo do site Apptio Education Services: [Criação e abertura de planos](https://community.ibm.com/community/user/viewdocument/creating-and-opening-plans-9-min "(Abre em uma nova guia ou janela)").

## Criar um plano orçamentário

O proprietário do processo orçamentário cria um novo plano orçamentário no início do ciclo de planejamento.

1. Selecione Planning > Plans > ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/new-plan-icon.jpg).
2. Em Plan Type (Tipo de plano ), selecione Budget (Orçamento ).
3. Digite o seguinte:

   | Item | Descrição |
   | --- | --- |
   | Ano de início do plano | Selecione o ano para o novo orçamento (normalmente, o ano fiscal). A definição é determinada pela configuração de seu calendário fiscal.  Para obter mais informações, consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning."). |
   | Duração do plano (anos) | Selecione a duração do plano.  Para obter mais informações, consulte [Planejar para vários anos](plan-multiple-years.html "Use os recursos de planejamento plurianual para planejar e acompanhar as finanças de TI em um horizonte de tempo contínuo e plurianual. Você pode dar suporte a planos de longo prazo e previsões contínuas para além dos limites do ano fiscal."). |
   | Referência de linha de base | Para incluir dados de linha de base em seu orçamento, selecione um plano de orçamento existente ou uma previsão anterior. Isso permite que você faça uma linha de base de dados de diferentes exercícios fiscais ou planeje para vários anos.  A criação de um plano a partir da linha de base deve ter o seguinte comportamento para diferentes tipos de dados: - Other Financials, Labor Demand, Labor Allocations - copie valores periódicos com base na data real do calendário, por exemplo, janeiro FY18. - Expenses > Labor - para períodos com valores diferentes de nulo, ele se comporta da mesma forma que Other Financials. Os períodos com valores nulos são preenchidos usando os campos Data de início, Data de término e Quantidade. - Contratos, ativos - geram todos os valores periódicos a partir de metadados. - Contratos (Amortização manual), Ativos (Depreciação manual) - comporta-se da mesma forma que Outros recursos financeiros.  Códigos de itens de linha de cópia  Se você selecionar essa opção, poderá optar por copiar os códigos de itens de linha da linha de base ou gerar novos códigos de itens de linha para os itens de linha copiados.  [Saiba mais sobre os códigos de itens de linha](line-item-codes.html)  Dados do plano de preenchimento automático  Essa opção será exibida se o plano de linha de base não contiver as mesmas datas fiscais que o plano recém-criado. O recurso Auto Fill Plan Data (Preenchimento automático de dados do plano) preenche os valores do período no novo plano que estaria vazio com o mesmo valor para aquele mês no último ano do plano de linha de base. Por exemplo, FY21 de fevereiro é copiado para FY22 e FY22 de fevereiro.  - O recurso Auto Fill Plan Data não funciona para Expenses > Labor. - Se o novo plano começar em um ano fiscal anterior ao plano de linha de base, os anos anteriores terão os campos Other Financials (Outras finanças) e Labor Demand (Demanda de mão de obra) em branco. Se você ativou Integrated Investment Planning  Os Grupos de Projetos não são trazidos para um novo plano, mas usam os últimos dados de referência publicados. Os grupos de projetos em um plano de linha de base que não estão nos últimos dados de referência de grupos de projetos publicados não são transferidos para o novo plano. |
   | Nome do plano | Digite o nome exclusivo do orçamento.  Para ajudar a distinguir os planos orçamentários das previsões em sua lista de planos, indique o tipo de plano no nome. |
4. Selecione Criar plano.

Quando a criação do plano é iniciada após o envio do formulário Create Plan (Criar plano), uma nova entrada é criada na página Plans (Planos ) com o novo nome do plano e o status é marcado como Pending (Pendente ).

Observação: Se o status de criação do plano for Pending (Pendente ), o plano não poderá ser selecionado na página de planos nem no seletor de planos de outras páginas.

![imagem](../../../../../03-media/apptio-planning/resources/images/it_planning_images/async-plan-create-1.jpg)

Quando a criação do plano estiver concluída, será exibida a caixa de diálogo de brinde indicando a conclusão da criação do plano. O plano agora pode ser selecionado na página de planos, bem como no seletor de planos em outras páginas.

![imagem](../../../../../03-media/apptio-planning/resources/images/it_planning_images/async-plan-create-2.jpg)

Assim, a criação do plano agora é um processo assíncrono.

A criação de planos, especialmente usando o plano de linha de base, pode levar vários minutos se houver uma grande quantidade de dados a serem copiados do plano de linha de base para o novo plano. O processo síncrono de criação de planos impede que o usuário realize outras tarefas enquanto o plano está sendo criado. Esse tempo pode ser efetivamente utilizado pelo administrador para realizar outras tarefas no aplicativo de planejamento até que a criação do plano seja concluída.

A partir de 4 de março de 2024 e da versão 3.64, esse recurso estará disponível em todos os ambientes principais. O processo de criação de planos agora é assíncrono. Você pode iniciar o processo de criação do plano, que continuará sendo executado em segundo plano, permitindo que o usuário realize outras tarefas.

Se Integrated Investment Planning estiver ativado, os projetos serão copiados para o novo plano com um dos seguintes métodos. Para saber mais sobre o Integrated Investment Planning, consulte [Introdução ao Integrated Investment Planning](iip/gs-integrated-investment-planning.html).

- Criar plano sem plano de linha de base - Se você estiver criando um plano sem um plano de linha de base, os projetos da dimensão de dados de referência "Projeto" serão adicionados ao plano.
- Criar plano com plano de linha de base - Se você estiver criando um plano com um plano de linha de base, os projetos do plano de linha de base serão adicionados ao novo plano.

Depois de criar um plano orçamentário, faça o seguinte:

1. Ajuste os valores da linha de base (opcional).

   Para obter mais informações, consulte [Inserir detalhes financeiros e ajustar valores de linha de base](enter-financial-details.html)
2. [Definir metas financeiras](set-financial-targets.html)
3. Abra o plano para que os proprietários do orçamento possam editar os itens de linha.

Para obter mais informações, consulte [Abrir um plano ou uma previsão.](open-plan-forecast.html "Após criar um plano ou previsão orçamentária, opcionalmente ajuste os valores de linha de base, defina as metas e abra o plano para que os proprietários do orçamento possam editar os itens de linha. Os proprietários de orçamento não podem ver um plano quando ele está no estado Novo. Quando você abre um plano, uma notificação por e-mail é enviada aos proprietários do orçamento e a todos os usuários que têm a permissão Edit & Submit associada aos objetos de custo desse plano.")

Os proprietários de orçamento não podem ver um plano quando ele está no estado Novo. Quando você abre um plano, uma notificação por e-mail é enviada aos proprietários do orçamento e a todos os usuários que têm a permissão Edit & Submit associada aos objetos de custo desse plano. Consulte [os dados de referência de Manage Cost Object Permissions (Gerenciar permissões de objetos de custo](manage-cost-object.html "As permissões de objetos de custo determinam quais usuários podem visualizar, editar, enviar ou aprovar planos em nível de departamento (objetos de custo). Cada departamento pode ter um ou mais usuários atribuídos com permissões de nível de edição e, para aprovações multinível, permissões de nível de aprovação.") ).

## Criar uma previsão

Antes de criar uma previsão, verifique as dimensões e os atributos reais que você deseja incluir na previsão.

Para verificar as dimensões e os atributos de sua empresa:

1. Selecione ![img](../../../../../03-media/apptio-planning/resources/images/icons/icon-settings_20x20.png) > Company Profile (Perfil da empresa).
2. Você pode encontrar as dimensões e os atributos em Habilitar recursos > Resumir dados financeiros reais até as seguintes dimensões e/ou atributos.

Para criar uma previsão:

1. Selecione Planning > Plans > ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/new-plan-icon.jpg).
2. Em Plan Type (Tipo de plano ), selecione Forecast (Previsão ).
3. Digite o seguinte:

   | Item | Descrição |
   | --- | --- |
   | Ano de início do plano | Selecione o ano para a nova previsão (normalmente o ano fiscal). A definição é determinada pela configuração de seu calendário fiscal.  Para obter mais informações, consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning."). |
   | Duração do plano (anos) | Selecione a duração do plano. |
   | Período inicial da previsão | Selecione o mês para a nova previsão. |
   | Referência de linha de base | se quiser incluir dados de linha de base em sua previsão, em Linha de base, selecione um plano orçamentário existente ou uma previsão anterior. |
   | Nome do plano | insira um nome exclusivo para a previsão. |

   A caixa de diálogo New Plan é aberta.
4. Selecione Criar plano.

Observação: Os dados reais serão extraídos do Gerenciamento de despesas para o plano de previsão com base em cada período. Os valores reais só aparecerão na visualização Despesa > Resumo. Para obter mais informações, consulte [Abrir e visualizar os dados reais](import-publish-actuals.html).Project Financial Planning -Integrated Investment Planning: Os dados reais só serão exibidos em todas as seções do plano se um projeto for aprovado. Os projetos no status Proposto não terão os valores reais inseridos em Todas as seções do plano.

Depois de criar um plano de previsão, faça o seguinte:

1. Ajuste os valores da linha de base (opcional).

   Para obter mais informações, consulte [Inserir detalhes financeiros e ajustar valores de linha de base](enter-financial-details.html).
2. [Definir metas financeiras](set-financial-targets.html)
3. Abra a previsão para que os proprietários do centro de custo possam editar os itens de linha.

Para obter mais informações, consulte [Abrir um plano ou uma previsão.](open-plan-forecast.html "Após criar um plano ou previsão orçamentária, opcionalmente ajuste os valores de linha de base, defina as metas e abra o plano para que os proprietários do orçamento possam editar os itens de linha. Os proprietários de orçamento não podem ver um plano quando ele está no estado Novo. Quando você abre um plano, uma notificação por e-mail é enviada aos proprietários do orçamento e a todos os usuários que têm a permissão Edit & Submit associada aos objetos de custo desse plano.")
