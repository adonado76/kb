---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Editar itens de linha de mão de obra"
breadcrumb: []
source_path: "it-planning/planning/create-labor-plan.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Editar itens de linha de mão de obra

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

Os detalhes de mão de obra planejada da equipe representam custos de mão de obra antecipados relacionados a novas contratações futuras ou compromissos internos ou externos e estão sujeitos a quaisquer regras de cálculo de custos de mão de obra que tenham sido definidas. Consulte [os dados de referência de Manage Labor Configuration](manage-labor-configuration.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor."). O gerenciamento dos detalhes de mão de obra da equipe planejada permite fazer o seguinte:

- Modelar e relatar os custos totalmente onerados da mão de obra planejada para todo o período de planejamento.
- Siga as regras aplicáveis de cálculo de custos de mão de obra para que os custos planejados de mão de obra sejam discriminados e projetados nos códigos corretos da conta do Razão durante todo o período de planejamento.

## Antes de começar

Antes de começar, certifique-se de ativar os recursos de planejamento de mão de obra. Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.").

## Inserir dados trabalhistas

Apptio recomenda que você atualize periodicamente os detalhes do seu parto planejado com novas informações. Trabalhe com detalhes de trabalho planejado na guia Trabalho, página Planejado. Depois que um recurso de mão de obra planejada começar a incorrer em custos, contabilize-o por meio do item de linha Mão de obra existente e remova-o dos itens Planejados. Consulte [Inserir ou importar dados de itens de linha](enter-import-line.html "Faça upload de dados em massa enviando um CSV para seu plano financeiro.").

1. Nos menus do plano no canto superior direito, selecione um plano, um tipo de objeto de custo e um objeto de custo ou grupo de objetos de custo.

   [Saiba mais sobre a navegação no Planejamento](navigate-apptio-planning.html "Este tópico fornece uma visão geral de como a navegação do Apptio Planning está organizada. Os itens de menu exibidos na sua conta dependem das suas permissões de usuário.")

   Observação: os proprietários de centros de custo só podem editar os centros de custo atribuídos a eles. Consulte [os dados de referência de Manage Cost Object Permissions (Gerenciar permissões de objetos de custo](manage-cost-object.html "As permissões de objetos de custo determinam quais usuários podem visualizar, editar, enviar ou aprovar planos em nível de departamento (objetos de custo). Cada departamento pode ter um ou mais usuários atribuídos com permissões de nível de edição e, para aprovações multinível, permissões de nível de aprovação.") ).
2. Navegue até Planning > Expenses (Despesas).
3. Selecione a guia Trabalho.
4. Selecione as subguias Planejado ou Existente.
5. Insira valores, importe um arquivo.csv (OBSERVAÇÃO : insira FALSE para o valor Is Existing Employee para indicar que um recurso é planejado e não atual) ou edite os detalhes do trabalho nas colunas a seguir:
   - Objeto de custo - Identificador exclusivo por objeto de custo, organizado em linhas correspondentes a cada tipo de objeto de custo (departamentos, serviços e projetos). Os próprios dados de referência do objeto de custo podem ser organizados em relacionamentos hierárquicos pai e filho entre departamentos e, se habilitados, serviços e projetos.
   - Alocações - Permite alocar mão de obra a um projeto, serviço ou pool de mão de obra (consulte [Alocar mão de obra do departamento](allocate-department-labor.html) ).
   - Tipo de funcionário - Determina se essa regra se aplica à equipe interna ou a recursos de trabalho externos, como fornecedores ou prestadores de serviços.
   - Função - Oferece opções disponíveis fornecidas pelos dados de referência das funções.
   - Localização - Oferece opções disponíveis fornecidas pelos dados de referência de Localização.
   - Fornecedor - Determina as opções disponíveis fornecidas pelos dados de referência do fornecedor.
   - Nome do funcionário - O nome de um recurso de trabalho específico, se conhecido, ou outro identificador exclusivo. Para várias pessoas, é possível rastrear de forma agregada e inserir um nome de equipe ou função, por exemplo, QA Team (Equipe de controle de qualidade).
   - Moeda - Visível somente quando várias moedas estão ativadas (consulte [Suporte para várias moedas](support-multiple-currencies.html)).
   - Remuneração base - O valor do salário base anual para esse recurso de mão de obra. Observe o seguinte:
     - Esse valor pode ser o salário bruto planejado de um indivíduo, o salário médio de uma equipe com várias pessoas ou algum outro valor.
     - Esse valor se torna a base para os cálculos das regras trabalhistas. Se estiver trabalhando com uma equipe de várias pessoas, o valor da Remuneração Base deve ser o valor médio por pessoa (não a soma da equipe). O valor médio por pessoa multiplicado pelo valor da quantidade resultará no valor de custo geral da equipe.
     - O valor da Remuneração base e o valor da Quantidade (1 para um único recurso) produzem os valores de remuneração mensal distribuídos por linha de mão de obra, que, por sua vez, produzem cumulativamente o valor total da remuneração base para o período de planejamento anual.
     - Na página Despesas, guia Resumo, os valores de remuneração mensal por linha de mão de obra são executados por meio de regras de cálculo de custos de mão de obra, alocados e cobrados nas contas corretas do Razão por mês aplicável (consulte [Gerenciar dados de referência de mão de obra](manage-labor-configuration.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") ). A soma das despesas resultantes de uma determinada linha de mão de obra OpEx representa a taxa de mão de obra onerada desse recurso de mão de obra.
   - Quantidade - Para uma alocação individual de recursos de mão de obra em tempo integral, insira 1. Para alocações fracionárias de um recurso em um centro de custo, insira um valor decimal (por exemplo, 0,5 para uma alocação de meio período). Para uma alocação de recursos de mão de obra que represente várias pessoas, insira a soma do efetivo planejado.
   - Datas de início e término - Essas datas determinam as alocações iniciais por mês do recurso de mão de obra no período de planejamento atual. Você pode inserir datas que precedem ou seguem o calendário fiscal ativo, mas somente as alocações dentro do calendário fiscal ativo são calculadas. O calendário fiscal é definido no perfil da empresa (consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.")). Para os meses dentro do calendário fiscal ativo, mas não dentro do intervalo de datas definido, o aplicativo Apptio Planning zerará as alocações de recursos.
   - Descrição - Insira uma descrição de texto para esse recurso de mão de obra. Esse é o mesmo valor de Descrição exibido na tabela OpEx Line Items.
   - Taxa de atividade de trabalho - Esse campo é aplicável se você estiver usando o módulo Planejamento de atividade de trabalho em Project Financial Planning (PFP). Em Configuração > Esquema e exportação.csv, o nome da coluna correspondente é Taxa de trabalho. O valor da taxa de mão de obra é definido automaticamente de acordo com os dados de referência da taxa de atividade de mão de obra do departamento. Caso o valor não esteja configurado nos dados de referência, esse campo aparecerá em branco. O valor nesse campo pode ser substituído pelo valor inserido pelo usuário. Esse valor indica a taxa de trabalho por hora cobrada pelo projeto quando o recurso correspondente é alocado ao projeto.
6. Adicione os ajustes de remuneração de mão de obra, conforme descrito [aqui](plan-labor-compensation.html "Os proprietários do processo orçamentário ou os usuários com permissões de proprietário de um objeto de custo podem contabilizar os ajustes planejados nas taxas de remuneração de mão de obra. Isso pode ser feito para mão de obra atual ou planejada. Você pode especificar uma alteração percentual na remuneração base por recurso de mão de obra e a data em que a alteração entrará em vigor.").

## Atribuições de mão de obra de contorno por mês

A linha do tempo mensal à direita da tabela de itens de linha de mão de obra mostra os registros mensais de alocações de recursos por linha de mão de obra. Na parte inferior, você vê os totais de funcionários de recursos de mão de obra por mês e, na coluna direita da tabela, os custos totais de mão de obra por linha de mão de obra e, no canto inferior direito, o total de custos de mão de obra.

As alocações iniciais de recursos por linha de mão de obra são calculadas pelo valor Quantidade por mês para cada mês dentro do intervalo Data de início e Data de término. Você pode editar ou contornar manualmente as alocações mensais de recursos.

Insira a alocação de recursos por item de linha do razão geral por mês do calendário desejado. Ao fazer isso, o custo total do recurso para o item de linha selecionado e o registro por mês serão atualizados.

Dica:

- Como em outras exibições de itens de linha, você pode adicionar ou remover colunas. Coloque o cursor do mouse no título da coluna, clique no botão de seta que aparece e selecione uma opção.
- Para adicionar novos itens de linha, coloque o cursor do mouse na coluna mais à esquerda de uma linha, clique no botão de seta que aparece e selecione uma opção.

## Visualizar custos de projetos delegados

Se o site Project Financial Planning Project Financial Planningestiver ativado, os proprietários do projeto poderão delegar os custos do projeto aos proprietários de departamentos e serviços. Todos esses proprietários podem exibir ou ocultar os custos delegados em seus relatórios financeiros. Consulte [Delegar custos do projeto](pfp/delegate-project-costs.html).

## Visualizar a demanda por mão de obra

Se Project Financial Planning ou Service Demand Planning estiver ativado, você poderá disponibilizar mão de obra para o trabalho de projeto ou serviço por meio de pools e alocações de recursos de mão de obra. Os proprietários de departamentos podem alocar para um projeto, serviço ou pool de mão de obra. Essas alocações departamentais também aparecem nas tabelas de alocação de mão de obra de seus projetos e serviços. Consulte [Alocar mão de obra do departamento](allocate-department-labor.html).

## Visualizar Custo de mão de obra totalmente onerado

Os responsáveis pelo orçamento agora podem visualizar facilmente o custo total da mão de obra diretamente nas colunas Expenses > Labor > FY total, eliminando a necessidade de navegar até a seção Expenses > Summary para obter essas informações. Anteriormente, essa coluna exibia apenas a Remuneração base x Quantidade.

Por exemplo, na guia Trabalho, você pode ver uma linha de trabalho com um FY24 total de US$ 196.888. Esse valor representa o custo de mão de obra totalmente onerado, calculado com base nas regras de alocação de mão de obra configuradas.

![img](../../resources/images/it%20planning_images/3.71-1.png)

O custo de mão de obra totalmente onerado é a soma das contas do razão geral geradas a partir das Regras de alocação de mão de obra na guia Resumo. Como mostrado, o total de FY24 na guia Resumo corresponde ao total de FY24 na guia Trabalho.

![img](../../resources/images/it%20planning_images/3.71-2.png)
