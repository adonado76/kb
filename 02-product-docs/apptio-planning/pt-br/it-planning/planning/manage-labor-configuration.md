---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configurar mão de obra"
breadcrumb: []
source_path: "it-planning/planning/manage-labor-configuration.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar mão de obra

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

As dimensões são as categorias de dados essenciais nos itens de linha do orçamento. Muitas dimensões incorporadas têm dependências de outras dimensões (consulte [Dependências de atributos e dimensões de dados de referência](manage-reference-data.html) para obter mais informações). Você pode importar dados de referência de dimensões de um arquivo.csv ou do site Costing Standard e exportar modelos de dados de referência de dimensões e dados de tabela (consulte [Gerenciar dimensões](manage-reference-data.html) ).

![imagem](../../resources/images/it%20planning_images/icon_video.png)

Assista a este vídeo do site Apptio Education Services: [Configuração de dados de referência: Dimensões do trabalho](https://community.ibm.com/community/user/viewdocument/configuring-reference-data-labor-d?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Abre em uma nova guia ou janela)").

## Gerenciar pools de mão de obra externos ou internos em dados de referência

◆ Aplica-se a: aplicativos Apptio Planning com Project Financial Planning (consulte [Introdução ao módulo Project Financial Planning](pfp/gs-project-financial.html "◆ Aplica-se a: Planejamento com planejamento financeiro de projetos.")  ) ou Service Demand Planning (consulte [Introdução ao módulo Service Demand Planning](sdp/gs-service-demand.html)  )

As tarefas desta seção exigem que você licencie Project Financial Planning ou Service Demand Planning e, em seguida, edite o Company Profile para ativar Project Financial Planning ou Service Demand Planning. Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.").

Defina pools de mão de obra externa para capturar o custo de mão de obra externa direta para seu projeto ou serviço. Observe que, antes de configurar pools de mão de obra externa, primeiro atualize as dimensões do seu departamento.

1. No perfil da empresa, ative o planejamento de mão de obra e, se licenciado, Project Financial Planning ou Service Demand Planning (consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.") ).
2. No menu de navegação esquerdo, selecione Configuração > Dados de referência > Pool de mão de obra externa ou Pool de mão de obra interna.
3. Selecione ![imagem](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) no canto superior direito da tabela, selecione Exportar > Exportar tudo.
4. Abra o arquivo.csv baixado e atualize os valores dos dados conforme necessário:
   - Código (obrigatório) - O identificador exclusivo abreviado do pool de mão de obra.
   - Nome (obrigatório) - O nome do pool de mão de obra.
   - Código do departamento (somente pool de trabalho interno) - O departamento associado ao pool de trabalho interno.
   - Categoria - Use essa coluna para expandir o tipo de pool de mão de obra. Exemplos de categorias incluem desenvolvimento, garantia de qualidade e gerenciamento de projetos.
   - Taxa - A taxa horária de um indivíduo no pool de mão de obra.
   - Fornecedor (somente pool de mão de obra externo) - O fornecedor associado ao pool de mão de obra.
   - Pool padrão (somente pool de mão de obra interna) - O pool de mão de obra a ser usado para alocações diretas por departamento. Só é possível selecionar um pool de mão de obra por departamento.
   - Código da moeda - A moeda comum para o pool de trabalho. Necessário quando o suporte a várias moedas estiver ativado no perfil da empresa. O valor da moeda comum do departamento deve ser o código ISO de três letras para a moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
5. Agora, Configuration > External Labor Pool ou Internal Labor Pool e, em seguida, importe o arquivo.csv atualizado.

## Gerenciar dados de referência de taxas de trabalho

Um proprietário ou administrador do processo orçamentário pode definir taxas de mão de obra para recursos de mão de obra internos e externos. Essas taxas de mão de obra podem ser vinculadas às dimensões Função, Local e Fornecedor.

As taxas de mão de obra fornecem os valores padrão do cartão de mão de obra, como a remuneração anual por função de mão de obra. Esses valores padrão são aplicados a trabalhadores específicos e podem ser personalizados diretamente por trabalhador. Consulte [Criar um plano de trabalho](create-labor-plan.html). As taxas de mão de obra para recursos de mão de obra interna provavelmente virão de seu sistema de recursos humanos. Para recursos de mão de obra externa, como fornecedores, o fornecedor deve fornecer os dados do cartão de mão de obra com base na função em um formato que você possa usar.

1. Habilite os recursos de planejamento de mão de obra (consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.") ).
2. No menu de navegação esquerdo, selecione Configuração > Dados de referência > Taxas de trabalho.
3. Selecione ![imagem](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) no canto superior direito da tabela, selecione Exportar > Exportar tudo.
4. Abra o arquivo.csv baixado e atualize os valores dos dados conforme necessário:
   - Tipo de funcionário - Determina se essa regra se aplica a recursos de trabalho internos ou externos (como fornecedores ou prestadores de serviços).
   - Função - As opções disponíveis para essa dimensão são fornecidas pelos dados de referência das funções.
   - Localização - As opções disponíveis para essa dimensão são fornecidas pelos dados de referência de Localização.
   - Fornecedor - As opções disponíveis para essa dimensão são fornecidas pelos dados de referência do fornecedor.
   - Código da moeda - A moeda comum para a alocação de mão de obra. Necessário quando o suporte a várias moedas estiver ativado. O valor da moeda comum do departamento deve ser o código ISO de três letras para a moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
   - Taxa básica - A taxa padrão de remuneração do trabalho.
5. Agora, Configuration > Reference Data > Labor Rates e, em seguida, selecione ![imagem](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) no canto superior direito da tabela. Agora, selecione Importar e importe o arquivo.csv atualizado.
6. Selecione ![imagem](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) e selecione Publicar para tornar as taxas de mão de obra disponíveis no planejamento e na gestão de despesas. Depois de publicar as taxas de mão de obra, você pode contabilizar os ajustes planejados para essas taxas para recursos de mão de obra específicos (consulte [Gerenciar dimensões personalizadas](manage-custom-reference.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") ).

## Gerenciar dados de referência de funções

As funções são títulos descritivos a serem aplicados aos recursos de trabalho. Os valores de função que você atribui aos recursos de mão de obra são os principais valores de pesquisa nas tabelas de taxas de mão de obra.

1. Habilite os recursos de planejamento de mão de obra (consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.") ).
2. No menu de navegação esquerdo, selecione Configuração > Dados de referência > Função.
3. A tabela de dados de referência da função inclui o nome da função do recurso. Não é possível editar diretamente os valores na tabela Roles. Em vez disso, selecione ![imagem](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) no canto superior direito da tabela, selecione Exportar > Exportar tudo. Abra o arquivo.csv baixado e atualize os dados das funções, e carregue e publique o arquivo.csv conforme necessário.

- **[Regras de alocação de mão de obra](../../it-planning/planning/manage-labor-allocation-rules.html)**  
   As tarefas abaixo só podem ser executadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.
- **[Calendários de trabalho](../../it-planning/planning/configure-working-days.html)**
- **[Summarize Labor Financials (Resumir finanças trabalhistas](../../it-planning/planning/labor-summarization.html)** )  
   Os usuários administradores podem especificar como desejam que os itens de linha das finanças trabalhistas sejam resumidos na guia Summary (Resumo). Em outras palavras, um usuário administrador pode especificar quais colunas de dados da guia Trabalho serão exibidas na guia Resumo.
- **[Ajustes de remuneração de mão de](../../it-planning/planning/plan-labor-compensation.html)** obra  
   Processo orçamentário Os proprietários ou usuários com permissões de proprietário de um objeto de custo podem contabilizar os ajustes planejados nas taxas de remuneração de mão de obra. Isso pode ser feito para mão de obra atual ou planejada. Você pode especificar uma alteração percentual na remuneração base por recurso de mão de obra e a data em que a alteração entrará em vigor.
