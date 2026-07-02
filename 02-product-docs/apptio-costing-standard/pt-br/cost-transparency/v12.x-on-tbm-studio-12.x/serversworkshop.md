---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Oficina de Servidores"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/serversworkshop.html"
images:
  - "resources/images/ct_images/servers-workshop.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Oficina de Servidores

## Preparando os dados de seus servidores

1. Se ainda não tiver feito isso, carregue os dados do servidor, incluindo:
   - Lista de servidores
   - Dados de monitoramento do servidor
2. Seguindo as Apptio práticas padrão, categorize cada conjunto de dados brutos na categoria de Servidores.

## Transformações de dados do servidor

Seus dados de servidor incluem todos os servidores físicos, hipervisores e servidores virtuais ou eles estão em conjuntos de dados separados? Se você tiver um conjunto de dados que combine qualquer um desses três tipos de servidores, precisará criar transformações para ter um conjunto de dados separado para cada um dos itens a seguir:

- Servidores físicos
- Hipervisores
- Virtual Servers

Isso geralmente requer a análise dos dados do servidor para determinar o que está incluído e como segmentar os servidores nessas três categorias. É possível usar a opção Filtro de dados na transformação para limitar os registros exibidos por meio da transformação.

## Relação entre servidores físicos, hipervisores e servidores

Um servidor físico é uma peça específica de hardware que pode ser um servidor físico dedicado ou uma máquina host para servidores virtuais.

Um hipervisor é um software de computador que executa servidores virtuais.

Um servidor virtual é um servidor que executa sua própria cópia de um sistema operacional e software, mas está hospedado em um servidor físico que pode ser compartilhado com vários servidores virtuais.

O diagrama abaixo mostra como o Apptio gerencia o relacionamento entre servidores físicos, hipervisores, servidores virtuais e servidores físicos dedicados.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/servers-workshop.png)

## Sobre os identificadores de servidores

O identificador do conjunto de dados mestre de servidores físicos é o ID do servidor físico. Você deve ter alguma forma de identificar cada servidor físico e usá-lo como ID do servidor físico.

O identificador do conjunto de dados mestre de hipervisores é o ID do hipervisor. Assim como acontece com os servidores físicos, você deve ter alguma forma de identificar cada hipervisor e usá-lo como ID do hipervisor.

O identificador do conjunto de dados mestre dos servidores é o ID do servidor. Você deve ter alguma maneira de identificar cada servidor e usá-la como ID do servidor.

## Colunas computadas comuns necessárias para servidores

Para os vários tipos de servidores (que você pode ter em um ou vários conjuntos de dados), há algumas colunas computadas que você pode querer ter.

- Perfil de virtualização (como físico, hipervisor ou virtual)
- Is Virtual Machine (como true ou false)

Em seguida, você pode usar essas novas colunas para filtrar suas transformações e criar chaves entre conjuntos de dados (consulte a próxima seção).

## Sobre as chaves do servidor

As chaves no conjunto de dados mestre do servidor físico são todas definidas pelo usuário. A lógica recomendada está na tabela abaixo.

| Chave | A chave de campo é baseada em | Lógica recomendada |
| --- | --- | --- |
| **Chave ITRT\_Server** | Definido pelo usuário | ="Asset\_Resource - Compute"&&OS    OS é o sistema operacional. O nome de sua coluna pode ter um nome diferente. |
| **Chave do servidor de armazenamento** | Definido pelo usuário | ="Chave do servidor de armazenamento" e nome do dispositivo    Nome do dispositivo é o nome do hardware que vincula o armazenamento ao servidor físico específico. O nome de sua coluna pode ter um nome diferente. Isso deve corresponder à Storage\_Server Key (Chave do servidor de armazenamento) que você definiu nos Dados mestre de armazenamento. |
| **Chave DC\_Server** | Definido pelo usuário | ="Chave do servidor DC"&&Localização    Use somente se estiver implementando o componente Data Centers. O Local é o nome do data center. O nome de sua coluna pode ter um nome diferente. |
| **Chave do servidor de ativos** | Definido pelo usuário | A lógica recomendada é "Asset\_Server" && ID do servidor |
| **Chave Phys\_Hyp** | Definido pelo usuário | =If(Virtualization Profile!= "Physical", "Phys\_Hyp Key"&&Location,"")    Ao verificar se o perfil de virtualização não é físico, você garante que apenas máquinas host e servidores virtuais tenham uma chave Phys\_Hyp. |
| **Chave Phys\_Server** | Definido pelo usuário | =If(Virtualization Profile="Physical", "Phys\_Server Key"&&Device Name,"")    Ao verificar se o perfil de virtualização é físico, você garante que somente os servidores físicos dedicados tenham a chave Phys\_Server. |

As chaves no conjunto de dados mestre do Hypervisors são todas definidas pelo usuário. A lógica recomendada está na tabela abaixo.

| Chave | A chave de campo é baseada em | Lógica recomendada |
| --- | --- | --- |
| **Chave Phys\_Hyp** | Definido pelo usuário | ="Chave Phys\_Hyp" && Localização |
| **Chave Hyp\_Server** | Definido pelo usuário | ="Chave do servidor Hyp" && Localização |

As chaves no conjunto de dados mestre dos servidores são todas definidas pelo usuário. A lógica recomendada está na tabela abaixo.

| Chave | A chave de campo é baseada em | Lógica recomendada |
| --- | --- | --- |
| **Chave Hyp\_Server** | Definido pelo usuário | ="Chave do servidor Hyp" && Localização |
| **Chave Phys\_Server** | Definido pelo usuário | ="Phys\_Server Key" && ID do servidor |
| **Chave Server\_App** | Definido pelo usuário | ="Server\_App" && ID do aplicativo |
| **Chave do servidor de comunicação** | Definido pelo usuário | ="Communication\_Server" && Conexão do servidor |

## Mapear dados para os dados mestre do servidor físico, dados mestre do hipervisor e dados mestre dos servidores

Mapeie os dados de seu servidor físico para o conjunto de dados mestre do servidor físico. A maior parte do mapeamento deve ser autoexplicativa neste ponto. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre dos servidores físicos ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

Mapeie seus dados do hipervisor para o conjunto de dados mestre do hipervisor. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre do hipervisor ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

Mapeie seus dados de servidor físico e virtual para o conjunto de dados mestre de servidores. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre dos servidores ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

A maioria dos mapeamentos deve ser autoexplicativa neste ponto. Em qualquer lugar em que você veja Unidades reais, Unidades orçadas, Contagem de itens ou Contagem de servidores, é possível definir **=1** se estiver usando o ID do servidor como identificador em cada um dos conjuntos de dados.

## Analise o objeto Servers nos modelos

| Modelo | Ações |
| --- | --- |
| **Custo** | Certifique-se de que os valores estejam fluindo para os objetos Physical Server, Hypervisor e Servers.  De Torres de recursos de TI a Servidor físico, aloque usando a Referência baseada em dados, ponderada por Unidades reais (essa é a configuração padrão). As chaves que unem as Torres de Recursos de TI e o Servidor Físico são a Asset\_Resource Key no lado das Torres de Recursos de TI e a ITRT\_Server Key no lado do Servidor Físico.  Do armazenamento ao servidor físico, aloque usando a referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem o Storage ao Physical Server são as colunas Storage\_Server Key em ambos os conjuntos de dados.  Do servidor físico ao hipervisor, aloque usando a referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem o servidor físico ao hipervisor são as colunas Phys\_Hyp Key em ambos os conjuntos de dados.  De servidor físico para servidores, aloque usando a referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem o servidor físico aos servidores são as colunas Phys\_Server Key em ambos os conjuntos de dados.  OBSERVAÇÃO: talvez seja necessário marcar a caixa Criar automaticamente muitos para muitos relacionamentos para essa alocação.  Do hipervisor aos servidores, aloque usando a referência baseada em dados, ponderada pela capacidade de memória (essa é a configuração padrão). As chaves que unem o hipervisor aos servidores são as colunas Hyp\_Server Key em ambos os conjuntos de dados. |
| **Orçamento** | Certifique-se de que os valores estejam fluindo para os objetos Physical Server, Hypervisor e Servers.  De Torres de recursos de TI a Servidor físico, aloque usando a Referência baseada em dados, ponderada por Unidades reais (essa é a configuração padrão). As chaves que unem as Torres de Recursos de TI e o Servidor Físico são a Asset\_Resource Key no lado das Torres de Recursos de TI e a ITRT\_Server Key no lado do Servidor Físico.  Do armazenamento ao servidor físico, aloque usando a referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem o Storage ao Physical Server são as colunas Storage\_Server Key em ambos os conjuntos de dados.  Do servidor físico ao hipervisor, aloque usando a referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem o servidor físico ao hipervisor são as colunas Phys\_Hyp Key em ambos os conjuntos de dados.  De servidor físico para servidores, aloque usando a referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem o servidor físico aos servidores são as colunas Phys\_Server Key em ambos os conjuntos de dados.  OBSERVAÇÃO: talvez seja necessário marcar a caixa Criar automaticamente muitos para muitos relacionamentos para essa alocação.  Do hipervisor aos servidores, aloque usando a referência baseada em dados, ponderada pela capacidade de memória (essa é a configuração padrão). As chaves que unem o hipervisor aos servidores são as colunas Hyp\_Server Key em ambos os conjuntos de dados. |

## Revisar relatórios do servidor

Os relatórios a seguir são atualizados após a configuração do objeto Servers:

- TCO do servidor
- Infra - TCO do servidor - Detalhe
- Infra - Resumo - Servidores
- Comparação de servidores
- Validade dos servidores
- Aplicativo Infra
- Infraestrutura de aplicativos - Detalhe da computação
- Dimensões dos dados - Servidores
- Qualidade dos dados - Recursos de TI
- Qualidade de dados - Servidores

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
