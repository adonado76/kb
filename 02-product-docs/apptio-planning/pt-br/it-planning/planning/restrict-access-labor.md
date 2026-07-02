---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Restringir o acesso aos detalhes do salário dos funcionários"
breadcrumb:
  - "Planning"
  - "Planejamento trabalhista"
source_path: "it-planning/planning/restrict-access-labor.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Restringir o acesso aos detalhes do salário dos funcionários

As tarefas abaixo só podem ser executadas por usuários atribuídos à função Admin. Consulte Permissões e funções do Frontdoor.

Sua organização pode querer proteger informações confidenciais, como taxas de remuneração. Você pode impedir que os usuários visualizem a guia Trabalho (incluindo os detalhes do salário do trabalho) atribuindo uma função personalizada que desabilite a ViewLabor permissão.

## Crie uma função personalizada que restrinja o acesso à guia Trabalho

Crie funções personalizadas para fornecer permissões exclusivas. Por exemplo, nos aplicativos Apptio Planning , todas as funções integradas permitem acesso aos detalhes do salário de mão de obra (se houver) na guia Mão de obra da visualização Itens de linha. Um administrador pode criar uma função personalizada que bloqueie o acesso à guia Labor e, em seguida, atribuir determinados usuários a essa função usando as instruções a seguir:

1. Habilite os recursos de planejamento de mão de obra. Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.").
2. No menu Apptio Planning , clique no botão Settings (Configurações ) (![ícone de configurações](../../resources/images/it%20planning_images/icon_gear.png)) e, em seguida, clique em **Access
   Administration**.
3. Selecione Roles (Funções ).
4. Verifique se a função personalizada não existe no momento. Você pode visualizar as permissões e os detalhes das funções clicando em Exibir na coluna Ações dessa função.
5. Selecione a função Proprietário do processo orçamentário a ser usada como modelo para criar a nova função personalizada. Na coluna Ações dessa função, clique em Clonar.
6. Insira um nome e uma descrição para a função (por exemplo, BPO sem acesso a Labor).
7. Na coluna Permission (Permissão ), desmarque a permissão ViewLabor. Observe que a restrição de acesso à guia Labor não afeta outras permissões e recursos nos aplicativos Apptio Planning .
8. Clique em Next e depois em Save.
9. No menu principal, clique em Aplicativos. Se a visibilidade de algum aplicativo tiver sido modificada e a nova função personalizada se aplicar a esse aplicativo, será necessário adicionar a nova função personalizada à visibilidade desse aplicativo.
10. Use as instruções em Modificar funções de usuário para atribuir usuários à nova função personalizada.

Na próxima vez que o usuário fizer login em um aplicativo Apptio Planning , o acesso à guia Trabalho será restrito. Para obter mais informações sobre o serviço **Access
Administration**
, consulte Sobre o Frontdoor, o console Apptio Access Administration .

## Ajustar as opções de resumo de trabalho

Os itens de linha financeira relacionados ao trabalho aparecem na tabela Despesas. Eles são resumidos em centros de custo e contas, que podem fornecer detalhes salariais. Além de limitar o acesso à guia Trabalho, você pode impedir que os usuários descubram os detalhes do salário ajustando a forma como os valores financeiros gerados pelo trabalho são resumidos.

1. No menu Componente, selecione Planning. Consulte [Navegar nos aplicativos Apptio Planning](navigate-apptio-planning.html "Este tópico fornece uma visão geral de como a navegação do Apptio Planning está organizada. Os itens de menu exibidos na sua conta dependem das suas permissões de usuário.") . > Despesas.
2. Na guia Resumo, selecione Ações > Opções de resumo de trabalho.
3. Selecione as dimensões e os atributos de dados a serem resumidos para os dados financeiros relacionados à mão de obra. A seleção de mais dimensões e atributos resulta em dados de mão de obra mais granulares; a seleção de menos opções resulta em dados de mão de obra menos granulares.
