---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Dados de referência do serviço"
breadcrumb: []
source_path: "it-planning/planning/sdp/manage-service-reference.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Dados de referência do serviço

aplica-se a: Planejamento com [Service Demand Planning](gs-service-demand.html). As tarefas abaixo exigem que você licencie o Service Demand Planning e, em seguida, [edite o Company Profile](../edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.") para ativar os recursos do Service Demand Planning . As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

OBSERVAÇÃO : O módulo Service Demand Planning não está mais disponível em Apptio. As informações abaixo são fornecidas para o benefício dos usuários atuais do Service Demand Planning.

As dimensões são as categorias de dados essenciais nos itens de linha do orçamento. Muitas dimensões incorporadas têm dependências de outras dimensões (consulte [Dependências de atributos e dimensões de dados de referência](../manage-reference-data.html) para obter mais informações). Você pode importar dados de referência de dimensões de um arquivo.csv ou do site Costing Standard e exportar modelos de dados de referência de dimensões e dados de tabela (consulte [Gerenciar dimensões](../manage-reference-data.html "(Abre em uma nova guia ou janela)") ).

![imagem](../../../resources/images/it%20planning_images/icon_video.png): Assista a este vídeo do site Apptio Education Services: [Configuração de dados de referência: Service Demand Planning Dimensões](https://community.apptio.com/videos/1996 "(Abre em uma nova guia ou janela)"). Ou veja todos os [recursos de vídeo e treinamento do site Apptio Planning](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Abre em uma nova guia ou janela)") .

## Gerenciar dados de referência da unidade de negócios

Os proprietários de serviços podem usar as unidades de negócios para ajudar a prever a demanda de serviços para outras áreas da organização. Antes de configurar os dados de referência das unidades de negócios, certifique-se de publicar a unidade de medida, as categorias de serviço e as dimensões de serviços (instruções a seguir).

1. No menu de navegação, selecione Configuration > Reference Data (Configuração > Dados de referência ).
2. Selecione a guia Service (Serviço ) na página Reference Data (Dados de referência).
3. Selecione > Unidade de negócios.
4. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
5. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
6. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
7. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualize os valores da tabela de dados conforme necessário:
   - Código (obrigatório) - O identificador exclusivo abreviado da unidade de negócios.
   - Nome (obrigatório) - O nome da unidade de negócios.
   - Código pai - Representa a hierarquia de sua unidade de negócios. Um valor de código pai é o valor de código de sua unidade de negócios pai ou de nível imediatamente superior (se houver).
   - Código do centro de custo - O identificador dos centros de custo correspondentes. Ao importar dados reais, eles são alocados por centro de custo e, em seguida, mapeados para um objeto de custo. Uma unidade de negócios pode ser associada a vários centros de custo e pode incluir itens de linha (volumes, mão de obra ou despesas) registrados para mais de um centro de custo. Adicione vários centros de custo à célula da tabela usando uma vírgula para separá-los.
   - Código da moeda - A moeda comum da unidade de negócios. Necessário quando o suporte a várias moedas estiver ativado. O valor da moeda comum da unidade de negócios deve ser o código ISO de três letras da moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
   - Grupo de preços - Determina o grupo de preços da unidade de negócios para modelos de preços baseados em região ou em camadas.
   - Preço unitário - Define o valor a ser cobrado quando uma unidade de uma unidade de negócios é usada.
8. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > guia Serviço > Unidade de negócios**.
9. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo > Importar.
10. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
11. Para cancelar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Reverter > Reverter**.

## Gerenciar dados de referência do grupo de preços

A dimensão Grupo de preços permite que o administrador configure modelos de preços regionais ou por níveis para seus proprietários de serviços. O Grupo de preços mapeia o provedor e os consumidores, o que ajuda a categorizar os preços de serviços personalizados para regiões ou consumidores. Antes de configurar os dados de referência do Grupo de preços, certifique-se de atualizar a estratégia de preços.

1. No menu de navegação, selecione Configuration > Reference Data (Configuração > Dados de referência ).
2. Selecione a guia Service (Serviço ) na página Reference Data (Dados de referência).
3. Selecione > Grupo de preços. A tabela de dados de referência do Grupo de preços inclui o nome da região ou grupo de consumidores ou provedores ao qual você deseja aplicar um preço específico. Os nomes dos modelos de preços regionais são abreviados como AU, EU e US. Os nomes dos modelos de precificação por camadas são Externo e Interno. Você pode omitir o valor usado para o rótulo Preço base no Perfil da empresa
4. Selecione ![imagem](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
5. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
6. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
7. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualizar departamentos, projetos, unidades de negócios ou serviços relevantes com o grupo de preços.
8. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > guia Serviço > Grupo de preços**.
9. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo > Importar.
10. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
11. Para cancelar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Reverter > Reverter**.

## Gerenciar a unidade de medida nos dados de referência

Os dados de referência da unidade de medida determinam como os volumes de serviços são medidos. Antes de definir os serviços, defina primeiro sua unidade de medida.

1. No menu de navegação, selecione Configuration > Reference Data (Configuração > Dados de referência ).
2. Selecione a guia Service (Serviço ) na página Reference Data (Dados de referência).
3. Selecione > Unidade de medida.
4. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
5. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
6. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
7. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualize os valores da tabela de dados conforme necessário:
   - Código (obrigatório) - O identificador exclusivo abreviado da unidade de negócios.
   - Nome (obrigatório) - O nome da unidade de negócios.
8. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > guia Serviço > Unidade de medida**.
9. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo > Importar.
10. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
11. Para cancelar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Reverter > Reverter**.

## Gerenciar dados de referência do serviço

Serviços, departamentos e projetos são tipos de objetos de custo.

1. Atualize os dados de referência da Unidade de medida para incluir a tabela de dados de referência do Código do serviço. Consulte a seção anterior: "Gerenciar dados de referência da unidade de medida"
2. No menu de navegação, selecione Configuration > Reference Data (Configuração > Dados de referência ).
3. Selecione a guia Service (Serviço ) na página Reference Data (Dados de referência).
4. Selecione > Serviço.
5. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
6. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
7. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
8. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualize os valores da tabela de dados conforme necessário:
   - Código (obrigatório) - O valor exclusivo do serviço.
   - Nome (obrigatório) - O nome do serviço.
   - Código pai - Representa a hierarquia de seus serviços. Um valor de código pai é o valor de código de sua conta pai ou de nível imediatamente superior (se houver). Os serviços listados com um valor de código pai de SC CNC, SC LOB ou SC CC são subordinados aos serviços de computação do cliente, linha de negócios e comunicação e colaboração.
   - Código da moeda - A moeda comum do serviço. Necessário quando o suporte a várias moedas estiver ativado. O valor da moeda comum deve ser o código ISO de três letras da moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
   - Grupo de preços - Determina o grupo de preços do serviço para modelos de preços baseados em região ou em camadas. Deixe em branco para usar o preço original.
   - Estratégia de precificação - O método usado para precificar seu serviço. As opções incluem:
     - Fixo - Um valor a ser cobrado (definido usando a coluna Preço unitário). Essa opção é necessária se você selecionou Fixo como modelo de preço no Perfil da empresa.
     - Dinâmico - Calcule dinamicamente o preço unitário com base na composição do custo do serviço e na demanda. Use essa opção somente se você selecionou Dinâmico como o modelo de preços no Perfil da empresa.
   - Código da unidade - O identificador exclusivo do item a ser quantificado para esse serviço.
   - Preço unitário - O valor a ser cobrado por uma unidade de serviço.
   - Código do centro de custo - O identificador dos centros de custo correspondentes. Ao importar dados reais, eles são alocados por centro de custo e, em seguida, mapeados para um objeto de custo. Um projeto pode ser associado a vários centros de custo e pode incluir itens de linha (volumes, mão de obra ou despesas) registrados em mais de um centro de custo. Adicione vários centros de custo à célula da tabela usando uma vírgula para separá-los.
9. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > guia Serviço > Serviço**.
10. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo > Importar.
11. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
12. Para cancelar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Reverter > Reverter**.

## Gerenciar dados de referência de categorias de serviço

Os dados de referência das categorias de serviço representam a estrutura hierárquica de serviços de sua organização. As categorias de serviço são visíveis no menu Subseção do plano e na página Serviços, Resumo.

1. No menu de navegação, selecione Configuration > Reference Data (Configuração > Dados de referência ).
2. Selecione a guia Service (Serviço ) na página Reference Data (Dados de referência).
3. Selecione > Categorias de serviço.
4. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
5. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
6. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
7. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualize os valores da tabela de dados conforme necessário:
   - Código (obrigatório) - O valor exclusivo da categoria de serviço.
   - Nome (obrigatório) - O nome da categoria de serviço.
   - Código pai - Representa sua hierarquia de categorias de serviço. Um valor de código pai é o valor de código de sua conta pai ou de nível imediatamente superior (se houver). As categorias de serviços com um valor de código pai de SCPS e SCEUCS são subordinadas a essas categorias de serviços.
   - Código da moeda - A moeda comum do serviço. Necessário quando o suporte a várias moedas estiver ativado. O valor da moeda comum deve ser o código ISO de três letras da moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
   - Grupo de preços - Determina o grupo de preços do serviço para modelos de preços baseados em região ou em camadas. Deixe em branco para usar o preço original.
   - Código do centro de custo - O identificador dos centros de custo correspondentes. Ao importar dados reais, eles são alocados por centro de custo e, em seguida, mapeados para um objeto de custo. Um projeto pode ser associado a vários centros de custo e pode incluir itens de linha (volumes, mão de obra ou despesas) registrados em mais de um centro de custo. Adicione vários centros de custo à célula da tabela usando uma vírgula para separá-los.
8. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > guia Serviço > Categorias de serviço**.
9. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo > Importar.
10. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
11. Para cancelar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Reverter > Reverter**.

## Gerenciar dados de referência de ajustes de preços de serviços

Os dados de referência do Service Price Adjustments permitem que você defina regras de precificação para modelos de precificação regional ou por níveis.

1. No menu de navegação, selecione Configuration > Reference Data (Configuração > Dados de referência ).
2. Selecione a guia Service (Serviço ) na página Reference Data (Dados de referência).
3. Selecione > Ajustes de preço de serviço.
4. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
5. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
6. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
7. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualize os valores da tabela de dados conforme necessário:
   - Grupo de preços ao consumidor - Aparece para categorias em camadas de um serviço, como interno ou externo.
   - Moeda - A moeda comum do serviço. Necessário quando o suporte a várias moedas estiver ativado. O valor da moeda comum deve ser o código ISO de três letras da moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
   - Grupo de preços do provedor - Determina o grupo de preços para o provedor de serviços.
   - Valor de ajuste - O preço ou valor percentual para ajustar o valor base. Para oferecer descontos, insira um número negativo. Por exemplo, um valor de -20 é igual a um desconto de US$ 20 ou 20% (dependendo do tipo de ajuste selecionado) na unidade de serviço.
   - Tipo de ajuste - Determina como os ajustes são aplicados. As seguintes opções estão disponíveis:
     - Absoluta - Uma taxa monetária fixa a ser aplicada ao preço unitário básico.
     - Porcentagem - Uma alteração percentual na taxa de preço unitário.
     - Valor - Usado apenas para preços escalonados. Essa é uma taxa monetária fixa a ser aplicada ao preço unitário básico.
8. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > guia Serviço > Ajustes de preço de serviço**.
9. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo > Importar.
10. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Publicar > Publicar**.
11. Para cancelar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > **Reverter > Reverter**.

DICA: Os dados de referência de permissões de objetos de custo determinam quem pode editar cada serviço e quem pode aprovar envios de planos orçamentários. Consulte [os dados de referência de Manage Cost Object Permissions (Gerenciar permissões de objetos de custo](../manage-cost-object.htm "(Abre em uma nova guia ou janela)") ).
