---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "CTF - Componente de torres de TI: instalar e configurar"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-ittowers-component.html"
images:
  - "resources/images/ct_images/gear_icon.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - Componente de torres de TI: instalar e configurar

O componente CTF - Torres de TI (Recursos) faz parte do módulo Costing Standard Foundation. O componente fornece insights sobre os custos das torres e subtorres de recursos de TI e compara os gastos das torres e subtorres de TI com o orçamento, em apoio às revisões operacionais e estratégicas mensais, trimestrais e anuais.

Aplica-se a: TBM Studio 12.4 e posterior, com o modelo v103 e posterior

## Usa

Você deve instalar o componente CTF - Cost Source antes de instalar o componente IT Towers. O componente instala o IT Resource Towers Master Data.

- Identificar as principais mudanças nas torres de TI nos gastos mês a mês e trimestre a trimestre
- Identificar as principais variações da torre de TI em relação ao orçamento
- Gerenciar os gastos da torre de TI de acordo com o orçamento
- Identificar as principais fontes de custo

## Instalar o componente

Para instalar o componente:

1. Abra o projeto Costing Standard .
2. Na guia Projeto, clique em **Componentes**.
3. Clique no componente **CTF - IT Tower**.
4. Clique em **Install (Instalar** ).

## Sistemas de fonte comum

A estrutura (ou taxonomia) das torres e subtorres de TI está definida no Modelo Unificado de TBM do site Apptio ( ATUM ). A taxonomia é carregada com seu projeto Costing Standard na lista de recursos do IT Resource Towers.

Alguns dos valores necessários para as torres e subtorres de TI não são alocados automaticamente por meio dos outros componentes do CTF (ou seja, os componentes Trabalho, Ativo fixo e Fornecedores). Como resultado, você precisa fazer o seguinte para extrair os dados adequados dos sistemas de origem e carregá-los no site Apptio :

- Mapeie seus centros de custo para torres e subtorres de TI
- Definir uma porcentagem de alocação real para centros de custo que são mapeados para várias torres e subtorres de TI
- Definir uma porcentagem de alocação orçada para centros de custo que são mapeados para várias torres e subtorres de TI

A equipe do Success Management trabalhará com você para determinar como mapear seus centros de custo e códigos de conta e como definir as porcentagens de alocação que funcionam melhor para a sua organização.

## Dados principais

Para obter uma descrição dos campos da tabela de dados mestre, consulte as informações na página do componente CTF - Torres de TI no produto. Para exibir a página:

1. Na guia Projeto, clique em **Componentes**.
2. Clique no componente **CTF - Torres de TI**.

## Campos obrigatórios e opcionais

Os campos a seguir são obrigatórios para os relatórios padrão da Torre de TI:

- Nome da subnível de recursos de TI
- Nome da torre de recursos de TI
- Proprietário da torre de recursos de TI
- Quantidade de torres de recursos de TI
- Unidade de medida

|  |  |  |
| --- | --- | --- |
|  |  |  |

Os campos a seguir são opcionais:

- Meta de custo unitário anual
- Sinalizador de roteamento de ativos
- Metacampo Asset)Resource Key
- Entregar
- Chave Fixed Asset\_ITRT
- Metacampo de chave Fixed Asset\_ITRT
- Metacampo ITRT\_Cloud\_Key
- Chave ITRT\_LPARs
- ITRT\_SaaS Chave
- Metacampo de chave Labor\_ITRT
- Referência mapeada
- Chave do provedor de serviços\_ITRT
- Mapeamento do tipo de serviço
- Jogo de Mesa Sub-Tower
- Metacampo da chave Time Tracking\_ITRT
- Meta de custo unitário
- Metacampo de chave Vendor\_ITRT

Para obter mais informações, consulte o Data Advisor. Para abrir o Data Advisor, abra uma instância ativa do site Apptio, clique no ícone Configurações (![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/gear_icon.png)) e, em seguida, clique em **Data Advisor > IT Towers**.

Além disso, há colunas para o proprietário da torre, a quantidade e a meta de custo unitário. Se estiver implementando o Benchmarking, será necessário preencher a coluna Quantidade. Você pode fazer download da IT Resource Towers Reference List, atualizar os dados e carregar o arquivo como um novo conjunto de dados. Em seguida, você pode mapear a nova lista de referência para o conjunto de dados mestre do IT Towers. Desde que você não altere a lista de torres e subtorres de recursos de TI, você estará em conformidade com a taxonomia do site ATUM.

## Identificadores de torre de recursos de TI

O identificador de objeto Other Cost Pools inclui o centro de custo, a torre de recursos de TI e a subtorre.

O identificador de objeto Torres de recursos de TI inclui a torre e a subtorre de recursos de TI.

## Colunas necessárias para vincular conjuntos de dados

Você também precisará considerar como vincular o IT Resource Towers Master Data a outros conjuntos de dados. A lista a seguir destaca alguns elementos de dados específicos necessários para vincular conjuntos de dados:

- Dados mestre da fonte de custos:
  - Centro de custo
  - Torre de recursos de TI
  - Subtracção de recursos de TI
- Dados mestre do trabalho:
  - Torre de recursos de TI
  - Subtracção de recursos de TI
- Dados mestre do ativo fixo
  - Torre de recursos de TI
  - Subtracção de recursos de TI
- Public Cloud Dados mestre
  - Torre de recursos de TI
  - Subtracção de recursos de TI
- Dados mestre do fornecedor
  - Torre de recursos de TI
  - Subtracção de recursos de TI

Se você não tiver dados suficientes para alocar entre a origem de custos e outros pools de custos, deixe esses custos no objeto origem de custos e não os aloque sem o mapeamento adequado.

Para obter mais informações sobre alocações, consulte [Alocação de custos entre projetos e Torres de recursos de TI no modelo de custos](https://community.apptio.com/docs/DOC-4330 "(Abre em uma nova guia ou janela)").

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
