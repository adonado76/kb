---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "release-notes"
title: "Cloudability : Novidades para 2024"
breadcrumb:
  - "Cloudability Premium"
  - "O que há de novo em Cloudability"
source_path: "release-notes/whats-new-2024.html"
images:
  - "images/cca-kubernetes129.jpg"
  - "images/cld_sustainability_metrics.jpg"
  - "images/container-cost-allocation-1.jpg"
  - "images/container-cost-allocation-2.jpg"
  - "images/container-kubernetes1.3.jpg"
  - "images/container_1.jpg"
  - "images/container_2.jpg"
  - "images/covergae-modal-commitmnet-portfolio.jpg"
  - "images/cur-1.jpg"
  - "images/cur-3.jpg"
  - "images/data-reprocess-1.jpg"
  - "images/focus-2.jpg"
  - "images/ibm_cloud_billing.jpg"
  - "images/kube_1.31.jpg"
  - "images/ms_azure_edited.jpg"
  - "images/oci2.jpg"
  - "images/oci3.jpg"
  - "images/oci_1.jpg"
  - "images/pod-level_visibility.jpg"
  - "images/vc1.jpg"
  - "images/vc2.jpg"
  - "images/vc3.jpg"
  - "images/vc4.jpg"
  - "images/vc5.jpg"
  - "images/vc6.jpg"
  - "images/workload-planning-gpu-1.jpg"
  - "images/workload-planning-gpu-2.jpg"
  - "images/workload-planning-oci-1.jpg"
  - "images/wp11.jpg"
  - "images/wp12.jpg"
  - "images/wp13.jpg"
  - "images/wp2.jpg"
  - "images/wp_1.jpg"
  - "images/wp_2a.jpg"
  - "images/wp_3.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cloudability : Novidades para 2024

## Filtragem estatística da interface do usuário do inventário de recursos – 25 de dezembro de 2024

Com esta versão, introduzimos uma nova opção na interface do usuário do Inventário de Recursos (tanto em AWS quanto em Azure ) que permite selecionar e exibir um subconjunto dos dados do Inventário de Recursos. A partir dos dados de inventário gerados para um serviço específico e um determinado período, agora você pode optar por exibir um subconjunto desses dados, seja os x primeiros recursos em número ou os x primeiros em porcentagem, com base na métrica de custo ou utilização de sua preferência.

Por exemplo: o Inventário de Recursos exibe 1.000 registros de um serviço d EC2, referentes a um período de sete dias. Você pode filtrar ainda mais essa exibição, optando por visualizar apenas os 25% superiores desses recursos, com base no Custo (Total). A aplicação desse filtro retornaria, então, os 250 principais recursos com base no Custo (Total), classificados do maior para o menor.

## Suporte à API pública para inventário de recursos - 24 de dezembro de 2024

Hoje, lançamos o suporte a pontos de extremidade de API públicos para os dados de inventário de AWS e Azure, que atualmente estão disponíveis por meio da interface do usuário do Cloudability. Esta versão atende às necessidades dos clientes que desejam extrair os dados por meio de programação. Anteriormente, esses dados só podiam ser acessados pela interface do usuário do Cloudability.

## vCPU Métrica de horas no “ Cloudability ” – 20 de dezembro de 2024

Hoje, temos o prazer de anunciar a expansão da métrica “ vCPU Hours” para incluir suporte ao “ Google Cloud Platform ” ( GCP ). Com base no lançamento dessa métrica para o AWS no início deste ano, os usuários agora também podem obter informações mais detalhadas sobre a utilização de recursos do GCP.

vCPU A métrica de horas oferece maior visibilidade sobre a utilização de recursos, permitindo uma atribuição de custos mais precisa e um planejamento de capacidade bem fundamentado. Ao calcular o tempo total de execução de um vCPUs e em todos os recursos, você passa a ter o conhecimento e a capacidade necessários para otimizar as cargas de trabalho de maneira eficaz.

Estamos trabalhando para ampliar o suporte à métrica “ vCPU Hours” para o Azure, o Oracle Cloud Infrastructure (OCI) e o IBM Cloud em 2025 e 2026.

## Compromisso de suporte às operações CUD do Cloud SQL do GCP — 19 de dezembro de 2024

Hoje, lançamos o suporte para as operações de criação, atualização e exclusão (CUD) do Cloud SQL d GCP.

Este é o terceiro tipo de compromisso do GCP que oferecemos, juntamente com os CUDs do Compute Engine e os Flex-CUDs do Compute Engine. GCP Os CUDs do Cloud SQL são um compromisso baseado em gastos, no qual você se compromete a gastar um determinado valor em dólares em troca de um desconto nos preços sob demanda. Elas funcionam de maneira semelhante aos tipos GCE CUD, na medida em que podem ser combinadas com preços negociados individualmente. Observe que o desconto do Cloud SQL também pode ser negociado e, frequentemente, torna-se menos vantajoso quando se negociam grandes descontos personalizados.

## Interface de usuário aprimorada para recomendações de compromisso do GCP — 19 de dezembro de 2024

Hoje, o site Cloudability apresentou uma experiência de interface de usuário aprimorada nas recomendações de compromisso do site GCP.

A experiência do usuário representou uma melhoria em relação à implementação existente do Compute CUDs, por meio da interface de usuário aprimorada “ GCP Commitment Recommendations”.

Além disso, a GCP só disponibilizou os Compute Flex-CUDs mais cedo. Incluímos também suporte para CUDs de computação baseados em recursos, o que proporciona uma taxa de economia muito maior em nossa nova e aprimorada experiência de interface do usuário.

## Alocação de custos compartilhados para estruturas do Kubernetes - Interface do usuário do Container Insights - 18 de dezembro de 2024

Hoje, lançamos a “Alocação de Custos Compartilhados” na interface do usuário do Container Insights. Esse novo recurso transforma a forma como os custos de infraestrutura compartilhada, como proxies de sistema e ferramentas de monitoramento, são acompanhados e alocados nos ambientes d Kubernetes.

Principais destaques

- Visibilidade granular : alocar custos compartilhados a espaços de nomes específicos do Kubernetes, proporcionando transparência aos proprietários de aplicativos e aos centros de custo
- Novas métricas : visualize os custos compartilhados alocados na interface do usuário com métricas como Custo compartilhado, Rede compartilhada e Memória compartilhada, entre outras
- Regras flexíveis : Defina e gerencie regras de alocação de custos compartilhados para configurações em toda a organização ou específicas de cada cluster

Data de início : Os custos compartilhados serão calculados apenas a partir da data de lançamento do recurso. As consultas anteriores a essa data exibirão resultados vazios na coluna “Custo compartilhado”.

Comportamento da regra :

- As regras se aplicam a datas futuras (em UTC) e não têm efeito retroativo
- As atualizações ou exclusões entram em vigor na data programada
- Várias regras são aplicadas em uma relação de união entre namespaces

Para obter instruções detalhadas sobre a configuração e esclarecimentos, consulte a Central de Ajuda.

Observação: Esse recurso garante uma alocação precisa de custos, ajudando você a melhorar a precisão do showback e do chargeback para recursos compartilhados.

## A alocação de custos de contêineres agora é compatível com a versão Kubernetes 1.31 - 18 de dezembro de 2024

A alocação de custos de contêineres agora é oficialmente suportada no Kubernetes, versão 1.31, em todos os provedores. Esse recurso permite que os clientes obtenham informações detalhadas sobre o uso de recursos de contêineres e os custos associados para clusters em execução no Kubernetes 1.31.

![Captura de tela do Containers CA](../../../../03-media/cloudability-premium/images/kube_1.31.jpg)

## Cloudability Container Insights: Apresentando a visibilidade granular no nível do pod - 17 de dezembro de 2024

Com esta versão, o Cloudability agora oferece informações detalhadas sobre custos e uso no nível do pod por meio do recurso Container Insights. Esse aprimoramento permite que você explore em profundidade uma visualização hierárquica abrangente, oferecendo uma granularidade sem precedentes na análise de custos de contêineres.

Principais recursos

- Acompanhamento granular de custos : Obtenha visibilidade das métricas de custo e uso no nível do pod
- Navegação hierárquica : explore de forma integrada, passando por Cluster → Espaço de nomes → Cargas de trabalho → Pods e contêineres
- Informações detalhadas : Entenda a alocação de custos e a utilização de recursos com uma profundidade sem precedentes

![Captura de tela do nível “Pod”](../../../../03-media/cloudability-premium/images/pod-level_visibility.jpg)

Esta versão disponibilizará a visibilidade no nível do pod a partir da data de lançamento e não refletirá períodos históricos.

## Cloudability para IBM Cloud – Gestão de Custos (GA) – 13 de dezembro de 2024

Hoje, a Apptio anuncia o lançamento em versão geral (GA) da integração do IBM Cloud com o Cloudability. Esta versão oferece aos profissionais d FinOps o acesso integrado e nativo aos custos d IBM Cloud, com dados diretos de uso dentro d Cloudability.

Como esse recurso pode ajudá-lo

Esta versão permite que os clientes do IBM Cloud :

- Atribuir os custos d IBM Cloud e às unidades de negócio com base em regras específicas, utilizando automaticamente as dimensões de negócio d Cloudability.
- Analise os gastos com o IBM Cloud e aumente o senso de responsabilidade da equipe, utilizando análises no nível dos recursos, painéis interativos multicloud e visualizações personalizadas.
- Promova a responsabilidade financeira por meio da criação de orçamentos e notificações de eventos n IBM Cloud.

![Explorador do Custo Real](../../../../03-media/cloudability-premium/images/ibm_cloud_billing.jpg)

Como gerenciar seus gastos com o IBM Cloud

IBM Cloud Os clientes podem dar início à sua jornada de gestão de custos adicionando as credenciais da sua conta. Cloudability importará os dados d IBM Cloud do mês atual assim que suas credenciais forem validadas. Para importar dados históricos adicionais, siga [estas etapas](https://cloud.ibm.com/docs/account?topic=account-exporting-your-usage&interface=ui#access-historical-data "(Abre em uma nova guia ou janela)") e, em seguida, entre em contato com a equipe de suporte do Apptio. Consulte a [documentação da API](../api-v3/getting_started_with_the_cloudability.html) para obter acesso programático e gerenciar as credenciais d IBM Cloud. Participe da conversa na [Comunidade Apptio](https://community.apptio.com/communities/apptioproducts?communitykey=f67c7e7c-be1c-4053-9845-2376da697342 "(Abre em uma nova guia ou janela)") para obter mais informações.

Mais informações sobre este lançamento

Nesta versão, também adicionamos tags personalizadas específicas para o IBM Cloud, que podem ser utilizadas como dimensão adicional nos relatórios:

- Nome do grupo de recursos: cldy:ibm:resourcegroupname
- ID do grupo de recursos: cldy:ibm:resourcegroupid
- ClusterID: cldy:ibm:clusterid
- ID do plano: cldy:ibm:planid
- ID do consumidor: cldy:ibm:consumerid
- Nome da instância como “Nome do recurso”

Com o lançamento desta versão geral (GA), os gastos gerenciados pelo IBM Cloud no Cloudability serão incluídos nos seus Custos Monitorados e estarão sujeitos ao seu Limite de Custos Monitorados contratado.

## Credenciais de fornecedor compartilhadas entre Cloudability Premium e Turbonomic - 10 de dezembro de 2024

A partir de hoje, as contas do CSP ( AWS, Azure e GCP ) e do APM ( Datadog, New Relic ) criadas em Cloudability como parte do pacote Premium passarão a ser compartilhadas com Turbonomic. Com esta versão, os clientes do Cloudability Premium não precisam mais configurar as mesmas contas na nuvem nas ferramentas Cloudability e Turbonomic, o que economiza um tempo significativo de configuração.

As versões subsequentes do Cloudability Premium se baseiam nesta versão para compartilhar e trocar dados. O fluxo de provisionamento de clusters no Cloudability está passando por uma pequena alteração que agora permite o download de dois scripts diferentes de instalação de agentes – Cloudability e Turbonomic – para os agentes no cluster que está sendo provisionado em Cloudability.

Recursos

Cloudability Os administradores agora podem solicitar as permissões adicionais necessárias para que o Turbonomic se integre ao Cloudability. como parte do site Cloudability Premium

implantação. Ao adicionar contas CSP ( AWS, Azure ou GCP ), são solicitadas permissões adicionais necessárias para que o Turbonomic se conecte a essas mesmas contas CSP como parte de relatórios de faturamento (credenciais básicas) e relatórios de utilização (credenciais avançadas); ou você pode optar por conceder permissões adicionais ao Turbonomic para executar ações ou automatizá-las por meio de políticas.

No caso de clientes existentes do Cloudability que estejam migrando para o Cloudability Premium, todas as contas CSP existentes precisam ser editadas, com a concessão de permissões adicionais e uma nova verificação, para que as mesmas contas na nuvem continuem coletando e processando dados.

No caso das contas APM ( Datadog, New Relic ), é necessário fornecer informações adicionais (e verificá-las novamente no caso de clientes existentes do Cloudability que estejam fazendo a atualização para o Cloudability Premium ).

Ao provisionar clusters no Cloudability, os administradores terão a opção de baixar os scripts de instalação do agente Cloudability, Turbonomic e Kubernetes. É necessário que ambos os agentes estejam em execução para que a alocação de custos d Kubernetes (disponível em Cloudability ) e as recomendações de otimização de custos (disponíveis em Turbonomic ) funcionem sem problemas.

Como esse recurso pode ajudá-lo

É necessário configurar as mesmas contas do CSP e do APM tanto no Cloudability quanto no Turbonomic para que esses dois produtos possam coletar, importar e processar dados de faturamento e utilização provenientes dessas fontes. Para economizar tempo de configuração, permitimos que a configuração das contas do CSP e do APM seja feita uma única vez no Cloudability, de modo que ambos os produtos possam aproveitar essa configuração e economizar tempo para os administradores. Depois que as contas forem configuradas e verificadas em Cloudability, essas configurações de conta são compartilhadas com Turbonomic, o que permite que os sondas do Turbonomic sejam executados sem problemas.

Da mesma forma, durante o provisionamento de clusters do Kubernetes, o administrador do Cloudability tem a opção de baixar os scripts de instalação Cloudability e Kubernetes, juntamente com as instruções de instalação. Somente após a instalação de ambos é que os recursos de alocação e otimização de custos passam a funcionar para os clusters do Kubernetes em implantações Premium.

## AWS S3 Ajuste de capacidade - Suporte à classe de armazenamento Glacier Instant Retrieval - 26 de novembro de 2024

Hoje, o Cloudability lançou o suporte às recomendações de ajuste de capacidade do Glacier Instant Retrieval do AWS S3. Os clientes passarão agora a receber recomendações de ajuste de capacidade para a classe de armazenamento “Glacier Instant Retrieval”, juntamente com as demais classes de “ S3 ” atualmente compatíveis.

Antes desta versão, as recomendações para a classe ` S3 ` não eram suportadas.

Onde encontrar a nova funcionalidade

Não é necessária nenhuma configuração adicional para começar a receber essas recomendações, desde que Cloudability esteja corretamente conectado a Amazon Web Services.

Para utilizar o novo recurso, siga estas etapas:

1. Na página inicial do Cloudability, acesse o menu “Otimizar” e selecione “Ajuste de recursos”.
2. Selecione a guia “ AWS ” na página “Rightsizing” e selecione a subguia “ S3 ”. As recomendações de ajuste de capacidade para o Glacier Instant Retrieval aparecerão na lista de recomendações, caso existam e não tenham sido filtradas.

Como esse recurso pode ajudá-lo

Amazon S3 oferece uma variedade de classes de armazenamento à sua escolha, com base nos requisitos de desempenho, acesso aos dados, resiliência e custo das suas cargas de trabalho. Com o objetivo de oferecer recomendações de dimensionamento adequado para o armazenamento de menor custo em diferentes padrões de acesso, agora serão fornecidas recomendações para a classe de armazenamento Glacier Instant Retrieval, além das outras classes atualmente suportadas pelo Cloudability. A classe de armazenamento Glacier Instant Retrieval é normalmente utilizada para dados de arquivo que exigem acesso imediato.

## Métricas de sustentabilidade na nuvem – 25 de novembro de 2024

Hoje, o Cloudability lançou métricas de sustentabilidade em nuvem multicloud com disponibilidade limitada\*. A partir de hoje, você pode visualizar essas métricas de forma rápida e fácil para obter informações sobre as emissões de carbono da nuvem pública.

Onde encontrar essas métricas

Essas novas métricas estão disponíveis nos relatórios e painéis do Cloudability e no Apptio BI.

- Emissões estimadas de carbono ( MTCO2e ): Essa métrica reflete as emissões estimadas de carbono em toneladas métricas de dióxido de carbono equivalente.
- Consumo de energia ( kWh ): Essa métrica indica o consumo de energia em quilowatts-hora.

Essas métricas estão disponíveis no nível do recurso para os serviços compatíveis.

| AWS | Azure | GCP | OCI |
| --- | --- | --- | --- |
| EC2 | Computação (sem GPU) | GCE | Computação (sem GPU) |
| EBS | Disco gerenciado | Disco persistente |  |
| RDS | Azure Banco de dados | SQL na nuvem |  |

Essas métricas também podem ser combinadas com as diversas métricas de custo disponíveis para obter uma visão conjunta das emissões de carbono e dos custos de um recurso ou de outras dimensões, como fornecedor, região e serviço, entre outras.

Você deve conseguir usar isso com suas configurações existentes de visualizações, mapeamentos de negócios, grupos de contas ou mapeamentos de tags. Esses dados também estão disponíveis por meio de exportações e das APIs Cloudability.

Passos para utilizar essas métricas

Configuramos um painel padrão no site Cloudability para facilitar o início, na seção “Todos os painéis ”, chamado “Painel de amostra de sustentabilidade na nuvem ”.

Para utilizar as métricas de sustentabilidade da nuvem:

1. Acesse a página inicial do Cloudability.
2. Clique em “Novo relatório”/“Adicionar widget”.
3. Na seção de métricas d Cloudability, role até a categoria “Sustentabilidade”.
4. Selecione as métricas.

![Métricas de sustentabilidade na nuvem](../../../../03-media/cloudability-premium/images/cld_sustainability_metrics.jpg)

\*Disponibilidade limitada: isso significa que todos os recursos e funções estão disponíveis, mas, no momento, estão sendo disponibilizados apenas para um segmento específico de clientes. Isso será estendido a todos os clientes nos próximos meses.

Nota:

Essas métricas estão disponíveis apenas para clientes que possuam os SKUs Cloudability Enterprise, Cloudability Standard e Cloudability Premium.

## Reprocessamento de dados no autoatendimento – 22 de novembro de 2024

Hoje, anunciamos a disponibilidade geral do recurso “Reprocessamento de Dados em Autoatendimento” para nossos clientes do Cloudability.

Esse recurso permite que você reprocesse seus dados sem precisar recorrer às equipes de Suporte ou de Sucesso do Cliente. Em comparação com o processo baseado em solicitações, esse recurso oferece um tempo de resposta mais rápido, elimina etapas manuais, aumenta a transparência nas solicitações dos usuários e melhora a experiência geral.

Com esta versão, também corrigimos um problema crítico em que os dados reprocessados não eram refletidos imediatamente nos Relatórios após a conclusão da tarefa, causando atrasos na visualização das informações atualizadas. Agora, após a conclusão do trabalho, você pode consultar os dados reprocessados no Reports imediatamente. Além disso, a aba Status da tarefa exibe a hora de conclusão da tarefa e o campo Motivo.

Durante a implementação inicial, recebemos comentários sobre algumas lacunas na experiência do usuário e no produto por parte de clientes que exportavam seus dados da nuvem do Cloudability (ou via CDI) para o Costing & Planning. Portanto, decidimos suspender temporariamente esse recurso para os clientes que utilizam a integração do Cloudability ou do CDI com o Costing & Planning; no entanto, ele estará disponível para os clientes que possuem apenas o Cloudability. Estamos trabalhando ativamente para aprimorar a experiência e esperamos lançar o recurso aprimorado no início do próximo ano. Cloudability Os clientes do módulo de Cálculo de Custos e Planejamento que tinham acesso durante a implantação inicial continuarão a manter esse acesso

O recurso não está ativado por padrão, pois se trata de um recurso opcional. Entre em contato com a Equipe de Suporte para obter acesso ao recurso.

Mais informações sobre o recurso

Quando ativado, esse recurso pode ser acessado navegando até  Organizar  >  Reprocessamento de dados no  Cloudability

![Reprocessamento de dados](../../../../03-media/cloudability-premium/images/data-reprocess-1.jpg)

Para clientes que utilizam exclusivamente o Cloudability, este é um processo de duas etapas para o Reprocess, no qual você pode selecionar o Período e enviar o trabalho. Você também pode acompanhar o status do trabalho na aba Status do Trabalho. Para obter instruções detalhadas, consulte [Reprocessamento de dados para usuários Cloudability](../product/data_reprocess.html#data_reprocess__Data).

Para clientes do Costing & Planning com o Cloudability ou o CDI: o recurso está suspenso. Consulte o documento ["Reprocessamento de dados para usuários Cloudability - Custos e Planejamento"](../product/data_reprocess.html#data_reprocess__Data2).

## Modelo de cobertura aprimorado em toda a carteira de compromissos d GCP — 19 de novembro de 2024

Hoje, lançamos a janela modal de cobertura aprimorada em todo o Portfólio de Compromissos do GCP.

Essa melhoria aprimora o modal de cobertura já existente, lançado anteriormente na página “Portfólio de Compromissos de Flex-CUDs” do site GCP, e estende esse modal a todas as páginas de portfólio do site GCP. Simplificamos a terminologia e dividimos a janela modal em duas seções. A seção de cálculo da porcentagem de cobertura inclui todas as informações necessárias para calcular a cobertura daquela página específica. A seção “Resumo da cobertura por fornecedor” apresenta, para maior comodidade, os valores de cobertura no nível do fornecedor.

![GCP cobertura](../../../../03-media/cloudability-premium/images/covergae-modal-commitmnet-portfolio.jpg)

## Apptio Transição da comunidade para IBM TechXchange - 1º de novembro de 2024

Atualmente, a comunidade Apptio fez a transição completa para IBM TechXchange.

As melhores práticas para aproveitar ao máximo a experiência do site IBM TechXchange estão listadas a seguir.

- Use e salve nos favoritos [esta nova página inicial](https://community.ibm.com/community/user/apptio/home "(Abre em uma nova guia ou janela)") dos grupos temáticos do Apptio.
- Acesse o grupo de tópicos relevante para suas necessidades; alguns dos grupos de tópicos com os quais você está familiarizado foram combinados em novos grupos de tópicos.

Os seguintes grupos de tópicos estão disponíveis:

- [Apptio](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=4100dfb8-fc23-4203-83c7-019253cf7c0b "(Abre em uma nova guia ou janela)") : Fundamentos de Cálculo de Custos, Padrão de Cálculo de Custos (CT-Foundation), Apptio Planning (ITP/ITFMF), Faturamento (Billing Standard), Análise Comparativa (Benchmarking), Integração com o ServiceNow
- [Cloudability](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=15c0e07d-35c0-49de-a84b-019253d13376 "(Abre em uma nova guia ou janela)") : Cloudability Financial Planning, Cloudability TotalCost, Apptio Turbonomic Integração
- [https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=55a3712d-1835-4ec2-bcd7-603e88cd9dd2](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=55a3712d-1835-4ec2-bcd7-603e88cd9dd2 "(Abre em uma nova guia ou janela)")
- [Plataforma](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8 "(Abre em uma nova guia ou janela)") : Apptio BI, ATUM, Automated Data Management, DataLink, Frontdoor, TBM Studio
- [Apptio para todos](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=2e85ed45-9b8a-486c-bd55-019253d466eb "(Abre em uma nova guia ou janela)")

- Quando estiver em seu grupo de tópicos, leia e contribua com todo o conteúdo habitual, como links rápidos, discussões, perguntas e blogs.
- Confira [esses recursos](https://community.ibm.com/community/user/participate/resources "(Abre em uma nova guia ou janela)") sobre como navegar e utilizar a comunidade.
- Comece a enviar solicitações de melhorias no [IBM Ideas](https://login.ibm.com/idaas/mtfim/sps/idaas/login?client_id=nwnjmzc5njetmzlkyi00&target=https%3a%2f%2flogin.ibm.com%2foidc%2fendpoint%2fdefault%2fauthorize%3fqsid%3dc75ff073-50e8-4426-8979-7e4b6b992e80%26client_id%3dnwnjmzc5njetmzlkyi00 "(Abre em uma nova guia ou janela)").

  - IBM utiliza um portal unificado de sugestões em [ideas.ibm.com](https://ideas.ibm.com/ "(Abre em uma nova guia ou janela)") para que você possa enviar sugestões sobre todos os produtos. A partir de hoje, essa lista foi ampliada para incluir os produtos recentemente adquiridos da Apptio. As ideias enviadas antes da aquisição serão disponibilizadas para as equipes de produtos e poderão ser adicionadas ao portal em uma data futura para garantir a continuidade.

Entre em contato com a equipe da comunidade pelo nosso novo e-mail,  [support@communitysite.ibm.com](mailto:support@communitysite.ibm.com "(Abre em uma nova guia ou janela)"),  caso tenha alguma dúvida ou necessidade.

## Fornecedores Externos e Suporte do FOCUS - 29 de outubro de 2024

Hoje, lançamos o gerenciamento de custos para provedores de nuvem terceirizados de forma nativa no Cloudability.

Isso representa uma melhoria significativa para o Cloudability, simplificando a forma como os profissionais de FinOps gerenciam os custos de fornecedores como Datadog, Databricks e Snowflake. O fato de esses dados de custo e uso estarem disponíveis nativamente na plataforma Cloudability permite que sejam utilizados em recursos como Mapeamento de Negócios, Visualizações e Painéis. Dependendo do fornecedor, esses dados podem ser importados por meio de um conector direto ou através do esquema FOCUS, adotado pelo setor.

Esta versão permite que os clientes do Cloudability :

- Importar dados de faturamento do Datadog, Databricks, Snowflake e MongoDB por meio de conectores diretos e de outros fornecedores, utilizando exportações compatíveis com o FOCUS.
- Atribua esses custos à empresa com base em suas regras específicas, utilizando os recursos de mapeamento de tags, grupos de contas e mapeamento de negócios.
- Analise esses gastos e aumente o senso de responsabilidade da equipe por meio de painéis interativos em ambiente multicloud e visualizações personalizadas.
- Promova a responsabilidade financeira por meio da definição de orçamentos e notificações sobre eventos.

![Foco no TCE](../../../../03-media/cloudability-premium/images/focus-2.jpg)

Entrada no FOCUS

Cloudability Os clientes agora podem obter maior flexibilidade importando dados de custos e uso de quaisquer fontes de dados ou fornecedores adicionais que ainda não sejam compatíveis com conectores diretos. Os dados de faturamento precisam ser convertidos para o formato FOCUS e enviados para as contas de armazenamen AWS, Azure ou GCP. Assim que o processo de credenciamento for validado, os clientes poderão gerar relatórios sobre esses gastos adicionais e alocá-los de volta à empresa.

Comece hoje mesmo a gerenciar seus gastos com fornecedores terceirizados

Você pode dar início à sua jornada de gerenciamento de custos adicionando credenciais para suas contas, seguindo as instruções na Central de Ajuda para [Datadog](../admin/connect-datadog-cost-usage_data.html), [Databricks](../admin/connect-databricks.html), [MongoDB](../admin/connect-mongodb.html), [Snowflake](../admin/connect-snowflake.html) e [FOCUS ingress](../admin/connect-custom-data-focus-ingress.html). Por padrão, o Cloudability importará os dados do mês atual após a validação de suas credenciais. Caso deseje que sejam importados dados de meses adicionais, entre em contato com a equipe do Apptio.

## Planejamento da carga de trabalho - Modelos de carga de trabalho - 24 de outubro de 2024

Hoje, lançamos os Modelos de Planejamento de Carga de Trabalho, que permitem aos usuários criar cargas de trabalho que podem ser facilmente compartilhadas como modelos em toda a organização.

Os modelos de carga de trabalho podem ser usados para personalizar aplicativos, divulgar configurações e recursos aprovados para novos aplicativos junto a outros usuários ou compartilhar exemplos específicos de carga de trabalho. Esses modelos são gerenciados pelos usuários com permissão de administrador do Cloudability, e qualquer pessoa da organização pode duplicá-los para que possam ser utilizados no planejamento de novos aplicativos.

Anteriormente, os usuários do Workload Planning podiam compartilhar cargas de trabalho, mas, por padrão, elas não eram visíveis em toda a organização. Com esta versão, as equipes de gerenciamento de mudanças ( FinOps ), bem como o arquiteto ou as equipes de engenharia, podem gerenciar e compartilhar facilmente configurações aprovadas no Cloudability.

Criação de modelos de planejamento de carga de trabalho

Para criar um modelo, os usuários com permissão de administrador no Cloudability podem simplesmente criar uma carga de trabalho, adicionar os recursos necessários e selecionar “Salvar como modelo” na etapa “Resumo ”. Os usuários podem exportar um modelo e também duplicá-lo para editar a cópia.

## AWS Rightsizing - Suporte à coleta de dados de memória “MBytes disponíveis” - 23 de outubro de 2024

Hoje, o Cloudability lançou AWS um recurso de ajuste de tamanho para a obtenção de métricas de utilização de memória por meio da métrica “Mbytes disponíveis” no agente CloudWatch para máquinas Windows AWS.

A partir de hoje, os clientes podem usar a configuração da métrica “Mbytes disponíveis” para fornecer ao Cloudability dados de memória mais precisos, a serem utilizados nas recomendações de ajuste de recursos.

Antes desta versão, o Cloudability AWS rightsizing suportava apenas a análise de métricas de utilização de memória AWS para máquinas Windows, utilizando a métrica “% de bytes comprometidos em uso”. Ambas as métricas continuarão sendo oferecidas daqui para frente.

Mais informações sobre este lançamento

Para habilitar a métrica de memória “Mbytes disponíveis” para análise de consumo, siga estas etapas:

1. No site Cloudability, acesse o menu Otimizar e, em seguida, selecione Ajuste de tamanho.
2. Selecione a guia “ AWS ” na página “Rightsizing”, cuja configuração padrão é “ EC2 ”.

As métricas de memória disponíveis são exibidas em um gráfico no painel de detalhes da recomendação de ajuste de tamanho.

AWS oferece várias opções para a inclusão de métricas de memória no agente do CloudWatch. Embora já houvesse suporte para a análise de métricas de memória em máquinas Windows por meio da métrica “% Committed Bytes InUse ”, alguns clientes já haviam configurado a métrica “Available Mbytes” e, por isso, não estavam visualizando as métricas de memória em suas recomendações de ajuste de recursos. Além de oferecer mais flexibilidade aos clientes, a métrica “Mbytes disponíveis” é, na verdade, uma medida de memória mais precisa, pois representa diretamente a quantidade de RAM livre, ao contrário da métrica “% de bytes comprometidos emuso ”, que abrange tanto a memória física quanto a memória virtual e, portanto, pode ser uma avaliação menos precisa.

## Ajuste de tamanho do grupo de computação – Opção de filtragem para redução do número máximo de instâncias - 22 de outubro de 2024

Hoje, o Cloudability lançou uma nova opção de filtragem no nível da página para páginas de ajuste de tamanho de grupos de computação ( AWS EC2 ASG, GCP GCE MIG), que oferece um novo método de filtragem de recomendações.

Anteriormente, quando selecionada, a opção “Redução do número máximo de instâncias” filtrava as recomendações, exibindo uma redução no número de instâncias — caso houvesse — para o tipo de instância atual. As outras opções de recomendação para uma instância, caso existam, serão exibidas no painel de detalhes, como de costume, após a recomendação principal. Isso oferece uma maneira fácil e rápida de mostrar a economia de custos obtida com a redução do número de instâncias em um grupo de computação, sem a necessidade de outras alterações.

Onde encontrar essa nova funcionalidade

1. No menu de navegação principal do Cloudability, acesse Otimizar e selecione Ajuste de tamanho.
2. Selecione a guia AWS ou GCP na página Rightsizing e acesse a subguia do grupo de computação ( EC2 ASG ou GCE MIG ).
3. Selecione o menu suspenso Opções e escolha Redução das principais contagens para filtrar as recomendações.

Mais informações sobre este lançamento

Já havia uma funcionalidade disponível para que os clientes pudessem filtrar as recomendações de grupos de computação, de modo que fossem exibidas apenas aquelas com reduções no número de instâncias. No entanto, isso ainda exigia mais reflexão e esforço para alterar os tipos de instância quando as recomendações assim o exigiam. Esse novo recurso filtra as recomendações para apresentar apenas os casos em que o tipo de instância permanece inalterado, mas uma redução no número de instâncias é sugerida como recomendação principal. Isso permite que os clientes identifiquem rapidamente e aproveitem as oportunidades de economia “fáceis de alcançar”, que exigem apenas uma redução no número de instâncias do grupo de computação. Essas recomendações também são exibidas como a principal recomendação por serem fáceis de usar.

## Suporte adicional a tipos de sistemas operacionais para máquinas virtuais no planejamento de cargas de trabalho — 21 de outubro de 2024

Hoje, lançamos o suporte a novos tipos de sistemas operacionais no Planejamento de Carga de Trabalho entre provedores de nuvem. Com essa melhoria, os usuários podem obter estimativas e recomendações do VM com base nos seguintes 11 sistemas operacionais:

- Red Hat Enterprise Linux
- Red Hat Enterprise Linux com HA
- Red Hat Enterprise Linux com o site SQL Server
- Red Hat Enterprise Linux com o padrão “ SQL Server ”
- Red Hat Enterprise Linux com o SQL Server Enterprise
- Red Hat Enterprise Linux for SAP
- SUSE Linux Enterprise Server
- Windows Server com o SQL Server Standard
- Windows Server com o site “ SQL Server ”
- Windows Server com o SQL Server Enterprise
- Ubuntu Prós

Antes desta versão, o Planejamento de Carga de Trabalho oferecia suporte apenas aos sistemas operacionais Windows e Linux, o que limitava os resultados das recomendações de Compute. Com a capacidade de visualizar os recursos d VM em diversos tipos de sistemas operacionais, os usuários agora podem encontrar opções mais econômicas para suas cargas de trabalho, comparando ofertas de vários fornecedores.

## Suporte à granularidade diária para dados de inventário de recursos — 14 de outubro de 2024

Hoje, introduzimos o suporte à granularidade diária para os dados do Inventário de Recursos do Cloudability. Anteriormente, o Resource Inventory oferecia suporte apenas a dados agregados mensais para todas as suas medidas (dimensões e métricas).

Com esta versão, os usuários poderão visualizar os dados diários do inventário de recursos para um intervalo de datas específico, utilizando o seletor de datas do aplicativo. (Mínimo de 1 dia e máximo de 31 dias por relatório)

## Apresentando a permissão “Administração de faturamento” no Cloudability - 9 de outubro de 2024

Hoje, lançamos uma nova permissão do Front Door chamada “ OrgCurrencyFeatureAccess ” para o Cloudability. Essa permissão permite que os usuários acessem a aba “Moeda” no perfil gerenciado.

Com essa permissão, os usuários podem definir a moeda padrão da organização. Atualmente, essa permissão é configurada no portal do Active Admin. Mudar isso para a “Porta da Frente” nos ajudará a centralizar todas as nossas permissões nesse local.

Observação: a permissão de administrador de faturamento no portal Active Admin estará disponível até 31 de janeiro de 2025; a partir dessa data, ela será descontinuada.

## Lançamento do Cloudability na região do Oriente Médio – 30 de setembro de 2024

Hoje, lançamos a hospedagem do Cloudability, nossa plataforma de gerenciamento de custos em nuvem, na região do Oriente Médio, no data center dos Emirados Árabes Unidos.

Como esse recurso pode ajudá-lo

Esta versão atende às necessidades específicas dos nossos clientes da região do Oriente Médio, garantindo que seus dados permaneçam dentro dos limites regionais. Ao localizar nossos serviços, nosso objetivo é capacitar as organizações a fortalecerem suas iniciativas de conformidade e se alinharem às diretrizes relativas aos dados de gestão de custos em nuvem.

Mais informações sobre o lançamento

O lançamento do serviço de hospedagem Cloudability na região do Oriente Médio reveste-se de grande importância para nossos clientes que atuam nessa região. A solução oferece uma gestão de custos em nuvem confiável e em conformidade, que prioriza a residência dos dados, reforça a privacidade dos dados e está alinhada às diretrizes de proteção de dados.

Observação: Os clientes sediados na região do Oriente Médio que tenham interesse em migrar dos EUA/UE para a região do Oriente Médio podem entrar em contato com seus respectivos gerentes de conta ou com a equipe de Sucesso do Cliente. Não é necessária nenhuma configuração ou instalação adicional para os clientes que estiverem se cadastrando diretamente no site Cloudability na região do Oriente Médio.

## Adicionados alertas de vencimento de compromissos para todos os tipos de compromisso suportados — 27 de setembro de 2024

Hoje, Cloudability anuncia o suporte a alertas de expiração para todos os tipos de compromisso anteriormente não suportados, incluindo AWS Savings Plans, Azure Savings Plans, GCP Compute Engine CUDs e GCP Compute Engine Flexible CUDs.

Além disso, o modelo de e-mail foi atualizado para utilizar terminologia independente de fornecedor e incluir campos adicionais, a fim de aprimorar o alerta.

## Cloudability - Permissões detalhadas para visualizações - 26 de setembro de 2024

Hoje, estamos implementando duas melhorias nesta versão.

- Adicionar uma nova permissão no Front Door chamada “ ViewsFeatureCreateOwnViewsAccess ”, que permitiria a um usuário ao qual essa permissão fosse atribuída criar, atualizar e excluir visualizações criadas por ele, com acesso somente para leitura às visualizações criadas por outras pessoas.
- Anteriormente, um usuário sem privilégios de administrador (função personalizada) ao qual havia sido atribuído o ViewsFeatureFullAccess não conseguia editar visualizações criadas por outras pessoas. Com esta versão, os usuários com essa função poderão atualizar ou excluir quaisquer visualizações adicionadas à sua organização no Cloudability.

O impacto para os clientes atuais seria que qualquer função de usuário em sua organização — seja uma função de nível administrativo ou uma função personalizada com a permissão ViewsFeatureFullAccess — passaria a poder editar ou excluir quaisquer visualizações criadas por qualquer pessoa em sua organização. Se quiserem restringir esse acesso, será necessário atribuir a esses usuários uma função personalizada com a permissão ViewsFeatureCreateOwnViewsAccess. Se tanto ViewsFeatureFullAccess quanto ViewsFeatureCreateOwnViewsAccess estiverem atribuídos à mesma função, então ViewsFeatureFullAccess — por ter privilégios superiores — terá precedência.

## Cloudability Container Insights: Apresentando o suporte ao compartilhamento de painéis - 19 de setembro de 2024

Hoje, temos o prazer de anunciar o lançamento do recurso de compartilhamento de painéis do Container Insights 2.0, projetado para aprimorar a colaboração e agilizar o acesso a métricas essenciais de contêineres em toda a sua organização.

Principais destaques

- Compartilhar painéis personalizados: Agora, os usuários podem compartilhar seus painéis personalizados internamente com toda a organização ou com membros específicos da equipe, permitindo uma divulgação mais ampla das informações.

- Permissões do painel: ajuste o controle de acesso atribuindo uma das seguintes funções:

  - Editor: Pode modificar o painel e gerenciar as permissões de compartilhamento.
  - Visualizador: Tem acesso somente para visualização, sem poder editar ou compartilhar o painel.

As permissões são facilmente gerenciadas e monitoradas em tempo real, proporcionando transparência sobre quem pode acessar e modificar cada painel. O proprietário do painel mantém controle total, incluindo a capacidade de editar, compartilhar e excluir o painel.

- Destaques e Favoritos: Os usuários podem marcar painéis como favoritos, tornando-os facilmente acessíveis a partir de uma lista suspensa. Os painéis marcados com estrela aparecem no topo da lista, ordenados em ordem alfabética para facilitar o acesso.

- Colaboração aprimorada: Facilite o trabalho em equipe de forma integrada, permitindo que os colegas contribuam para painéis compartilhados, seja editando-os ou visualizando-os. Isso garante que todos tenham acesso às informações mais atualizadas. Embora os usuários não possam filtrar ou mover widgets no painel, eles podem usar a opção “Salvar como painel” para criar um novo painel com base no original, o que lhes permite explorar os dados e personalizá-lo de acordo com suas necessidades.

Como começar

1. Criar um painel: Crie um painel personalizado adicionando métricas-chave e widgets que atendam às suas necessidades.

1. Compartilhar: Use a opção de compartilhamento do painel para conceder acesso a toda a organização ou a membros específicos da equipe, atribuindo as funções adequadas.

![Captura de tela do CCA](../../../../03-media/cloudability-premium/images/container-cost-allocation-1.jpg)

1. Gerenciar permissões: Controle e atualize quem pode visualizar, editar ou gerenciar o painel por meio de configurações intuitivas.

![compartilhar contêineres do painel](../../../../03-media/cloudability-premium/images/container-cost-allocation-2.jpg)

Esse recurso simplifica o compartilhamento de métricas essenciais dos contêineres, tornando as informações mais acessíveis e úteis para todas as equipes. Ao aprimorar a colaboração, as equipes podem promover uma melhor tomada de decisões e garantir que todos estejam alinhados em relação aos principais dados sobre contêineres.

## Adicionada a dimensão “Nome do recurso” para o faturamento por nível de recurso do GCP — 17 de setembro de 2024

Hoje, lançamos uma nova dimensão de relatórios, chamada “Nome do recurso”, em toda a análise do Cloudability. No momento, este lançamento é destinado ao GCP, mas será atualizado em breve para o Azure e o OCI.

Novidades desta versão

Essa dimensão representa o nome atribuído aos recursos d GCP, como o nome de uma instância d VM, o nome de um disco ou o nome de um banco de dados. Esse detalhe corresponde ao que os usuários veem no console do GCP ao interagir com recursos e está alinhado com a coluna “Nome global do recurso” no Faturamento por nível de recurso do GCP. Esta é a primeira de várias versões que servirão como atualizações fundamentais para nosso suporte a descontos baseados em compromissos.

Benefícios para os usuários

Atribuição de custos aos recursos : os usuários podem associar custos à sua infraestrutura imediatamente.

Relatórios e painéis de controle fáceis de usar : os usuários terão mais clareza nos relatórios, eliminando a necessidade de analisar detalhes desnecessários, como caminhos completos de API.

## Portfólio Consolidado de Compromissos e Melhorias — 12 de setembro de 2024

Hoje, lançamos três melhorias na carteira de compromissos, abrangendo cada um dos três fornecedores compatíveis.

Novidades desta versão

- Portfólio de Compromissos Consolidado : As páginas “Portfólio de Reservas” e “RI Planner” foram atualizadas para “Portfólio de Compromissos” e “Recomendações de Compromissos”, respectivamente, a fim de refletir uma nomenclatura independente de fornecedores. Além disso, o suporte a compromissos baseados em gastos agora está consolidado por fornecedor na página única do portfólio, com as páginas de compromissos reorganizadas em conjunto sob  Otimizar  .
- AWS & Melhorias na carteira dos Planos de Economia Azure : A tabela e os KPIs foram atualizados, e o painel de detalhes foi adicionado para corresponder às versões correspondentes dos Planos de Economia.
- GCP Aprimoramentos no portfólio : as páginas “Todos os compromissos” e “Todos os recursos de computação” foram adicionadas para apresentar o desempenho em nível agregado. Os KPIs atualizados na página do portfólio de CUDs de Compute baseados em recursos agora correspondem aos CUDs de Compute Flex d GCP. Por fim, as tabelas agrupadas e não agrupadas mostram a propriedade e como o compartilhamento afeta o desempenho.

Esta é a primeira de várias versões que servirão como atualizações fundamentais para nosso suporte a descontos baseados em compromissos. Para [obter](../product/commitment-portfolio.html) mais informações sobre compromissos, consulte Introdução à carteira de compromissos. Participe da discussão em nosso [Anúncio da Comunidade](https://community.apptio.com/login?returnurl=https%3a%2f%2fcommunity.apptio.com%2fviewdocument%2fnotice-upcoming-launch-consolidate%3fcommunitykey%3df67c7e7c-be1c-4053-9845-2376da697342%26tab%3dlibrarydocuments "(Abre em uma nova guia ou janela)").

## Suporte da coluna RIS para Business Dimensions – 5 de setembro de 2024

Com esta versão, os usuários do inventário de recursos podem adicionar dimensões de negócios como uma coluna na interface do usuário do Cloudability para seus relatórios de inventário.

Isso os ajudaria a comparar seus dados de estoque com as dimensões de negócios criadas em sua organização.

## Cloudability Container Insights - Apresentando o KPI “Índice de Eficiência (Uso)” - 3 de setembro de 2024

Com esta versão, o Cloudability introduziu uma nova métrica de KPI, a Pontuação de Eficiência (Uso), que oferece uma visão clara e prática da eficiência de custos em todos os recursos dentro de um contêiner, namespace, carga de trabalho, cluster e muito mais. Essa métrica está disponível como uma opção predefinida que os usuários podem adicionar facilmente aos seus painéis, selecionando-a na categoria de widgets predefinidos, na seção “Adicionar widget ”.

O que é a Pontuação de Eficiência (Uso)

O Índice de Eficiência (Uso) é calculado comparando-se o custo dos recursos consumidos ativamente (uso) com o custo total dos recursos reservados (provisionados ou alocados). Essa pontuação ajuda as equipes a avaliar a eficácia com que os recursos reservados estão sendo utilizados e destaca ineficiências, como o provisionamento excessivo ou a subutilização. Uma pontuação mais alta indica maior eficiência no uso de recursos, enquanto uma pontuação mais baixa revela áreas com potencial para otimização.

Este KPI foi concebido para fornecer às equipes uma visão mais aprofundada sobre a utilização de seus recursos, auxiliando nas decisões relacionadas à alocação de recursos, ao ajuste de capacidade e às estratégias de otimização.

## Cloudability para IBM Cloud – Gerenciamento de Custos (Beta) - 30 de agosto de 2024

Hoje, a Apptio anuncia o lançamento da integração do IBM Cloud com o Cloudability. Esta versão oferece aos profissionais d FinOps o acesso integrado e nativo aos custos d IBM Cloud, com dados diretos de uso dentro d Cloudability.

Como esse recurso pode ajudá-lo

Esta versão permite que os clientes do IBM Cloud :

- Atribuir os custos d IBM Cloud e às unidades de negócio com base em regras específicas, utilizando automaticamente as dimensões de negócio d Cloudability.
- Analise os gastos com o IBM Cloud e aumente o senso de responsabilidade da equipe, utilizando análises no nível dos recursos, painéis interativos multicloud e visualizações personalizadas.
- Promova a responsabilidade financeira por meio da criação de orçamentos e notificações de eventos n IBM Cloud.

![IBM Cloud painel de controle](../../../../03-media/cloudability-premium/images/ibm_cloud_billing.jpg)

Como gerenciar seus gastos com o IBM Cloud

IBM Cloud Os clientes podem dar início à sua jornada de gestão de custos adicionando as credenciais da sua conta. Cloudability importará os dados d IBM Cloud do mês atual assim que suas credenciais forem validadas. Para a importação de dados adicionais, entre em contato com a equipe do Apptio. Consulte a [documentação da API](../api-v3/getting_started_with_the_cloudability.html) para obter acesso programático e gerenciar as credenciais d IBM Cloud. Participe da conversa na [Comunidade Apptio](https://community.apptio.com/blogs/alok-jain/2024/08/26/cloudability-for-ibm-cloud-cost-management-faq "(Abre em uma nova guia ou janela)") para obter mais informações.

Mais informações sobre este lançamento

Não será cobrado nenhum valor pelas despesas com a nuvem gerenciada d IBM Cloud durante o período Deta. No entanto, os gastos gerenciados pelo IBM Cloud no Cloudability serão incluídos nos seus Custos Monitorados após o lançamento da versão geral (GA) e estarão sujeitos ao seu Limite de Custos Monitorados contratado. Atualmente, o lançamento do GA está previsto para 15 de novembro de 2024, podendo ser adiado para uma data posterior.

## GCP Rightsizing – Suporte detalhado para faturamento - 28 de agosto de 2024

Com esta versão, a Cloudability lançou o suporte ao faturamento por nível detalhado no Rightsizing do GCP, o que possibilita diversos novos recursos que não estavam disponíveis anteriormente.

A partir de hoje, os usuários que tiverem o faturamento detalhado d GCP e ativado perceberão que o Rightsizing d GCP agora conta com:

- Uma opção de base de custo “efetiva” para recomendações de computação
- Suporte para visualizações baseadas em mapeamentos de tags, mapeamentos de negócios e grupos de contas
- Suporte à filtragem com base em mapeamentos de tags/negócios
- Mapeamentos de tags de recursos visíveis no painel de detalhes da recomendação
- Exportações que contêm mapeamentos de tags de recursos

Antes desta versão, Cloudability GCP O Rightsizing não dispunha de um meio de acessar os dados detalhados necessários para fornecer esses itens de suporte à paridade de recursos do CSP.

Essa funcionalidade já estava disponível para os clientes nas áreas aplicáveis do rightsizing para AWS e Azure, mas não estava disponível para GCP. Os mesmos problemas encontrados no redimensionamento de AWS e Azure sem esses recursos estão agora resolvidos também para GCP. A base de custo efetiva leva em consideração o impacto histórico das Instâncias Reservadas (RIs) e dos Planos de Economia (SPs) para calcular o custo do tipo de recurso atual ao longo do período do relatório. O suporte a visualizações e filtragem com base em mapeamentos de tags, mapeamentos de negócios e grupos de contas permite que os usuários criem e visualizem uma experiência e um conjunto de dados mais personalizados. Os mapeamentos de tags visíveis permitem que os usuários vejam quais mapeamentos de tags estão associados a um recurso, a fim de tomarem uma decisão mais informada sobre uma recomendação. As exportações que contêm mapeamentos de tags de recursos também fornecem aos usuários essas informações adicionais, que podem ser utilizadas de qualquer forma em que as exportações forem utilizadas pelo cliente.

Como ativar o faturamento detalhad GCP

Para configurar o faturamento detalhad GCP, consulte [Adicionar uma nova credencial de conta para faturamento detalhado](../admin/connect-google-cloud.html).

Observe também que o suporte ao faturamento detalhado por nível de serviço ( GCP ) não inclui, no momento, os dados de custo do cluster ( GKE ).

Onde encontrar essa nova funcionalidade

1. No menu de navegação principal d Cloudability, acesse o item de menu Otimizar e selecione Ajuste de tamanho.
2. Selecione a guia “ GCP ” na página “Rightsizing”. As funcionalidades adicionais incluídas nesta versão estarão disponíveis aqui.

## Melhorias na interface do usuário para o inventário de recursos - 26 de agosto de 2024

Com esta versão, padronizamos a interface do usuário do Inventário de Recursos específica para os elementos, como parte da padronização geral da plataforma e da conformidade com as normas de acessibilidade.

Esses elementos são os seguintes.

1. O estilo de exibição das guias “ AWS ” e “ Azure ”, na parte superior, deve ser consistente com o de outros módulos em Cloudability.
2. Ajustar o estilo de exibição do menu suspenso de serviço e mês, bem como os textos de preenchimento, para que fiquem consistentes com os demais módulos do Cloudability.
3. Tamanho e espessura da fonte.
4. Tamanho e estilo de exibição dos ícones de exportação e medidas no canto superior direito da  Estoque  grade.
5. Experiência no carregamento de dados.
6. Estilo de exibição dos ícones “Mostrar” / “Ocultar” das medidas (dimensões/métricas).

## Cloudability Aprimoramentos no Container Insights 2.0 – 16 de agosto de 2024

Filtro global para pares de chave/valor de rótulo

Introduzimos uma nova opção de filtro global no painel da interface do usuário do Container Insights, permitindo que você filtre seus dados de custo e uso com base em pares específicos de chave/valor de rótulo. Essa melhoria oferece uma visão mais detalhada das suas cargas de trabalho em contêineres, permitindo a filtragem de acordo com rótulos como “app”, “env” ou quaisquer outros rótulos personalizados que você utilize em seus ambientes.

Principais recursos

- Filtro de chaves de etiqueta: Selecione uma das chaves de etiqueta disponíveis para restringir a exibição dos dados de custo a cargas de trabalho ou ambientes específicos.
- Filtro por valor de rótulo: refine ainda mais seu filtro especificando valores de rótulo, o que proporciona informações precisas sobre a alocação de custos.

Para usar esse recurso, é necessário fornecer pelo menos um valor de rótulo para a filtragem. Você também pode selecionar vários valores, conforme suas necessidades. Nosso objetivo é capacitá-lo a aproveitar as etiquetas em seus ambientes para criar painéis intuitivos, permitindo uma análise mais aprofundada dos custos dos seus contêineres.

![Filtragem CCA](../../../../03-media/cloudability-premium/images/container_1.jpg)

Widgets de tabela personalizáveis

Com base em nossos recursos já existentes para widgets personalizados de KPIs e gráficos, lançamos agora widgets personalizados de tabelas no painel de alocação de custos de contêineres, ampliando sua capacidade de adaptar a visibilidade dos custos às suas necessidades específicas.

Esse recurso permite que você modifique e configure os widgets de tabela para apresentar os dados que melhor atendam aos seus casos de uso.

Principais recursos:

- Seleção de tabela: exiba dados de custo e uso por cluster, rótulo, nó ou namespace, oferecendo flexibilidade na forma de visualizar e gerenciar seus recursos do Kubernetes.
- Condições de filtro: Personalize sua tabela aplicando filtros com base em várias métricas, como Cluster, Espaço de Nomes, Carga de Trabalho, Contêiner, Nó ou rótulos específicos, como app, env, project e outros. Isso ajuda você a se concentrar nos dados mais relevantes para a sua análise.
- Funcionalidade de edição de widgets: edite facilmente os widgets de tabela existentes para ajustar os dados exibidos ou os critérios de filtragem, garantindo que seu painel reflita as informações mais atualizadas e relevantes.
- Opções de exportação: Após personalizar seu widget, você pode exportar os dados para análises adicionais ou elaboração de relatórios.

![Cluster CCA](../../../../03-media/cloudability-premium/images/container_2.jpg)

## Planejamento de carga de trabalho – Suporte a GPU para máquinas virtuais – 16 de julho de 2024

Hoje, lançamos o suporte à configuração de GPU para máquinas virtuais no Planejamento de Carga de Trabalho. Com essa melhoria, os usuários podem especificar com facilidade o número de GPUs necessárias para suas cargas de trabalho e recebem estimativas de custo e recomendações de recursos de GPU no AWS, Azure, GCP e OCI.

Antes desta versão, o Workload Planning oferecia suporte apenas a algumas instâncias de GPU de diversos fornecedores e não proporcionava visibilidade sobre os requisitos específicos da GPU. Agora, os usuários não só podem comparar custos entre diferentes fornecedores, mas também visualizar detalhes de configuração, como o número de GPU s, a memória da GPU e o modelo da GPU (quando fornecidos pelos provedores de serviços em nuvem), o que os ajuda a encontrar o recurso de GPU com a melhor relação custo-benefício para suas cargas de trabalho.

![Suporte a GPU no WP](../../../../03-media/cloudability-premium/images/workload-planning-gpu-1.jpg)

![Recomendação do WP sobre o VM](../../../../03-media/cloudability-premium/images/workload-planning-gpu-2.jpg)

## Suporte para o relatório de custos e uso (CUR) do AWS 2.0 - 16 de julho de 2024

Hoje lançamos o suporte para a exportação padrão de dados do Relatório de Custos e Uso (CUR) do AWS 2.0/ no Cloudability. A partir de hoje, os usuários do Cloudability podem utilizar o AWS CUR 2.0 para importar seus dados de custo e uso do AWS.

Isso amplia o formato de dados compatível com os relatórios de custo e uso do AWS, que agora contam com algumas opções:

- AWS CUR antigo
- AWS Exportação de dados padrão / CUR 2.0

Antes desta versão, o Cloudability oferecia suporte apenas à exportação AWS CUR, que agora foi renomeada como exportação “Legacy CUR” pelo AWS.

Os clientes atuais que utilizam o CUR legado d AWS podem continuar utilizando o CUR legado sem qualquer impacto na ingestão ou na disponibilidade dos dados no Cloudability.

Como ativá-lo

Os clientes precisariam configurar a exportação de dados padrão do CUR 2.0/ no Console AWS.

O cliente deve configurar os itens a seguir no Console d AWS :

- Exportação padrão de dados

- CUR 2.0

  - Incluir IDs de recursos s
  - Granularidade temporal : por hora
  - Seleção de colunas - Todas (Todas as colunas serão selecionadas por padrão)
  - Tipo de compactação e formato de arquivo: gzip - text/csv
  - Controle de versões de arquivos como Substituir o arquivo de exportação de dados existente

Observação: o formato Parquet não é compatível com o CUR 2.0.

Depois de definir as configurações acima, siga as etapas abaixo em Cloudability

1. Acesse Configurações > Credenciais de fornecedor > AWS.
2. Selecione e edite a conta do Pagador Principal.
3. Adicione o nome do bucket “ S3 ”, o prefixo do relatório de custos e uso e o nome do relatório de custos e uso em Cloudability.
4. Salve e baixe o modelo do CFT.
5. Execute o modelo CFT.
6. Verificar credenciais.

![Criar captura de tela da exportação](../../../../03-media/cloudability-premium/images/cur-1.jpg)

![Captura de tela da exportação de dados](../../../../03-media/cloudability-premium/images/cur-3.jpg)

## GCP Suporte a tipos personalizados de máquinas virtuais (sistema operacional Windows) para o Planejamento de Cargas de Trabalho — 11 de julho de 2024

Hoje, temos o prazer de anunciar a introdução de estimativas de custo para máquinas virtuais personalizadas do GCP com o sistema operacional “Windows” no Workload Planning, com suporte aos tipos de máquina N4, N2, N2D, E2 e N1.

Esta é uma extensão da versão [de suporte a tipos de máquinas virtuais personalizadas GCP](#gcp_custom_virtual_machine_type_support_for_workload_planning_%E2%80%93_june_14,_2024_ "(Abre em uma nova guia ou janela)"), anunciada em 14 de junho de 2024.

## Permissões de apenas visualização para o módulo “Orçamentos” no Cloudability – 11 de julho de 2024

Hoje, temos o prazer de apresentar uma nova permissão de usuário no Front Door chamada BudgetsFeatureViewOnlyAccess, que permite que os usuários (aos quais essa permissão foi atribuída) visualizem e se inscrevam em orçamentos criados em sua organização.

Essa permissão não permite que os usuários criem novos orçamentos nem modifiquem ( Editar / Excluir ) os orçamentos existentes.

## Cloudability Container Insights 2.0 - 11 de julho de 2024

Hoje, temos o prazer de anunciar uma série de melhorias importantes no Cloudability Container Insights. O Container Insights 2.0 apresenta várias melhorias destinadas a fornecer informações abrangentes sobre cargas de trabalho em contêineres nos clusters do Kubernetes e do OpenShift. Esta versão apresenta um layout atualizado e novos recursos, como o índice de eficiência e a funcionalidade de detalhamento ampliada.

A nova interface do usuário é a página inicial padrão do recurso Container Insights. No entanto, você pode alternar facilmente entre as duas experiências clicando no botão indicado nas capturas de tela abaixo.

![Captura de tela do CCA](../../../../03-media/cloudability-premium/images/container_1.jpg)

![Mais CCA](../../../../03-media/cloudability-premium/images/container_2.jpg)

Nota:

Não vamos descontinuar o Container Insights 1.0 imediatamente. Você terá a opção de alternar entre as duas versões por um determinado período, para que possa se familiarizar com a nova interface. Forneceremos informações proativas sobre a futura data de descontinuação do Container Insights 1.0.

Recursos introduzidos

1. Painéis personalizáveis

   Adicionamos painéis personalizáveis, que permitirão que você crie visualizações e monitore os indicadores-chave de desempenho (KPIs) que são importantes para você.

   Recursos incluídos:

   - Painel padrão: Inclui widgets pré-configurados para uma visão rápida do custo total do cluster, do custo de inatividade e de outras métricas essenciais. Cada usuário tem seu próprio painel padrão.
   - Índice de Eficiência: uma nova métrica para avaliar a eficiência na alocação de recursos.
   - Visualização aprimorada: inclui KPIs, linhas de tendência, os X principais widgets, gráficos de séries temporais e widgets de tabela para uma visão abrangente da sua pegada de contêineres.
   - Recursos de personalização:

     Suporte ao filtro de fornecedores de nuvem para filtragem no nível do painel

     Funcionalidade de seleção múltipla para seleção de clustersEsta versão oferece suporte à criação de painéis personalizados, além de vários tipos de widgets personalizados. Você também pode excluir e adicionar widgets personalizados no painel padrão e configurá-los como seus painéis personalizados.
2. Visualização em mapa de árvore

   A visualização em mapa de árvore oferece uma visualização hierárquica dos clusters, permitindo uma análise mais aprofundada até o nível do contêiner:

   - Visualização hierárquica: permite aprofundar a análise, passando de clusters para namespaces, cargas de trabalho e contêineres.
   - Visualização da pontuação de eficiência: integra as pontuações de eficiência na visualização Treemap para avaliações rápidas.

   Tanto os painéis quanto a visualização em mapa de árvore oferecem suporte a filtros globais para data, agrupamentos e base de custo.   
    Os widgets são organizados com os KPIs na parte superior e as tabelas na parte inferior, para garantir a melhor visibilidade possível.

   Recurso detalhado de exploração de dados

   Nossa funcionalidade aprimorada de detalhamento permite uma navegação fluida:

   - No painel, acesse o widget de tabela e selecione um cluster para visualizar seus namespaces na visualização em mapa de árvore.
   - Selecione um namespace em um Treemap para explorar as cargas de trabalho que o compõem.
   - Ao clicar em uma carga de trabalho, são exibidos os contêineres que a compõem.

     Em cada nível de granularidade, é possível compreender os diferentes componentes de custo e a pontuação de eficiência.

     Informações adicionais

     Para obter detalhes detalhados sobre os contêineres dentro de uma carga de trabalho:

     - Clique em um contêiner para visualizar os nós nos quais ele está operando.
     - As atualizações no painel de detalhes fornecem informações relevantes para cada agrupamento de contêineres, garantindo que você tenha acesso aos detalhes mais lógicos.Nova coluna de custos: Custos diversos

     Como parte desta atualização, estamos lançando uma nova coluna na página Container Insights chamada “Custos Diversos”, disponível no widget Tabela. Esta coluna refletirá os custos específicos do cluster e, inicialmente, terá valor nulo para todos os provedores de serviços em nuvem (CSPs). Vamos disponibilizar isso primeiro para a GCP, com planos de ampliar o suporte a outros CSPs em um futuro próximo. Esses custos abrangem despesas adicionais associadas a aplicativos em contêineres que vão além de nós, volumes e transferência de dados. Eles incluem diversos serviços e recursos necessários para as operações do cluster, oferecendo uma visão abrangente de todos os custos relacionados à execução de aplicativos em contêineres.
3. Índice de eficiência de custos

   O Índice de Eficiência de Custos é um KPI que mede a relação custo-benefício geral da alocação de recursos em um ambiente de contêineres. Ele compara o custo utilizado com o que é considerado a parcela justa ou o custo total. Para compreender esse índice, é preciso analisar três tipos principais de custos: custo de participação justa, custo de utilização e custo de ociosidade.

   Custo da parcela justa / Custo total

   O custo de participação justa representa a proporção do custo total do nó atribuída a um contêiner com base na porcentagem de cada recurso (CPU, memória, GPU) que lhe foi alocada. Esse valor é calculado multiplicando-se o custo do nó para cada recurso pela porcentagem de participação justa desse recurso alocada ao contêiner. O custo total de repartição equitativa para um contêiner é a soma desses valores para todos os recursos.

   Custo de utilização

   O custo de utilização reflete o custo real dos recursos utilizados por um contêiner. É calculado multiplicando-se o custo do nó de cada recurso pela porcentagem de utilização desse recurso no nó. Assim como o custo de participação equitativa, o custo total de utilização de um contêiner é a soma dos custos de utilização de todos os recursos.

   Custo de inatividade

   O custo de inatividade é calculado subtraindo-se o custo de utilização do custo de participação justa. Representa o custo dos recursos que são alocados, mas não utilizados, o que indica ineficiência.

   Cálculo do Índice de Eficiência de Custos

   O Índice de Eficiência de Custos é calculado comparando-se o custo utilizado com o custo de participação justa, refletindo a eficiência no uso de recursos em todos os recursos dentro de um contêiner, namespace, carga de trabalho ou cluster. Essa pontuação ajuda a identificar ineficiências e áreas com potencial para otimização, como o redimensionamento de clusters ou nós, ou a melhoria das restrições de afinidade de pods para cargas de trabalho.

   Um Índice de Eficiência de Custos mais baixo indica maior ineficiência, sugerindo oportunidades mais significativas de redução de custos e otimização nesse ambiente.

Nota:

Entre em contato com o suporte caso tenha dúvidas sobre esse recurso ou queira enviar sugestões.

## A Alocação de Custos de Contêineres agora é compatível com a versão Kubernetes 1.30 - 8 de julho de 2024

Hoje, temos o prazer de anunciar que a Alocação de Custos de Contêineres agora é oficialmente compatível com o Kubernetes, versão 1.30, em todos os provedores.

Esse recurso permite que os clientes obtenham informações detalhadas sobre o uso de recursos de contêineres e os custos associados para clusters em execução no Kubernetes 1.30.

![CCA x Kubernetes](../../../../03-media/cloudability-premium/images/container-kubernetes1.3.jpg)

## Ampliação dos mapeamentos de tags e rótulos - 4 de julho de 2024

Aumentamos em 20 o número de mapeamentos de tags e rótulos disponíveis no Cloudability.

Isso significa que os clientes agora podem ter até 50 dimensões de relatório na plataforma específicas para tags ou rótulos mapeados. Isso será especialmente útil para clientes que utilizam uma infraestrutura multicloud e possuem muitas chaves de tag ou rótulo em seu ambiente. Cloudability Os administradores podem adicionar esses mapeamentos adicionais no recurso “Mapeamento de tags e rótulos”.

## Aprimoramento dos recursos marcáveis - 4 de julho de 2024

Hoje, lançamos uma melhoria significativa para os recursos marcáveis no Cloudability. Historicamente, o Tag Explorer definia de forma ampla “despesas marcáveis” como qualquer item de custo que possuísse um ID de recurso. Isso fez com que algumas rubricas de custo fossem classificadas como “marcáveis”, embora o uso subjacente não fosse marcável. Com esta versão, o Tag Explorer agora reconhece automaticamente quais serviços específicos do AWS e do Azure oferecem suporte à marcação, o que permite uma categorização precisa nas guias “Despesas marcáveis” e “Despesas não marcáveis”.

Caso deseje que isso seja aplicado a meses anteriores para auxiliar na análise histórica de tags, solicite um reprocessamento à sua equipe de sucesso do cliente.

## Planejamento de carga de trabalho – Suporte ao OCI Burstable VM – 1º de julho de 2024

Com esta versão, o Workload Planning agora oferece recomendações para máquinas virtuais com capacidade de pico (burstable) da OCI, permitindo que os usuários aproveitem os recursos de pico, que oferecem uma solução econômica para cargas de trabalho com padrões variáveis de uso da CPU.

Novidades desta versão

Anteriormente, o Planejamento de Carga de Trabalho fornecia recomendações para máquinas virtuais, sem a opção de selecionar instâncias com capacidade de pico, que estava disponível no Estimador de Custos da OCI. Com esta versão, os usuários agora podem escolher uma utilização de CPU de referência de 12.5 % ou 50% para instâncias com capacidade de pico, o que representa uma fração de cada núcleo da CPU. A linha de base indica o número mínimo de CPUs que podem ser utilizadas continuamente.

Para cada linha de base, o Planejamento de Carga de Trabalho fornece a estimativa de custo associada: optar por uma linha de base de 12.5 % oferece até 87.5 % de economia, enquanto uma linha de base de 50% proporciona até 50% de economia.

Nota:

Existem quatro tipos de máquinas virtuais OCI que suportam configurações com capacidade de pico: VM.Standard3.Flex, VM.Standard.E3.Flex, VM.Standard.E4.Flex e VM.Standard.E5.Flex.

Atualização importante

Recentemente, lançamos o suporte às datas de lançamento de alguns serviços no Resource Inventory (instantâneos do EBS, instâncias do RDS, buckets do S3 e instantâneos do Redshift ). No entanto, com a data de lançamento de um snapshot do EBS, detectamos um problema de desempenho no pipeline de custos do Cloudability; por esse motivo, decidimos adiar as datas de lançamento dos snapshots do EBS no Resource Inventory. Vamos relançar esse recurso assim que tivermos uma solução alternativa estável disponível. Observe que as datas de lançamento dos serviços que não sejam instantâneos do EBS continuarão disponíveis para uso.

## Suporte ao inventário de recursos para visualizações criadas com o Business Dimensions - 26 de junho de 2024

Hoje, lançamos o suporte ao Inventário de Recursos para visualizações criadas com dimensões de negócios.

Anteriormente, o Inventário de Recursos não conseguia resolver visualizações criadas com o uso de dimensões de negócios e, sempre que o usuário selecionava uma visualização criada com o uso de dimensões de negócios, aparecia uma página intitulada “Visualização restrita ”. Com esta versão, o Resource Inventory passará a resolver visualizações criadas com dimensões de negócios e poderá, efetivamente, suportar qualquer visualização do tipo “ Cloudability ” criada pelo cliente.

Mais informações sobre este lançamento

Dessa forma, também removeríamos o acesso privilegiado existente ao Inventário de Recursos por meio da permissão “Front Door” denominada “ AWSResourceInventoryFullAccess ” e ativaríamos esse recurso para todos os usuários da organização do cliente, pois o usuário administrador agora pode definir limites de dados para os dados do inventário de recursos por meio de visualizações.

Além disso, removemos a permissão privilegiada no Front Door que está vinculada ao recurso “Inventário de Recursos” ( AWSResourceInventoryFullAccess ). Isso tornaria o recurso disponível para todos os usuários de uma organização, independentemente de quaisquer direitos de permissão, de forma semelhante a módulos como Relatórios, True Cost Explorer etc.

Dessa forma, também removeríamos o acesso privilegiado existente ao Inventário de Recursos por meio da permissão “Front Door” denominada “ AWSResourceInventoryFullAccess ” e ativaríamos esse recurso para todos os usuários da organização do cliente, pois o usuário administrador agora pode definir limites de dados para os dados do inventário de recursos por meio de visualizações.

Já removemos a permissão privilegiada no Front Door que está vinculada ao recurso “Inventário de Recursos” ( AWSResourceInventoryFullAccess ). Isso tornaria o recurso disponível para todos os usuários de uma organização, independentemente de quaisquer direitos de permissão, de forma semelhante a módulos como Relatórios, True Cost Explorer etc.

## Experiência do usuário aprimorada para credenciais de fornecedores - 24 de junho de 2024

Hoje, lançamos atualizações nas Credenciais de Fornecedores que proporcionam uma melhor experiência ao usuário para os usuários do Cloudability. À medida que o Cloudability amplia a integração de fontes de dados, introduzimos uma interface de usuário mais escalável para novas fontes de dados, com melhor desempenho, compatível com o A11y e uma melhor experiência do usuário.

Novidades desta versão

Com esta versão, você pode:

- Identifique rapidamente as fontes de dados disponíveis no Cloudability.
- Tenha uma interface de usuário que seja escalável, levando em conta as integrações atuais e as expansões futuras.
- Tenha acesso a uma interface de usuário do A11y em conformidade com as normas de acessibilidade.
- Desfrute de um melhor desempenho nos tempos de carregamento da interface do usuário das credenciais de fornecedores.
- Utilize os novos recursos de filtragem e pesquisa nas colunas individuais das credenciais de fornecedores.
- Expandir e recolher todas as contas no nível da conta principal do pagador/faturamento.
- Classifique os detalhes com base em colunas individuais.
- A legibilidade melhorou, pois aprimoramos as taxas de contraste.

Passos para visualizar a nova experiência do usuário

1. No site Cloudability, acesse Configurações > Credenciais do fornecedor.
2. Para adicionar uma nova fonte de dados, clique em Adicionar fonte de dados. Isso mostrará todas as fontes de dados disponíveis para um cliente. ![Adicionar captura de tela da fonte de dados](../../../../03-media/cloudability-premium/images/vc1.jpg)
3. Selecione uma fonte de dados para a qual você deseja inserir as credenciais.![adicionar uma captura de tela d AWS](../../../../03-media/cloudability-premium/images/vc2.jpg)
4. Agora, a janela pop-up “Adicionar conta durante a autenticação” é exibida no lado direito.
5. Após a autenticação, você poderá visualizar uma aba correspondente à fonte de dados.![AWS captura de tela adicionada](../../../../03-media/cloudability-premium/images/vc3.jpg)

   Nota:

   As etapas de credenciamento para cada fonte de dados permanecem as mesmas.
6. Nessa aba, você poderá pesquisar e filtrar por colunas individuais. ![Captura de tela do filtro “ AWS ”](../../../../03-media/cloudability-premium/images/vc4.jpg)
7. Clique em “…” para realizar várias ações, como antes. Adicionamos um texto junto com os ícones:
   - Visualizar detalhes
   - Editar conta
   - Verificar novamente a conta
   - Archive
   - Excluir
8. As contas principais (conta do pagador principal e conta de cobrança, entre outras) serão ocultadas por padrão. Clique em cada conta para visualizar o próximo nível de subcontas (contas vinculadas, assinaturas ou projetos, entre outros) ou use os ícones “Expandir tudo” e “Recolher tudo”, recém-introduzidos. ![Conta 1 AWS](../../../../03-media/cloudability-premium/images/vc5.jpg)![Detalhes da conta da AWS](../../../../03-media/cloudability-premium/images/vc6.jpg)
9. A interface de usuário das credenciais de fornecedores agora oferece suporte ao carregamento diferido, proporcionando melhor desempenho nos tempos de carregamento da interface.

## Suporte a tipos personalizados de máquinas virtuais para planejamento de cargas de trabalho – 14 de junho de 2024

Com esta versão, os usuários do Workload Planning agora podem obter estimativas de custo para máquinas virtuais personalizadas do GCP, com suporte aos tipos de máquina N4, N2, N2D, E2 e N1.

Novidades desta versão

Anteriormente, o Planejamento de Carga de Trabalho oferecia suporte apenas a tipos de máquinas predefinidos para o serviço “ GCP ”, que possuem um número pré-definido de “ vCPUs ” e uma quantidade fixa de memória, e são cobrados a um preço fixo. Nesta versão, o Workload Planning oferece recomendações para VMs padrão e personalizadas, com base nas informações fornecidas sobre a taxa de utilização da memória ( vCPU ) e na memória. Isso permite que você escolha a capacidade de processamento e a quantidade de memória sem precisar trocar o tipo de máquina. Se não houver uma combinação de “ vCPU ” e memória, o Planejamento de Carga de Trabalho priorizará a necessidade de “ vCPU ” e buscará a quantidade de memória mais próxima.

Nota:

Esta versão oferece suporte apenas ao sistema operacional “Free”, listado como “ Linux ” no Planejamento de Carga de Trabalho, enquanto as VMs personalizadas com o sistema operacional “Windows” terão suporte em uma versão futura.

## Suporte do RIS à dimensão “Data de lançamento” para mais serviços – 14 de junho de 2024

Com esta versão, o Resource Inventory passará a oferecer suporte à dimensão “data de lançamento” para os seguintes serviços do AWS :

1. EBS Instantâneos
2. RDS Instâncias
3. Redshift Instantâneos
4. S3 Baldes
   1. s3:ListAllMyBuckets
   2. redshift:DescribeClusterSnapshots

Mais informações sobre este lançamento

Os usuários atuais do Cloudability precisam adicionar essas duas novas permissões para obter as dimensões de data de lançamento para S3 e Redshift :

Recomenda-se atribuir essas permissões a uma função do IAM d Cloudability, por meio do console do AWS, navegando até IAM > Gerenciamento de acesso > Funções > Função Cloudability (ou sua função personalizada criada para Cloudability ) e atribuir as duas permissões acima a Cloudability MonitorResourcesPolicy na guia Permissões.

Nota:

Para novos usuários, essas permissões já estariam incluídas no script de credenciamento AWS.

## Permissões de visualização detalhada para os módulos “Organize” e “Budgets” no Cloudability - 14 de junho de 2024

Com esta versão, introduzimos três novas permissões no módulo “Organizar” do Cloudability, que permitem aos usuários (com permissões atribuídas) acessar e visualizar os dados nessas respectivas telas, mas não editá-los.

Novidades desta versão

As três novas permissões são:

| Nome da permissão | Descrição |
| --- | --- |
| AccountGroupManagementFeatureViewOnlyAccess | Permitir que os usuários, atribuídos a uma função com essa permissão, visualizem contas e grupos de contas no item de menu “Grupos de contas” do recurso Cloudability, mas não possam editá-los |
| BusinessMappingsFeatureViewOnlyAccess | Permitir que os usuários, atribuídos a uma função com essa permissão, visualizem os mapeamentos de negócios e suas definições no item de menu “Mapeamentos de negócios” ( Cloudability ), mas não possam editá-los |
| TagsAndLabelsFeatureViewOnlyAccess | Permitir que os usuários atribuídos a uma função com essa permissão visualizem todas as dimensões do Cloudability e suas chaves de tag mapeadas, bem como os rótulos do Kubernetes, no item de menu “Tags” do Cloudability, mas sem poder editá-los |

## Colunas de exportação exibidas na interface do usuário do Inventário de Recursos – 13 de junho de 2024

Nesta versão, você terá uma opção adicional de exportação (no canto superior direito da tabela de estoque), além da exportação dos dados completos do estoque, que permite exportar apenas os dados das colunas exibidas na interface do usuário. Anteriormente, não era possível exportar (para CSV ) apenas as colunas selecionadas na interface do usuário do inventário de recursos.

## Preferências de ajuste de tamanho – Suporte à exclusão de classes do Storage/S3 – 30 de maio de 2024

Hoje, o Cloudability lançou novas configurações globais na seção “Preferências de Rightsizing” que permitem excluir recomendações de “ storage/S3 ” de objetos para classes de armazenamento específicas, com base nos valores inseridos.

Novidades desta versão

Antes desta versão, o Cloudability oferecia filtragem por classe apenas para recomendações de otimização de espaço de armazenamento de objetos no nível da página e apenas para as principais recomendações apresentadas, sem a possibilidade de filtrar globalmente ou com base em recomendações individuais.

A partir de hoje, você pode filtrar de forma rápida e fácil as recomendações de ajuste de capacidade para o armazenamento de objetos ( storage/S3 ) em nível global, a fim de ocultar as recomendações relacionadas a classes de armazenamento de objetos indesejadas.

Para ativar esse recurso, siga as etapas abaixo:

1. A partir do menu de navegação principal do Cloudability, acesse o item de menu “Configurações” e selecione “Preferências de redimensionamento ”.
2. Selecione a guia “Preferências de armazenamento de objetos” na página e marque a opção “Excluir recomendações nas quais a classe de armazenamento recomendada contenha os seguintes valores”.
3. Nessa opção, haverá campos de texto nos quais você poderá inserir valores adicionais; isso excluirá quaisquer recomendações de armazenamento de objetos nas quais a classe contenha esses valores.

   Nota:

   As alterações nessas configurações podem levar até 24 horas para entrar em vigor.

## Cloudability Melhorias na família de produtos – 28 de maio de 2024

Hoje, lançamos melhorias na família de planos de uso “ Cloudability ”. Essas melhorias se aplicam aos dados de custos do Cloudability provenientes de três provedores de serviços em nuvem (CSPs): Amazon Web Services ( AWS ), Microsoft Azure e Google Cloud Platform ( GCP ). Esta atualização melhora a qualidade do mapeamento e oferece uma cobertura mais ampla para que os itens de custo sejam categorizados na família de uso apropriada.

Como esse recurso pode ajudá-lo

Essa mudança levará a uma redução no número de itens não mapeados (mapeados como “Outros”), corrigirá imprecisões identificadas anteriormente e aprimorará os mapeamentos existentes. Além disso, agora há um mapeamento de mais serviços em todos os CSPs. As alterações serão refletidas nas rubricas de custo a partir de 1º de maio de 2024 e, automaticamente, em quaisquer meses reprocessados.

A seguir, apresentamos alguns exemplos do que poderia mudar como resultado disso:

- Você poderá observar que a solicitação da API da família “Usage” mudará para “IO” em alguns serviços, como o AWS Sagemaker. A alteração afeta principalmente as operações de leitura e gravação.
- Especificamente no caso do ` AWS `, você poderá observar mudanças de “IO” para “Transferência de dados”. Isso serve para alinhar com as unidades subjacentes ( BytesTransferred ) pelas quais é cobrado.

## Melhorias na usabilidade da página “Tags e rótulos” – 23 de maio de 2024

Com esta versão, lançamos duas melhorias:

1. Anteriormente, quando você fazia uma pesquisa e adicionava uma chave de tag específica a uma dimensão do Cloudability, o texto da pesquisa e os resultados costumavam desaparecer, dificultando a seleção múltipla de várias chaves de tag a partir do mesmo texto de pesquisa. Agora, você pode manter o texto da pesquisa e os resultados da pesquisa mesmo depois de adicionar uma chave de tag.
2. Antes, os nomes das tags com sequências longas eram cortados, o que dificultava a leitura do nome completo. Agora, ajustamos a altura da linha para exibir o nome completo da chave da tag e também adicionamos uma dica de ferramenta para facilitar a leitura.

## Inclusão de novos KPIs para “Recursos Totais” e “Instantâneos Totais” no “ EC2 ” no Inventário de Recursos – 17 de maio de 2024

Com esta versão, o Resource Inventory passará a oferecer suporte a dois novos KPIs para o EC2, o que proporcionará a você uma visibilidade mais detalhada dos dados. São eles:

1. Recursos totais (número total de recursos do EC2, incluindo tanto instâncias do EC2 quanto instantâneos)
2. Total de instantâneos (número total de instantâneos do EC2 ).

## Suporte a preços personalizados para CUDs de gastos com computação do GCP – 17 de maio de 2024

Hoje, lançamos novos preços personalizados para os Compute Flex-CUDs d GCP. Como parte desse novo recurso, você poderá alternar entre preços de varejo (de tabela) e preços personalizados (EDP) ao selecionar a base de custo nas páginas de portfólio de reservas e recomendações do site Cloudability.

Novidades desta versão

O botão de alternância entre preços personalizados e preços de varejo já está disponível, permitindo alternar facilmente entre as duas opções sempre que necessário.

Para ativar esse recurso, siga as etapas abaixo:

1. Acesse Cloudability > Otimizar > Planejador de instâncias reservadas > GCP > Tipo de compromisso = Compute Engine Flexible-CUDs
2. Acesse Cloudability > Insights > Portfólio de reservas > GCP > Tipo de compromisso = Compute Engine Flexible-CUDs

   Ou,

   Alterne o seletor de Base de Custo entre Varejo e Personalizado.

Mais informações sobre este lançamento:

Esse novo recurso oferece maior flexibilidade para calcular e estimar os custos com a nuvem, utilizando conceitos de “ Cloudability ”, com a vantagem adicional de permitir que você decida antecipadamente qual modelo de precificação é mais adequado para você.

## Normalização de nomes inconsistentes de regiões do Azure - 17 de maio de 2024

Hoje, lançamos uma melhoria nos nomes das regiões do Azure para garantir a consistência nos relatórios. Essa melhoria padroniza os nomes das regiões d Azure.

Como esse recurso pode ajudá-lo

Anteriormente, os clientes enfrentavam inconsistências em que as mesmas regiões do Azure tinham nomes diferentes (por exemplo, "EastUS" e “US East” para a mesma região). Esta versão resolverá o problema e evitará a necessidade de criação de tabelas de mapeamento adicionais por parte do cliente. Isso normalizará os nomes das regiões d Azure, o que proporcionará aos clientes a granularidade necessária para a elaboração de relatórios.

Por exemplo: Após essa alteração, em vez de retornar “Hong Kong” ou “ "HongKong (East Asia)” como região, o relatório retornaria “ EastAsia::Eastasia ”.

## Adiar/Ignorar recomendações de ajuste de tamanho no Cloudability – 14 de maio de 2024

Hoje, lançamos um novo recurso de otimização de recursos que permite ocultar (adiar) as recomendações de otimização para recursos específicos por um período personalizável. A partir de hoje, você pode adiar recomendações específicas de redimensionamento para aumentar a eficiência durante a análise e a implementação dessas recomendações.

Como esse recurso pode ajudá-lo

Esse recurso aumenta a eficiência ao reduzir o número de recomendações desejadas apresentadas, bem como ao eliminar qualquer confusão associada à exibição contínua de recomendações que já foram consideradas não passíveis de ação no momento.

Etapas para ativar o adiamento das recomendações de ajuste de capacidade

1. Acesse o menu de navegação principal do Cloudability, vá até o item de menu “Otimizar” e selecione “Rightsizing ”.
2. Selecione a página do fornecedor e do serviço de Rightsizing desejados.

## OCI - Tipo, categoria e família de instância de suporte – 11 de maio de 2024

Hoje lançamos o suporte a três dimensões para as instâncias do OCI Compute: “tipo de instância”, “categoria de instância” e “família de instâncias”. Essas dimensões oferecem a você maior detalhamento e flexibilidade na elaboração de relatórios sobre seus gastos com OCI e no acompanhamento dos custos entre os fornecedores.

Mais informações sobre este lançamento

Antes desta versão, era necessário utilizar a dimensão “descrição do item” para gerar relatórios sobre instâncias OCI. No entanto, essa abordagem apresentava desafios na geração de relatórios de forma integrada e na identificação fácil de picos de custo. Com esta versão, agora você pode aproveitar essas três novas dimensões para gerar relatórios sobre seus gastos com o OCI, além de compreender melhor e categorizar as instâncias de computação.

Nota:

Essa melhoria exigirá que você reprocesse os dados para garantir que as novas dimensões sejam aplicadas com precisão aos seus registros anteriores.

## Azure MCA - Suporte às APIs de gerenciamento de custos do Azure – 9 de maio de 2024

Esta versão traz o suporte às APIs de gerenciamento de custos do Azure com credenciais do Cloudability para clientes do Azure MCA, além do uso de exportações do Azure. Agora você pode utilizar essas APIs no Cloudability para obter tanto o custo real quanto o custo amortizado, por meio das APIs de gerenciamento de custos.

Etapas para credenciar uma conta MCA do Azure usando as APIs de gerenciamento de custos d Azure

1. Acesse a página de credenciamento do site Cloudability e selecione “ Azure ”.
2. Clique em Adicionar Credencial.
3. Selecione “Contrato de Cliente da Microsoft ” (MCA) como tipo de cont Azure.
4. Insira o ID da conta de faturamento Azure, o ID do locatário Azure e o ID da assinatura.
5. Insira NA nos demais campos.
6. Clique em Gerar script de configuração.
7. Baixe e instale o script “ PowerShell ” em Azure.
8. Clique em “Verificar credencial” na interface do usuário do Cloudability.

   O sinal de visto verde indica que a adição da conta por meio das APIs de gerenciamento de custos d Azure foi bem-sucedida.

   ![Azure Gestão de Custos](../../../../03-media/cloudability-premium/images/ms_azure_edited.jpg)

Para os clientes atuais do MCA que utilizam exportações para o Azure com o Azure Storage, não é necessário fazer nada. No caso de exportações do Azure que utilizam o Azure Storage, continuaremos a obter os arquivos do Gerenciamento de Custos do Azure a partir do local configurado.

## Planejamento da Carga de Trabalho GA – 7 de maio de 2024

Hoje, temos o prazer de anunciar a disponibilidade geral do Planejamento de Cargas de Trabalho do Cloudability, o que marca um marco significativo após seu lançamento inicial em 2023. Esse recurso permite que as equipes de FinOps e e Engenharia estimem os custos de novas cargas de trabalho, com base nos requisitos de recursos e em preços personalizados. Ao planejar uma nova carga de trabalho, isso ajuda as equipes a comparar facilmente os preços e as opções de configuração dos recursos em nuvem no AWS, Azure, GCP e OCI, agilizando os processos de tomada de decisão.

Como esse recurso pode ajudá-lo

Com esta versão GA, os administradores do Cloudability passam a ter maior controle sobre as recomendações do Planejamento de Carga de Trabalho, graças à introdução das novas Preferências de Planejamento de Carga de Trabalho. Aqui, os administradores podem definir opções padrão para o tipo de contrato de carga de trabalho (por exemplo: Sob Demanda, Spot), compromissos e inserir mais descontos ou acréscimos. Além disso, as permissões de planejamento de cargas de trabalho foram aprimoradas, permitindo que os administradores do Cloudability supervisionem as cargas de trabalho criadas pelos usuários em toda a organização, promovendo a transparência e facilitando o compartilhamento contínuo de informações entre as equipes.

Cloudability O Planejamento de Cargas de Trabalho representa um recurso inédito no setor, que permite aos usuários definir cargas de trabalho com boa relação custo-benefício, utilizando todos os recursos necessários e levando em consideração as opções de implantação em diversos provedores de nuvem. Isso promove maior eficiência e alinhamento entre as equipes financeiras e técnicas.

![Introdução ao WP](../../../../03-media/cloudability-premium/images/wp_1.jpg)

Preferências de planejamento da carga de trabalho

Esses novos controles, introduzidos como parte do GA, estão disponíveis para os administradores do Cloudability por padrão. Isso permite que as equipes d FinOps em definam e restrinjam centralmente as opções para o Planejamento de Cargas de Trabalho. Qualquer uma dessas configurações é opcional e não é obrigatória para utilizar o Planejamento de Carga de Trabalho.

1. Acesse Cloudability Configurações > Preferências de planejamento de carga de trabalho.
2. Desative a disponibilidade de um CSP específico utilizando a opção “Permitir provedor de serviços ”.
3. Defina as preferências de tipo de contrato de locação e as opções padrão de compromisso para seus usuários. Você também tem a opção de bloquear a seleção de compromissos para os usuários.
4. Incorpore qualquer desconto ou acréscimo adicional aos custos da sua carga de trabalho. Observe que esse valor é adicionado a qualquer preço personalizado, que já está incluído no Planejamento de Carga de Trabalho.
5. Clique em Salvar para aplicar as alterações imediatamente. As preferências atualizadas afetarão as cargas de trabalho existentes e as novas. ![Preferências do WP](../../../../03-media/cloudability-premium/images/wp_2a.jpg)

   Permissões para planejamento da carga de trabalho

   Cloudability Os administradores têm acesso ao Planejamento de Carga de Trabalho e às Preferências de Planejamento de Carga de Trabalho por meio da permissão WorkloadPlacementFullAccess. Eles podem criar e gerenciar suas cargas de trabalho, visualizar as cargas de trabalho criadas por todos os usuários da organização (sem direito de edição) e atualizar as preferências de planejamento de cargas de trabalho. Eles podem editar as cargas de trabalho de outras pessoas quando essas forem compartilhadas diretamente com eles com direitos de edição.

   Por padrão, os usuários sem privilégios de administrador podem criar e editar suas próprias cargas de trabalho por meio da permissão WorkloadPlanningFeatureCanAccess. Eles também podem visualizar e, eventualmente, editar as cargas de trabalho compartilhadas com eles, dependendo da permissão concedida pelo proprietário da carga de trabalho.

   Criamos uma permissão adicional: WorkloadPlanningPreferencesViewOnly. Ele pode ser adicionado a uma função personalizada para visualizar as Preferências de Planejamento de Carga de Trabalho, o que ajudará os usuários a compreender melhor a configuração do recurso.

   ![Permissões do WP](../../../../03-media/cloudability-premium/images/wp_3.jpg)

   Suporte para preços personalizados

   O Planejamento de Carga de Trabalho sempre exibe os custos incluindo quaisquer preços personalizados (por exemplo, para EDP) para o AWS, o Azure e o OCI. Caso as organizações não tenham um acordo de preços personalizado com um fornecedor específico, aplicamos, por padrão, os preços de “varejo”.

   No caso do “ GCP ”, é possível habilitar a exportação de dados de preços personalizados da conta de faturamento do “ GCP ” para obter preços personalizados no “Workload Planning”.

   Mais informações sobre este lançamento

   Visite [Obter recomendações para o planejamento de carga de trabalho](../product/get-recommendations-for-workload-planning.html) e [Preferências de planejamento de carga de trabalho](../product/workload-planning-preferences.html) para obter mais informações ou participe da discussão na [Comunidade Apptio](https://community.apptio.com/login?returnurl=https%3a%2f%2fcommunity.apptio.com%2fblogs%2fsoline-plichta%2f2024%2f05%2f08%2fcloudability-workload-planning-ga-faq "(Abre em uma nova guia ou janela)").

## Método de ajuste de uso mínimo para os Compute Flex-CUDs do GCP – 6 de maio de 2024

Hoje, lançamos um novo método de ajuste das recomendações de compromisso para os Compute Flex-CUDs do GCP, denominado “Uso Mínimo”. Com esta versão, você pode ajustar a recomendação de gasto com base no número mínimo de horas de uso. Isso inclui a possibilidade de excluir os 1% e 5% mais baixos das horas de uso.

Observação: Não são necessárias credenciais ou permissões adicionais.

## Suporte à exportação de dados de gerenciamento de custos do Azure para o Azure Storage com particionamento de arquivos – 6 de maio de 2024

A partir de hoje, o Cloudability passará a oferecer suporte à exportação de dados de gerenciamento de custos do Azure para o Azure Storage com particionamento habilitado para clientes do Azure. Isso se aplicaria a ambos os tipos de exportação:

- Detalhes de custo e uso (reais)
- Detalhes de custo e uso (amortizados)

  Como esse recurso pode ajudá-lo

  Recentemente, o Azure aprimorou a experiência de armazenamento no Azure para os clientes e tornou o particionamento na(s) exportação(ões) uma configuração padrão, o que divide o arquivo exportado em vários arquivos, com base no tamanho do conjunto de dados.

  Antes desta versão, o Cloudability não oferecia suporte a arquivos de exportação de gerenciamento de custos com partição, o que causava problemas na ingestão de dados para clientes do Azure em exportações recém-criadas. Isso não é mais um problema, pois o Cloudability passou a oferecer suporte a arquivos Azure com a partição ativada.

  Nota:

  Trata-se de uma alteração no back-end e não envolve nenhuma alteração ou atualização na interface do usuário do Cloudability. Azure A importação de dados para os clientes com exportações mais antigas continuará sem que eles precisem fazer nenhuma alteração.

  Nota:

  Os clientes que ativaram o particionamento de arquivos ao criar exportações de gerenciamento de custos devem criar uma nova exportação antes de adicionar credenciais em Cloudability.

## Recomendações de reestruturação para funções d AWS Lambda o em Cloudability – 19 de abril de 2024

A partir de hoje, os usuários podem obter recomendações de ajuste de capacidade para as funções d AWS Lambda, que oferecem oportunidades de redução de custos ao identificar recursos cuja capacidade pode ser ajustada para se adequar melhor às cargas de trabalho subjacentes.

Antes desta versão, as recomendações de ajuste de pessoal para funções d AWS Lambda não estavam disponíveis no Cloudability. A disponibilização dessas recomendações diretamente no site Cloudability oferece aos usuários uma fonte de recomendações mais abrangente e independente para otimizar ainda mais seus gastos com o AWS.

Como ativar as recomendações de ajuste de capacidade para o AWS Lambda

Para ativar esse recurso, siga as etapas abaixo:

1. Ative [o monitoramento aprimorado do Lambda Insights](https://docs.aws.amazon.com/lambda/latest/dg/monitoring-insights.html "(Abre em uma nova guia ou janela)") para permitir que o Cloudability recupera métricas de memória das suas funções Lambda.
2. Crie ou baixe o modelo de credencial atualizado do AWS em Cloudability e, em seguida, envie o novo modelo de credencial para o Console de Gerenciamento do AWS.
3. No menu de navegação principal do Cloudability, acesse o item de menu Otimizar e selecione Ajuste de recursos.
4. Selecione a guia “ AWS ” na página “Rightsizing ” e, na seção de serviços disponíveis do “ AWS ”, selecione a guia “Lambda ”. Quaisquer recomendações existentes sobre o ajuste de escala do Lambda serão exibidas aqui.

Nota:

Essas recomendações, bem como os dados subjacentes a elas, estarão agora disponíveis em todas as áreas do site Cloudability onde são exibidos dados de ajuste de tamanho para outros serviços do AWS.

## Categorização de dimensões e métricas na interface do usuário do inventário de recursos – 3 de abril de 2024

Adicionamos cabeçalhos nas Configurações da Tabela (menu deslizante à esquerda) na interface do Inventário de Recursos, que separarão as dimensões e as métricas em duas seções diferentes.

Nesta versão, as dimensões aparecem na parte superior, enquanto as métricas aparecem na parte inferior ao rolar a tela para baixo nas Configurações da tabela.

## Lançamento do “ Cloudability ” na região da Ásia-Pacífico – 2 de abril de 2024

Esta versão apresenta a disponibilização do Cloudability, nossa plataforma de gerenciamento de custos de nuvem, na região da Ásia-Pacífico (APAC).

Como esse recurso pode ajudá-lo

Esta versão atende às necessidades específicas de nossos clientes da região da Ásia-Pacífico (APAC), garantindo que seus dados permaneçam dentro dos limites dessa região. Ao localizar nossos serviços, nosso objetivo é capacitar as organizações a fortalecerem suas iniciativas de conformidade e se alinharem às diretrizes relativas aos dados de gestão de custos em nuvem.

Mais informações sobre o lançamento

O lançamento do serviço de hospedagem Cloudability na região da Ásia-Pacífico (APAC) reveste-se de grande importância para nossos clientes que atuam nessa região. A solução oferece uma gestão de custos em nuvem confiável e em conformidade, que prioriza a residência dos dados, reforça a privacidade dos dados e está alinhada às diretrizes de proteção de dados.

Nota:

Os clientes sediados na região da Ásia-Pacífico (APAC) que tenham interesse em migrar dos EUA para a região da Ásia-Pacífico (APAC) podem entrar em contato com seus respectivos gerentes de conta ou com a equipe de Sucesso do Cliente.

Nota:

Não é necessária nenhuma configuração ou instalação adicional para os clientes que estão se cadastrando diretamente no site Cloudability na região da Ásia-Pacífico (APAC).

## Suporte a descontos baseados em compromisso para os descontos de uso comprometido flexíveis do Compute Engine do GCP – 28 de março de 2024

Hoje lançamos o suporte a descontos baseados em compromissos para os Compromissos Baseados em Gastos do Compute Engine do GCP (CUDs flexíveis).

A partir de hoje, os usuários passam a ter acesso a duas novas páginas:

- Na página “Portfólio de Compromissos ”, os usuários podem obter informações sobre o desempenho, definir alertas de vencimento e gerenciar seu portfólio de CUDs Flexíveis.

- Na página “Recomendações de compromisso”, os usuários podem receber e ajustar recomendações ideais para avaliar futuras compras por compromisso.

Como esse recurso pode ajudá-lo

Com esta versão, reconfiguramos e introduzimos um novo conjunto de KPIs e metadados de compromisso nas páginas de portfólio e de recomendações. Essas informações vão ajudá-lo a gerenciar e compreender melhor o desempenho de seus compromissos atuais. Para os clientes que apresentam um nível de compromisso abaixo do esperado devido à incerteza na aplicação do risco financeiro às decisões de compromisso, nossas melhorias na página “Recomendações de Compromisso” lhes darão confiança para assumir compromissos mais ousados, a fim de aumentar a economia líquida.

Mais informações sobre o lançamento

Nas próximas versões, continuaremos a desenvolver funcionalidades adicionais para ajudá-lo a compreender as vantagens e desvantagens entre os diferentes prazos, tipos e estratégias de compromisso. Reorganizaremos a arquitetura da informação em toda a funcionalidade de Desconto Baseado em Compromisso e buscaremos oferecer suporte à maioria dos tipos de compromisso baseados em gastos do programa “ GCP ”.

Nota:

As páginas Portfólio de Reservas e Planejador de Instâncias Reservadas passarão a se chamar Portfólio de Compromissos e Recomendações de Compromissos e serão reorganizadas lado a lado na seção Otimizar em breve.

## Alocação de custos de contêineres para o Kubernetes Versão 1.29 – 26 de março de 2024

A alocação de custos de contêineres agora é oficialmente compatível com a versão 1.29 do Kubernetes em todos os provedores.

Esse recurso permite que os clientes obtenham informações detalhadas sobre o uso de recursos de contêineres e os custos associados para clusters em execução no Kubernetes, versão 1.29.

![Mais melhorias no CCA K8S](../../../../03-media/cloudability-premium/images/cca-kubernetes129.jpg)

## Suporte do OCI no planejamento de cargas de trabalho – Aprimoramentos – 26 de março de 2024

Hoje, lançamos duas melhorias no recurso “Suporte a OCI no Planejamento de Cargas de Trabalho”:

• Agora você pode selecionar o modelo de preços “Reserva de Capacidade” para suas máquinas virtuais OCI.

• Você pode obter informações sobre os valores da Unidade de Desempenho de Volume (VPU) para o seu “Volume em Bloco” do OCI.

Como esse recurso pode ajudá-lo

Antes desta versão, os usuários que desejavam modelar cargas de trabalho para a OCI no Workload Planning só podiam utilizar os planos de preços On-Demand ou Spot (preemptível). Com esta atualização, agora você pode selecionar “Reserva de Capacidade” como opção de tipo de contrato ao adicionar um recurso à sua carga de trabalho, da mesma forma que a opção disponível no [Estimador de Custos da](https://www.oracle.com/cloud/costestimator.html "(Abre em uma nova guia ou janela)") OCI. É importante observar que a “Reserva de Capacidade” é compatível apenas com máquinas virtuais e oferece um desconto adicional de 15%, que é perdido assim que a capacidade for utilizada. Para obter mais detalhes sobre a Reserva de Capacidade do OCI, consulte a [Documentação do OCI](https://docs.oracle.com/en-us/iaas/content/compute/tasks/reserve-capacity.htm "(Abre em uma nova guia ou janela)").

Vale lembrar que qualquer “preço personalizado” ou “desconto personalizado” para o OCI já está, por padrão, incluído no preço do recurso exibido no Planejamento de Carga de Trabalho.

Reserva de capacidade

Agora é possível selecionar “Reserva de Capacidade” como tipo de contrato preferencial para OCI nas informações gerais; a dica de ferramenta foi atualizada de acordo. Ao escolher esse tipo de contrato de locação, ele se tornará a opção padrão para as recomendações de máquinas virtuais.

![Captura de tela da reserva de capacidade do OCI](../../../../03-media/cloudability-premium/images/oci_1.jpg)

Na recomendação, você encontrará as opções de tipos de contrato “sob demanda”, “reserva de capacidade” e “spot” (preemptível), que permitem comparar as opções de preço antes de adicionar um recurso à sua carga de trabalho.

![Atualizações do OCI VM](../../../../03-media/cloudability-premium/images/oci2.jpg)

Valores da VPU

Você tem visibilidade dos valores da Unidade de Desempenho de Volume (VPU no armazenamento em bloco do OCI) na tela de recomendações “Armazenamento Conectado”. Essas informações não estão disponíveis para outros provedores de serviços em nuvem.

![Captura de tela do Attached Storage](../../../../03-media/cloudability-premium/images/oci3.jpg)

## Aprimoramentos nas métricas de utilização de contêineres no Cloudability – 4 de março de 2024

Fizemos melhorias nas nossas métricas de utilização na página de insights sobre contêineres do Cloudability.

Esta atualização alinha as métricas de memória exibidas com as utilizadas nos cálculos de alocação, a fim de melhorar a consistência, e corrige o uso do sistema de arquivos no EKS para garantir relatórios precisos. Para esclarecer, essas melhorias não afetarão o custo nem a metodologia de alocação de custos e foram projetadas para refletir com maior precisão as métricas de utilização na página de informações sobre contêineres.

## Aprimoramento da métrica “Custo (Lista)” no Cloudability – 23 de fevereiro de 2024

A funcionalidade da métrica “Custo (Lista)” foi aprimorada. Anteriormente, certos descontos em tarifas privadas e pacotes apareciam como créditos na métrica, o que resultava em valores incorretos. No entanto, a métrica “Custo (de tabela)” foi concebida para fornecer aos usuários o custo sob demanda de cada item de linha, sem incluir informações sobre descontos e créditos. Essa melhoria resolve o problema.

## Atualização das permissões do “ Azure ” na interface do usuário – 23 de fevereiro de 2024

Hoje lançamos algumas atualizações na lista de permissões do Azure, disponível em Cloudability.

• A partir de hoje, os usuários do Azure terão a permissão de função “Leitor de Inscrições” para contas EA do Azure e a permissão de função “Leitor de Conta de Cobrança” para contas MCA do Azure na interface do usuário. Antes desta versão, era exibida aos usuários apenas a permissão da função “Leitor de Matrículas” para todas as contas do Azure.

• Para os clientes que utilizam a função personalizada “ Azure ”, adicionamos a exibição das permissões abaixo na interface do usuário. Essas faziam parte das permissões que solicitamos durante o processo de credenciamento de assinaturas do Azure, mas não estavam visíveis na interface do usuário.

## Aumento do limite máximo de etiquetas “ Kubernetes ” no recurso “Tags & Labels” – 31 de janeiro de 2024

Aumentamos o número máximo de etiquetas “ Kubernetes ” disponíveis em nosso recurso “Tags e Etiquetas” de 10 para 20. Com essa melhoria, você pode incorporar um número maior de rótulos “ Kubernetes ”, facilitando uma melhor organização das dimensões das tags sintéticas, adaptadas aos seus casos de uso específicos.

## Planejamento da carga de trabalho: Duplicação de recursos – 23 de janeiro de 2024

Hoje, lançamos o Planejamento de Carga de Trabalho – Duplicação de Recursos. A partir de hoje, você pode duplicar facilmente seus recursos dentro de uma carga de trabalho. Esse recurso também ajudará você a planejar suas cargas de trabalho com mais rapidez, permitindo uma análise eficiente de cenários hipotéticos.

Como esse recurso pode ajudá-lo

Antes desta versão, os usuários enfrentavam o desafio de ter que inserir manualmente seus requisitos várias vezes ao avaliar diferentes opções para seus recursos em nuvem ou ao comparar custos entre várias regiões. Agora, você pode clonar seus recursos e ajustar os requisitos com facilidade. Isso também permitirá que você explore diversas configurações para seus recursos em nuvem com facilidade e precisão.

Como habilitar a duplicação de recursos em uma carga de trabalho

1. Crie uma carga de trabalho e adicione um recurso.
2. Selecione o ícone “Duplicar recurso” para clonar seu recurso. ![Duplicação de recursos no WP](../../../../03-media/cloudability-premium/images/wp11.jpg)
3. Atualize o nome do recurso duplicado e altere os requisitos.

   ![Nome do recurso duplicado](../../../../03-media/cloudability-premium/images/wp12.jpg)

   Nota:

   Agora é possível ter recursos em diferentes regiões dentro de uma determinada carga de trabalho. Você pode atualizar a região do recurso no recurso “Pesquisar tipo de recurso (opcional)”.

Mais informações sobre o lançamento

Exemplo de caso de uso: Duplicar recursos para comparar os custos d AWS EC2 e entre duas regiões

1. Crie uma carga de trabalho e adicione um recurso. Use a opção “pesquisar tipo de recurso” para obter uma estimativa de custo para um serviço “ t4g.2xlarge ” na região us-west 1.![pesquisar tipo de recurso](../../../../03-media/cloudability-premium/images/wp13.jpg)
2. Duplique o recurso e renomeie-o.
3. Atualize a região para us-west-2 para o seu recurso duplicado.

   ![atualizar tipo de recurso](../../../../03-media/cloudability-premium/images/wp2.jpg)

## Ajuste do tamanho do cluster de contêineres – 19 de janeiro de 2024

Esta versão inclui recomendações de ajuste de recursos para clusters do Kubernetes nos serviços AWS, Azure e GCP.

Temos o prazer de apresentar a mais recente inovação em nosso conjunto de ferramentas de otimização: o Container Cluster Rightsizing. Com o objetivo de permitir que os clientes equilibrem de forma eficiente a redução de custos com o desempenho da carga de trabalho, esse recurso oferece uma solução robusta para o dimensionamento das VMs que dão suporte aos clusters d Kubernetes. Essa funcionalidade está disponível no recurso de ajuste de capacidade do Cloudability, na guia“Contêineres”, e já está pronta para ser utilizada pelos clientes.

Como esse recurso pode ajudá-lo

Cloudability Os usuários já podiam, anteriormente, aproveitar as recomendações de ajuste de recursos para otimizar o Kubernetes no nível da carga de trabalho — ajustando as configurações de solicitação e limite dos contêineres. Este lançamento traz um novo conjunto de recomendações, desta vez no nível do cluster. O recurso avalia os grupos definidos pelo fornecedor que dão suporte a cada cluster: Grupos de Nós ASG para AWS, Pools de Nós para Azure e GCP. As recomendações se baseiam na análise do histórico de uso de recursos desses grupos, com foco na utilização da CPU e da memória. Para cada cluster, a ferramenta recomenda, em seguida, o tipo de instância e o número de instâncias com a melhor relação custo-benefício que atenderão aos requisitos de recursos a cada hora ao longo do período do relatório.

No caso do Cloudability, para gerar essas recomendações no nível do cluster, importamos seus dados de uso do VM por meio das credenciais habituais do AWS, Azure e GCP. Resumindo, se você já estiver configurado para receber recomendações de ajuste de tamanho d VM, essas recomendações de cluster já estarão disponíveis.

Principais destaques

- Você pode consultar todas as informações sobre os clusters e o resumo das economias na visualização em lista. A visualização detalhada de cada cluster inclui gráficos de utilização para auxiliar na tomada de decisões.
- Ele oferece várias recomendações por cluster, com combinações de tipo e número de instâncias em diversos níveis de risco, atendendo a diferentes zonas de conforto operacional.
- Este lançamento não inclui recomendações para grupos compostos por instâncias spot.
- Para este lançamento, cada recomendação consiste em um único tipo de instância, priorizando a uniformidade e a simplicidade.

## AWS Limpeza das permissões CAR e DBR – 18 de janeiro de 2024

Nesta versão, removemos a exibição das permissões antigas do tipo “ AWS ” para o Relatório Detalhado de Faturamento (DBR) e o Relatório de Alocação de Custos (CAR).

O suporte ao Relatório Detalhado de Faturamento (DBR) e ao Relatório de Alocação de Custos (CAR) do AWS não está mais disponível em Cloudability; no entanto, na visualização de permissões, continuávamos exibindo as permissões relacionadas ao DBR e ao CAR até agora com um “x” vermelho. Nesta versão, removemos a exibição das permissões DBR e CAR da interface do usuário.

Como esse recurso pode ajudá-lo

Isso garante que os clientes d AWS tenham uma visão mais clara das permissões relevantes relacionadas aos relatórios de custo e uso do AWS.

## Definição de métricas de custo padrão para os módulos do Cloudability – 17 de janeiro de 2024

Com esta versão, agora é possível definir uma métrica de custo padrão específica para cada módulo — como o True Cost Explorer e o Rightsizing, entre outros — a partir da lista de todas as métricas compatíveis com o respectivo módulo.

Como esse recurso pode ajudá-lo

Cada módulo do Cloudability oferece suporte a um conjunto específico de métricas de custo, como Custo (Total), Custo (de Tabela) e Custo (Amortizado), entre outras. Anteriormente, “Custo (Total)” era a métrica de custo exibida por padrão nesses módulos. Essa funcionalidade permite que você defina a métrica de custo preferida da sua organização como a métrica de custo padrão para cada módulo. Essa opção aparecerá em Perfil > Configurações da organização no site Cloudability, exclusivamente para usuários com a função de administrador do Cloudability.

A métrica de custo definida para cada módulo será aplicada como métrica padrão para todos os usuários em toda a organização Cloudability.

## Cloudability introduz suporte à Infraestrutura em Nuvem d Oracle s (OCI) no Planejamento de Cargas de Trabalho — 16 de janeiro de 2024

Hoje lançamos o suporte à Infraestrutura em Nuvem d Oracle (OCI) no Planejamento de Cargas de Trabalho. A partir de hoje, os usuários podem estimar com facilidade os custos de novas cargas de trabalho implantadas na OCI, o que lhes permite tomar decisões informadas sobre o provisionamento. Além disso, agora eles podem comparar com facilidade os preços dos recursos em nuvem entre AWS, Azure, GCP e OCI. Antes deste lançamento, os usuários precisavam usar a calculadora de preços de cada fornecedor para esse fim.

![Suporte da OCI no WP](../../../../03-media/cloudability-premium/images/workload-planning-oci-1.jpg)

Mais informações sobre o lançamento

Os principais destaques desta versão incluem:

- Modelagem simples de cargas de trabalho do OCI : Agora você pode modelar facilmente cargas de trabalho do OCI com recomendações de recursos que abrangem vários tipos de serviços\*, como Máquina Virtual, Armazenamento Conectado, Object Storage e Balanceador de Carga.
- Suporte a preços personalizados : as estimativas de custo no Planejamento de Carga de Trabalho já incluem quaisquer preços personalizados, permitindo que você faça um planejamento mais realista.
- Comparação de recursos entre nuvens : É possível identificar facilmente a solução mais econômica comparando os requisitos de recursos e as estimativas de custo entre os principais provedores de nuvem – AWS, Azure, GCP e OCI.

Nota:

O Managed Database ainda não é compatível com o OCI.

## Cloudability Melhoria: Atualização do nome do serviço para as regras do F5 para o produto WAF da AWS – 11 de janeiro de 2024

Nesta versão, corrigimos a denominação do serviço “ ““F5 Rules for AWS WAF”.

Como esse recurso pode ajudá-lo

Anteriormente, nossa solução mapeava incorretamente a taxa do marketplace referente às “Regras d ““F5 para o WAF AWS ” como “WAF AWS ” no nome do serviço. Isso já foi alterado para refletir com precisão as cobranças sob o nome do serviço “ AWS Marketplace”. Como parte dessa melhoria, também resolvemos outros casos específicos em que as cobranças do marketplace não estavam sendo mapeadas corretamente para um nome de serviço d AWS.

## Métrica de custo (total) aprimorada no Cloudability para o AWS - 5 de janeiro de 2024

Esta versão traz uma melhoria na métrica “Custo (Total)”, com impacto limitado para alguns dos clientes que monitoram os gastos com o “ AWS ”. Isso afeta apenas as partidas que se referem a instâncias reservadas (RI) parciais e sem pagamento antecipado, mantendo os valores no nível agregado inalterados.

Como esse recurso pode ajudá-lo

Essa melhoria ajudará você a aumentar a clareza das métricas de custo e a simplificar parte do trabalho de reconciliação.

Mais informações sobre o lançamento

No entanto, a métrica “Custo (Total)” sempre teve como objetivo fornecer uma representação fiel do custo da fatura – a coluna “ “LineItem/UnblendedCost” ” no arquivo CUR. No entanto, houve uma exceção a essa regra, implementada na época para garantir uma [transição](https://www.apptio.com/blog/switch-to-aws-cur/ "(Abre em uma nova guia ou janela)") consistente entre os arquivos DBR e CUR. A lógica foi aplicada a esses dois tipos de itens:

- Para usos abrangidos por um RI – utilize “reservation/RecurringFeeForUsage”, em vez de “LineItem/UnblendedCost”.
- Para itens de linha RI recorrentes – use “reservation/UnusedRecurringFee”, em vez de “LineItem/UnblendedCost”.

Isso garantiu que os itens de uso tivessem o valor de RI consumido atribuído a eles, em vez de um valor zero. Isso significa que o custo foi transferido das linhas de cobrança mensal recorrente para as linhas de cobrança por uso. Isso ajudou a manter um comportamento consistente com o arquivo DBR mais antigo, agora obsoleto, mas teve a desvantagem de o Custo (Total) não ser uma métrica de caixa puramente “pass-through”. Como o Cloudability não oferece mais suporte ao DBR, essas regras especiais para a métrica “Custo (Total)” foram removidas, e a métrica aprimorada está refletida na coluna “ lineItem/UnblendedCost ”.

Nota:

Essas mudanças entrarão em vigor a partir de janeiro de 2024. Elas também serão válidas para dezembro de 2023, caso a AWS ainda não tenha finalizado sua cobrança. Além disso, as alterações terão efeito retroativo no caso de qualquer reprocessamento de cobrança.

Caso tenha alguma dúvida, precise de mais assistência ou queira que os dados históricos sejam reprocessados de acordo com o novo método, entre em contato com a equipe responsável pela sua conta ou com o suporte.

## Suporte à definição de preços personalizados para o redimensionamento do GCP — 3 de janeiro de 2024

Esta versão adiciona suporte a preços personalizados ao recurso “Rightsizing” do GCP para o Cloudability, de modo que os descontos contratuais e outros preços específicos do cliente sejam aplicados às recomendações e funcionalidades de rightsizing do GCP.

Como esse recurso pode ajudá-lo

Isso permite aplicar os descontos contratuais recebidos do seu GCP às recomendações de ajuste de capacidade do GCP. Isso também oferece a você uma visão mais precisa da economia de custos alcançada por meio da otimização de seus recursos. Isso aumentará a precisão das recomendações de redimensionamento, chamando a atenção para oportunidades de redução de custos e, ao mesmo tempo, identificando recursos que podem ser redimensionados para se adequarem melhor às suas cargas de trabalho subjacentes.

Mais informações sobre o lançamento

É necessário que você conceda ao Cloudability acesso aos seus dados de preços personalizados para ativar esse recurso. Assim que essa configuração for concluída com sucesso, os novos preços do GCP, específicos para o cliente, serão aplicados automaticamente às recomendações de ajuste de recursos e às funcionalidades do GCP. A principal funcionalidade de reajuste de capacidade do GCP pode ser acessada navegando até Otimizar > Reajuste de capacidade > GCP. GCP Os custos por nível de recurso estarão disponíveis em Cloudability, na seção Relatórios e painéis, selecionando a coluna “ID do recurso”.
