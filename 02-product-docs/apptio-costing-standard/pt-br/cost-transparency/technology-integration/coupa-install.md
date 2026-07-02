---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Instale e configure o Vendor Insights usando os dados da Coupa"
breadcrumb:
  - "Costing Standard"
  - "Integrações tecnológicas"
  - "Informações sobre fornecedores Coupa"
  - "Informações sobre fornecedores Coupa Introdução"
source_path: "cost-transparency/technology-integration/coupa-install.html"
images:
  - "resources/images/vi_images/vi/coupa/coupa5.jpg"
  - "resources/images/vi_images/vi/coupa/coupa6.jpg"
  - "resources/images/vi_images/vi/coupa/coupa7.jpg"
  - "resources/images/vi_images/vi/coupa/coupa_8.jpg"
  - "resources/images/vi_images/vi/coupa/coupa_9.jpg"
  - "resources/images/vi_images/vi/coupa/coupa__10.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Instale e configure o Vendor Insights usando os dados da Coupa

**Visão geral**

Este documento fornece instruções para a TBMA implementar Vendor Insights usando os dados Coupa do Conector Coupa Datalink (Classic).

**Pré-requisitos**

Antes de instalar Vendor Insights os componentes, você deve ter:

1. TBM Studio 12.6.1 e Datalink (Classic) 4.8 (Build 11122 ou superior). Se você não estiver executando a versão correta ou tiver dúvidas sobre a versão que está executando, entre em contato com o suporte ao cliente Apptio para obter ajuda.
2. Um projeto TBM Studio novo ou existente dedicado a Vendor Insights existe com configurações de tempo definidas, verificadas e calculadas no ambiente de desenvolvimento. **DICA** : Siga o mesmo período de tempo usado em Costing Standard ou crie um período de tempo que comece no início do ano atual.
   - Se você deseja Vendor Insights que seja um produto independente, crie um novo tipo de projeto personalizado. Caso contrário, você pode instalar o Vendor Insights componente em um projeto existente.
3. O Coupa foi configurado para Apptio. Para saber mais, [consul](coupa-configure-data.html) te Configurar o Coupa para o Apptio. Caso contrário, os seguintes campos não estarão disponíveis no Conector Coupa Datalink (Classic) :
   - **Torre de TI** - Dados Mestres do Fornecedor
   - **Subtorre de TI** - Dados mestre do fornecedor
   - **Pool de custos** - Dados mestre de contas a pagar, dados mestre de pedidos de compra
   - **Subconjunto de custos** - Dados mestre de contas a pagar, dados mestre de pedidos de compra
4. O Conector Coupa do Datalink (Classic) foi configurado e executado para os dados iniciais e delta dos seguintes objetos Coupa. A saída de cada um dos conectores Coupa deve ser colocada na pasta`z_Coupa_Raw` em TBM Studio . Para saber mais, consulte[Configure os dados do Vendor Insights Coupa para Apptio](config-coupa.html).   
   Isso resulta nas seguintes tabelas:  

   | Objeto Coupa | Modo de recuperação | Catálogo | Exemplo de nome da tabela de saída |
   | --- | --- | --- | --- |
   | Fornecedores | Dados  iniciais Delta Data | z\_Coupa\_Rawz\_Coupa\_Raw | Coupa\_Fornecedor\_Inicial\_RawCoupa\_Fornecedor\_Delta\_Raw |
   | Contratos | Dados  iniciais Delta Data | z\_Coupa\_Rawz\_Coupa\_Raw | Contrato Coupa Inicial Bruto Contrato  Coupa Delta Bruto |
   | Ordens de Compra | Dados  iniciais Delta Data | z\_Coupa\_Rawz\_Coupa\_Raw | Coupa\_PO\_Inicial\_RawCoupa\_PO\_Delta\_Raw |
   | Linhas de ordem de compra | Dados  iniciais Delta Data | z\_Coupa\_Rawz\_Coupa\_Raw | Coupa\_PO\_Linha\_Inicial\_RawCoupa\_PO\_Linha\_Delta\_Raw |
   | Contas de linha de ordem de compra | Dados  iniciais Delta Data | z\_Coupa\_Rawz\_Coupa\_Raw | Coupa\_PO\_Linha\_Conta\_Inicial\_RawCoupa\_PO\_Linha\_conta\_Delta\_Raw |
   | Faturas | Dados  iniciais Delta Data | z\_Coupa\_Rawz\_Coupa\_Raw | Coupa\_Fatura\_Inicial\_BrutaCoupa\_Fatura\_Delta\_Bruta |
   | Linhas da fatura | Dados  iniciais Delta Data | z\_Coupa\_Rawz\_Coupa\_Raw | Coupa\_Fatura\_Linha\_Inicial\_RawCoupa\_Fatura\_Linha\_Delta\_Raw |
   | Contas de linhas de fatura | Dados  iniciais Delta Data | z\_Coupa\_Rawz\_Coupa\_Raw | Coupa\_Fatura\_Linha\_Conta\_Inicial\_RawCoupa\_Fatura\_Linha\_Conta\_Delta\_Raw |

**Instruções**

**Tarefa 1: Instalar os Vendor Insights componentes**

1. Abra o projeto no Studio.
2. Clique **na** guia Projeto.
3. **ClickComponentes**.
4. Clique em**Vendor Insights Fundação** e, em seguida**, clique em Instalar**.
5. Clique em**Vendor Insights PO** e, em seguida**, clique em Instalar**.
6. Clique em**Vendor Insights Contratos** e, em seguida**, clique em Instalar**.
7. Verifique seu projeto.

Pode ser necessário atualizar as configurações de visibilidade na Administração do Access para visualizar o Vendor Insights projeto e os relatórios.

**Tarefa 2: Mapeie as tabelas de transformação do Coupa para os conjuntos Vendor Insights de dados principais.**

Anexe as seguintes tabelas de transformação aos conjuntos de dados Vendor Insights principais. Como os nomes dos campos nas tabelas de transformação são idênticos aos dos conjuntos de dados Vendor Insights principais, os nomes dos campos são mapeados automaticamente entre si (salvo indicação em contrário).

Você mapeará as seguintes Vendor Insights tabelas para as tabelas associadas do Coupa Transform:

| Vendor Insights mesa | Tabela de transformação da Coupa |
| --- | --- |
| Dados mestre do fornecedor | Coupa\_Transformar\_Fornecedor |
| Dados mestre de contas a pagar | Coupa\_Transformar\_Fatura |
| Dados mestre de ordens de compra | Coupa\_Transformar\_PO |
| Dados principais dos contratos | Coupa\_Transformar\_Contrato |
| Ordem de compra para dados mestre do contrato | Coupa\_Transformar\_PO-em-Contrato |

  

Para os campos de exceção, nada precisa ser mapeado.

**Tarefa 2.1: ar dados mestre do fornecedor**

Mapeie os seguintes campos de dados mestres para os **campos Coupa\_Transform\_Supplier** associados:

| Campo de dados mestre | Campo Coupa\_Transformar\_Fornecedor |
| --- | --- |
| **ID do fornecedor principal** | `=Parent Vendor ID` |
| **Nome do fornecedor principal** | `=Parent Vendor Name` |
| **Contrato de fornecedor** | `=Vendor Contact` |
| **Descrição do fornecedor** | `=Vendor Description` |
| **Nome do fornecedor** | `=Vendor Name` |
| **Serviço de fornecedores** | `=Vendor Service` |

**2.2: de tarefas Dados mestre de contas a pagar**

Mapeie os seguintes campos de dados mestres para os **campos Coupa\_Transform\_Invoice** associados:

| Campo de dados mestre | Campo Coupa\_Transform\_Invoice |
| --- | --- |
| **Conta** | `=Account` |
| **Descrição da conta** | `=Account Description` |
| **Identificação de contas a pagar** | `=Vendor Contact` |
| **Centro de Custos** | TBD |
| **Nome do centro de custos** | `=Cost Center Name` |
| **Responsável pelo centro de custos** | `=Cost Pool` |
| **Subgrupo de custos** | `={Cost Sub-Pool}` |
| **Departamento** | `=Department` |
| **Descrição do departamento** | `=Department Description` |
| **Descrição** | `=Description` |
| **Data da fatura** | `=Invoice Date Orig` |
| **Número da Fatura** | `=Invoice Number` |
| **Valor monetário** | `=Monetary Amount` |
| **Número do pedido de compra** | `=Purchase Order Number` |
| **ID do Fornecedor** | `=Vendor ID` |
| **Metacampo chave do fornecedor** | `=Vendor ID` |
| **Nome do fornecedor** | `=Vendor Name` |

**2.3: de tarefas Dados mestre de pedidos de compra**

Mapeie os seguintes campos de dados mestres para os **campos associados Coupa\_Transform\_PO** :

| Campo de dados mestre | Campo Coupa\_Transform\_PO |
| --- | --- |
| **Quantia** | `Amount` |
| **Centro de Custos** | `Cost Center` |
| Nome do centro de custos | `Cost Center Name` |
| **Responsável pelo centro de custos** | `Cost Center Owner` |
| **Departamento** | `Department` |
| **Descrição do departamento** | `Department Description` |
| **Valor monetário anterior** | `Prior Monetary Amount` |
| **Data do pedido de compra** | `Purchase Order Date` |
| **Descrição do pedido de compra** | `Purchase Order Description` |
| **Número do pedido de compra** | `Purchase Order Number` |
| **Status do pedido de compra** | `Purchase Order Status` |
| **Solicitante** | `Requester` |
| **ID do Fornecedor** | `Vendor ID` |
| **Nome do fornecedor** | `Vendor Name` |

**2.4: ar contratos de tarefas Dados mestre**

Mapeie os seguintes campos de dados mestres para os **campos Coupa\_Transform\_Contracts** associados:

| Campo de dados mestre | Campo Coupa\_Transform\_Contracts |
| --- | --- |
| **Valor do contrato** | `=Contract Amount` |
| **Descrição do contrato** | `=Contract Description` |
| **ID do contrato** | `=Contract Number` |
| **Número do contrato** | `=Contract Number` |
| **Titular do contrato** | `=Contract Owner` |
| **E-mail do proprietário do contrato** | `=Contract Owner Email` |
| **Título do contrato** | `=Contract Title` |
| **Número do centro de custos** | `=Contract Title` |
| **Título do contrato** | `=Cost Center Number Lookup` |
| **Pool de custos** | � |
| **Subgrupo de custos** | � |
| **Data de Término** | `=Contract End Date` |
| **Função** | � |
| **Gasto mínimo comprometido** | `Minimum Committed Spend` |
| **Contrato dos Pais** | `Parent Contract` |
| **Planos de renovação** | `Renewal Plans` |
| **Data de Início** | `=Contract Start Date` |
| **Estado** | `=Status` |
| **ID do Fornecedor** | `=Vendor ID` |
| **Gerente de fornecedores** | `=Vendor Manager` |
| **Nome do fornecedor** | `=Vendor Name` |
| **Tipo de fornecedor** | `=Vendor Type` |
| **Dias de notificação do contrato** | `=Contract Notify Days` |

  

**2.5: e de tarefas PO para dados mestre do contrato**

Mapeie os seguintes campos de dados mestre para os campos associados **Coupa\_Transform\_PO-to-Contract** :

- **ID do contrato**`=Contract ID`
- **Número do pedido de compra**`=Purchase Order Number`

**Tarefa 3: Configurar o componente Vendor Insights Foundation**

O componente Vendor Insights Fundação contém os conjuntos de dados, modelos e relatórios usados para racionalizar os fornecedores e compreender os gastos com fornecedores. Para obter mais informações sobre este componente, consulte [Instalar o componente Vendor Insights Foundation](task1-install-foundation.html). Vendor Insights É necessária uma configuração para atualizar os campos do modelo e do mapa que não estão disponíveis no Coupa.

Os campos listados estão faltando nas tabelas a seguir. Esses campos afetam os relatórios em Vendor Insights :

Dados mestre do fornecedor:

- Gerente de fornecedores
- Tipo de fornecedor
- Pool de custos
- Proprietário do fornecedor
- Torre de Recursos de TI
- Subtorre de Recursos de TI
- Função do fornecedor
- Serviço de fornecedores
- Localização do fornecedor

Dados mestre de contas a pagar:

- Conta
- Descrição da conta
- Subgrupo de custos
- Pool de custos
- Centro de Custos
- Nome do centro de custos
- Responsável pelo centro de custos
- Departamento
- Descrição do departamento
- Descrição do pedido de compra

Dados mestre da ordem de compra:

- Centro de Custos
- Nome do centro de custos
- Departamento
- Descrição do departamento

Dados principais do contrato:

- Titular do contrato
- Função
- Dias de notificação do contrato
- Departamento
- Criticidade do contrato
- Gerente de fornecedores

**Tarefa 4: Configurar o componente Vendor Insights PO**

O componente Vendor Insights PO contém os conjuntos de dados, modelos e relatórios utilizados para gerenciar ordens de compra (POs). Para obter mais informações sobre este componente, [consulte task2-install-po.html](task2-install-po.html). É necessária uma configuração Vendor Insights adicional para atualizar os campos do modelo e do mapa que não estão disponíveis no Coupa.

**Tarefa 4.1: Configurar o modelo de Contas a Pagar**

Para configurar alocações, crie um modelo para alocar custos do driver ( **Dados mestre de contas a pagar** ) para o destino resultante ( **Ordens de compra** ). Essa alocação será armazenada em uma métrica **chamada Pagável**.

Para fazer isso, você verificará o modelo de contas a pagar que deseja configurar, configurará as contas a pagar para alocação de pedidos de compra e, em seguida, configurará as contas a pagar para alocação de fornecedores.

1. No **StudioProject Explorer**, expanda **a** categoria Informações sobre fornecedores e **clique em Contas a pagar**.
2. Na **gu** ia Início, **clique em Finalizar compra**.

**Tarefa 4.1.1: Configurar contas a pagar para alocações de pedidos de compra**

1. Adicione **um** passo de modelo e, em seguida, na **lista Selecionar uma métrica**, **selecione Contas a pagar**.
2. **Em Sub** alocações, clique na linha de alocação **(Ordens de Compra)**.
3. Na **página ATRIBUIÇÃO PARA**, expanda **a** seção Distribuição, desmarque a **caixa** de seleção Relação de dados e **clique em Aplicar**. Isso remove a alocação anterior (padrão).
4. Selecione novamente **a caixa de seleção Relação de dados** e adicione a seguinte nova alocação:
   - Na subseção Relação de dados, clique na caixa abaixo e, em seguida**Coluna de origem**, na **Dados mestre de contas a pagar**coluna, selecione**Número do pedido de compra**.
   - Na subseção Relação de dados, clique na caixa **abaixo de Coluna** de destino e, em seguida, **na** coluna Tabela mestre de pedidos de compra, **selec** ione Número do pedido de compra.
   - **C** lique em OK para salvar a configuração.
5. Salve suas alterações.

No exemplo a seguir, a distribuição após a configuração inclui:

- **Coluna de origem** : DADOS MESTRE DE CONTAS A PAGAR - Número do pedido de compra
- **Coluna de destino** : DADOS MESTRE DA ORDEM DE COMPRA - Número da ordem de  
   compra **DICA** : Ao mapear contas a pagar e dados de compra, use o campo mais granular que identifica exclusivamente os dados da ordem de compra.

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa6.jpg)

**4.1.2: de tarefas Configurar alocações de contas a pagar a fornecedores**

1. No **StudioProject Explorer**, expanda **a** categoria Informações sobre fornecedores e **clique em Contas a pagar**.
2. Adicione **um** passo de modelo e, em seguida, na **lista Selecionar uma métrica**, **selecione Contas a pagar**.
3. **Em Subalocações**, clique na linha de alocação **(Fornecedores)**.
4. Na **página ATRIBUIÇÃO PARA**, expanda **a** seção Distribuição, desmarque a **caixa** de seleção Relação de dados e **clique em Aplicar**. Isso remove a alocação anterior (padrão).
5. Selecione novamente **a caixa de seleção Relação de dados** e adicione a seguinte nova alocação:
   - Na **Relação de dados**subseção, clique na caixa abaixo e, em seguida**Coluna de origem**, na coluna**Dados mestre de contas a pagar**, selecione**ID do fornecedor**.
   - Na **sub** seção Relação de dados, clique na caixa **abaixo de Coluna** de destino e, em seguida, na **col** una Tabela mestre de fornecedores, **selecione ID do fornecedor**.
   - **C** lique em OK para salvar a configuração.

No exemplo a seguir, a distribuição após a configuração inclui:

- **Coluna de origem** : DADOS MESTRE DE CONTAS A PAGAR - ID do fornecedor
- **Coluna de destino** : DADOS MESTRE DO FORNECEDOR - ID do fornecedor

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa5.jpg)

**Tarefa 4.2: Configurar o modelo de ordem de compra**

Para configurar alocações, crie um modelo para alocar custos do driver ( **Dados mestre de contas a pagar** ) para o destino resultante ( **Ordens de compra** ). Essa alocação será armazenada em uma métrica **chamada Pagável**. Para fazer isso, você verificará o modelo de contas a pagar que deseja configurar, configurará o pedido de compra para a alocação do fornecedor e, em seguida, configurará o pedido de compra para a alocação do contrato.

1. No **StudioProject Explorer**, expanda **a** categoria Informações sobre fornecedores e **clique em Ordens de compra**.
2. Na **gu** ia Início, **clique em Finalizar compra**.

**Tarefa 4.2.1: Configurar alocações de pedidos de compra para fornecedores**

Nestas instruções, a ordem de compra é mapeada para o fornecedor usando o ID do fornecedor (melhor prática). Se o ID do fornecedor não existir, **use o nome normalizado do fornecedor**.

1. Adicione **um** passo de modelo e, em seguida, na **lista Selecionar uma métrica**, **selecione Contas a pagar**.
2. **Em Subalocações**, clique na linha de alocação **(Fornecedores)**.
3. Na **página ATRIBUIÇÃO PARA**, expanda **a** seção DE, clique **no X** ao lado da condição para excluir a condição existente.  
    ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa7.jpg)
4. Na **página ALLOCATION TO (ATRIBUI** ÇÃO PARA), na **se** ção From (De), marque **a** caixa de seleção Send only remaining values (after the other rules run) (Enviar apenas os valores restantes (após a execução das outras regras)).
5. Na **página ATRIBUIÇÃO PARA**, expanda **a** seção Distribuição, desmarque a **caixa** de seleção Relação de dados e **clique em Aplicar**. Isso remove a alocação anterior (padrão).
6. Selecione novamente **a caixa de seleção Relação de dados** e adicione a seguinte nova alocação:
   - Na **Relação de dados**subseção, clique na caixa abaixo e, em seguida**Coluna de origem**, na coluna**Dados mestre de ordens de compra**, selecione**ID do fornecedor**.
   - Na **sub** seção Relação de dados, clique na caixa **abaixo de Coluna** de destino e, em seguida, na **col** una Tabela mestre de fornecedores, **selecione ID do fornecedor**.
   - **C** lique em OK para salvar a configuração.
7. Salve suas alterações.

Neste exemplo, a distribuição após a configuração inclui:

- **Coluna de origem** : DADOS MESTRE DE PEDIDOS DE COMPRA - ID do fornecedor
- **Coluna de destino** : DADOS MESTRE DO FORNECEDOR - ID do fornecedor

**Tarefa 4.2.2: Configurar alocações de pedidos de compra para contratos**

1. Adicione **um** passo de modelo e, em seguida, na **lista Selecionar uma métrica**, **selecione Contas a pagar**.
2. **Em Subalocações**, clique na linha de alocação **(PO para contrato)**.
3. Na **página ATRIBUIÇÃO PARA**, expanda **a** seção Distribuição, desmarque a **caixa** de seleção Relação de dados e **clique em Aplicar**. Isso remove a alocação anterior (padrão).
4. Selecione novamente **a caixa de seleção Relação de dados** e adicione a seguinte nova alocação:
   - Na **sub** seção Relação de dados, clique na caixa **abaixo de Coluna de origem** e, em seguida, **na** coluna Dados mestre de ordens de compra, **selec** ione Número da ordem de compra.
   - Na **Relação de dados**subseção, clique na caixa abaixo de**Coluna de destino** e, em seguida, na coluna**Ordem de compra para dados mestre do contrato**, selecione**Número do pedido de compra**.
   - **C** lique em OK para salvar a configuração.
5. Salve suas alterações.

Neste exemplo, a distribuição após a configuração inclui:

- **Coluna de origem** : DADOS MESTRE DE PEDIDOS DE COMPRA - Número do pedido de compra
- **Coluna de destino** : DADOS MESTRE DO CONTRATO DE PEDIDO - Número do pedido de compra

**Tarefa 4.3: Configurar o modelo de ordem de compra para contrato**

Para configurar alocações, crie um modelo para alocar custos do driver ( **Dados mestre de contas a pagar** ) para o destino resultante ( **Ordens de compra** ). Essa alocação será armazenada em uma métrica **chamada Pagável**. Para isso, você verificará o modelo de ordem de compra para contrato que deseja configurar e, em seguida, configurará a ordem de compra para a alocação do contrato.

1. No **StudioProject Explorer**, expanda **a** categoria Insights dos fornecedores e **clique em PO para contrato**.
2. Na **gu** ia Início, **clique em Finalizar compra**.

**Tarefa 4.3.1: Configurar alocações (PO para "PO para contratos")**

Para configurar as alocações de PO para fornecedores:

1. Na **página Modelo**, clique na linha que vai para a alocação **(PO para contrato)**.
2. Na caixa **de** diálogo ATRIBUIÇÃO, expanda **a** seção **Distribuição** e desmarque a caixa de seleção Relação de dados para remover a atribuição OOTB. **C** lique em Sim na caixa **de** diálogo Aviso de legado. ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa_8.jpg)
3. Na caixa **de** diálogo ATRIBUIÇÃO, expanda **a** seção Distribuição e marque **a** caixa de seleção Relação de dados para adicionar uma nova atribuição.
4. Na **gu** ia Origem, **clique em Escolher coluna** **e**, em Dados mestre do pedido de compra, **selecione Número do pedido de compra**.
5. Na **gu** ia Destino, **clique em Escolher coluna** **e**, em PO para dados mestre do contrato, **selecione Número do pedido de compra**.
6. De volta à **página Modelo**, verifique se a seguinte distribuição é exibida:
   - **Coluna de origem** - Dados mestre do pedido de compra - Número do pedido de compra
   - **Coluna de destino** - PO para dados mestre do contrato - Número do pedido de compra![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa_9.jpg)
7. **C** lique em OK.
8. Salve suas alterações.

**Tarefa 4.3.2: Configurar alocações (“PO para contratos” para contratos)**

1. **Em Subalocações**, clique na linha de alocação **(Contratos)**.
2. Na **página ATRIBUIÇÃO PARA**, expanda **a** seção Distribuição, desmarque a **caixa** de seleção Relação de dados e **clique em Aplicar**. Isso remove a alocação anterior (padrão).
3. Selecione novamente **a caixa de seleção Relação de dados** e adicione a seguinte nova alocação:
   - Na **Relação de dados**subseção, clique na caixa abaixo e, em seguida**Coluna de origem**, na coluna**Ordem de compra para dados mestre do contrato**, selecione**ID do contrato**.
   - Na **Relação de dados**subseção, clique na caixa abaixo de**Coluna de destino** e, em seguida, na coluna**Dados principais dos contratos**, selecione**Número do contrato**.
   - **C** lique em OK para salvar a configuração.

A distribuição após a configuração inclui:

- **Coluna de origem** : DADOS MESTRE DO CONTRATO DE PO - ID do contrato
- **Coluna de destino** : DADOS MESTRE DO CONTRATO - Número do contrato

**Tarefa 4.4: Configurar o modelo Contratos**

Para configurar as alocações, crie um modelo para alocar o custo do driver ( **Dados mestre de contas a pagar** ) para o destino resultante ( **Ordens de compra** ). Essa alocação será armazenada em uma métrica **chamada Pagável**.

**Resumo das etapas** :

1. Confira **a** tabela de dados mestre de aplicativos.
2. Junte essa tabela **aos dados mestre da aplicação Contratos**.
3. Confira o **modelo** de contratos.
4. Configure a alocação dos contratos aos fornecedores.
5. Em seguida, configure os contratos para a alocação de contratos para aplicativos.

**Tarefa 4.4.1: Verifique o modelo de contrato**

1. No **Explorador de Projetos**, expanda a**Vendor Insights** categoria e clique no **modelo Contratos**.
2. Na **guia** Início, **clique em** Finalizar para começar a fazer alterações.
3. Na **página Modelo**, **selec** ione Contas a pagar **na** lista suspensa Selecionar uma métrica.

**Tarefa 4.4.2: Configurar alocações (“PO para contratos” para contratos)**

1. Na **página Modelo**, clique na linha **que** vai para (Contratos) a partir do driver **(PO para Contrato)**.
2. Na caixa **de** diálogo ATRIBUIÇÃO, expanda **a** seção **Distribuição** e desmarque a caixa de seleção Relação de dados para remover a atribuição OOTB. **C** lique em Sim na caixa **de** diálogo Aviso de legado.
3. Na caixa **de** diálogo ATRIBUIÇÃO, expanda **a** seção Distribuição e marque **a** caixa de seleção Relação de dados para adicionar uma nova atribuição.
4. Na **gu** ia Origem, **clique em Escolher coluna** e, **em PO para dados mestre do contrato**, **selecione ID do contrato**.
5. Na **gu** ia Destino, **clique em Escolher coluna** e, **em Dados mestre** de contratos, **selecione Número do contrato**.

   ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa__10.jpg)

**4.4.3: ar tabelas de junção**

Os usuários do 12.4x e versões anteriores devem seguir este conjunto de instruções para garantir que a alocação **do** modelo de contratos funcione conforme o esperado.

1. No **StudioProject Explorer**, **clique em Dados Mestres** de Aplicações.
2. Na **gu** ia Início, **clique em Finalizar compra**.
3. Adicione **uma** etapa de junção, **clique em Adicionar link** e selecione o seguinte (observe que juntar os dados mestres em vez dos dados brutos é uma prática recomendada). **O** TheJoinstep será o último passo:
   - **Na** lista de tabelas, **selecione Dados mestre de aplicações.**
   - **Na** lista Coluna, **selecione ID das aplicações.**
   - **Na lista** De para, **selecione Contratos para Dados mestre de aplicações**.
   - Na **lista Coluna para**, **selecione ID do aplicativo**
4. **C** lique em OK.
5. Clique **na e** tapa Tabelas para revisar o resultado do mapeamento da tabela.
6. **C** lique em Salvar.

**Tarefa 4.4.4: Configurar contratos para alocações de fornecedores**

1. No **StudioProject Explorer**, expanda **a** categoria “Informações sobre fornecedores” e **clique em “Contratos** ”.
2. Adicione **um** passo de modelo e, em seguida, na **lista Selecionar uma métrica**, **selecione Contas a pagar**.
3. **Em Subalocações**, clique na linha de alocação **(Fornecedores)**.
4. Na **página ATRIBUIÇÃO PARA**, expanda **a** seção Distribuição, desmarque a **caixa** de seleção Relação de dados e **clique em Aplicar**. Isso remove a alocação anterior (padrão).
5. Selecione novamente **a caixa de seleção Relação de dados** e adicione a seguinte nova alocação:
   - Na **Relação de dados**subseção, clique na caixa abaixo e, em seguida**Coluna de origem**, na coluna**Dados principais dos contratos**, selecione**Nome do fornecedor normalizado**.
   - Na subseção Relação de dados, clique na caixa abaixo e, em seguida**Coluna de destino**, na coluna**Dados mestre do fornecedor**, selecione**Nome do fornecedor normalizado**.
   - **C** lique em OK para salvar a configuração.

A distribuição após a configuração inclui:

- **Coluna de origem** : DADOS MESTRE DE CONTRATOS - Nome do fornecedor normalizado
- **Coluna de destino** : DADOS MESTRE DO FORNECEDOR - Nome normalizado do fornecedor

**Tarefa 4.4.5: Configurar contratos para alocações de aplicativos**

1. No **StudioProject Explorer**, expanda **a** categoria “Informações sobre fornecedores” e **clique em “Contratos** ”.
2. Adicione **um** passo de modelo e, em seguida, na **lista Selecionar uma métrica**, **selecione Contas a pagar**.
3. Em **Subalocações**, clique na linha de alocação **(Contratos para Aplicações)**.
4. Na **página ATRIBUIÇÃO PARA**, expanda **a** seção Distribuição, desmarque a **caixa** de seleção Relação de dados e **clique em Aplicar**. Isso remove a alocação anterior (padrão).
5. Selecione novamente **a caixa de seleção Relação de dados** e adicione a seguinte nova alocação:
   - Na **Relação de dados**subseção, clique na caixa abaixo e, em seguida**Coluna de origem**, na coluna**Dados principais dos contratos**, selecione**ID do contrato**.
   - Na **Relação de dados**subseção, clique na caixa abaixo de**Coluna de destino** e, em seguida, na coluna**Contratos para dados mestre de aplicações**, selecione**ID do contrato**.
   - **C** lique em OK para salvar a configuração.

A distribuição após a configuração inclui:

- **Coluna de origem** : DADOS MESTRE DE CONTRATOS - ID do contrato
- **Coluna de destino** : CONTRATOS PARA DADOS MESTRE DE APLICAÇÕES - ID do contrato

**Tarefa 5: Configurar o componente Vendor Insights Contratos**

Saiba mais em <task3-install-contracts.html>.
