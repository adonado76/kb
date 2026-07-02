---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Criar um projeto"
breadcrumb:
  - "Costing Standard"
  - "Configuração"
source_path: "cost-transparency/configuration/config-create.html"
images:
  - "resources/images/studio_images/2a.png"
  - "resources/images/studio_images/4a.png"
  - "resources/images/studio_images/ad1.png"
  - "resources/images/studio_images/ad6.png"
  - "resources/images/studio_images/config1.png"
  - "resources/images/studio_images/config2b.png"
  - "resources/images/studio_images/config6.png"
  - "resources/images/studio_images/da.png"
  - "resources/images/studio_images/load4a.png"
  - "resources/images/studio_images/load6.png"
  - "resources/images/studio_images/load7.png"
  - "resources/images/studio_images/load9.png"
  - "resources/images/studio_images/lod2a.png"
  - "resources/images/studio_images/map3.png"
  - "resources/images/studio_images/mapcol2.png"
  - "resources/images/studio_images/master2.png"
  - "resources/images/studio_images/pt1.png"
  - "resources/images/studio_images/pt3.png"
  - "cost-transparency/configuration/clip_image002_-1253255458.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Criar um projeto

Os projetos agrupam conjuntos de dados, métricas, modelos e relatórios. Ao criar um novo projeto, você pode escolher entre estes tipos principais: Padrão de Custeio, Personalizado. Você pode criar vários projetos

1. Acesse o TBM Studio
   1. Faça login em **IBM Apptio**.
   2. No iniciador de aplicativos, selecione **TBM Studio**.
   3. Certifique-se de que possui as permissões necessárias (normalmente, de administrador)

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/config1.png)
2. **Passo 2: Criar um novo projeto**
   1. No TBM Studio, navegue até o ícone ![](../../../../../03-media/apptio-costing-standard/cost-transparency/configuration/clip_image002_-1253255458.png) **Configurações** no canto superior direito.
   2. Clique em **Novo Projeto**.

      ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/config2b.png)
   3. **Uma caixa de diálogo Novo projeto será aberta.**
   4. Insira um **nome para o projeto** que identifique claramente o objetivo (por exemplo, *Padrão de Custos* ACME).
   5. Em seguida, escolha um **Tipo de Projeto**
   6. Clique em **Criar**.

      ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/config6.png)

## Tipo de projeto

Ao criar um novo projeto, você tem duas opções:

- **Crie um projeto de aplicativo.** Os projetos de aplicação servem como modelos para novos projetos. Quando você cria um projeto de aplicativo, o aplicativo cria automaticamente conjuntos de dados, métricas, modelos e relatórios com base no modelo do aplicativo. Os modelos de aplicação incluem: Transparência de custos para o padrão de custos, Fundamentos de custos para o projeto Essentials
- **Crie um projeto personalizado.** Um projeto em branco não possui conjuntos de dados, modelos, métricas ou relatórios. Crie um novo projeto personalizado se não quiser continuar o trabalho anterior. Isso inclui: Personalizado (Plataforma, v120+ )

Observação: os projetos Costing Essentials e Custom (Plataforma, v200+ ) são licenciados separadamente.

Para obter mais informações sobre configurações adicionais do projeto, clique [aqui.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-about-studio-project "(Abre em uma nova guia ou janela)")

## Configurar horário

O tempo do projeto define as datas de início e término de um projeto e o tipo de períodos que serão utilizados.

Em um projeto com prazo definido, as datas de início e término são definidas para os dados e o ano fiscal é definido. Em um projeto com tempo definido, você pode inserir dados regularmente, alocá-los a um período específico e ver as tendências ao longo da duração do projeto. Você pode visualizar os dados do relatório do mês ou período atual, ou de períodos trimestrais, semestrais ou anuais. O aplicativo suporta calendários gregorianos, 445, 454, 544 e 13 períodos.

Para obter mais informações sobre como a IBM Apptio apoia projetos com prazo determinado, clique [aqui.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-enable-time-project "(Abre em uma nova guia ou janela)")

**Defina o prazo do projeto**

1. No estúdio da TBM.
2. Clique na guia Projeto na faixa de opções.
3. Clique em Configurações de tempo. A caixa de diálogo Configurar definições de tempo do projeto é exibida conforme mostrado abaixo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/pt3.png)
4. Selecione um período de início do projeto e um período de término do projeto. Selecione as datas que incluem os dados históricos que você importará para o projeto.

   Observação: depois de definir a data de início do projeto, não será possível alterá-la. No entanto, você pode alterar a data de término do projeto.
5. Configure quaisquer outras definições de tempo adequadas ao seu projeto.
6. Clique em Configurar hora.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/pt1.png)

Para obter mais detalhes sobre as opções de calendário disponíveis e como configurá-las, clique [aqui.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-configure-project-time-settings "(Abre em uma nova guia ou janela)")

## Instalando Componentes

Um componente do aplicativo Costing Standard reúne relatórios e métricas para fornecer insights sobre o seu negócio. Um componente também pode instalar uma ou mais tabelas de modelos em seu projeto

****Instalar um componente****

1. Verifique se você está no início do tempo em seu projeto.
2. Na guia Projeto, clique em **Componentes**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/2a.png)
3. Na área Disponível da tela Configuração de Componentes, clique no ícone que corresponde ao componente que você deseja instalar.
4. Na página de detalhes do componente, clique em **Instalar**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/4a.png)

Observação: não é possível desinstalar um componente depois que ele tiver sido instalado. Você pode desativar um componente que remove os relatórios associados, mas mantém as tabelas e métricas.

Depois de instalar todos os componentes no Costing Standard, todos os relatórios de nível superior serão adicionados. Se o cliente não quiser visualizar nenhum desses relatórios de nível superior, ele terá que criar um projeto personalizado ou poderá desativar os relatórios individualmente.

**Carregar dados**

As tabelas de dados mestre oferecem uma maneira de mapear seus dados para os dados exigidos pelo aplicativo CT.

Cada componente do Padrão de Cálculo de Custos (CT) possui uma tabela de dados mestre. A tabela de dados mestre fornece estrutura aos dados relacionados. Relatórios, alocações e outros itens de configuração estão vinculados à estrutura da tabela de dados mestre. Você não carrega dados diretamente nas tabelas de dados mestre. Em vez disso, você anexa ou mapeia os dados (usando a etapa Mapear no pipeline de dados) às tabelas. Isso garante que a estrutura das tabelas de dados mestre não seja alterada.

Você deve carregar seus dados de origem no aplicativo. Depois de carregar os dados, você pode mapeá-los para a tabela de dados mestre de um componente. As tabelas de dados que você carregar devem conter campos que possam ser mapeados para os campos obrigatórios nas tabelas de dados mestre. As tabelas de dados não precisam conter todos os campos das tabelas de dados mestre.

Para obter mais detalhes sobre os tipos de dados que podem ser carregados e os diferentes métodos disponíveis para carregar dados, clique [aqui.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload "(Abre em uma nova guia ou janela)")

O procedimento geral para carregar uma tabela de origem é apresentado abaixo:

1. Clique na guia **Página inicial** na faixa de opções.
2. Clique no menu **Novo** e, em seguida, clique em **Tabela**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/lod2a.png)
3. Na caixa de diálogo Criar tabela, insira um nome para a tabela.
4. Insira uma categoria. À medida que você começa a digitar, os nomes das categorias correspondentes que já existem serão exibidos. Além disso, você pode inserir um novo nome de categoria. As categorias são usadas para organizar as tabelas no Explorador de Projetos.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load4a.png)
5. Clique em **OK**. O aplicativo cria a tabela e exibe a etapa Origem no pipeline de transformação, conforme mostrado abaixo.
6. Clique na opção “**Upload de arquivo** ”. Para obter mais informações sobre outras opções, clique [aqui](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload "(Abre em uma nova guia ou janela)").

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load6.png)
7. Será criada uma etapa de upload onde o usuário poderá clicar/arrastar o arquivo ou clicar com o botão direito do mouse para colar o arquivo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load7.png)
8. Uma etapa de importação é adicionada ao pipeline.
9. Clique na etapa **Importar** no pipeline e revise as configurações:
   - Iniciar importação na linha - Indique a primeira linha da tabela a ser incluída na importação.
   - Colunas a excluir - Indique se há colunas que deseja excluir.
   - Codificação de texto - Se o arquivo de dados usar uma codificação de caracteres específica, selecione o esquema de codificação na lista. Se você não tiver certeza sobre a codificação, selecione a opção Detectar automaticamente a codificação.
   - Delimitado - Selecione o caractere que separa os campos de dados no arquivo. Na maioria das vezes, será uma vírgula.
   - Qualificador de texto - Se houver caracteres de texto especiais nos dados, indique o qualificador de texto usado para envolver esses caracteres.
   - Colunas - Revise as colunas listadas à direita e, se desejar, altere os tipos de coluna. Para filtrar por tipo de coluna (chave, texto, número, data), clique em um ícone de tipo no campo de pesquisa da coluna Tipo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load9.png)
10. Para revisar a tabela carregada, clique na etapa **Tabela** no pipeline.
11. Se a tabela estiver aceitável, clique em **Salvar** na faixa de opções.
12. Quando terminar as edições, clique em **Check-in** na faixa de opções. Para mais informações sobre check-in e check-out, clique [aqui.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-best-practices-check-out-check-in "(Abre em uma nova guia ou janela)")

Para obter mais detalhes sobre funcionalidades adicionais relacionadas ao upload de tabelas, clique [aqui.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload-file "(Abre em uma nova guia ou janela)")

**Excluir uma tabela**

1. Confira a tabela.
2. Na guia **Página inicial**, no grupo **Documento**, clique em **Excluir**.
3. Verifique na tabela.

## Mapeie os dados para os dados mestres

Depois de carregar uma tabela de dados de origem e transformá-la, se necessário, você pode mapeá-la para uma tabela de dados mestre. Use as instruções a seguir para mapear dados para uma tabela de dados mestre.

Existem dois métodos disponíveis para mapear dados para conjuntos de dados mestres:

- Colunas do mapa (preferencial)
- Anexar tabelas

**Colunas do mapa**

O método principal (e preferencial) para mapear dados é usar o recurso Map Columns.The O recurso Map Columns destina-se a transformar seu conjunto de dados de origem.

Se os dados forem reutilizados para vários conjuntos de dados mestres, crie uma nova tabela usando a fonte da tabela existente para cada conjunto de dados mestres e, em seguida, adicione colunas de mapeamento.

**Adicione a etapa do pipeline Map Columns e escolha um destino**

1. Crie ou verifique uma tabela e adicione dados à tabela. Além disso, você pode aplicar etapas de pipeline transformadoras, como Partição por data.
2. Passe o cursor sobre as etapas do pipeline e clique **em +** para adicionar uma nova etapa ao pipeline. **As colunas do mapa** ficam disponíveis, a menos que haja uma etapa Modelo adicionada.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/mapcol2.png)

   Observação: se a tabela foi revertida e o upload de dados não, a etapa não estará disponível até que você adicione qualquer outra etapa e, em seguida, adicione Colunas do mapa.
3. Clique em **Colunas do mapa** e selecione um destino. Se você não encontrar o conjunto de dados mestre que esperava, vá para **Componentes** e instale o componente necessário.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/map3.png)

## Mapeie para uma coluna do conjunto de dados mestre

1. Revise as colunas de destino. Estas são as colunas nos conjuntos de dados mestres que podem ser mapeadas. Alguns podem já estar mapeados porque um cabeçalho de coluna na sua tabela corresponde a um valor esperado no destino.
2. Selecione **Escolher fonte** na coluna Fonte ou, para alterar um mapeamento, selecione um dos outros valores nessa coluna.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/master2.png)
3. Selecione um dos nomes das colunas na lista suspensa. Esta lista mostra todas as colunas da tabela com um tipo de coluna correspondente ao destino.

   Observação: a tabela de pré-visualização a seguir não será atualizada até que a alteração seja salva.

   Dica: se você não encontrar as colunas desejadas na lista suspensa, elas podem não ser do tipo compatível com o destino. Vá para a etapa Importar e altere a opção Substituição de tipo conforme necessário. Se a coluna esperada foi criada no pipeline de transformação, use ou altere a etapa Fórmulas.
4. Para inserir uma sequência de caracteres ou um número para todas as linhas, selecione **Insira um valor fixo para todas as linhas**. Como resultado, todas as linhas da tabela mostram o mesmo valor para essa coluna. Esta opção não avalia fórmulas. Para usar uma fórmula, adicione a etapa **Fórmulas** e, em seguida, mapeie a coluna adicional resultante.
5. Insira o valor e clique **em OK**. Agora você mapeou duas colunas adicionais para o conjunto de dados mestre, selecionando uma coluna da sua tabela e inserindo um valor.

**Adicionar uma coluna personalizada ao conjunto de dados mestre**

1. Para adicionar uma coluna que não existe no conjunto de dados mestre, clique em **Adicionar coluna personalizada**. Essas adições serão mantidas entre as atualizações sem nenhuma ação especial.
2. Digite o nome da coluna que deseja adicionar e escolha o tipo. Selecione uma fonte para essa coluna, escolhendo outra coluna na tabela ou um valor fixo.
3. Clique em **OK**. As colunas adicionadas são sempre opcionais. Salve a tabela para ver a coluna na pré-visualização.

**Anexar dados**

Este método é menos preferível porque personaliza o conjunto de dados mestres, o que aumenta o tempo de atualizações para receber novos conteúdos.

1. No **Project Explorer**, clique na tabela de dados mestre desejada.
2. Confira a tabela.
3. No pipeline de transformação, clique na etapa **Anexar**.
4. Clique em **Anexar tabela** na área de detalhes.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ad1.png)
5. Selecione uma tabela de dados de origem e clique em **Avançar.**
6. Mapeie as colunas de origem para as colunas do conjunto de dados mestre usando o seguinte **Adicionar a...** Imagem dos dados mestres.

   Observação: um asterisco (\*) na coluna Dados Mestres indica que o campo é obrigatório para preencher completamente os relatórios relacionados a esse conjunto de dados. O mapeamento parcial é permitido. Se você não tiver todos os dados necessários, poderá mapear um subconjunto dos campos obrigatórios, embora isso possa resultar na perda de dados em um ou mais relatórios.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ad6.png)
7. Clique em Save.

## Validar alocações do modelo

Use a visualização da tabela do modelo para validar o fluxo de valor em um modelo. Depois de carregar e mapear os dados de origem para a tabela de dados mestre apropriada, as tabelas modeladas associadas devem começar a mostrar os impulsionadores unitários e as alocações.

Uma tabela modelada pelo Padrão de Custeio é uma tabela à qual foi adicionada uma etapa Modelo. A tabela modelada é uma transformação de uma tabela de dados mestre. Por exemplo, a tabela Origem de custos é uma transformação da tabela Dados mestre de origem de custos. Não é possível adicionar etapas adicionais ao pipeline de transformação às tabelas modeladas pelo Padrão de Custeio. As únicas etapas de transformação exibidas para tabelas modeladas são **Origem** e **Modelo**.

**Diagrama de alocação de motoristas**

Se você clicar em uma tabela de modelo no **Project Explorer** e, em seguida, clicar na etapa Model no pipeline de transformação, um diagrama de alocação de driver será exibido, conforme mostrado abaixo. Use o diagrama para verificar o fluxo de valor de e para a tabela.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/da.png)

O diagrama mostra o fluxo de valor para a métrica do modelo selecionada no campo **Selecionar uma métrica** acima do diagrama. Na Figura A acima, a métrica é Custo. Você pode selecionar qualquer uma das métricas do modelo definidas para o projeto.

**Faça alterações**

Você pode fazer alterações nas alocações no modelo padrão de cálculo de custos. Você pode modificar as alocações existentes e adicionar novas alocações. Antes de fazer alterações em um modelo, você deve entender completamente como criar e modificar modelos.

Para obter informações sobre como trabalhar com modelos, consulte [Sobre o Model Studio.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-about-model-studio "(Abre em uma nova guia ou janela)")

## Instalando novas soluções de cálculo de custos IBM Apptio em projetos de modelos mais antigos

Use a página existente - https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=configuration-installing-new-apptio-costing-solutions-older-template-projects
