---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Encontre seu caminho no TBM Studio"
breadcrumb: []
source_path: "studio/admin/navigate-tbm-studio.html"
images:
  - "resources/images/ap_images/ui-nav-apptio.png"
  - "resources/images/ap_images/ui-nav-max.png"
  - "resources/images/ap_images/ui-nav-min.png"
  - "resources/images/icons/icon-help.png"
  - "resources/images/icons/icon-settings.png"
  - "resources/images/icons/icon-user-account.png"
  - "resources/images/studio_images/staging.png"
  - "resources/images/studio_images/studioimages/icons/arrow-and-clockicon.png"
  - "resources/images/studio_images/studioimages/icons/pencilicon.png"
  - "resources/images/studio_images/studioimages/icons/person_icon.png"
  - "resources/images/studio_images/studioimages/icons/plusicon.png"
  - "resources/images/studio_images/studioimages/tbm-studio-panes.png"
  - "resources/images/studio_images/studioimages/tbm-studio-toolbar.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Encontre seu caminho no TBM Studio

## Barra de ferramentas

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/tbm-studio-toolbar.png)

|  |  |  |
| --- | --- | --- |
|  | Todos os produtos | Navegar para outro produto Apptio |
|  | Intervalo de data | Alternar entre períodos de tempo |
|  | Meio ambiente | Alternar entre os ambientes de desenvolvimento, preparação e produção  [Saiba mais sobre o meio ambiente](#FindyourwayaroundTBMStudio__Environments) |
|  | Ajuda | Será possível:  - pesquisar na Central de Ajuda - enviar feedback |
|  | Configurações do aplicativo | Será possível:  - ir para a administração do aplicativo - criar ou importar um novo projeto - Altere seu domínio - Configurar a segurança em nível de linha - exibir detalhes do aplicativo, como a versão e o ambiente |
|  | Configurações de perfil | Será possível:  - gerenciar seu perfil - fazer-se passar por outro usuário Dica: Os administradores podem querer fazer isso para verificar as permissões de um usuário ou para solucionar problemas. - efetuar logout |

## Navegação

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/tbm-studio-panes.png)

## Painel de projetos

No painel Projetos, você pode visualizar uma lista de todos os projetos no seu locatário e selecionar o projeto no qual deseja trabalhar.

- Para minimizar o painel Projetos, selecione ![](../../../../../03-media/apptio-tbm-studio/resources/images/ap_images/ui-nav-min.png). Para maximizar o painel novamente, selecione ![](../../../../../03-media/apptio-tbm-studio/resources/images/ap_images/ui-nav-max.png).

## Painel Project Explorer

O painel Project Explorer inclui seções para cada tipo de documento:

- **Tabelas** : Lista as tabelas que foram carregadas no aplicativo.
- **Métricas** : Lista as métricas calculadas e do modelo.
- **Perspectivas** : Lista os campos adicionados de outra seção que estão disponíveis para a criação de relatórios.
- **Relatórios** : Lista os relatórios de objetos gerados pelo aplicativo e os relatórios personalizados criados pelos usuários. Ele também lista os relatórios de modelos.
- **Tempo** : Liste os valores como meses, trimestres e metades que podem ser usados para agrupar dados em gráficos e tabelas em relatórios.

Quando você seleciona uma seção, ela se expande. Somente uma seção pode ser expandida por vez.

- Para minimizar o painel Project Explorer, clique na seta Minimizar no canto superior direito do painel.
- Para ajustar a largura do painel Project Explorer, arraste o divisor vertical.

Há também vários ícones que aparecem no Project Explorer:

| Ícone | Dica de ferramenta (exibida ao passar o mouse sobre ela) | Detalhes |
| --- | --- | --- |
|  | *"Este documento foi verificado por você"* | Você fez o check-out do projeto de preparação para edição. |
|  | *"Este documento foi verificado para <inserir nome de usuário aqui>"* | Alguém além do usuário atual fez o check-out. Passe o mouse sobre o ícone para saber o nome de usuário de quem fez o check-out. |
|  | *"Para compartilhar este documento, clique em check-in"* | Um novo item em seu espaço de trabalho. Você o criou e ainda não fez o check-in. Ele não ficará visível para outros usuários até que seja feito o check-in. |
|  | *"Este documento está sendo calculado. Ele estará disponível quando os cálculos forem concluídos."*  **Após o cálculo, a dica de ferramenta é alterada:**  *"Há uma versão mais recente deste documento disponível. Para obter a nova versão, clique em Atualizar espaço de trabalho."* | O item acabou de ser registrado por você e está sendo calculado no momento. O ícone será atualizado quando o cálculo do check-in for concluído.  **Após o cálculo:**  O item foi registrado por você ou por outro usuário desde a última atualização do seu espaço de trabalho. Clique em Update Workspace (Atualizar espaço de trabalho) para carregar a versão atual. |

## Ambientes

Há três ambientes em TBM Studio:

- Desenvolvimento
- Preparação
- Produção

Para alterar os ambientes, use o menu Ambiente na barra de ferramentas.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/staging.png)

Observação: Nas versões R11.x de TBM Studio, cada um dos três ambientes tinha um URL separado. Agora, todos os três ambientes estão agregados em um único URL.

## Ambiente de desenvolvimento

Quando você faz o check-out de um documento no seu espaço de trabalho e o edita, automaticamente está trabalhando no ambiente de desenvolvimento. As edições que você faz são locais em seu espaço de trabalho. Se outros usuários estiverem editando objetos em TBM Studio, você verá as listagens dos respectivos ambientes de desenvolvimento. Quando não houver documentos com check-out para edição, você será automaticamente transferido para o ambiente de teste.

Se outros usuários estiverem trabalhando em TBM Studio e tiverem um ou mais documentos verificados, você verá os ambientes deles listados no menu Environment (Ambiente). Se você tiver os privilégios de acesso corretos, poderá alternar para o ambiente de desenvolvimento de outro usuário e editar os documentos que ele verificou.

## Ambiente de preparação

Quando você faz o check-in de um documento, ele é registrado no ambiente de preparação. Todas as edições feitas por todos os usuários são agregadas no ambiente de teste.

## Ambiente de produção

O administrador do Apptio pode promover um projeto do ambiente de preparação para o ambiente de produção. Os usuários que têm acesso somente para visualização em Apptio estão sempre visualizando o ambiente de produção. Se o ambiente de preparação não tiver sido promovido para o ambiente de produção, o ambiente de produção não será exibido no menu Ambiente.

## Documentos e guias de documentos

Um documento é um objeto que pode ser editado. Os documentos incluem tabelas, métricas, perspectivas e relatórios. Quando você faz o check-out de um documento, uma guia é exibida na parte inferior do painel Detalhes/Visualização de dados. As guias são como as guias de planilha no Excel. Você pode alternar entre duas exibições de um documento usando os comandos do menu **Exibir** na guia Página **inicial** :

- **Mostrar documento** : Essa é a visualização de edição padrão de um documento.
- **Mostrar alterações** : Exibe uma lista das alterações feitas no documento.

Para excluir um documento, você deve fazer o check-out, excluí-lo usando o comando **Excluir** na guia Página **inicial** e, em seguida, fazer o check-in novamente. Para localizar um documento no Project Explorer, use o campo de pesquisa na parte superior de uma seção. No exemplo abaixo, a pesquisa é para todas as tabelas que têm a palavra "data" no título.

![](../../resources/images/studio_images/studioimages/studio_project%20explorer_data%20centers%20info.png)

## Check-out e check-in

Para editar um documento, você deve verificá-lo.

- Na guia Página **inicial**, no grupo **Documento**, clique em **Check-out**.

Quando você faz o check-out de um documento, ele é bloqueado para que outras pessoas não possam editá-lo. Você pode salvar as alterações no documento sem acionar um novo cálculo. Quando terminar de editar um documento, salve-o e faça o check-in novamente.

- Na guia Página **inicial**, no grupo **Documento**, clique em **Check-in**.

Isso aciona um recálculo e outras pessoas verão as alterações que você fez no documento. As alterações serão disponibilizadas no ambiente de teste. [Saiba mais sobre o check-out de documentos](bp-check-out.html "(Abre em uma nova guia ou janela)")

## Atualização com mudanças recentes

Ao trabalhar em TBM Studio, você pode atualizar documentos e espaços de trabalho usando as opções **Updates (Atualizações** ) na guia **Home**. As opções incluem:

- Update Document (Atualizar documento) - Atualiza o documento ativo no momento com todas as alterações registradas.
- Update Workspace (Atualizar espaço de trabalho) - Atualiza seu espaço de trabalho com as alterações de todos os documentos com check-out no momento.
- Auto Calculate (Cálculo automático) - Atualize todos os documentos que você fez check-out sempre que salvar um documento.
- Para ativar as opções Atualizar documento ou Atualizar espaço de trabalho, selecione primeiro Auto-Calculate (Cálculo automático).

## Salvamento automático

Em TBM Studio, as ações a seguir acionam um salvamento automático de todos os documentos verificados:

- Criação de um novo documento.
- Mudança de uma etapa em uma transformação para outra etapa ou criação de uma nova etapa de transformação.
- Mudança de uma guia de documento para outra.
