---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Componente de botão"
breadcrumb: []
source_path: "studio/reports/button.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png"
  - "resources/images/studio_images/studioimages/icons/edit_21x21_icon.png"
  - "resources/images/studio_images/studioimages/reports/rep147.png"
  - "resources/images/studio_images/studioimages/reports/rep148.png"
  - "resources/images/studio_images/studioimages/studio/aug114.png"
  - "resources/images/studio_images/studioimages/studio/stu629.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componente de botão

**Aplica-se a** : TBM Studio R.12.0 e posterior.

Use o componente **Button** em relatórios para fornecer links para qualquer relatório em um projeto. Além disso, use os botões para alterar o período de tempo exibido no momento para um relatório e para adicionar e excluir linhas em uma tabela. Por exemplo, consulte o botão Orçamento do aplicativo abaixo:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu629.png)

Quando você adiciona um botão a um relatório, pode alterar sua aparência, adicionar gráficos e definir ações para o botão.

Observação: Tenha cuidado ao criar um botão que navega para um relatório. Se ele exibir um relatório que exija cálculos significativos, isso poderá afetar o desempenho do sistema.

## Adicionar um botão

Na guia **Relatório**, clique no ícone **Botão**. O aplicativo adiciona o objeto de botão ao relatório, conforme mostrado na imagem a seguir. O botão está contido em um painel de componente de relatório padrão.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug114.png)

## Alterar a aparência de um botão

Depois de adicionar um botão a um relatório, você pode alterar sua aparência. Além disso, você pode substituir ou complementar o texto do botão com uma imagem personalizada.

Para alterar a aparência do botão:

1. No canto superior esquerdo do componente do botão, clique no pequeno triângulo ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png) para abrir o menu **Actions (Ações** ) e clique em **Properties (Propriedades** ). A caixa de diálogo **Propriedades** é exibida:![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep147.png)
2. Use os campos da guia **Botão** para alterar a aparência do botão. Os campos são descritos a seguir.
   - **Button Text (Texto do botão** ) - O texto inserido nesse campo é exibido no botão. Normalmente, esse será um rótulo estático. No entanto, você pode usar texto dinâmico nesse campo. Para obter informações sobre texto dinâmico, consulte [Caixa de texto HTML](html.html "Aplica-se a: TBM Studio 12.0 e posterior"). Você também pode substituir ou complementar o texto em um botão com uma imagem da biblioteca de imagens Apptio inserindo o código HTML que faz referência à imagem.
   - **Dica de ferramenta do botão** - O texto inserido nesse campo será exibido como uma dica de ferramenta quando o usuário mover o ponteiro do mouse sobre o botão.
   - **Ativado** - Determina se o botão está ativo, desativado ou oculto.
     - Para ocultar o botão, digite a palavra "hidden" (oculto) no campo.
     - Para desativar o botão, digite a palavra "disabled" no campo. O botão aparecerá em cinza e não poderá ser selecionado.
     - Você pode inserir uma função que será avaliada para determinar o estado do botão. Por exemplo, para ativar um botão se o custo for superior a US$ 5.000, você digitaria `<%=IF(Cost>5000,"enabled","disabled")%>`. Para obter mais informações sobre funções, consulte "Introdução a fórmulas e funções" no *Guia do Studio*.
   - **Button Color (Cor do botão** ) - Define a cor de fundo do botão.
   - **Button Text Color (Cor do texto do botão** ) - Define a cor do texto.
   - **Tamanho do texto** - Define o tamanho do botão e o texto exibido no botão. Além disso, você pode redimensionar um botão arrastando a borda do painel que o circunda. O tamanho mínimo do botão é limitado pela quantidade de texto exibida.
   - **Crescimento do botão**
     - **Auto** : Define o botão com o tamanho padrão.
     - **Horizontal** : Aumenta o comprimento do botão para que ele se ajuste ao painel ao redor.
   - **Panel Background Color (Cor de fundo do painel** ) - Define a cor do painel que circunda o botão.
3. Para visualizar suas alterações, clique em **Apply (Aplicar** ). Para salvar suas alterações, clique em **OK**.

## Definir as ações para um botão

Quando um usuário clica em um botão, ele pode executar uma ação com script, alterar a data e/ou navegar para um relatório.

Para definir as ações de um relatório:

1. Na caixa de diálogo **Propriedades**, selecione a guia **Ações** no cabeçalho. O aplicativo exibe os seguintes campos:![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep148.png)
2. Preencha os campos.
   - **Ação do servidor** - Um script de servidor pode ser inserido nesse campo usando a linguagem de script Apptio. O script é executado primeiro, antes que as entradas nos campos **Change Date** e **Navigate** sejam executadas. Esse é um recurso avançado usado pelos consultores do Apptio Customer Success.
   - **Change Date (Alterar data** ) - Selecione uma opção na lista suspensa ou insira uma data no campo **Date (Data** ) na parte inferior da lista. O formato da data é período:ano. Exemplos: January:FY2012, P3:FY2012.
     - Para aceitar uma entrada no campo **Data**, clique no sinal de mais à direita do campo.
     - Para limpar a configuração **Alterar data**, selecione **Limpar data selecionada** na lista suspensa.
   - **Navigate (Navegar** ) - Insira um link para um documento usando a sintaxe do estilo Wiki. Consulte [Codificação de links para outros relatórios](coding-links-to-other-reports.html "Aplica-se a: TBM Studio 12.0 e posterior") para obter detalhes e exemplos.
   - **Botão Voltar** - Quando essa opção estiver selecionada, ao clicar no botão, o usuário voltará ao último relatório em que estava. Isso fornece ao usuário uma alternativa aos breadcrumbs do relatório. Essa opção substitui qualquer entrada feita nos campos Server Action (Ação do servidor), Change Date (Alterar data) e Navigate (Navegar).
   - **Enviar formulário** - Se o botão for colocado em um formulário, ele enviará o formulário quando clicado.
3. Para visualizar suas alterações, clique em **Apply (Aplicar** ). Para salvar suas alterações, clique em **OK**.

## Definir as propriedades gerais

As propriedades gerais são descritas abaixo.

- **Nome** - Digite um nome a ser exibido no cabeçalho do botão acima do componente. O nome é exibido quando a opção **Mostrar cabeçalho** é selecionada.
- **Legenda** - Insira informações adicionais sobre o componente. As informações são exibidas com base na configuração do campo **Caption Position (Posição da legenda** ).
- **Caption Position (Posição da legenda** ) - Na lista, selecione uma posição de legenda em relação ao botão: **Superior**, **Inferior**, **Esquerda** ou **Direita**, ou selecione **Ocultar** para não exibir a legenda.
- **Show Header (Mostrar cabeçalho** ) - O cabeçalho do componente exibe o conteúdo do campo **Name (Nome** ). Selecione essa opção para tornar visível o cabeçalho do componente. Quando o cabeçalho está oculto, é possível pausar o ponteiro do mouse no componente para exibir o cabeçalho.
- **Show Border (Mostrar borda** ) - Selecione essa opção para exibir uma borda ao redor da tabela. Quando a borda está oculta, é possível pausar o ponteiro do mouse no componente para exibir a borda.
- **Wrap Title (Envolver título** ) - Envolve o texto inserido no campo **Name (Nome** ) para acomodar a largura do componente.

## Definir propriedades avançadas

As propriedades **avançadas** incluem:

- **Atualização automática quando os cálculos terminam** - Quando o aplicativo exibe um botão, ele o exibe com os dados calculados que estão disponíveis no momento. Em muitos casos, o aplicativo pode estar calculando novos valores em segundo plano. Se você quiser que os resultados sejam exibidos quando os cálculos forem concluídos, selecione essa opção. Essa opção se aplica somente à tabela selecionada no momento. Essa opção está disponível somente quando a **Política de cálculo** (na caixa de diálogo **Cálculo do projeto** ) de um projeto está definida como **Publicação dinâmica**.
- **Habilitar guias de aplicativos no projeto** - Essa opção não está mais ativa na versão 12.0 do produto. É um recurso herdado das versões v.11.x do produto.
- **Dados URL** - Exibe o caminho para a tabela que fornece os dados para o relatório. Você pode inserir uma função de tabela nesse campo clicando no ícone **Editar caminho de dados** ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/edit_21x21_icon.png) à direita do campo. O aplicativo exibe a caixa de diálogo **Editar caminho**.
- **Create New Project (Criar novo projeto** ) - Se você selecionar um valor para esse campo, o aplicativo criará um novo projeto quando o usuário clicar no botão. Há duas opções:
  - **Derivado** - O aplicativo cria um projeto separado com base em um projeto existente. Use isso quando quiser preservar o projeto antigo para referência. A exclusão do projeto original não exclui o projeto derivado.
  - **Instantâneo do projeto atual** - O aplicativo marca um ponto no tempo no registro do projeto existente e cria um novo projeto. O novo projeto está vinculado ao projeto antigo. Se você excluir o projeto antigo, o novo projeto será excluído.

  Observação: Se estiver criando um novo projeto, você deve preencher os campos **Derive Generated Project From (Derivar projeto gerado de** ) e **Project Start Date (Data de início do projeto** ).
- **Derive Generated Project From (Projeto derivado gerado de** ) - Use ao criar um novo projeto derivado. Digite o nome do projeto que será usado como base para o projeto derivado. O nome deve incluir o exemplo domain.For :

  ```
  abc_company.com:Project
                123
  ```
- **Data de início do projeto** - Use ao criar um novo projeto derivado. Insira a data de início a ser atribuída ao projeto derivado. Você pode usar qualquer um dos formatos de data compatíveis. Um formato típico é MMM-FYyyyy.For, por exemplo: JAN FY2012.
- **Make Personal Project (Criar projeto pessoal** ) - Cria um projeto que somente a pessoa que criou o projeto pode acessar. Adiciona o ID do usuário da pessoa que clicou no botão ao nome do projeto. Por exemplo, se psmith@abc \_company.com clicar no botão e inserir um nome de projeto "new-project", o nome completo do projeto será "\_psmith@abc \_company.com\_new-project. "Observe o sublinhado na frente do nome do projeto.
