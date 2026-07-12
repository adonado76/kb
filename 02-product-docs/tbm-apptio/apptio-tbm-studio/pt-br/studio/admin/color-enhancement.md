---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Paleta de cores personalizada"
breadcrumb: []
source_path: "studio/admin/color-enhancement.html"
images:
  - "resources/images/studio_images/blank-palette.png"
  - "resources/images/studio_images/ccp-applycp_991x445.png"
  - "resources/images/studio_images/ccp-colorpalette.png"
  - "resources/images/studio_images/ccp-defaultccp.png"
  - "resources/images/studio_images/ccp-menu_179x417.png"
  - "resources/images/studio_images/ccp-popup.png"
  - "resources/images/studio_images/ccp-rcpopup.png"
  - "resources/images/studio_images/ccp-reportcollection.png"
  - "resources/images/studio_images/enable-dcp.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Paleta de cores personalizada

O administrador do Apptio, o administrador e o administrador do parceiro têm a flexibilidade de definir, gerenciar e aplicar cores corporativas a coleções de relatórios e relatórios no TBM Reports Studio. Ele permite que os administradores alinhem a estética visual de seus relatórios com as diretrizes de marca da organização e proporciona uma melhor experiência do usuário. A paleta de cores pode ser definida somente no nível do ambiente, e não no nível da instância.

Para ativar o recurso Custom Color Palette na interface do usuário, navegue até a guia **Project (Projeto** ) > **Enable Features (Ativar recursos** ) > e selecione a opção **Enable Color Enhancement (Ativar aprimoramento de cores** ).

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/enable-dcp.png)`

## Criar paleta de cores personalizada

No canto superior direito, selecione **Configurações** > **Paleta de cores personalizada**. Essa opção está disponível somente para as funções Apptio Admin, Admin e Partner Admin.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-menu_179x417.png)

A janela pop-up Paleta de cores personalizadas é exibida. Para um usuário iniciante, a paleta de cores personalizadas estará em branco, sem nenhuma cor.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/blank-palette.png)

Escolha a paleta de cores uma de cada vez, começando da esquerda para a direita. Ao selecionar a primeira cor, o sistema aplicará automaticamente gradientes dessa cor ao restante das 11 cores. O administrador tem a opção de atualizar as cores manualmente.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-popup.png)

Depois de selecionar as 12 cores, selecione o botão **Save (Salvar** ). As cores selecionadas aqui estarão disponíveis para serem aplicadas aos relatórios e às coleções de relatórios no ambiente de todos os projetos. Se o código HEX estiver incorreto, será exibida uma mensagem de erro apropriada.

Observação: se um cliente não tiver várias cores em seu guia de estilo, as variações da cor aplicada serão geradas automaticamente.

## Paleta de cores personalizada

Cada paleta de cores tem 12 cores, e há 10 paletas que podem ser criadas e personalizadas. Se houver mais de 12 dimensões, as variações das 12 cores serão aplicadas às dimensões adicionais no gráfico.

## Nomear a paleta de cores

O nome da paleta de cores deve ser alfanumérico, pode conter "espaço", "-" e "\_" e não deve exceder 30 caracteres.

Há dois tipos de paletas disponíveis:

**Paleta personalizada** : Podem ser criadas e gerenciadas pelos administradores, de acordo com os estilos de cores de suas organizações.

**Paleta de predefinições** : Essas são as cores padrão do Apptio que não podem ser personalizadas. Elas estão disponíveis no nível da coleção de relatórios e do relatório, e não ao criar as paletas personalizadas.

## Atualizando a paleta de cores personalizadas

Se você quiser alterar qualquer cor em uma paleta de cores existente, o gradiente automático não estará ativo. O restante das cores permanecerá o mesmo.

## Aplicar a paleta de cores

## Nível do relatório

Navegue até **TBM Studio** > **Projetos** > **Relatórios** e selecione qualquer relatório. Por padrão, as cores do Apptio serão consideradas no relatório.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-defaultccp.png)

Na guia **Home**, **verifique** o relatório. Navegue até a guia **Report (Relatório** ) e selecione a opção **Color Palette (Paleta de cores** ).

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-colorpalette.png)

O menu Aplicar paleta de cores é aberto no painel direito, com a lista de paletas de cores personalizadas e predefinidas.

Selecione a paleta de cores personalizada ou as predefinições de sua escolha a serem aplicadas ao relatório.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-applycp_991x445.png)

Uma mensagem de confirmação é exibida e a cor personalizada é aplicada ao relatório. A paleta de cores selecionada será destacada para facilitar a identificação.

A paleta de cores também será aplicada a todos os tipos de gráfico, exceto Waterfall e Treemap. A paleta de cores não é aplicável a tabelas, cores de fonte/rótulo, fatiadores, plano de fundo e KPI. Para saber mais, consulte [Definir cores padrão em gráficos](../reports/set-default-colors-charts.htm "(Abre em uma nova guia ou janela)").

## Nível de coleções de relatórios

Na guia **Project (Projeto** ), selecione **Report Collections (Coleções de relatórios** )

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-reportcollection.png)

A janela pop-up Gerenciar coleção de relatórios é exibida

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-rcpopup.png)

Ao selecionar a paleta de cores, todos os relatórios dentro da coleção de relatórios terão automaticamente a mesma paleta de cores aplicada à coleção de relatórios.

Observação: Se um novo relatório for adicionado à coleção de relatórios, a paleta de cores do relatório não será alterada automaticamente para a da coleção de relatórios. O administrador deve alterá-lo manualmente no nível do relatório.
