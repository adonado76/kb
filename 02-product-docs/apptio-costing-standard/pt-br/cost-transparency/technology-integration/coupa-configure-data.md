---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Configurar dados do Coupa para o Apptio"
breadcrumb:
  - "Costing Standard"
  - "Integrações tecnológicas"
  - "Informações sobre fornecedores Coupa"
  - "Informações sobre fornecedores Coupa Introdução"
source_path: "cost-transparency/technology-integration/coupa-configure-data.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configurar dados do Coupa para o Apptio

**Visão geral**

Depois que os dados do Coupa forem exportados e estiverem disponíveis no BIIT, eles precisarão ser transformados para serem usados pelo Vendor Insights . Este documento fornece instruções para preparar os dados do Coupa a serem integrados no Vendor Insights .

Quando os dados são importados do Coupa através do Conector Datalink (Classic) :

- Os dados são exportados para tabelas individuais, uma por objeto Coupa, pelos modos de recuperação inicial e delta.
- Tanto os dados iniciais quanto os dados delta são anexados à tabela de transformação de cada objeto Coupa.
- A etapa Remover Duplicatas é usada para determinar os dados mais recentes do Coupa.
- O centro de custos e o departamento associados à despesa são pesquisados a partir dos dados de RH usando o e-mail do solicitante da Coupa.
- Os valores dos itens são somados para determinar o valor total da fatura ou do pedido de compra.
- Essas tabelas de transformação são então mapeadas Vendor Insights para Conjuntos de Dados Mestres (MDS) para permitir Vendor Insights que os relatórios sejam gerados.

**Pré-requisitos**

Os seguintes dados devem existir:

- Fornecedor – inicial
- Fornecedor – delta
- Contratos – inicial
- Contratos – delta
- Ordens de compra – inicial
- Ordens de compra – delta
- Linhas de ordem de compra – inicial
- Linhas de ordem de compra – delta
- Contas de linha de ordem de compra – inicial
- Contas de linha de ordem de compra – delta
- Faturas – inicial
- Faturas – delta
- Linhas da fatura – inicial
- Linhas da fatura – delta
- Contas de linhas de fatura – inicial
- Contas de linha de fatura - delta

**NOTA** : Se os dados iniciais completos forem recuperados todos os meses, os dados delta não serão necessários.

**Instruções**

**Tarefa 1: Recuperar dados de RH**

Recupere os seguintes campos do seu sistema de RH:

- Nome Completo
- E-mail
- Centro de Custos
- Nome do centro de custos
- Responsável pelo centro de custos
- Departamento
- Descrição do departamento

**Tarefa 2: Criar a tabela de referência de RH**

Os dados de RH são usados para determinar o centro de custos e o departamento associados a cada despesa. O e-mail do solicitante do Coupa é usado para determinar o centro de custos e o departamento. Os dados de RH fornecem dados complementares para garantir que quaisquer dados que possam não existir em uma implementação pronta para uso do Coupa estejam disponíveis em Apptio.

1. Crie uma tabela e carregue a tabela bruta **de RH** :
   - **Nome da tabela** - Dados brutos de RH
   - **Categoria** - Vendor Insightsz\_\_Raw
   - **Fonte dos dados** - Upload de arquivo
   - **Fonte de dados inicial** - <Dados de RH>
   - **Utilização** - Lista de usuários, endereços de e-mail e hierarquia organizacional da fonte de dados original
2. Crie as seguintes tabelas de dados mestre de referência:
   - **Nome da tabela** - Dados mestre de RH.
   - **Categoria** - z\_Vendor Insights.
   - **Fonte dos dados** - Upload de arquivo.
   - **Fonte de dados inicial** - Acesse [[ %=GlobalVariables.CompanyName% ] Comunidade](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?documentkey=e2b877ae-b6b8-4bf4-9e2f-36e0caec62b3 "(Abre em uma nova guia ou janela)") e baixe o arquivo chamado Dados Mestres de RH.
   - **Utilização** - Dados mestre para anexar os dados brutos de RH. Lista de usuários, endereços de e-mail e hierarquia organizacional da fonte de dados original.
3. Anexe as tabelas brutas às tabelas de dados mestres:
   - **Nome da tabela de dados mestre** - Dados mestre de RH
   - **Nome da tabela de dados brutos** - Dados brutos de RH
   - **Colunas mapeadas da tabela de dados mestre:**
     - Nome Completo
     - E-mail
     - Centro de Custos
     - Nome do centro de custos
     - Responsável pelo centro de custos
     - Departamento
     - Descrição do departamento

Exemplo de mapeamento usando dados de demonstração (mapeamento dos dados mestres de RH para os dados brutos de RH):

- Nome completo - Nome completo
- E-mail - E-mail
- Centro de custos - Centro de custos
- Nome do centro de custos - Nome do centro de custos
- Responsável pelo centro de custos - Responsável pelo centro de custos
- Departamento - Departamento
- Descrição do departamento - Descrição do departamento

**Tarefa 3: Criar tabelas de correspondência de status Coupa- Apptio**

Os status dos pedidos de compra da Coupa são mais detalhados do que o relatório de burndown de pedidos de compra, que espera o status de pedido de compra aberto ou fechado.

Acesse [[ %=GlobalVariables.CompanyName% ] Comunidade](https://community.apptio.com/community/user/apptio/communities/community-home/all-news/viewdocument?DocumentKey=e2b877ae-b6b8-4bf4-9e2f-36e0caec62b3 "(Abre em uma nova guia ou janela)") e baixe o arquivo chamado Coupa PO Status para Apptio Status Tablematch.

Crie uma tabela de mapeamento e, em seguida, carregue a planilha contendo o status padrão para o objeto de ordem de compra do Coupa.

| Nova tabela: nome da tabela | Categoria | Origem de dados | Fonte inicial dos dados |
| --- | --- | --- | --- |
| Coupa\_Apptio\_Status\_Tabela de correspondência | z\_Coupa\_Transformar | Upload de arquivo | Status da ordem de compra da Coupa para o status da Apptio |

**Tarefa 4: Criar tabelas de transformação Coupa**

Crie tabelas de transformação, acrescente os dados brutos do Coupa e transforme os dados. Cada uma dessas tabelas de transformação exigirá várias etapas para serem colocadas no formato final, prontas para serem anexadas aos conjuntos de dados principais.

Visão geral das etapas necessárias para as tabelas de transformação:

1. Crie as tabelas de transformação.
2. Anexe a fonte de dados delta à tabela.
3. Adicione fórmulas para garantir que todos os campos esperados da Coupa estejam presentes.
4. Remova as linhas duplicadas da tabela para que apenas os registros mais recentes existam.
5. Adicione fórmulas para calcular campos adicionais necessários para mapear as tabelas de Vendor Insights dados mestres.
6. Mapeie a tabela de transformação bruta para o conjunto de dados mestre apropriado.

**Tarefa 4.1: Criar as tabelas de transformação**

Antes de criar as tabelas de transformação, visualize as tabelas brutas e certifique-se de que a coluna **Substituição de tipo** esteja preenchida. Caso contrário, preencha cada célula da coluna com a substituição de tipo apropriada.

1. Crie as seguintes tabelas de transformação para cada um dos objetos Coupa para mesclar os dados iniciais e delta e garantir que todos os campos necessários para mapear a tabela de dados mestre existam. Crie cada tabela de transformação como uma nova tabela usando os nomes na tabela a seguir.   
    **DICA** : Aprenda a [criar uma tabela no TBM Studio](../../studio/data_studio/create-table.html "Aplica-se a: TBM Studio 12.0 e posterior").   

   | Nova tabela: nome da tabela | Categoria | Origem de dados | Fonte inicial dos dados |
   | --- | --- | --- | --- |
   | Coupa\_Transformar\_Fornecedor | z\_Coupa\_Transformar | Tabela existente | <Dados brutos da Coupa (dados iniciais do fornecedor)> |
   | Coupa\_Transformar\_Linha\_da\_Fatura\_Conta | z\_Coupa\_Transformar | Tabela existente | <Dados brutos do Coupa (dados da conta da linha da fatura inicial)> |
   | Coupa\_Transformar\_Linha\_da\_Fatura | z\_Coupa\_Transformar | Tabela existente | <Dados brutos do Coupa (dados iniciais da linha da fatura)> |
   | Coupa\_Transformar\_Fatura | z\_Coupa\_Transformar | Tabela existente | <Dados brutos do Coupa (dados iniciais da fatura)> |
   | Coupa\_Transformar\_Linha\_de\_Pedido\_de\_Compra\_Conta | z\_Coupa\_Transformar | Tabela existente | <Dados brutos do Coupa (dados iniciais da conta da linha de pedido)> |
   | Coupa\_Transformar\_Linha\_PO | z\_Coupa\_Transformar | Tabela existente | <Dados brutos do Coupa (dados iniciais da linha do pedido de compra)> |
   | Coupa\_Transformar\_PO | z\_Coupa\_Transformar | Tabela existente | <Dados brutos do Coupa (dados iniciais da ordem de compra)> |
   | Coupa\_Transformar\_Contrato | z\_Coupa\_Transformar | Tabela existente | <Dados brutos da Coupa (dados do contrato inicial)> |
2. Clique na etapa **Fonte** e, em seguida, clique em **Tabela existente**.
3. Na etapa **Tabela existente**, selecione os valores **da Tabela de entrada** associados à tabela criada (consulte a etapa 1 para obter esses valores).
4. Adicione a etapa Anexar à transformação de dados.
   - Clique em **Anexar tabela** e selecione o nome da tabela delta a ser anexada.   
        
      **Exemplo** : Coupa\_Fornecedor\_Delta\_Raw)
   - Mapeie os nomes dos campos delta para as tabelas de transformação. Cada campo deve corresponder 1 a 1.
   - (Opcional) Se houver campos adicionais nos dados delta que não faziam parte dos dados iniciais, adicione esses campos adicionais dos dados delta a esta tabela de transformação.
5. Adicione a etapa **Fórmulas** e, em seguida, adicione a seguinte fórmula a todas as seis tabelas de transformação:
   - **Nome da coluna** - Chave
   - **Tipo** - Etiqueta
   - **Fórmula** -  `=trim(Coupa ID)`
6. Adicione a etapa **Remover Duplicatas** e selecione o seguinte:
   - **Coluna-chave** - Chave
   - **Coluna de comparação** - Atualizado em
   - **Tipo de comparação** - Maior
7. Para a  `Coupa_Transform_PO_New`  tabela, adicione a etapa **Ocultar e Renomear**. Em seguida, clique em **Adicionar colunas** e adicione as seguintes colunas:   

   | Nome da coluna | Visível | Renomear para |
   | --- | --- | --- |
   | Departamento | Selecionado | Descrição do departamento |
   | Data do pedido de compra | Selecionado | Data da ordem de compra Orig |
   | Número do pedido de compra | Selecionado | Número da ordem de compra |
8. Alguns campos do Coupa podem estar faltando porque não foram preenchidos ou configurados no Coupa. Se um campo não existir, adicione o nome do campo que falta e preencha o campo com um valor em branco. A saída de dados do Coupa pode estar sem algum dos seguintes campos:
   - Centro de Custos
   - Departamento
   - Torre
   - Subtorre
   - Pool de custos
   - Subgrupo de custos
9. São necessárias fórmulas para mesclar dados de várias fontes e converter o formato dos dados para o valor necessário nas tabelas de dados Vendor Insights mestres. Clique em **Fórmulas** e adicione as seguintes fórmulas às tabelas de transformação:

**4.2: ar tarefa Coupa\_Transformar\_Fornecedor**

Neste exemplo, todos os campos com o valor "" não estão presentes nos dados brutos do Coupa.

| Nome da coluna | Tipo | Fórmula |
| --- | --- | --- |
| Mercadoria padrão | Rótulo | `=if(Vendor Description = "Default Commodity:", "",Default Commodity Ref)` |
| Referência padrão de mercadoria | Rótulo | `=Right(Vendor Description, len(Vendor Description)-find(": ",Vendor Description))` |
| Serviço de fornecedores | Rótulo | `=Default Commodity` |
| ID do fornecedor principal | Rótulo | **NOTA** : Na lista **Selecionar coluna para editar**, selecione o tipo de dados.    `=Parent Vendor Coupa ID & " - " & Parent Vendor ID` |
| Localização do fornecedor | Rótulo | `=Primary Address City&&Primary Address State&&Primary Address Country` |
| ID do Fornecedor | Rótulo | **NOTA** : Na lista **Selecionar coluna para editar**, selecione o tipo de dados.    `=Coupa ID & " - " & Vendor ID` |
| Número | Numérico | `=1` |
| Torre de TI | Rótulo | `=""` |
| Subtorre de TI | Rótulo | `=""` |
| Cidade do endereço principal | Rótulo | `=""` |
| País do endereço principal | Rótulo | `=""` |
| Endereço principal Estado | Rótulo | `=""` |
| Tipo de fornecedor | Rótulo | `=""` |

**4.3: ar tarefa Coupa\_Transformar\_Linha\_de\_Fatura\_Conta**

| Nome da coluna | Tipo | Fórmula |
| --- | --- | --- |
| Nome do centro de custo da linha | Rótulo | `={Account Segment 02}` |
| Número do centro de custo da linha | Rótulo | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| Linha PO | Rótulo | `=Purchase Order Number&" - " & PO Line Num` |
| Valor da ordem de compra | Numérico | `=SumIf(PO Coupa ID,PO Coupa ID, Item Total)` |
| Número | Numérico | `=1` |

**Tarefa 4.4: Coupa\_Transform\_Invoice\_Line**

Os dados do centro de custos podem vir do Coupa por meio de um campo personalizado, um campo de segmento de conta ou podem exigir que você procure os dados usando os dados de RH. O valor do centro de custos precisa ser mapeado para o nome do campo esperado a ser usado por outras fórmulas.

No exemplo a seguir, o nome do centro de custo é armazenado no campo **Segmento de conta 02** nos dados brutos do Coupa. Se o valor estiver em branco, o número do centro de custos precisa ser consultado em uma tabela de referência (Dados mestre de RH).

Se os dados do centro de custos não existirem nos dados brutos do Coupa, use a fórmula  `=""` .

| Nome da coluna | Tipo | Fórmula |
| --- | --- | --- |
| ID da conta | Rótulo | `=Trim(Account ID If)` |
| ID da conta Se | Rótulo | `=left(Account,Find(" - ",Account))` |
| Referência da conta | Rótulo | `=right(Account,len(Account)- Find(" - ",Account)-2)` |
| Descrição da conta | Rótulo | `=trim(Account Desc If)` |
| Descrição da conta Se | Rótulo | `=if(Account CONTAINS " - ",Account Desc Ref,Account)` |
| Descrição da conta Ref | Rótulo | `=right(Account,len(Account)- Find(" - ",Account)-2)` |
| Número | Numérico | `=1` |
| Nome do centro de custo da linha | Rótulo | `={Account Segment 02}` |
| Número do centro de custo da linha | Rótulo | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| ID da fatura Coupa str | Rótulo | `=trim(Invoice Coupa ID)` |

**4.5: ar tarefa Coupa\_Transformar\_Fatura**

| Nome da coluna | Tipo | Fórmula |
| --- | --- | --- |
| Centro de Custos | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Center Number from Line)` |
| Nome do centro de custos | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Center Name from Line)` |
| Responsável pelo centro de custos | Rótulo | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Cost Center Owner)` |
| Torre | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Tower)` |
| Subtorre | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,{Sub-Tower})` |
| Pool de custos | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Pool)` |
| Subgrupo de custos | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Sub Pool)` |
| Departamento | Rótulo | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Department)` |
| Descrição do departamento | Rótulo | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Department Desc)` |
| Conta | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Account ID)` |
| Descrição da conta | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Account Desc)` |
| Data da fatura abreviada | Formato da data:   mm   dd   aaaa | `=Dateformat(Split(Invoice Date,1,"T"),"MM/dd/yyyy")` |
| Data da fatura Texto resumido | Rótulo | `=Invoice Date Abridged` |
| Descrição | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Invoice Line Description)` |
| ID do contrato Coupa | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Contract Coupa ID)` |
| ID do fornecedor pai na Coupa | Rótulo | `=Lookup(Vendor Coupa ID,Coupa_Transform_Supplier,Coupa ID,Parent Vendor Coupa ID)` |
| Número da ordem de compra | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,PO No)` |
| ID PO Coupa | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,PO Coupa ID)` |
| Número da Fatura | Rótulo | `=if(Invoice ID="", "Coupa Invoice ID: "&Coupa ID, Invoice ID)` |
| Número do pedido de compra | Rótulo | `=if(PO Coupa ID="" OR PO No ="","",PO Coupa ID & " - " & PO No)` |
| ID do Fornecedor | Rótulo | **NOTA** : Na lista **Selecionar coluna para editar**, selecione o tipo de dados.    `=Vendor Coupa ID & " - " & Vendor ID` |
| Nome do fornecedor | Rótulo | **NOTA** : Na lista **Selecionar coluna para editar**, selecione o tipo de dados. |
| Identificação de contas a pagar | Rótulo | `=Coupa ID` |
| Número | Numérico | `=1` |

**4.6: ar tarefa Coupa\_Transformar\_Linha\_PO\_Conta**

| Nome da coluna | Tipo | Fórmula |
| --- | --- | --- |
| Nome do centro de custo da linha | Rótulo | `={Account Segment 02}` |
| Número do centro de custo da linha | Rótulo | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| Linha PO | Rótulo | `=Purchase Order Number&" - " & PO Line Num` |
| Valor da ordem de compra | Numérico | `=SumIf(PO Coupa ID,PO Coupa ID, Item Total)` |
| Número | Numérico | `=1` |

**4.7: ar tarefa Coupa\_Transformar\_Linha\_PO**

| Nome da coluna | Tipo | Fórmula |
| --- | --- | --- |
| Nome do centro de custo da linha | Rótulo | `={Account Segment 02}` |
| Número do centro de custo da linha | Rótulo | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| Linha PO | Rótulo | `=Purchase Order Number&" - " & PO Line Num` |
| Valor da ordem de compra | Numérico | `=SumIf(PO Coupa ID,PO Coupa ID, Item Total)` |
| Número | Numérico | `=1` |

**4.8: ar tarefa Coupa\_Transform\_PO**

| Nome da coluna | Tipo | Fórmula |
| --- | --- | --- |
| Centro de Custos | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Cost Center Number from Line)` |
| Nome do centro de custos | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Cost Center Name from Line)` |
| Responsável pelo centro de custos | Rótulo | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Cost Center Owner)` |
| Torre | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Tower)` |
| Subtorre | Rótulo | `=Lookup(Coupa ID,Coupa_PO_Line,PO Coupa ID,{Sub-Tower})` |
| Pool de custos | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Pool)` |
| Subgrupo de custos | Rótulo | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Cost Sub Pool)` |
| Departamento | Rótulo | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Department)` |
| Descrição do departamento | Rótulo | **NOTA** : Na lista **Selecionar coluna para editar**, selecione o tipo de dados. |
| Quantia | Numérico | `=Requisition Total Amount` |
| Amount\_derivedFromPOLine | Numérico | `=Lookup(Coupa ID, Coupa_Transform_PO_Line,PO Coupa ID,PO Amount)` |
| Data do pedido de compra | Formato da data:   mm   dd   aaaa | `=Dateformat(Split(PO Date Orig,1,"T"),"MM/dd/yyyy")` |
| PO-1 | Rótulo | `=PO No&" - 1"` |
| PO-2 | Rótulo | `=PO No&" - 2"` |
| PO-3 | Rótulo | `=PO No&" - 3"` |
| PO-4 | Rótulo | `=PO No&" - 4"` |
| PO-1 Pesquisa | Rótulo | `=Lookup({PO-1},Coupa_Transform_PO_Line,{PO-Line},Item Name)` |
| PO-2 Pesquisa | Rótulo | `=Lookup({PO-2},Coupa_Transform_PO_Line,{PO-Line},Item Name)` |
| PO-3 Pesquisa | Rótulo | `=Lookup({PO-3},Coupa_Transform_PO_Line,{PO-Line},Item Name)` |
| PO-2 Se | Rótulo | `=if({PO-2 Lookup}="", "","; " & {PO-2 Lookup})` |
| PO-3 Se | Rótulo | `=if({PO-3 Lookup}="", "","; " & {PO-3 Lookup})` |
| Descrição do pedido de compra | Rótulo | `={PO-1 Lookup}&{PO-2 If}&{PO-3 If}` |
| Status Superior | Rótulo | `=Upper(Status)` |
| Status do pedido de compra | Rótulo | `=Lookup(Status Upper,Coupa_Apptio_Status_Tablematch,Coupa Status,Apptio Status)` |
| Número do pedido de compra | Rótulo | `=PO No` |
| ID do Fornecedor | Rótulo | `=Vendor Coupa ID & " - " & Vendor ID` |
| Nome do fornecedor | Rótulo | **NOTA** : Na lista **Selecionar coluna para editar**, selecione o tipo de dados. |
| Valor monetário anterior | Numérico | `=Accounts Payable Raw Historic:Prior Years Monetary Amount[PO=Purchase Order Number]` |
| Solicitante | Rótulo | **NOTA** : Na lista **Selecionar coluna para editar**, selecione o tipo de dados. |
| Número | Numérico | `=1` |

**4.9: ar a tarefa Coupa\_Transform\_Contract**

| Nome da coluna | Tipo | Fórmula |
| --- | --- | --- |
| Número do centro de custos | Rótulo | `=""` |
| Pesquisa do número do centro de custos | Rótulo | `=if(Cost Center Number!="",Cost Center Number,Cost Center HR Lookup)` |
| Pesquisa de centro de custos HR | Rótulo | `=Lookup(Contract Owner Email,HR Data Master Data,Email,Cost Center)` |
| Pesquisa por departamento | Rótulo | `=if(Cost Center Number!="",Department CC HR Lookup,Department Email HR Lookup)` |
| Departamento CC Pesquisa de RH | Rótulo | `=Lookup(Cost Center Number,HR Data Master Data,Cost Center,Department)` |
| Pesquisa de e-mail do departamento de RH | Rótulo | `=Lookup(Contract Owner Email,HR Data Master Data,Email,Department)` |
| Número | Numérico | `=1` |
| Data de início do contrato | Formato da data:   mm   dd   aaaa | `=DateFormat(split(Start Date,1,"T"),"MM/dd/yyyy")` |
| Data de término do contrato | Formato da data:   mm   dd   aaaa | `=DateFormat(split(End Date,1,"T"),"MM/dd/yyyy")` |
| ID do fornecedor Coupa str | Rótulo | `=Trim(Vendor Coupa ID)` |
| Gerente de fornecedores | Rótulo | `=Lookup(Vendor Coupa ID str,Vendor Master Data,Vendor ID,Vendor Manager)` |
| Tipo de fornecedor | Rótulo | `=Lookup(Vendor Coupa ID str,Vendor Master Data,Vendor ID,Vendor Type)` |
| Contrato dos Pais | Rótulo | **NOTA** : Na lista **Selecionar coluna para editar**, selecione o tipo de dados. |
| Planos de renovação | Rótulo | `""` |
| Responsável pelo centro de custos | Rótulo | Proprietário do centro de custos JHL (pesquisar pelo e-mail do proprietário do contrato) |

Para a tabela **Coupa\_Transform\_Invoice** :

1. Adicione a etapa **Partição de data** à transformação de dados.
2. Marque a caixa de seleção **Datas são representadas em linhas**.
3. Na lista **Coluna de data de início**, selecione **Texto abreviado da data da fatura**. Deixe a lista **da coluna Data de Fim** em branco.

**Tarefa 4.10: Criar uma tabela de mapeamento (PO para contrato)**

Além das tabelas de transformação anteriores, é necessária uma tabela de mapeamento para vincular o pedido de compra aos dados do contrato para Vendor Insights .

1. Crie a seguinte tabela de transformação como uma nova tabela.   
    **DICA** : Aprenda a [criar uma tabela no TBM Studio](../../studio/data_studio/create-table.html "Aplica-se a: TBM Studio 12.0 e posterior").
   - **Nome da tabela** - Coupa\_Transform\_PO-to-Contract
   - **Categoria** - z\_Coupa\_Transform
   - **Fonte de dados** - Tabela existente
   - **Fonte dos dados** - Coupa\_Transform\_PO\_Line
2. Clique na etapa **Fonte** e, em seguida, clique em **Tabela existente**.
3. Na etapa **Tabela existente**, selecione o valor **da tabela de entrada** **Coupa\_Transform\_PO\_Line**.
4. Adicione a etapa Filtro e, em seguida, adicione dois filtros usando os seguintes parâmetros:
   - Nome da coluna - **ID do contrato Coupa**, Valor do filtro - **Não é nulo**
   - Nome da coluna - **PO Coupa ID**, Valor do filtro - **Não é nulo**
5. Adicione a etapa **Grupo** e, em seguida, adicione o agrupamento **PO-Contrato Coupa ID**.
6. Adicione a etapa **Fórmulas** e, em seguida, adicione as seguintes fórmulas:

   | Nome da coluna | Tipo | Fórmula |
   | --- | --- | --- |
   | ID do contrato | Rótulo | `=Contract Coupa ID & " - " & Contract ID` |
   | Número do pedido de compra | Rótulo | `=PO Coupa ID & " - " & Purchase Order Number` |
7. Salve suas alterações.
