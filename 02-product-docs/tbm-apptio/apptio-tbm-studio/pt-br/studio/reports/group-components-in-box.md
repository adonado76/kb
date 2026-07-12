---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Agrupar componentes em uma caixa"
breadcrumb: []
source_path: "studio/reports/group-components-in-box.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png"
  - "resources/images/studio_images/studioimages/reports/rep144.png"
  - "resources/images/studio_images/studioimages/reports/rep145.png"
  - "resources/images/studio_images/studioimages/studio/aug159.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Agrupar componentes em uma caixa

**Aplica-se a** : TBM Studio 12.0 e posterior

Se estiver criando um relatório com muitos componentes, pode ser útil agrupar visualmente os componentes adicionando uma borda ao redor deles. Por exemplo, a imagem a seguir mostra dois conjuntos de componentes sem bordas. Um conjunto de componentes mostra os custos da unidade de negócios e o outro conjunto mostra os custos do data center:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep144.png)

A adição de bordas, conforme mostrado na imagem a seguir, esclarece a relação entre o gráfico e a tabela em cada conjunto. A colocação de componentes de relatório em uma caixa de grupo os agrupa fisicamente para que possam ser movidos como um grupo.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep145.png)

## Adicionar uma caixa de grupo

1. Na guia **Relatório**, clique no ícone **Grupo**. O aplicativo adiciona a caixa de grupo ao relatório.
2. Mova e redimensione a caixa conforme necessário.
3. Para mover a caixa, clique no cabeçalho e arraste-a para o novo local.
4. Para redimensionar a caixa, arraste as bordas da borda.

## Adicionar componentes a uma caixa de grupo

Para adicionar componentes a uma caixa de grupo, selecione os componentes e arraste-os para a caixa. Redimensione a caixa de grupo para acomodar os objetos. Quando você arrastar a caixa de grupo, os objetos da caixa também serão movidos, mantendo suas posições relativas na caixa.

## Organizar componentes em uma caixa de grupo

Se você colocar vários objetos em uma caixa de grupo, poderá organizar os componentes manualmente ou usando as ferramentas de **Layout de grupo** na guia **Grupo**. A vantagem das opções de layout **Vertical** e **Horizontal** é que, se um componente colocado no grupo estiver oculto para um conjunto de usuários, os componentes restantes serão organizados para preencher o espaço ocupado pelo componente ausente.

As opções de layout de grupo são descritas abaixo:

- **Manual** - Você pode posicionar os componentes em qualquer lugar do grupo e eles permanecerão onde você os colocou.
- **Vertical** - Alinha automaticamente os componentes verticalmente usando as configurações da opção **Spacing (Espaçamento** ).
- **Horizontal** - Alinha automaticamente os componentes horizontalmente usando as configurações da opção **Spacing (Espaçamento** ).
- **Spacing (Espaçamento** ) - Exibe uma caixa de diálogo na qual você pode definir o espaçamento vertical e horizontal entre os componentes.

## Tamanho automático

A caixa de grupo pode ter um tamanho fixo ou pode mudar de tamanho dinamicamente. Se a caixa tiver um tamanho fixo, ela não mudará de tamanho com base no número de componentes exibidos. Se o número de componentes em uma caixa de grupo fizer com que a caixa de grupo exiba barras de rolagem, as barras de rolagem serão exibidas mesmo que haja apenas um componente exibido na caixa.

Se a caixa for definida para ser dimensionada dinamicamente, ela se ajustará para acomodar o tamanho dos componentes incluídos na caixa. Use as opções de **Auto Sizing (Dimensionamento automático** ) na guia **Group (Grupo** ) para controlar como a caixa de grupo se ajusta aos componentes.

## Alterar o ícone de uma caixa de grupo

Você pode alterar o ícone padrão de uma caixa de grupo. Os arquivos gráficos de ícones são armazenados em um servidor central em uma coleção Icon Experience. Para alterar o ícone de uma caixa de grupo em um relatório, altere o caminho do ícone no HTML da caixa de grupo.

Para alterar o ícone de uma caixa de grupo:

1. Em uma janela separada do navegador, acesse este link: http://<yourapptiodomain>.apptio.com/graphics/IconExperience/search.html
2. Procure o ícone que você deseja usar.
3. Quando tiver localizado o ícone, selecione-o nas listas à esquerda.
4. À direita, localize o ícone de tamanho que você deseja usar.
5. Clique com o botão direito do mouse no ícone e selecione Copiar local da imagem.
6. Cole-o no Bloco de Notas e copie o endereço URL para o ícone que começa com a palavra "graphics" Exemplo: graphics/IconExperience/v\_collections\_png/computer\_network\_security/24x24/plain/server\_lock.png.
7. Abra o menu **Ação** da caixa de grupo e selecione **Propriedades**.
8. Na guia **General (Geral** ), cole o novo URL **no campo Grouping Image URL** (Imagem de agrupamento ).

## Adicionar um título à borda

Um elemento tradicional de muitos aplicativos é um título incorporado na borda das caixas de grupo. Você pode adicionar facilmente títulos incorporados a caixas de grupo em relatórios, conforme mostrado na imagem a seguir. Neste exemplo, o título Application Costs (Custos de aplicativos) foi adicionado à caixa de grupo:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug159.png)

Para adicionar um título à borda de uma caixa de grupo:

1. Clique com o botão direito do mouse dentro da caixa de grupo e selecione **Propriedades** no menu pop-up.
2. Na guia **General (Geral** ) da caixa de diálogo **Properties (Propriedades** ), insira o texto do título no campo **Grouping Border Title (Título da borda de agrupamento** ).

## Adicionar um fundo colorido

Para adicionar um fundo colorido a uma caixa de grupo:

1. Clique com o botão direito do mouse dentro da caixa de grupo e selecione **Propriedades** no menu pop-up.
2. Na guia **General (Geral** ) da caixa de diálogo **Properties (Propriedades** ), abra a lista suspensa do campo **Grouping Style (Estilo de agrupamento** ) e selecione uma cor.
3. Para ver a nova cor, clique no botão **Apply (Aplicar** ).

## Bordas da caixa de grupo

Há várias opções que podem ser usadas para controlar a aparência das bordas em uma caixa de grupo. Os elementos das bordas são identificados na imagem a seguir. Todas as opções, exceto uma, estão localizadas na guia **Geral** da caixa de diálogo **Propriedades** da caixa de grupo:

![imagem](../../resources/images/studio_images/studioimages/visio%20diagrams/group-box-borders.png)

Como controlar cada um dos elementos é descrito abaixo:

- O nome da caixa de grupo vem do campo **Nome**.
- Para exibir o nome da caixa de grupo, selecione a opção **Mostrar cabeçalho**.
- A borda externa é controlada pelo campo **Show Border**. Quando a opção está marcada, a borda externa é exibida.
- O ícone e o título na borda interna são exibidos quando a opção **Show Inner Border (Mostrar borda interna** ) está marcada.
- O texto da borda interna vem do campo **Título da borda de agrupamento** na guia **Geral**.
- O formato do texto no título da borda interna é controlado pelo campo **Título da borda de agrupamento** na guia **Estilos** da caixa de diálogo **Propriedades** da caixa de grupo. O estilo é controlado com a inserção de um estilo CSS Apptio. Esse é um recurso avançado usado pelos consultores de Sucesso do Cliente do Apptio.

## Redimensionamento automático de caixas de grupo

Se você tiver colocado várias tabelas em uma caixa de grupo e uma ou mais dessas tabelas estiver configurada para ter tamanho automático com base em seu conteúdo, você poderá configurar a caixa de grupo para redimensionar também. Isso garante que o tamanho da caixa de grupo corresponda ao tamanho das tabelas. Você pode definir a largura, a altura ou ambas para redimensionar. O redimensionamento funciona somente no modo Exibir. Quando você estiver editando um relatório, a caixa de grupo não será redimensionada.

Para definir as opções de redimensionamento:

1. Selecione a caixa de grupo.
2. Na guia Group (Grupo), selecione uma das opções de redimensionamento.

## Definir as propriedades

Para editar as propriedades de uma caixa de grupo, exiba a caixa de diálogo **Propriedades** seguindo um destes procedimentos:

- No canto superior esquerdo do ícone, clique no pequeno triângulo ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png) ao lado do nome do componente para exibir o menu **Actions (Ações** ). No menu **Ações**, clique em **Propriedades**.
- Clique com o botão direito do mouse em qualquer lugar dentro das bordas do componente e selecione **Propriedades** no menu pop-up.

As propriedades **gerais** não descritas nas seções acima são descritas a seguir:

- **Nome** - Digite um nome a ser exibido no cabeçalho do componente acima do componente quando **Show Header** for selecionado.
- **Legenda** - Insira informações adicionais sobre o componente. As informações são exibidas com base na configuração do campo **Caption Position (Posição da legenda** ).
- **Caption Position (Posição da legenda** ) - Na lista, selecione uma posição de legenda relativa ao botão: **Superior**, **Inferior**, **Esquerda** ou **Direita**, ou selecione **Ocultar** para ocultar a legenda.
- **Show Header (Mostrar cabeçalho** ) - O cabeçalho do componente exibe o conteúdo do campo **Name (Nome** ). Selecione essa opção para tornar o cabeçalho do componente visível (o padrão). Quando o cabeçalho está oculto, é possível exibi-lo ao pausar o ponteiro do mouse no componente.
- **Mostrar borda** - Selecione essa opção para exibir uma borda ao redor da caixa de grupo. Quando a borda está oculta, é possível exibi-la ao pausar o ponteiro do mouse no componente.
- **Wrap Title (Envolver título** ) - Envolve o texto inserido no campo **Name (Nome** ) para acomodar a largura do componente.
- **Show Inner Border (Mostrar borda interna** ) - Selecione essa opção para exibir um título na borda interna. O texto do título é retirado do campo Título da borda do agrupamento.
- **Agrupamento de imagens URL** - Para alterar o ícone exibido na borda interna, insira o endereço URL no arquivo de imagem do ícone. O endereço URL do ícone padrão é mostrado abaixo:`/graphics/IconExperience/v_collections_png/computer_network_security/48x48/shadow/envelope_cushioned.png`
- **Título da borda de agrupamento** - O texto inserido nesse campo é exibido como o título na borda interna.
- **Background Color (Cor de fundo** ) - Controla a cor de fundo da área dentro da borda interna.

A propriedade Styles inclui:

- **Título da borda do agrupamento** - Formata o texto exibido na borda interna da caixa de grupo. Digite um estilo Apptio CSS (Cascading Style Sheet) para aplicar um formato. Esse é um recurso avançado usado pelos consultores do Apptio Customer Success.

A propriedade **Advanced** inclui:

- **Atualização automática quando os cálculos terminam** - Quando o aplicativo exibe um componente Group Box, ele o exibe com os dados calculados disponíveis no momento. Em muitos casos, o aplicativo pode estar calculando novos valores em segundo plano. Se você quiser que os resultados sejam exibidos quando os cálculos forem concluídos, marque essa opção.
