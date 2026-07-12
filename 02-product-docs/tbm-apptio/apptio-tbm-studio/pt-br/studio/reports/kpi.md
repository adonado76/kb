---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Indicadores-chave de desempenho (KPIs)"
breadcrumb: []
source_path: "studio/reports/kpi.html"
images:
  - "resources/images/studio_images/kpi-1_706x440.png"
  - "resources/images/studio_images/kpi-popup.png"
  - "resources/images/studio_images/kpi-rename_693x449.png"
  - "resources/images/studio_images/rename-kpi_267x531.png"
  - "resources/images/studio_images/studioimages/reports/rep250.png"
  - "resources/images/studio_images/studioimages/studio/stu519.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Indicadores-chave de desempenho (KPIs)

**Aplica-se a** : TBM Studio 12.0 e posterior

Você pode exibir indicadores-chave de desempenho (KPIs) em painéis e outros relatórios adicionando um componente KPI.

![Custos do servidor](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep250.png)

Um componente KPI exibe qualquer número de métricas que você desejar e inclui os seguintes recursos:

- Setas para mostrar a variação em relação ao período anterior.
- Slicers para aplicar aos componentes de KPI.

## Adicionar um componente KPI

1. Exiba um relatório e dê uma olhada nele.
2. Na guia **Relatório**, no grupo **Consulta**, clique em **KPI**. O componente KPI é adicionado ao relatório e a caixa de diálogo Configuração de KPI é exibida:![Adicionar um componente KPI](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu519.png)
3. Selecione um objeto modelado no menu abaixo de **KPI Configuration**.
4. Arraste os campos que deseja exibir como KPIs de **Tabelas**, **Cálculos** e outras perspectivas para a área de **KPIs**.
5. Se os KPIs adicionados não aparecerem inicialmente no componente KPI, talvez não haja espaço suficiente. Arraste as bordas do componente KPI para alterar seu tamanho e permitir espaço para que todos os valores fiquem visíveis.

## Exibir e ocultar KPIs

1. Selecione o componente KPI.
2. Na guia KPI, clique em **Show/Hide Panels (Mostrar/Ocultar painéis** ) e selecione os KPIs que deseja que fiquem visíveis no KPI component.The lista de KPIs em **Show/Hide Panels (Mostrar/Ocultar painéis** ) depende totalmente da **configuração de KPI** do componente.

## Mostrar borda do componente KPI

Para ativar ou desativar a borda de um componente KPI, clique com o botão direito do mouse no componente KPI, clique em **Properties (Propriedades** ), selecione ou desmarque **Show Border (Mostrar borda** ) e, em seguida, **Apply (Aplicar** ). Por padrão, os componentes KPI não têm a borda visível.

## Renomear o rótulo de KPI nos relatórios (BETA)

**Aplica-se a** : 12.11.6 e posterior

O administrador pode ativar esse recurso em **TBM Studio** > **Projeto** > **Ativar recursos** > **Permitir renomeação de KPIs**.

![Renomear rótulo de KPI](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rename-kpi_267x531.png)

Para renomear o KPI, faça o seguinte:

1. Adicionar um componente de relatório de KPI a um relatório
2. Arraste as métricas para o painel de configuração do KPI

   Clique com o botão direito do mouse no KPI e selecione **Renomear**.

   ![Renomear a configuração de KPI](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/kpi-1_706x440.png)
3. O pop-up Renomear KPI é exibido.

   ![Renomear pop-up de KPI](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/kpi-popup.png)
4. Digite o nome apropriado para o KPI e selecione **OK**. O KPI foi renomeado com sucesso.

   ![Renomeação bem-sucedida de KPI](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/kpi-rename_693x449.png)

## Filtrar os valores

Depois de adicionar valores a um KPI, você pode filtrar os valores arrastando os campos da perspectiva **Tabelas** para a área **Filtros**. Os filtros se aplicam a todos os valores exibidos no KPI. Por exemplo, suponha que você tenha um componente KPI que exibe informações de custo para todas as unidades de negócios. Você pode filtrar o KPI para exibir os custos de um conjunto específico de unidades de negócios.

Para filtrar os valores de KPI para um conjunto específico de unidades de negócios:

1. Clique no KPI.
2. Arraste o campo **Business Unit** da seção **Dimensions (Dimensões** ) do **Project Explorer** para a área **Filters (Filtros** ).
3. Clique com o botão direito do mouse no campo **Business Unit** e clique em **Edit Filter (Editar filtro** ).
4. Selecione as unidades de negócios que você deseja incluir nos valores de KPI.

## Adicionar indicadores de desvio

Para indicar a variação de um valor em relação ao período anterior, você pode adicionar um valor percentual e setas indicadoras ao KPI.

![Adicionar variação](../../resources/images/studio_images/studioimages/studio_kpi_add%20variance%20indicators.png)

Para adicionar um indicador de variação a um valor em um componente de KPI:

1. Clique no componente KPI.
2. Clique na guia KPI.
3. Clique no valor do componente KPI ao qual você deseja adicionar o indicador.
4. Clique no ícone Comparações na barra de ferramentas do KPI.
5. Em Trend Type (Tipo de tendência), selecione uma opção.
6. Selecione uma opção de exibição.
7. Em Trend Direction (Direção da tendência), selecione uma das opções para o indicador.
   - Para cima é verde: Se o valor do período atual for maior do que o valor do período anterior, exibirá a seta em verde. Por exemplo, você pode escolher essa opção se a porcentagem de tempo de atividade do servidor tiver aumentado.
   - Up is Red: Se o valor do período atual for maior que o valor do período anterior, exiba a seta em vermelho. Por exemplo, você pode escolher essa opção se o número de tíquetes do Help Desk tiver aumentado.
8. Para fechar o menu suspenso de opções, clique fora da caixa suspensa.
9. Para salvar as alterações, clique em Save (Salvar) na guia Home (Página inicial).

## Adicionar valores secundários

Um valor secundário é um valor exibido abaixo do valor principal. No exemplo da imagem, o valor secundário é Orçamento, e o valor (40%) em vermelho indica que o orçamento está 40% abaixo do valor de custo.

![Adicionar secundário](../../resources/images/studio_images/studioimages/studio_kpi_secondary%20values.png)

Para exibir um valor secundário:

1. Clique no componente KPI.
2. Clique na guia KPI.
3. Clique no valor do componente KPI ao qual você deseja adicionar o valor secundário.
4. Clique no ícone Secundário na guia KPI.
5. Selecione um valor.
   - Os valores secundários são limitados aos valores exibidos atualmente no KPI. Normalmente, quando você adiciona um valor secundário, oculta o mesmo valor na parte principal do KPI.
   - Para ocultar um valor, clique no ícone Show/Hide (Mostrar/Ocultar) na guia KPI e selecione o valor que deseja ocultar.

## Adicionar valores terciários

Um valor terciário é um valor percentual exibido à direita do valor principal. Um valor terciário pode comparar a mudança mês a mês ( MoM ) no valor principal ou a variação entre os valores principal e secundário (Acima/Abaixo). No exemplo da imagem, o valor terciário está indicando que o custo está 66% acima do valor orçado:

![Adicionar valores terciários](../../resources/images/studio_images/studioimages/studio_kpi_business_unit_costs.jpg)

Observação: somente os KPIs com campos numéricos na seção Tabelas ou perspectivas personalizadas podem ter valores terciários.

## Notação abreviada

É possível exibir números em um KPI usando a notação K/M/B (mil/milhões/bilhões). Para usar a notação:

1. Clique em um valor no componente KPI e clique na opção Shorthand na guia KPI.
2. Selecione a quais valores (primário/secundário) a abreviação deve ser aplicada.
3. Selecione os tipos de notação de destino para a notação abreviada.

## Alterar as cores do KPI

Você pode alterar as cores de cada elemento em um KPI clicando em **Colors (Cores** ) na guia **KPI**. As cores podem ser aplicadas separadamente a cada valor em uma barra de KPI ou ao componente como um todo, se nenhum valor for selecionado.

## Quebrar o texto do nome

Quando selecionado, o nome do valor primário será agrupado se for muito longo para caber na largura do KPI.

## Propriedades KPI

Assim como em outros componentes de relatório, você pode editar as propriedades de um componente KPI. Para editar as propriedades de um componente KPI, localize o menu **Properties (Propriedades** ) executando uma das seguintes ações:

- No canto superior esquerdo do componente, clique no pequeno triângulo ao lado do nome do componente para exibir o menu **Ações**. No menu **Ações**, selecione **Propriedades**.
- Clique com o botão direito do mouse em qualquer lugar dentro das bordas do componente e selecione **Propriedades**.

**Propriedades gerais**

- **Nome** : Digite um nome a ser exibido no cabeçalho da nota acima do componente. O nome é exibido quando a opção **Show Header** é selecionada.
- **Legenda** : Insira informações adicionais sobre a nota. As informações são exibidas com base na configuração do campo **Caption Position (Posição da legenda** ). Você pode usar código HTML no campo, mas o código HTML não pode incluir links. A restrição do código HTML é por motivos de segurança.
- **Posição da legenda** : Na lista, selecione uma posição de legenda em relação à nota: Superior, Inferior, Esquerda ou Direita, ou selecione Ocultar para não exibir a legenda.
- **Mostrar cabeçalho** : O cabeçalho do componente exibe o conteúdo do campo Nome. Selecione essa opção para tornar o cabeçalho do componente visível (o padrão). Quando o cabeçalho está oculto, é possível pausar o ponteiro do mouse no componente para exibi-lo.
- **Mostrar borda** : Selecione essa opção para exibir uma borda ao redor da tabela. No modo Editar, você pode exibir uma borda oculta ao pausar o cursor sobre a tabela.
- **Título de quebra** : Envolve o texto inserido no campo Nome para acomodar a largura do KPI.

## Propriedade avançada

- **Atualização automática quando os cálculos terminam** : Quando o aplicativo exibe uma nota, ele a exibe com os dados calculados que estão disponíveis no momento. Em muitos casos, o aplicativo pode estar calculando novos valores em segundo plano. Se você quiser que os resultados sejam exibidos quando os cálculos forem concluídos, marque essa opção. A opção se aplica somente à tabela selecionada no momento. Essa opção está disponível somente quando a **Política de cálculo** (na caixa de diálogo **Editar projeto** ) de um projeto está definida como **Publicação dinâmica**.

Para obter mais informações sobre como alterar o tipo e a formatação dos KPIs, consulte [Dica: O tipo e o formato influenciam a aparência dos KPIs](https://community.apptio.com/docs/DOC-5400 "(Abre em uma nova guia ou janela)").
