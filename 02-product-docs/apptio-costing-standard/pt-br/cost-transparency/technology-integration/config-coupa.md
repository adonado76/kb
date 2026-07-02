---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Configure o Coupa para o Apptio"
breadcrumb:
  - "Costing Standard"
  - "Integrações tecnológicas"
  - "Informações sobre fornecedores Coupa"
  - "Informações sobre fornecedores Coupa Introdução"
source_path: "cost-transparency/technology-integration/config-coupa.html"
images:
  - "resources/images/vi_images/vi/coupa/coupa1.jpg"
  - "resources/images/vi_images/vi/coupa/coupa2.jpg"
  - "resources/images/vi_images/vi/coupa/coupa3.jpg"
  - "resources/images/vi_images/vi/coupa/coupa4.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configure o Coupa para o Apptio

Este documento fornecerá instruções para configurar o Coupa para permitir a integração entre o Apptio e o Coupa.

O público-alvo deste documento é o administrador do Coupa, que irá alterar as configurações no Coupa.

A Gestão de Negócios de Tecnologia (TBM) fornece aos líderes de tecnologia padrões e melhores práticas validadas para comunicar o custo, a qualidade e o valor dos investimentos em TI aos seus parceiros de negócios. Apptio é a criadora e líder do setor de TBM, com sua própria taxonomia proprietária de TBM ( Apptio ) ( ATUM ).

Apptio O conjunto de soluções da impulsiona a transformação digital, traduzindo os custos de tecnologia em todo o portfólio de TI (incluindo sistemas locais, fornecedores, projetos e sistemas em nuvem) em uma visão holística e centrada nos negócios. Os clientes aproveitam essa visão para definir metas futuras, medir resultados comerciais e orientar decisões de investimento.

Ao integrar o Coupa com o Apptio, juntos, eles oferecem suporte a melhorias de processos que afetam os resultados financeiros de uma organização, de acordo com os padrões TBM.

**Visão geral da integração**

Existem diferentes níveis de integração que podem ser alcançados. São os seguintes:

- Importe os dados existentes do Coupa para o Apptio sem qualquer alteração
- Configure a taxonomia TBM (torre de TI e pool de custos) Apptio no Coupa
- Exiba a taxonomia TBM ( Apptio ) aos usuários no momento do envio de uma requisição

Para importar os dados do Coupa diretamente para o Apptio, o conector Coupa Datalink (Classic) da Apptio é usado para extrair os dados do Coupa diretamente para o Apptio. Posteriormente, os dados são integrados ao Padrão de Custos e Vendor Insights aos produtos d Apptio. O Conector Coupa Datalink (Classic) utilizará OAuth para autenticar na Coupa e recuperar os dados da Coupa utilizando a API Rest da Coupa.

Abaixo estão as etapas para configurar o Coupa para diferentes níveis de integração:

- Recupere dados do Coupa para o Apptio usando o conector Coupa Datalink (Classic). Isso envolve a criação de credenciais usadas pelo Conector Apptio Coupa Datalink (Classic) para extrair os dados do Coupa.
- Obtenha detalhes sobre a IT Tower e o Cost Pool dos usuários do Coupa para disponibilizar os dados em Apptio. Isso envolve a criação de campos personalizados para os usuários selecionarem os detalhes da Torre de TI e do Pool de Custos ao criar objetos Coupa (por exemplo: requisições, faturas, etc.).
- Veja a taxonomia TBM da Coupa. Isso envolve a criação de uma política que será exibida para determinados tipos de despesas.

Os detalhes da Torre de TI e do Pool de Custos podem ser configurados adicionando os detalhes diretamente nos campos personalizados dos objetos Coupa Item ou atribuindo a Torre e os Pools de Custos à árvore de commodities Coupa, para que sejam aplicados por padrão a todos os itens de forma genérica. A decisão sobre a melhor abordagem deve ser discutida durante o workshop de implementação.

**Dados recuperados do Coupa**

Vendor Insights precisa da seguinte lista de dados do sistema:

- Fornecedores
- Contratos
- Requisitos
- Ordem de compra
- Faturas

**Instruções**

**Tarefa 1: Criar credenciais**

Para configurar o conector Coupa Datalink (Classic) do Apptio para importar dados do Coupa para o Apptio, siga as etapas descritas no [Guia do conector Coupa](../../datalink-classic/datalink/connectorguides/c-coupa.html).

**Tarefa 2: Criar campos personalizados Torre de TI e Pool de custos**

No Apptio, para saber quais fornecedores e custos estão associados a quais torres de TI e pools de custos na taxonomia TBM da Apptio ( ATUM ), os dados são recuperados do Coupa quando o usuário seleciona o valor apropriado ao criar uma requisição ou uma fatura.

Os valores podem ser configurados para que sejam padronizados diretamente a partir do item ou a partir da mercadoria Coupa de forma genérica. A equipe de implementação precisará decidir qual método usar:

1. [COMMODITIES] A definição padrão da árvore de commodities garantirá a consistência em toda a plataforma de compras Coupa e assegurará que a torre de TI e os pools de custos sejam definidos como padrão para todos os itens em todas as requisições dos usuários.   
    Isso também permitirá que os produtos punchout sejam predefinidos a partir da seleção dos catálogos punchout. No entanto, isso pode exigir alguma reflexão por parte da equipe de implementação sobre o mapeamento dos códigos UNSPSC para a árvore de commodities da Coupa.   
    Consulte a página de sucesso: [Portal de sucesso da Coupa](https://success.coupa.com/support/docs/core_apps/procurement/catalogs_and_items/catalogs/unspsc_codes "(Abre em uma nova guia ou janela)").
2. [ITENS] A predefinição de cada item no Coupa garantirá que cada item seja definido com a torre de TI e os pools de custos exatos. Isso exigirá que TODOS os itens sejam mapeados. Se um item não estiver mapeado, ele deverá ser alterado manualmente no Coupa antes que a requisição seja concluída.

Para que o usuário selecione a torre de TI e o pool de custos, é necessário configurar o seguinte no Coupa:

- A lista de pesquisa para torres de TI e pools de custos
- Os valores de pesquisa para torres de TI e listas de pesquisa de pools de custos
- Os campos personalizados para torres de TI e pools de custos nos seguintes objetos Coupa:
  - Itens, se [ITENS] for configurado, ou Mercadorias, se [MERCADORIAS] for configurado
  - Requisitos
  - Ordens de Compra
  - Faturas
- Os valores padrão da torre de TI e do pool de custos para itens

**Tarefa 2.1: Criar pesquisas**

Os campos personalizados irão procurar os valores nas listas de pesquisa. Portanto, é necessária uma lista de pesquisa para cada campo personalizado e, como resultado, são necessárias as seguintes listas de pesquisa:

- Apptio centros de custos
- Apptio torres

Esta lista de grupos de custos e torres tem dois níveis, para que o usuário possa selecionar o subgrupo de custos e a subtorre específicos para o item adquirido.

**Etapas detalhadas** :

1. Navegue até **Pesquisas** (Configuração > Configuração da empresa > Pesquisas > Criar).
2. Criar pesquisa **Apptio Pools de custos** (definir Nível 1 e Nível 2).

   | Campo | Valor |
   | --- | --- |
   | Nome | Apptio Grupos de custos |
   | Descrição | Subgrupos de custos para TI |
   | Ativo | Verificação |
   | Grupos de conteúdo | Todos |
   | Nível 1 Nome | Apptio Pool de custos |
   | Nível 2 Nome | Apptio Subgrupo de custos |
3. Criar pesquisa **Torre Apptio** (definir Nível 1 e Nível 2).   
      

   | Campo | Valor |
   | --- | --- |
   | Nome | Apptio Torres |
   | Descrição | Subtorres para TI |
   | Ativo | Verificação |
   | Grupos de conteúdo | Todos |
   | Nível 1 Nome | Apptio Torre |
   | Nível 2 Nome | Apptio Subtorre |

**Tarefa 2.2: ar valores de pesquisa de carga**

Os valores para as listas de pesquisa " Apptio " (Grupos de custos de produtos) e " Apptio " (Grupos de torres) precisam ser carregados no Coupa. A lista de centros de custo ( Apptio ) deve conter a hierarquia dos possíveis valores dos centros de custo e subcentros de custo. A lista de torres ( Apptio ) deve conter a hierarquia dos valores possíveis para torres e subtorres.

Os valores que serão carregados devem ser os valores usados na sua instância Apptio, que geralmente é a taxonomia ATUM. Para obter uma cópia da lista de taxonomia padrão ATUM para fazer o upload, entre em contato com Apptio. A pessoa com acesso para configurar o Apptio pode então exportar a lista de torres de TI e pools de custos do Apptio a partir das seguintes tabelas:

| Apptio nome da tabela | Descrição |
| --- | --- |
| Lista de referência de custos compartilhados | Lista de centros de custo e subcentros de custo |
| Lista de referência da torre de recursos de TI | Lista de torres e subtorres |

Pode haver uma versão diferente da taxonomia ATUM que está sendo usada e, portanto, é importante recuperar a mesma versão que está sendo empregada para configurar Apptio.

Essa lista exportada precisa ser formatada no formato de valor de pesquisa da Coupa.

Para obrigar os usuários a fornecer os valores de Apptio Cost Pools e Apptio Tower para todos os itens recém-adquiridos, os campos personalizados para pools de custos e torres serão campos obrigatórios. Isso pode não fazer sentido para itens que não estão relacionados a gastos com tecnologia, como marcadores ou cadeiras. Portanto, outra opção, como Despesas não técnicas, deve ser adicionada à lista de valores de pesquisa para que o usuário possa selecionar esse valor.

**Etapas detalhadas** :

1. Navegue até **Valores de pesquisa** (Configuração > Configuração da empresa > Valores de pesquisa > Carregar do arquivo).
2. Carregue os dados **do pool de custos ( Apptio )** usando o formato padrão **Coupa Lookup Value** (Selecione Arquivo > Iniciar upload).

   | Campo | Valor |
   | --- | --- |
   | Consulta | Apptio Grupos de custos |
   | Pai | [Valor principal do pool de custos] |
   | Nome | [Nome do pool de custos ou subpool de custos] |
3. Carregue os dados **da torre** Apptio usando o formato padrão **Coupa Lookup Value** (Selecione Arquivo > Iniciar upload).   
      

   | Campo | Valor |
   | --- | --- |
   | Consulta | Apptio Torres |
   | Pai | [Valor pai da torre de TI] |
   | Nome | [Nome da torre de TI ou subtorre de TI] |

**Tarefa 2.3: Adicionar campos personalizados**

Para que os usuários possam selecionar os valores de " Apptio " (Grupos de custos) e " Apptio " (Torres de custos) ao enviar um novo objeto Coupa, é necessário adicionar campos personalizados aos objetos Coupa existentes.

Adicione esses campos personalizados aos seguintes objetos Coupa se [ITENS] precisarem ser configurados:

| Objeto Coupa | Seção | Solicitação de campo personalizado | Nome do campo personalizado |
| --- | --- | --- | --- |
| Item | Itens | Apptio Subgrupo de custos | apptio\_custo\_subgrupo |
| Item | Itens | Apptio Subtorre | apptio\_sub\_torre |
| Requisição | Itens | Apptio Subgrupo de custos | apptio\_custo\_subgrupo |
| Requisição | Itens | Apptio Subtorre | apptio\_sub\_torre |
| Ordens de Compra | Linhas | Apptio Subgrupo de custos | apptio\_custo\_subgrupo |
| Ordens de Compra | Linhas | Apptio Subtorre | apptio\_sub\_torre |
| Faturas | Linhas | Apptio Subgrupo de custos | apptio\_custo\_subgrupo |
| Faturas | Linhas | Apptio Subtorre | apptio\_sub\_torre |

Adicione esses campos personalizados aos seguintes objetos Coupa se [COMMODITIES] precisar ser configurado:

| Objeto Coupa | Seção | Solicitação de campo personalizado | Nome do campo personalizado |
| --- | --- | --- | --- |
| Mercadorias | N/A | Apptio Subgrupo de custos | apptio\_custo\_subgrupo |
| Mercadorias | N/A | Apptio Subtorre | apptio\_sub\_torre |
| Requisição | Itens | Apptio Subgrupo de custos | apptio\_custo\_subgrupo |
| Requisição | Itens | Apptio Subtorre | apptio\_sub\_torre |
| Ordens de Compra | Linhas | Apptio Subgrupo de custos | apptio\_custo\_subgrupo |
| Ordens de Compra | Linhas | Apptio Subtorre | apptio\_sub\_torre |
| Faturas | Linhas | Apptio Subgrupo de custos | apptio\_custo\_subgrupo |
| Faturas | Linhas | Apptio Subtorre | apptio\_sub\_torre |

Crie um grupo de conteúdo chamado especificamente **APPTIO**. Este grupo de conteúdo deve ser atribuído a usuários avançados d Apptio ou aprovadores de commodities de TI para garantir que esses usuários possam ver e editar os valores da sub-torre e do subconjunto de custos. A intenção é que os usuários finais regulares não precisem ver esses campos, pois eles são mapeados a partir dos valores padrão de [ITENS] ou [COMODIDADES].

**Etapas detalhadas** :

1. Navegue até **Campos personalizados** (Configuração > Configuração da empresa > Campos personalizados).
2. Para **[ITENS]**, adicione campos personalizados ao objeto **Item** na seção **Itens**.
   1. Adicione um campo personalizado para **Subgrupo de custos de Apptio**.
   2. Adicione um campo personalizado para **a Subtorre Apptio**.

   | Campo | Valor - para pools de custos | Valor - para torres de TI |
   | --- | --- | --- |
   | Prompt | Apptio Subgrupo de custos | Apptio Subtorre |
   | Nome do Campo | apptio\_custo\_subgrupo | apptio\_sub\_torre |
   | Tipo | Consulta | Consulta |
   | Quem pode ver este campo personalizado? | APPTIO | APPTIO |
   | Consulta | Apptio Grupos de custos | Apptio Torres |
   | Ativo | Verificação | Verificação |
   | Editável | Verificação | Verificação |
   | Mostrar no catálogo | Verificação | Verificação |
   | Necessário | Verificação | Verificação |
3. Para **[COMMODITIES]**, adicione campos personalizados ao objeto **Commodities**.
   1. Adicione um campo personalizado para **Subgrupo de custos de Apptio**.
   2. Adicione um campo personalizado para **a Subtorre Apptio**.
   3. | Campo | Valor - para pools de custos | Valor - para torres de TI |
      | --- | --- | --- |
      | Prompt | Apptio Subgrupo de custos | Apptio Subtorre |
      | Nome do Campo | apptio\_custo\_subgrupo | apptio\_sub\_torre |
      | Tipo | Consulta | Consulta |
      | Quem pode ver este campo personalizado? | APPTIO | APPTIO |
      | Consulta | Apptio Grupos de custos | Apptio Torres |
      | Ativo | Verificação | Verificação |
      | Editável | Verificação | Verificação |
      | Necessário | Verificação | Verificação |
4. Adicione campos personalizados ao objeto **Requisito** na seção **Itens**.
   1. Adicione um campo personalizado para **Subgrupo de custos de Apptio**.
   2. Adicione um campo personalizado para **a Subtorre Apptio**.

      | Campo | Valor - para pools de custos | Valor - para torres de TI |
      | --- | --- | --- |
      | Prompt | Apptio Subgrupo de custos | Apptio Subtorre |
      | Nome do Campo | apptio\_custo\_subgrupo | apptio\_sub\_torre |
      | Tipo | Consulta | Consulta |
      | Quem pode ver este campo personalizado? | APPTIO | APPTIO |
      | Consulta | Apptio Grupos de custos | Apptio Torres |
      | Padrões de [ITENS] | Item: Apptio Custo do subgrupo | Item: Sub-Torre Apptio |
      | Padrões de [COMMODITIES] | Apptio : Subgrupo de custos de commodities | Produto: Subtorre Apptio |
      | Ativo | Verificação | Verificação |
      | Editável | Verificação | Verificação |
      | Necessário | Verificação | Verificação |

      **NOTA** : Certifique-se de que o **padrão** é do **Item: …** para a configuração **[ITENS]** ou **Mercadorias: …** para a configuração **[MERCADORIAS]**.
5. Adicione campos personalizados ao objeto **Pedidos de compra**, na seção **Linhas**.
   1. Adicione um campo personalizado para **Subgrupo de custos de Apptio**.
   2. Adicione um campo personalizado para **a Subtorre Apptio**.
6. Adicione campos personalizados ao objeto **Faturas** na seção **Linhas**.

   | Campo | Valor - para pools de custos | Valor - para torres de TI |
   | --- | --- | --- |
   | Prompt | Apptio Subgrupo de custos | Apptio Subtorre |
   | Nome do Campo | apptio\_custo\_subgrupo | apptio\_sub\_torre |
   | Tipo | Consulta | Consulta |
   | Quem pode ver este campo personalizado? | APPTIO | APPTIO |
   | Consulta | Apptio Grupos de custos | Apptio Torres |
   | Padrões de | linha de requisição: Apptio Subconjunto de custos | linha de requisição: Apptio Sub-Torre |
   | Ativo | Verificação | Verificação |
   | Editável | Verificação | Verificação |
   | Necessário | Verificação | Verificação |

   1. Adicione um campo personalizado para **Subgrupo de custos de Apptio**.
   2. Adicione um campo personalizado para **a Subtorre Apptio**.

| Campo | Valor - para pools de custos | Valor - para torres de TI |
| --- | --- | --- |
| Prompt | Apptio Subgrupo de custos | Apptio Subtorre |
| Nome do Campo | apptio\_custo\_subgrupo | apptio\_sub\_torre |
| Tipo | Consulta | Consulta |
| Quem pode ver este campo personalizado? | APPTIO | APPTIO |
| Consulta | Apptio Grupos de custos | Apptio Torres |
| Padrões de | linha de pedido: Apptio Custo do subgrupo | linha de pedido: Apptio Sub-Tower |
| Ativo | Verificação | Verificação |
| Editável | Verificação | Verificação |
| Necessário | Verificação | Verificação |

**Tarefa 2.4: Vincule itens aos pools e torres de custos padrão Apptio**

**NOTA** : Isso só é necessário se a configuração [ITENS] for seguida, em que cada item exigirá um pool de custos Apptio e subtorres Apptio atribuídas a eles.

Quando um usuário seleciona um item para compra, fornecer um valor padrão para os valores “ Apptio ” (Pool de custos) e “ Apptio ” (Torre de custos) facilita o envio de uma requisição ou fatura pelo usuário. Vincule os itens aos valores padrão do Pool de Custos ( Apptio ) e da Torre de Custos ( Apptio ) para que o valor padrão apareça ao criar uma nova requisição, conforme mostrado abaixo.

**Etapas detalhadas** :

1. Navegue até **Valores de pesquisa** (Configuração > Fornecedores > Itens > Carregar do arquivo).
2. Atualize os itens existentes para incluir os valores de Apptio **Cost Pools** e Apptio **Towers**.
   - Apptio Subgrupo de custos
   - Apptio Subtorre

**Tarefa 2.5: Criar uma visualização personalizada na requisição**

Para visualizar todas as requisições e seus custos associados Apptio tower e Apptio, crie uma nova visualização personalizada.

**Etapas detalhadas** :

1. Navegue até **Campos personalizados** (Requisições > Linhas de requisição > Exibir > Criar exibição).
2. Crie uma nova visualização e clique em **Salvar**.

| Campo | Valor |
| --- | --- |
| Nome | Apptio Torre |
| Visibilidade | Todos |
| Editável por todos | Verificação |
| Comece com a visualização | Todos |
| Condições | Apptio A sub-torre não está em branco |
| Colunas | Criado por (cabeçalho)   Req #   Req Linha #   Item   Fornecedor Total   da linha   Status (cabeçalho)   Mercadoria   Apptio Custo Sub-Pool   Apptio Sub-Torre   Ações |

**Tarefa 3: Criar uma política de taxonomia TBM**

Para permitir que o usuário visualize a taxonomia TBM Apptio como uma política ao criar uma nova requisição que inclua gastos com tecnologia, crie uma nova política para exibir a taxonomia TBM Apptio.

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa4.jpg)

**Etapas detalhadas** :

1. Navegue até **Políticas** (Configuração > Aquisições > Políticas de compra > Criar).
2. Crie uma nova política para **a Taxonomia TBM Apptio** e salve.

**Outras considerações sobre o projeto**

Como todos os campos personalizados têm um grupo de conteúdo da APPTIO, o cliente, durante a implementação, precisará decidir quais usuários avançados ou aprovadores de commodities de TI podem ver/editar as requisições específicas da APPTIO.

Esses usuários devem ter o grupo de conteúdo APPTIO atribuído a eles.

Também deve haver uma etapa de aprovação para garantir que esses usuários avançados possam editar e alterar a requisição em questão como parte da etapa de aprovação. Vá para **Configuração -> Grupos** para adicionar um novo aprovador.

Adicione os aprovadores da APPTIO a este grupo de aprovação editando seus perfis de usuário.

Crie etapas **de aprovação** para **requisições** e **faturas** (se necessário) para garantir que o grupo de usuários Apptio aprove os gastos de TI relacionados ao Apptio.

Um exemplo de etapa **de aprovação** poderia ser:

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa1.jpg)![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa2.jpg)

Quando uma requisição é enviada com uma despesa relacionada a Apptio, o grupo de usuários Apptio será adicionado para aprovação:

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa3.jpg)

**NOTA** : Essas considerações de design devem ser discutidas com o cliente para garantir que suas políticas de aprovação estejam alinhadas com a abordagem. Esta é uma recomendação sobre como esse processo poderia funcionar.
