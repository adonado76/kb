---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Dados de referência da configuração do projeto"
breadcrumb: []
source_path: "it-planning/planning/pfp/manage-project-configuration.html"
images:
  - "resources/images/icons/icon-options_23x20.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Dados de referência da configuração do projeto

◆ Aplica-se a: Apptio Planning aplicativos com [Project Financial Planning](gs-project-financial.html "◆ Aplica-se a: Planejamento com planejamento financeiro de projetos."). As tarefas abaixo exigem que você licencie o site Project Financial Planning. Para ativar os recursos do site Project Financial Planning , consulte [Editar o perfil da empresa](../edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.").

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

|  |  |
| --- | --- |
| ícone da câmera | Assista a este vídeo do site Apptio Education Services: [Configuração de dados de referência: Project Financial Planning Dimensions (Dimensões](https://community.ibm.com/community/user/viewdocument/configuring-reference-data-project?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Abre em uma nova guia ou janela)") ). |

## Gerenciar dados de referência do projeto

As dimensões são as categorias de dados essenciais nos itens de linha do orçamento. Muitas dimensões incorporadas têm dependências de outras dimensões (consulte [-](../manage-reference-data.html) para obter mais informações). Você pode importar dados de referência de dimensões de um arquivo.csv ou do site Costing Standard e exportar modelos de dados de referência de dimensões e dados de tabela (consulte [Gerenciar dimensões](../manage-reference-data.html "(Abre em uma nova guia ou janela)") ).

Dica: Os usuários atribuídos à função de administrador têm um atalho para publicar dados de referência do projeto. Na guia Lista da visualização Resumo de todos os projetos, use o botão Ações, comando Publicar em dados de referência. Lembre-se de que, depois que os dados do projeto forem publicados dessa forma, você não poderá reverter para os dados de referência anteriores do projeto. Se você quiser arquivar esses dados, exporte-os para o formato.csv antes de publicá-los dessa forma.

Os projetos são um tipo de objeto de custo. As informações a seguir descrevem os campos das dimensões do projeto.

1. No menu de navegação, selecione Configuration > Reference Data (Configuração > Dados de referência ).
2. Selecione a guia Project (Projeto ) na página Reference Data (Dados de referência).
3. Na tabela Projeto, selecione Projeto.
4. Selecione ![mais opções](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Exportar.
5. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
6. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
7. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualize os valores da tabela de dados conforme necessário:
   - Código - O identificador exclusivo de um projeto.
   - Nome - O nome do projeto.
   - Código pai - Representa a hierarquia do seu projeto. Um valor de código pai é o valor de código de sua conta pai ou de nível imediatamente superior (se houver).
   - Allow Any Cost Center (Permitir qualquer centro de custo ) - Um valor VERDADEIRO permite que você atribua o projeto a qualquer centro de custo. Um valor FALSO tem como padrão o centro de custo atual.
   - Valor do benefício - O valor monetário esperado do projeto concluído. Esse valor e o período do benefício são usados para calcular o retorno sobre o investimento.
   - Período de benefício - O número de meses até que o projeto retorne um benefício monetário. Esse período e o valor do valor do benefício são usados para calcular o retorno sobre o investimento.
   - Código da moeda - A moeda comum do projeto. Esse valor é necessário quando o suporte para várias moedas está ativado no Company Profile (consulte [Suporte para várias moedas](../support-multiple-currencies.html) ). O valor da moeda comum deve ser o código ISO de três letras da moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
   - Descrição - Um resumo do projeto.
   - Duração - O tempo de vida esperado do projeto em número de meses.
   - Est. CapEx (não mão de obra) - O valor estimado das despesas de capital ( CapEx ) para o projeto. Isso é usado para avaliação de demanda versus capacidade.
   - Est. Mão de obra externa - O número estimado de funcionários externos (por exemplo, fornecedores) para o projeto. Isso é usado para avaliação de demanda versus capacidade.
   - Taxa de mão de obra externa estimada - A taxa de pagamento estimada para mão de obra externa para os projetos. Isso é usado para avaliação de demanda versus capacidade.
   - Est. Mão de obra interna - O número estimado de funcionários internos para o projeto. Isso é usado para avaliação de demanda versus capacidade.
   - Est. Taxa de mão de obra interna - A taxa de pagamento estimada para a mão de obra interna do projeto. Isso é usado para avaliação de demanda versus capacidade.
   - Est. Capitalização da mão de obra - A taxa estimada de capitalização da mão de obra interna e externa para o projeto. Isso é usado para avaliação de demanda versus capacidade.
   - Est. OpEx (não mão de obra) - O valor estimado das despesas operacionais ( OpEx ) para o projeto. Isso é usado para avaliação de demanda versus capacidade.
   - Classificação do grupo - Um valor numérico que indica a classificação relativa do projeto entre todos os grupos de projetos.
   - Grupo de preços - Determina o grupo de preços do projeto para modelos de preços baseados em região ou em camadas.
   - Gerente de projeto - O gerente de projeto designado. Escolha entre as contas de usuário definidas em Enhanced Access Administration.
   - Status do projeto - Valor do status do projeto.
   - Classificação - Um valor numérico que indica a classificação relativa do projeto entre todos os projetos.
   - Pontuação - Um valor numérico que indica a pontuação geral relativa do projeto entre todos os grupos de projetos.
   - Pontuação substituída - Essa dimensão é usada na exportação e importação de dados de referência do projeto. Ao exportar dados, essa dimensão indica se o valor de Pontuação foi calculado automaticamente (valor Falso) ou substituído manualmente (Verdadeiro). Ao importar dados, True significa que o valor da pontuação substituirá qualquer valor calculado automaticamente. False significa ignorar o valor de Score carregado e, em vez disso, calcular automaticamente um valor.
   - Data de início - A data de início planejada para o projeto.
   - Código do centro de custo - O identificador dos centros de custo correspondentes. Ao importar os dados reais, eles são alocados por centro de custo e, em seguida, mapeados para o objeto de custo. Um projeto pode ser associado a vários centros de custo e pode incluir itens de linha (volumes, mão de obra ou despesas) registrados em mais de um centro de custo. Adicione vários centros de custo à célula da tabela usando uma vírgula para separá-los.
8. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > Projeto**.
9. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo **> Importar**.
10. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Publicar > Publicar.
11. Para cancelar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Reverter > Reverter.

Os dados de referência Permissões de objetos de custo determinam quem pode editar cada projeto e quem pode aprovar os envios de planos orçamentários.

## Gerenciar dados de referência do grupo de projetos

Os dados de referência do Grupo de Projetos representam a estrutura hierárquica de projetos de sua organização. Os grupos de projetos são visíveis no menu Subseção do plano e na página Resumo dos projetos.

1. No menu de navegação, selecione Configuration > Reference Data (Configuração > Dados de referência ).
2. Selecione a guia Project (Projeto ) na página Reference Data (Dados de referência )
3. Na tabela Projeto, selecione Grupo de projetos.
4. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Exportar.
5. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
6. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
7. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualize os valores da tabela de dados conforme necessário:
   - Código - O identificador exclusivo do grupo de projetos.
   - Nome - O nome do grupo de projetos.
   - Código pai - Representa a hierarquia dos grupos de projetos. Um valor de código pai é o valor de código de sua conta pai ou de nível imediatamente superior (se houver).
   - Código da moeda - A moeda comum do grupo de projetos. Esse valor é necessário quando o suporte a várias moedas está ativado no perfil da empresa. O valor da moeda comum deve ser o código ISO de três letras da moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
   - Grupo de preços - Determina o grupo de preços do projeto para modelos de preços baseados em região ou em camadas.
   - Código do centro de custo - O identificador dos centros de custo correspondentes. Ao importar os dados reais, eles são alocados por centro de custo e, em seguida, mapeados para um objeto de custo. Um projeto pode ser associado a vários centros de custo e pode incluir itens de linha (volumes, mão de obra ou despesas) registrados em mais de um centro de custo. Adicione vários centros de custo à célula da tabela usando uma vírgula para separá-los.
8. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > Grupo de projetos**.
9. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo **> Importar**.
10. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Publicar > Publicar.
11. Para cancelar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Reverter > Reverter.

## Gerenciar dados de referência de tipos de atividade

A dimensão Tipos de atividade é usada por Labor Activity Planning. Consulte o [recurso Acesso antecipado: Planejamento de atividades trabalhistas](../labor-activity-planning.html "Os aplicativos de planejamento Apptio 2.45 versão de 20 de março de 2019 introduziram um modo alternativo para o planejamento de mão de obra do projeto chamado Labor Activity Planning. O administrador ou o proprietário do processo orçamentário pode tornar os recursos de planejamento de atividades de mão de obra visíveis na interface."). Essa dimensão é usada para associar itens de linha de alocação e demanda a um tipo de atividade.

1. No menu de navegação, selecione Configuration > Reference Data (Configuração > Dados de referência ).
2. Selecione a guia Standard Dimensions (Dimensões padrão ) na página Reference Data (Dados de referência ).
3. Selecione > Tipos de atividade.
4. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Exportar.
5. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
6. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
7. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualize os valores da tabela de dados conforme necessário:
   - Nome - Descreve a natureza do trabalho para a atividade.
   - É capitalizável - Identifica a atividade como uma atividade capitalizável.
   - Conta de transferência - O código da conta do registro geral do projeto a partir do qual o custo da atividade é debitado.
   - Conta de transferência - O código da conta do registro geral do departamento no qual o custo da atividade é creditado.
8. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > Grupo de projetos**.
9. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo **> Importar**.
10. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Publicar > Publicar.

## Gerenciar os dados de referência das taxas de atividade de trabalho do departamento

A dimensão Department Labor Activity Rates é usada pelo site Labor Activity
Planning. Consulte o [recurso Acesso antecipado: Planejamento de atividades de trabalho](../labor-activity-planning.html "Os aplicativos de planejamento Apptio 2.45 versão de 20 de março de 2019 introduziram um modo alternativo para o planejamento de mão de obra do projeto chamado Labor Activity Planning. O administrador ou o proprietário do processo orçamentário pode tornar os recursos de planejamento de atividades de mão de obra visíveis na interface."). Essa dimensão é usada para definir uma taxa de mão de obra para funções específicas.

1. No menu de navegação, selecione Configuration > Reference Data.
2. Selecione a guia Standard Dimensions (Dimensões padrão ) na página Reference Data (Dados de referência ).
3. Selecione as taxas de atividade trabalhista do departamento.
4. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Exportar.
5. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
6. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
7. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualize os valores da tabela de dados conforme necessário:
   - Departamento - O identificador exclusivo do departamento.
   - Centro de custo - O identificador dos centros de custo correspondentes.
   - Tipo de funcionário - Um recurso de trabalho interno ou externo (como fornecedores ou prestadores de serviços).
   - Função - As opções disponíveis para essa dimensão são fornecidas pelos dados de referência das funções.
   - Moeda - A moeda comum para alocação de atividade de trabalho. Necessário quando o suporte a várias moedas estiver ativado (consulte [Suporte a várias moedas](../support-multiple-currencies.dita "(Abre em uma nova guia ou janela)") ). O valor da moeda comum do Departamento deve ser o código ISO de três letras para a moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
   - Taxa de trabalho - A taxa de remuneração por hora padrão.
8. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > Taxas de atividade de trabalho do departamento**.
9. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo **> Importar**.
10. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Publicar > Publicar

## Gerenciar os dados de referência das taxas de atividade de trabalho do projeto

A dimensão Taxas de atividade de trabalho do projeto é usada pelo site Labor Activity
Planning. Consulte o [recurso Acesso antecipado: Planejamento de atividades trabalhistas](../labor-activity-planning.html "Os aplicativos de planejamento Apptio 2.45 versão de 20 de março de 2019 introduziram um modo alternativo para o planejamento de mão de obra do projeto chamado Labor Activity Planning. O administrador ou o proprietário do processo orçamentário pode tornar os recursos de planejamento de atividades de mão de obra visíveis na interface."). Essa dimensão é usada para definir uma taxa de trabalho para atividades de trabalho específicas.

1. No menu de navegação, selecione Configuration > Reference Data.
2. Selecione a guia Standard Dimensions (Dimensões padrão ) na página Reference Data (Dados de referência )
3. Selecione Taxas de atividade de trabalho do projeto.
4. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Exportar.
5. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
6. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
7. Abra o arquivo.csv baixado. Não altere os títulos das colunas ou a estrutura de dados do arquivo. Atualize os valores da tabela de dados conforme necessário:
   - Função - As opções disponíveis para essa dimensão são fornecidas pelos dados de referência das funções.
   - Fornecedor - As opções disponíveis para essa dimensão são fornecidas pelos dados de referência do fornecedor.
   - Moeda - A moeda comum para alocação de atividade de trabalho. Necessário quando o suporte a várias moedas estiver ativado (consulte [Suporte a várias moedas](../support-multiple-currencies.dita "(Abre em uma nova guia ou janela)")). O valor da moeda comum do Departamento deve ser o código ISO de três letras para a moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
   - Taxa de trabalho - A taxa de remuneração por hora padrão.

     OBSERVAÇÃO : As taxas de atividade de trabalho do projeto são diferentes da remuneração salarial dos recursos. A taxa de atividade definida se aplica a uma atribuição de recurso a uma atividade em um projeto (e não à remuneração base desse recurso específico). Os dois valores podem ser (e provavelmente serão) diferentes.
8. Salve o arquivo no formato.csv. Agora, selecione **Configuração > Dados de referência > Taxas de atividade de trabalho do projeto**.
9. Selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Importar. Arraste e solte o arquivo com os dados na área destacada da janela Importar arquivo **> Importar**.
10. Para publicar as alterações, selecione ![mais ícone](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Publicar > Publicar

Consulte [Gerenciar configuração de pontuação](score-manage.html) para obter mais informações sobre o gerenciamento de pontuação aplicável a projetos.
