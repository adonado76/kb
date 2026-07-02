---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "release-notes-premium"
title: "Novidades do Cloudability Premium"
breadcrumb:
  - "Cloudability Premium"
  - "O que há de novo em Cloudability"
source_path: "release-notes-premium/whats-new.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Novidades do Cloudability Premium

## Cloudability Premium compatível com Kubernetes versão 1.35 e OpenShift versão 4.21 - 25 de junho de 2026

Cloudability Premium agora oferece suporte a Kubernetes, versão 1.35 e OpenShift, 4.21. Esta atualização garante a compatibilidade contínua com as versões mais recentes do Kubernetes e do OpenShift nos principais provedores de nuvem, permitindo que os clientes mantenham total visibilidade dos custos dos contêineres à medida que adotam versões mais recentes do Kubernetes ou do OpenShift.

## Cloudability Premium Incorpora as ações recomendadas do SQL do “ Azure ” à experiência do usuário do “ Cloudability ” para o redimensionamento avançado — 25 de junho de 2026

Cloudability ampliou os serviços compatíveis com o conjunto de recursos do Advanced Rightsizing, adicionando o SQL d Azure. Assim como nos outros serviços compatíveis com o Advanced Rightsizing, os usuários com permissões adequadas podem visualizar as ações recomendadas, verificar as dependências, as possíveis economias ou investimentos, compreender as políticas que motivaram essa ação recomendada e muito mais.

Os usuários também podem executar essas ações diretamente a partir da interface do usuário do Cloudability.

## Cloudability Contêineres avançados — Experiência em alocação de contêineres e ativos no Cloudability — Experiência do usuário — 24 de junho de 2026

Cloudability lançou uma experiência aprimorada de análises de contêineres, oferecendo a poderosa funcionalidade de alocação de contêineres do Cloudability Advanced Containers (com tecnologia Kubecost), agora disponível diretamente na experiência do Cloudability para clientes que possuem tanto o Cloudability quanto o Cloudability Advanced Containers.

Esta versão inclui suporte para painel de controle, agregação múltipla/única, configuração de custos compartilhados e moreIn Além disso, a funcionalidade de ativos do Kubecost também está disponível em Cloudability. Os usuários podem utilizar essa funcionalidade para visualizar e explorar em detalhes ativos como Nó, Disco, Rede, LoadBalancer, ClusterManagement, etc. Isso integra nativamente mais recursos do Cloudability Advanced Containers (com tecnologia Kubecost) ao Cloudability, eliminando a necessidade de alternar entre aplicativos e simplificando os fluxos de trabalho.

## Detecção de anomalias configurável – 23 de junho de 2026

Atualmente, o recurso de detecção de anomalias do Cloudability oferece dimensões de anomalias configuráveis, permitindo que os administradores selecionem até 4 tags e dimensões de mapeamento de negócios mais relevantes para sua organização. Isso garante que os picos de custo sejam identificados em relação às dimensões que são relevantes para suas equipes, em vez de padrões definidos pelo sistema. As dimensões de anomalia configuráveis estão restritas exclusivamente à configuração no nível de administrador.

## Cloudability Premium Integra as ações recomendadas do " AWS RDS " à experiência do usuário do " Cloudability " para o redimensionamento avançado - 5 de junho de 2026

Cloudability ampliou os serviços compatíveis com o conjunto de recursos do Advanced Rightsizing, adicionando o serviço de gerenciamento de dispositivos ( AWS RDS ). Assim como nos outros serviços compatíveis com o Advanced Rightsizing, os usuários com permissões adequadas podem visualizar as ações recomendadas, verificar as dependências, as possíveis economias ou investimentos, compreender as políticas que motivaram essa ação recomendada e muito mais.

Os usuários também podem executar essas ações diretamente a partir da interface do usuário do Cloudability.

## Credenciais de fornecedores - Permissões granulares de buckets do GCS – 3 de junho de 2026

Como parte das melhorias do IAM no GCP, aperfeiçoamos o script de integração Cloudability GCP para usar permissões específicas do bucket Google Cloud Storage em vez de permissões de armazenamento mais amplas no nível do projeto.

Com esta atualização, as permissões de armazenamento do GCP estão sendo transferidas de CloudabilityRole\_Billing para uma nova função personalizada no nível do projeto, CloudabilityRole\_Bucket. Esta função foi criada para permitir o acesso apenas aos recursos necessários do bucket do GCS.

Essa alteração aumenta a segurança ao limitar o acesso ao armazenamento a buckets específicos, em vez de permitir um acesso mais amplo a todos os buckets do projeto, em conformidade com o princípio do privilégio mínimo.

As permissões abaixo foram transferidas para o novo endereço CloudabilityRole\_Bucket.

- storage.buckets.get
- storage.buckets.getIamPolicy
- storage.multipartUploads.abort
- storage.multipartUploads.create
- storage.multipartUploads.list
- storage.multipartUploads.listParts
- storage.objects.create
- storage.objects.delete
- storage.objects.get
- storage.objects.list
- storage.objects.update

Observação: esta atualização entrará em vigor com a renovação das credenciais dos clientes atuais. É possível baixar o modelo mais recente editando a conta existente.

## Cloudability A Advanced Containers anuncia suporte à visualização parcial - 2 de junho de 2026

Atualmente, o recurso “ Cloudability ” do Advanced Containers oferece suporte à visualização parcial, permitindo que as organizações limitem a experiência do Advanced Containers a um subconjunto específico de contas na nuvem. Isso permite implantações multilocatárias e ambientes com controle de acesso, nos quais diferentes usuários ou equipes devem visualizar apenas os dados de custos relevantes para suas contas.

O suporte a visualizações parciais se aplica **apenas** a visualizações baseadas em contas. As visualizações devem ser definidas com base na associação à conta na nuvem, utilizando IDs/nomes de contas d AccountGroups,, ou por fornecedor — outros tipos de visualização, como as baseadas em rótulos ou tags, não são compatíveis nesta versão.

Nesta versão:

- Agora está disponível **um Seletor de Visualizações** na interface do usuário dos Contêineres Avançados, permitindo que os usuários selecionem e alternem entre as visualizações configuradas. A visualização selecionada é mantida no ` URL ` e no armazenamento do navegador, facilitando a criação de favoritos e o compartilhamento de visualizações específicas.
- Todos os dados de custos — alocações, ativos e resultados do preenchimento automático — são filtrados automaticamente para as contas associadas à visualização ativa.
- A visualização ativa é mantida ao alternar entre as experiências do Advanced Containers incorporadas e independentes.
- As páginas e os widgets que não suportam filtragem baseada em visualização exibem uma mensagem clara, em vez de mostrar dados fora do escopo.

## Cloudability A Advanced Containers anuncia o recurso de credenciais compartilhadas - 2 de junho de 2026

Hoje, o Cloudability Advanced Containers (CAC) oferece o recurso de credenciais compartilhadas, eliminando a necessidade de configurar integrações de faturamento na nuvem separadamente dentro do Kubecost. As credenciais de custos de nuvem gerenciadas no Cloudability agora são reconhecidas automaticamente pelo Advanced Containers, oferecendo aos clientes um único local para gerenciar suas integrações em nuvem.

Nesta versão:

- As integrações em nuvem configuradas no Cloudability são automaticamente refletidas no Advanced Containers — não é necessário realizar configurações duplicadas.
- A página de configurações de Integrações na Nuvem agora exibe credenciais provenientes de Cloudability, com um link direto para o Serviço de Credenciais do Cloudability para qualquer gerenciamento de credenciais.
- Os dados de custos da nuvem são importados automaticamente pelo pipeline do Cloudability, garantindo a precisão do CAC.
- **A API de status de custos na nuvem** atualizada oferece visibilidade em tempo real sobre o estado da importação de custos na nuvem por conta configurada.
- Quando o Cloudability Advanced Containers está em uso, os custos de nuvem são gerenciados pelo Cloudability, e as funcionalidades duplicadas na versão autônoma do Advanced Containers — como custos de nuvem, relatórios de custos de nuvem, orçamentos de custos de nuvem e cobranças — são removidas.

## CFP Intelligent Forecasting BETA - 1º de junho de 2026

Hoje, lançamos o recurso de Previsão Inteligente para o CFP. Essa nova experiência ajuda as equipes a manter os planos do CFP atualizados, renovando as linhas de previsão existentes com projeções baseadas nos dados reais mais recentes, ao mesmo tempo em que oferece aos usuários maior visibilidade e controle sobre como essas projeções são geradas.

O CFP Intelligent Forecasting traz para os planos do CFP a mesma experiência de previsão baseada em modelos utilizada na página “Previsão Aprimorada”. Os usuários podem abrir uma linha de previsão específica, analisar dados históricos reais, visualizar projeções de vários modelos de previsão, comparar visualmente essas projeções com os valores do plano atual e aplicar o modelo que melhor reflita os gastos futuros esperados.

**Principais recursos**

- Análise interativa da previsão – visualize um minigráfico embutido que mostra o histórico de gastos reais e as projeções atualizadas diretamente na tabela de linhas de previsão
- Maior precisão nas previsões – utilize o mecanismo de Previsão Inteligente para avaliar vários modelos e recomendar o mais adequado para cada linha de previsão
- Comparação e controle de modelos – comparar os resultados de modelos alternativos e aplicar um modelo diferente quando o modelo recomendado não refletir os gastos futuros esperados
- Comparação entre plano e valor – compare visualmente as projeções geradas pelo modelo com os valores do plano atual
- Suporte à reestimativa – aplicar os resultados do modelo selecionado para atualizar os períodos históricos com os dados reais e os períodos futuros com novas estimativas de previsão

**Escopo**

Esta versão oferece suporte à reestimativa interativa de linhas de previsão individuais nos planos do CFP. Os usuários podem acessar a Previsão Inteligente a partir de uma linha de previsão (clicando no ícone de expansão para exibir o minigráfico de previsão), analisar os dados reais e as projeções mais recentes, comparar os resultados do modelo recomendado com os de modelos alternativos, comparar os valores projetados com os valores atuais do plano e aplicar um modelo selecionado para atualizar os valores de previsão no plano.

**O que vem a seguir**

Na GA, o CFP Intelligent Forecasting passará a oferecer suporte para salvar seleções de modelos e refazer previsões em massa, facilitando aos usuários a atualização das previsões com base nos dados reais mais recentes, como parte de um ciclo regular de atualizações mensais.

**Disponibilidade e Habilitação**

O CFP Intelligent Forecasting está disponível para todos os clientes da CFP. A Previsão Inteligente requer a funcionalidade “Atualizar Dados Reais”; portanto, esse recurso deve estar ativado antes que a Previsão Inteligente possa ser utilizada.

Tanto a opção “Atualizar valores reais” quanto a “Previsão inteligente” podem ser ativadas na guia “Avançado” da página “Preferências do plano”, localizada em “Configurações” no painel de navegação à esquerda do Cloudability. A Previsão Inteligente é ativada automaticamente para os clientes que ativaram a opção “Atualizar Valores Reais” durante o período inicial de implementação.

Saiba mais sobre [previsões inteligentes](../product/efp-forecast.html)

## Cloudability A Commitments anuncia o suporte do AWS à página de visão geral aprimorada do Commitment Manager – 1º de junho de 2026

Na segunda-feira, 1º de junho, a equipe de Compromissos do Cloudability lançou a página de visão geral do Gerenciador de Compromissos aprimorado. Esta nova página substitui o Gerenciador de Compromissos existente, oferecendo funcionalidades equivalentes e aprimorando-a para funcionar perfeitamente como página inicial em toda a funcionalidade de Compromissos do Cloudability. Nesta versão, a nova página de visão geral, chamada simplesmente *de* “Commitment Manager” no menu de navegação à esquerda, oferece suporte aos serviços do AWS nos quais oferecemos um tipo de compromisso: All Compute, RDS, Redshift, Elasticache e OpenSearch.

***Nova funcionalidade***

- · O aspecto do gráfico é semelhante ao do gráfico da página de detalhes da recomendação. Este gráfico foi recentemente aprimorado com o lançamento do [AWS Support for Commitment Management 2.0](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=cloudability-whats-new-in#topic__cldy-commit-mgmt-2.0 "(Abre em uma nova guia ou janela)").
- KPI aprimorados, incluindo taxa de economia e cobertura. Os KPIs na página de Visão geral são os mesmos apresentados nas seções Portfólio e Recomendações.
- Seleção simplificada do período de análise.
- A granularidade do KPI permite as opções Semana, Mês e Total.
- Botão de alternância para comparação de KPIs.
- Tipos de custo suportados pelo gráfico: Custo real, Equivalente sob demanda (ODE).

***Funcionalidade de paridade***

- Nível de detalhamento do relatório diário.
- Visualizações de custo/economia: O botão de alternância entre custo e economia foi removido. Essas informações agora estão representadas em um único gráfico.
- Alternar recomendações: transferido para a barra de cabeçalho, abaixo do menu suspenso “Tipo de recomendação”.
- Links de navegação para as páginas Portfólio e Recomendações.

***Funcionalidade obsoleta***

- Seleção do relatório diário: O intervalo de tempo do relatório nesta página agora é mensal. Isso simplifica a página e a adapta ao principal caso de uso, que é uma visão geral de alto nível do seu desempenho e das oportunidades.
- Discriminação do gráfico por serviço: os relatórios agregados entre serviços continuam sendo oferecidos, mas os custos não são mais discriminados explicitamente por serviço.
- Seleção dos critérios de recomendação: A recomendação agora assume a recomendação ideal.
- A página anterior do Gerenciador de Compromissos foi descontinuada e substituída por esta nova página. A página antiga não é mais compatível e não pode ser restaurada.

Para obter mais informações, consulte nossa documentação de ajuda [na](../product/using_commitment_manager_to_align_the_organization_on_commitment_strategy.html) seção “Visão geral do Gerenciador de Compromissos para alinhar a organização à estratégia de compromisso”.

## Cloudability Governance adiciona suporte ao Azure (Pré-visualização pública) – 29 de maio de 2026

Hoje temos o prazer de anunciar o suporte do Azure para o Cloudability Governance.

Os clientes que operam predominantemente ou parcialmente em uma nuvem d Microsoft Azure, agora podem experimentar os recursos do Cloudability Governance.

Essa expansão permite que empresas com grande volume de faturamento ( Azure ) finalmente utilizem os recursos automatizados e proativos de governança e prevenção de custos do Cloudability Governance, em vez de depender exclusivamente de ferramentas reativas pós-faturamento.

## Azure Credenciamento MCA - Atribuição automática da função de Leitor de conta de cobrança – 25 de maio de 2026

Esta versão automatiza a atribuição da função “Billing Account Reader” ao principal de serviço “ Cloudability ” para contas MCA do Azure, ajudando os clientes a se cadastrarem mais rapidamente.

Antes desta versão, os clientes precisavam atribuir essa função manualmente.

## Melhorias na experiência do usuário no Rightsizing do Cloudability - 28 de maio de 2026

Hoje, estamos lançando várias melhorias na experiência do usuário no Rightsizing do Cloudability, que tornam a navegação e o uso dos recursos do Rightsizing mais eficientes e intuitivos. A lista de melhorias inclui:

- **A seleção de serviços passou a ser feita por meio de um menu, em vez de guias**. À medida que mais serviços são adicionados ao Rightsizing, substituímos o seletor de serviços baseado em guias por um menu mais eficiente, semelhante ao da página “Compromissos”.
- **Removida a etiqueta duplicada do tipo de serviço da área do painel**. O tipo de serviço agora é exibido apenas no seletor de serviços, eliminando informações redundantes e liberando espaço valioso na tela.
- **A base de custo mudou de botões de opção para**. O seletor de base de custo foi convertido em um menu, semelhante à interface do Gerenciador de Compromissos, proporcionando uma experiência de usuário mais consistente. Para serviços que suportam apenas uma única base de custo, este campo é somente para leitura.
- **A linha do tempo foi renomeada para “Período de análise” com um seletor**. O seletor de linha do tempo foi renomeado para “Período de análise” para se alinhar à terminologia utilizada no Commitment Manager. O seletor foi alterado de botões de opção para um menu, a fim de economizar espaço na tela. Para serviços que suportam apenas um único período de análise, este campo é somente para leitura.

## Atualizações na base de cálculo das recomendações avançadas no Cloudability Premium - 28 de maio de 2026

Hoje, Cloudability Premium atualizou a terminologia relativa à base de custo nas páginas sobre “Rightsizing” para refletir melhor como as Recomendações Avançadas são calculadas e para distinguir claramente entre a metodologia de base de custo das Recomendações Avançadas e das Recomendações Básicas.

Até hoje, tanto as recomendações avançadas quanto as básicas listavam as opções de base de custo disponíveis como “Efetiva” e “Sob demanda”, mas essas opções tinham significados diferentes nas recomendações básicas e nas avançadas.

As bases de cálculo avançadas para recomendações foram atualizadas para “Ajustada” e “Ajustada e amortizada”, a fim de refletir melhor os cálculos subjacentes dos custos dos recursos de origem e de destino.

**Ajustado** — calculado com base no custo de caixa de um determinado recurso, incluindo suas taxas privadas, quando disponíveis (onde o custo de compromisso é considerado como $0), e comparado com o custo de caixa projetado para o estado futuro e a cobertura esperada dos compromissos aplicáveis a esse recurso durante o período de análise retrospectiva. Esse cálculo é denominado "On Demand" na documentação do Cloudability Premium : Interface de Otimização de Carga de Trabalho e Turbonomic.

**Amortizado ajustado** — calculado com base no custo amortizado de um determinado recurso e nos compromissos associados que se aplicaram a ele durante o período de análise retrospectiva (incluindo taxas privadas, quando disponíveis). O custo futuro do estado é calculado com base na forma como se prevê que esses compromissos sejam aplicados, quais partes se espera que permaneçam sob demanda e quais compromissos (se houver) serão liberados para serem aplicados em outras áreas. Esse cálculo é denominado "Efetivo" na interface de usuário do Cloudability Premium : Workload Optimization e na documentação Turbonomic.

## Azure Credenciamento MCA - Atribuição automática da função de Leitor de conta de cobrança – 25 de maio de 2026

Esta versão automatiza a atribuição da função “Billing Account Reader” ao principal de serviço “ Cloudability ” para contas MCA do Azure, ajudando os clientes a se cadastrarem mais rapidamente.

Antes desta versão, os clientes precisavam atribuir essa função manualmente.

## Métricas calculadas em painéis e relatórios – 21 de maio de 2026

Temos o prazer de apresentar as Métricas Calculadas para os painéis e relatórios do Cloudability. Esse recurso avançado permite definir métricas econômicas por unidade e KPIs sofisticados a partir de uma plataforma centralizada, proporcionando maior visibilidade sobre os gastos com nuvem e a eficiência operacional por meio de métricas personalizadas e reutilizáveis.

Gerenciamento centralizado de métricas: crie, edite e exclua métricas calculadas a partir de um único painel na área de produtos Business Mappings. Defina as métricas uma vez e reutilize-as em todos os painéis e relatórios, eliminando configurações redundantes e garantindo a consistência.

Criação flexível de fórmulas: crie fórmulas personalizadas utilizando constantes numéricas, operadores aritméticos básicos e métricas existentes. O suporte a fórmulas flexíveis permite análises sofisticadas adaptadas às necessidades da sua empresa, incluindo indicadores de economia por unidade, como custo por recurso ou custo por cluster.

Permissões baseadas em funções: controles de acesso aprimorados garantem uma governança adequada com três níveis de permissão: Administrador (acesso total para criar, editar e excluir todas as métricas), Editar (criar e modificar suas próprias métricas) e Visualizar (acesso somente para leitura).

## Terminologia consistente nas telas de credenciais de fornecedores – 19 de maio de 2026

Hoje, atualizamos a terminologia em todas as telas de credenciais de fornecedores para garantir a consistência.

- A seção "Otimização de recursos" foi renomeada para "Ajuste avançado de recursos"
- Atualizei a seção de informações para incluir consistentemente as opções “Automatizar ações” e “Ajuste avançado de recursos”
- Nomes alterados dos botões de permissão: "Somente leitura" e "Automatizar ações"

  Observação: isso não afeta a funcionalidade atual. É uma atualização exclusivamente voltada para a experiência do usuário.

## Cloudability A Commitments adiciona suporte ao portfólio para a capacidade de processamento provisionada do Microsoft Foundry – 19 de maio de 2026

Hoje, lançamos o suporte ao [Microsoft Foundry Provisioned Throughput (PTU)](https://learn.microsoft.com/en-us/azure/cost-management-billing/reservations/microsoft-foundry "(Abre em uma nova guia ou janela)"). O [décimo terceiro](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=discount-commitment-types-in-cloudability "(Abre em uma nova guia ou janela)") tipo de compromisso do Azure a ser oferecido, as PTUs da Foundry oferecem um desconto em serviços de IA em troca de um compromisso de um mês ou um ano com o uso por hora. Esse tipo de compromisso é classificado como um compromisso baseado em recursos e, como tal, requer a seleção de parâmetros de uso específicos: Região, Tipo de implantação e Opção de pagamento. Nesta versão, apenas a carteira é compatível com esse tipo de compromisso. Consideraremos a possibilidade de elaborar recomendações no futuro.

Para obter mais informações, visite a documentação de ajuda do gerenciamento de compromissos. (editado)

## Mapeamento de definições de negócios de importação e exportação por meio da interface do usuário – 15 de maio de 2026

- Exportação: Agora, os usuários podem exportar definições individuais do Business Mapping diretamente da interface do usuário para um arquivo JSON, facilitando o compartilhamento ou o backup da configuração do BM.
- Importação: Agora, os usuários também podem importar definições de BM para um BM já existente. O arquivo JSON importado preenche a interface do usuário com novos valores, permitindo que os usuários revisem e validem as alterações.

Esse recurso permite que os clientes gerenciem suas definições de BM inteiramente por meio da interface do usuário, sem a necessidade de acessar a API, simplificando o processo de importação e exportação de configurações de BM.

## Cloudability A Commitments anuncia o suporte ao AWS para gerenciamento de compromissos 2.0 – 13 de maio de 2026

Hoje, a equipe de Compromissos do Cloudability disponibilizou suporte ao AWS para o Gerenciamento de Compromissos 2.0. Com esta versão, os usuários verão a Carteira de Compromissos e as Recomendações adaptadas para oferecer suporte à funcionalidade básica do 2.0, que inclui, entre outros:

- KPI aprimorados, incluindo taxa de economia e cobertura
- Agrupe “todas” as páginas, quando aplicável, em todo o portfólio
- Suporte ao modal de cobertura
- Página de detalhes das recomendações renovada
- Recurso de ajuste personalizado das recomendações

Esta versão ajuda os usuários a elaborar um estudo de viabilidade para uma estratégia de compromisso alinhada às melhores práticas. Especificamente, os usuários agora podem personalizar as recomendações do " Cloudability " para incluir análises de sensibilidade tanto para a estratégia de longo prazo quanto para a próxima compra incremental. Isso permite que os usuários combinem tipos de compromisso baseados em prazo, alavancagem de gastos e recursos, e ajustem esses valores para mais ou para menos com base em projeções de uso futuro.

Além disso, essa funcionalidade começa a integrar as páginas personalizadas de compromissos aos relatórios, o que proporciona a transparência que nossos clientes exigem para aproveitar nosso aplicativo em casos de uso relacionados à gestão de compromissos, estornos e showback.

**Como posso obter ajuda?**

Nosso conteúdo de ajuda foi reescrito para acompanhar essas importantes melhorias. O conteúdo começa com [“Otimização de custos na nuvem” em Cloudability](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=optimize-cloud-cost-optimization-in-cloudability "(Abre em uma nova guia ou janela)"). Do ponto de vista tático, [os artigos “Utilizando a carteira de compromissos para compreender o desempenho histórico](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=management-using-commitment-portfolio-understand-historical-performance "(Abre em uma nova guia ou janela)") ” e [“Utilizando as recomendações de compromissos para analisar oportunidades de economia”](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=management-using-commitment-recommendations-analyze-savings-opportunities "(Abre em uma nova guia ou janela)") oferecem orientações sobre como aproveitar ao máximo as novas páginas de carteira e recomendações.

**E agora?**

Essa funcionalidade já havia sido concluída para os compromissos do programa “ GCP ” no final de 2024. Vamos agora nos concentrar em disponibilizar recursos de paridade para o Azure.

## Cloudability A Commitments anuncia melhorias nas recomendações de compromissos do programa “ AWS ” – 13 de maio de 2026

Hoje, a equipe do Cloudability Commitments apresentou melhorias significativas nas recomendações do AWS Commitments. Esta versão pode ser considerada uma subversão de [Cloudability A Commitments anuncia o suporte a AWS para gestão de compromissos 2.0 – 13 de maio de 2026](#whats-new__cldy-commit-mgnmt2.0). Estamos destacando isso separadamente para chamar a atenção para as nuances relacionadas às melhorias nas recomendações. Os usuários podem esperar as seguintes melhorias:

*Introdução da abordagem de cobertura baseada em custos* — Com a introdução do KPI de cobertura no sistema de gestão de custos de produção ( AWS ), estamos utilizando dados de custos reais em vez de horas de uso alocadas. Isso diferirá da métrica de taxa de cobertura reservada nos relatórios, uma vez que a cobertura nesse caso é calculada com base nas horas de uso. Tanto no Portfólio de Compromissos quanto nas Recomendações, a cobertura é determinada diretamente pelo custo, mais especificamente pela parcela dos seus gastos equivalentes ao modelo sob demanda que foi coberta por um compromisso em um determinado period.This. Essa mudança torna a cobertura mais relevante para a tomada de decisões financeiras. É difícil comparar as horas de uso entre os diferentes tipos de instância, e elas não correspondem diretamente ao que você está gastando ou economizando. A cobertura baseada nos custos sim. Com o Cost Explorer do AWS calculando a cobertura das Instâncias Reservadas em horas de uso, a abordagem baseada em custos do Cloudability oferece uma visão financeiramente mais precisa, que reflete o impacto real em dólares dos seus compromissos, em vez de uma estimativa baseada em horas que pode variar significativamente entre famílias e tamanhos de instâncias. No que diz respeito aos Planos de Poupança, acreditamos que agora estamos alinhados com a forma como o AWS calcula a cobertura de forma nativa.

*Recomendação baseada nos compromissos existentes ao longo do período de análise* — Anteriormente, as Recomendações de Compromisso levavam em conta apenas a cobertura *atual* dos compromissos ao gerar nossas recomendações. Agora, utilizaremos toda a cobertura disponível ao longo do período de análise selecionado. Embora isso tenha a desvantagem de poder ser menos preciso — por exemplo, se um compromisso foi adquirido ou expirou durante o período de análise —, agora torna mais simples o processo de elaboração da recomendação. Ao acessar a página de detalhes da recomendação, você verá agora um gráfico que mostra apenas os custos. A maneira correta de usar esse recurso agora é analisar o uso ao longo do período de análise e selecionar novamente o período de análise que melhor represente o futuro. Em muitos casos, isso exigiria que os usuários reduzissem o período de análise para apenas uma ou duas semanas, em vez do mês inteiro predefinido. Espera-se que essa alteração tenha um impacto mínimo nos valores recomendados aos clientes após o lançamento. Acreditamos que isso seja uma melhoria, pois o gráfico agora representa com precisão o seguinte: “E se eu tivesse mantido essa recomendação durante todo o período de análise selecionado?”

*Incluir/excluir planos de economia existentes nas recomendações de instâncias reservadas* - Agora oferecemos a possibilidade de ignorar planos de economia existentes nas recomendações de instâncias reservadas do EC2. Devido à natureza fungível dos Planos de Poupança, eles costumam ser alocados de forma variável pelo AWS. Consequentemente, os horários em que os planos de economia foram atribuídos a uma determinada combinação de Família de Instâncias/Região/Conta/SO causariam uma variabilidade significativa em nossas recomendações, devido a pequenas diferenças no período de análise. Esse recurso permite ignorar os Planos de Economia, uma vez que o uso variável poderia ser aplicado em outro lugar caso a Instância Reservada existisse. Isso oferece aos nossos usuários flexibilidade para continuar aproveitando a taxa de economia mais vantajosa das Instâncias Reservadas.

*Incluir/Excluir contas vinculadas* - Agora oferecemos a possibilidade de gerar recomendações individuais para cada conta vinculada de um pagador. Quando o recurso de compartilhamento está ativado, continuamos a agregar todas as contas vinculadas a uma conta de pagador ao analisar o uso. Isso mostra como o site AWS distribui os RIs e oferece as melhores economias. A diferença é que, quando o recurso de compartilhamento estiver desativado e o usuário selecionar uma conta de pagador, ele passará a ver uma recomendação para cada conta, em vez de apenas uma recomendação para o uso na conta de pagador.

**Como posso obter ajuda?**

Nosso conteúdo de ajuda foi reescrito para acompanhar essas melhorias. O conteúdo começa com [“Otimização de custos na nuvem” em Cloudability](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=optimize-cloud-cost-optimization-in-cloudability "(Abre em uma nova guia ou janela)").

## Guias do painel nos painéis do Cloudability – 12 de maio de 2026

Hoje, estamos lançando uma melhoria nos painéis do Cloudability, adicionando suporte a **abas nos painéis,** o que permite que nossos clientes organizem melhor o conteúdo dos painéis em várias abas dentro de um único painel. Isso permite que os usuários agrupem widgets por fornecedor, por equipe, por unidade de negócios ou de qualquer outra forma que torne os painéis mais úteis e melhor adaptados aos casos de uso de cada cliente.

- Os usuários podem arrastar e soltar as guias para alterar sua ordem
- Os usuários podem duplicar abas inteiras para copiá-las entre painéis
- Os usuários podem arrastar e soltar um widget para movê-lo para uma guia diferente
- Ao copiar widgets, os usuários podem escolher para qual guia desejam copiá-los

## Cloudability A Commitments anuncia suporte à preferência de colunas em todos os compromissos – 12 de maio de 2026

Hoje, a equipe do Cloudability Commitments implementou uma pequena melhoria em sua tabela. Para as tabelas em todo o portfólio e as recomendações em AWS e GCP, agora salvamos a seleção das colunas exibidas/ocultadas no armazenamento local do seu computador. Assim, sua seleção de colunas agora será mantida entre as sessões. É importante notar que cada página de compromissos tem um conjunto diferente de colunas e uma ordem diferente definida como padrão. Para obter mais informações, consulte a [seção “Noções básicas sobre a Tabela de Compromissos”](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=cloudability-commitment-table-basics "(Abre em uma nova guia ou janela)") em nossa Central de Ajuda.

## Recomendações de compromisso: detalhes das melhorias no gráfico – 11 de maio de 2026

Hoje, a equipe do Compromissos do Cloudability anuncia oficialmente uma série de melhorias na página de detalhes das recomendações. Isso faz parte, formalmente, da versão [“ 2.0 ”](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=cloudability-whats-new-in#topic__cldy-commit-mgmt-2.0 "(Abre em uma nova guia ou janela)") do Commitment Management. Esta alteração está ganhando uma postagem separada aqui, pois se aplica tanto ao site AWS quanto ao GCP.

***Seleção da equação diferencial ordinária (EDO) assumida*** : foi adicionado um botão de alternância para a seleção da EDO assumida (equivalente à opção sob demanda) na página “Detalhes da recomendação”, permitindo que os usuários ignorem a EDO assumida para obter um gráfico de custos mais simples. Desativar a opção reduz o eixo Y e dá mais destaque ao custo.

***Recurso de divisão de compromissos*** : Agora, os usuários podem dividir os compromissos na página “Detalhes da recomendação”, visualizando os compromissos atuais somados ou detalhados individualmente. Isso facilita a análise de uma recomendação cuja cobertura poderia ser abrangida por um tipo de compromisso diferente.

***Informações do gráfico atualizadas*** : A legenda do gráfico foi redesenhada para permitir a rolagem e apresentar os custos agregados em um formato semelhante a um balanço financeiro, exibindo dados por hora juntamente com totais resumidos para melhorar a legibilidade e facilitar a análise rápida.

***Custo total removido do menu suspenso de tipos de gráfico*** : o Custo total não está mais disponível como tipo de gráfico, uma vez que os totais agora podem ser acessados por meio da dica de ferramenta atualizada. Os controles de alternância foram atualizados de acordo com o feedback dos usuários, que apontaram que a seleção anterior era confusa.

***Renomeação do tipo de recomendação*** : O tipo de recomendação de nível superior “Personalizado” passou a se chamar “Modificado”, e o tipo de recomendação “Ajustado” passou a se chamar “Personalizado”. Essas alterações resolvem os conflitos de nomenclatura causados pela renomeação da lista de base de custo. Para obter mais informações, consulte “[Como usar recomendações de compromisso para analisar oportunidades de economia](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=management-using-commitment-recommendations-analyze-savings-opportunities "(Abre em uma nova guia ou janela)") ”.

## Cloudability A Commitments anuncia melhorias menores e diversas no compromisso GCP – 11 de maio de 2026

Hoje, a equipe do Cloudability Commitments anuncia oficialmente uma série de melhorias em nosso suporte ao GCP. São as seguintes:

- Seleção aprimorada de contas para um grande número de contas em toda a carteira e recomendações: os clientes podem ter milhares de contas. Agora, consolidamos as contas vinculadas na conta do pagador. Isso é especialmente útil para compromissos, uma vez que eles geralmente são adquiridos/compartilhados no nível da conta do pagador. Os usuários não precisam mais rolar a tela sem parar nem saber exatamente qual conta procurar.
- Custo da carteira no período de análise: Agora, apresentamos o custo total para o período de análise, além do custo restante. Os clientes podem querer comparar esse número com o que constam nos relatórios. Você não precisa mais adicionar essa coluna manualmente nem exportar a tabela para um arquivo CSV para fazer a soma.
- Taxas de poupança de carteira (PSR) e de compromisso (CSR) na carteira: O CSR e o PSR são claramente diferentes. O CSR é a taxa de poupança ponderada dos seus compromissos ao longo do período de análise. A PSR é a taxa de poupança da sua carteira. CSR = Economia / Equivalente sob demanda do custo de compromisso. PSR = Economia / Despesas autorizadas. Ver esses dois valores lado a lado ajuda a distinguir os dois KPIs. Para obter mais informações, consulte “[Indicadores-chave de desempenho de compromissos](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=cloudability-commitment-key-performance-indicators "(Abre em uma nova guia ou janela)") ”.

## Cloudability adiciona suporte às recomendações de níveis do " Azure Blob Storage " – 11 de maio de 2026

Hoje, adicionamos suporte às recomendações de níveis d Azure Blob Storage. Cloudability Os usuários agora podem otimizar os custos de armazenamento d Azure, recebendo recomendações inteligentes para configurações de camadas de acesso no nível do contêiner, incluindo as opções Hot, Cool, Cold, Archive e Smart Tier.

Para cada contêiner, o Cloudability analisa o uso do armazenamento, os padrões de acesso e os custos operacionais para identificar configurações incorretas de camadas. As recomendações calculam os custos mensais totais em todos os planos disponíveis, incluindo taxas de exclusão antecipada e custos de recuperação, para sugerir a configuração ideal que minimize os custos sem comprometer os requisitos de desempenho.

Essas recomendações seguem o mesmo formato das recomendações de otimização de camadas já existentes em AWS S3 e Google Cloud Storage e podem ser visualizadas na página Rightsizing Explorer. O recurso oferece suporte tanto às transições tradicionais entre camadas quanto à otimização automática do Smart Tier d Azure, proporcionando flexibilidade para diferentes estratégias de gerenciamento de armazenamento.

Para obter mais informações, consulte [Azure Blob Storage rightsizing](../product/rightsizing-for-azure-blob-storage.html).

Nota:

Os clientes devem conceder permissões de " 'Microsoft.Storage/storageAccounts/read' " para que todos os elementos desse recurso funcionem conforme o esperado.

## Previsão aprimorada - 4 de maio de 2026

Lançamos a página **“Previsão Aprimorada”** – uma experiência nova e aprimorada de previsão em nuvem para o Cloudability.

A página "Previsão Aprimorada" representa uma grande atualização em relação à versão anterior do recurso de previsão, oferecendo as mesmas funcionalidades essenciais de previsão, mas com muito mais flexibilidade, transparência e controle. Os usuários podem escolher seus próprios fatores de previsão, analisar todos os detalhes das linhas de itens da previsão, aproveitar as vantagens de uma Previsão Inteligente mais precisa, comparar visualmente os resultados dos modelos e integrar as previsões aos fluxos de trabalho orçamentários.

**Funcionalidades novas e aprimoradas (em comparação com a página de previsão anterior)**

- Fatores de despesa selecionáveis pelo usuário – escolha suas próprias dimensões, em vez dos fatores fixos utilizados pela página de previsão antiga
- Detalhamento completo das linhas de previsão – analise todas as linhas de previsão, não apenas as 20 principais
- Maior precisão nas previsões – utiliza o Intelligent Forecast Engine para avaliar vários modelos e selecionar automaticamente o mais adequado, em vez de se basear em um único modelo fixo
- Comparação e controle interativos de modelos – analise os detalhes dos modelos, compare visualmente os resultados de modelos alternativos e aplique um modelo diferente quando necessário
- Análise detalhada no estilo Pivot – agrupe, resuma, classifique e filtre os detalhes das linhas de previsão diretamente na tabela

[Saiba mais sobre a Previsão Aprimorada](../product/efp-forecast.html)

## Registro e monitoramento no planejamento de cargas de trabalho - 29 de abril de 2026

Esta versão introduz suporte para serviços de registro e monitoramento no AWS, Azure e OCI. No caso do serviço " GCP ", o Planejamento de Carga de Trabalho atualmente oferece suporte apenas ao registro de logs. Isso é semelhante à forma como os usuários já podem criar orçamentos para serviços como máquinas virtuais e bancos de dados.

Os usuários podem selecionar o serviço adequado no menu suspenso “Tipo de serviço”: “Registro e monitoramento” para AWS, Azure e OCI, e “Registro” para GCP. Após inserir a capacidade necessária e, opcionalmente, definir sua configuração específica, o Planejamento de Carga de Trabalho gerará opções de preços adaptadas às suas necessidades.

## Mudança do nome do " Turbonomic " em FrontDoor para " Cloudability Premium - Workload Optimization" - 29 de abril de 2026

Cloudability Premium Os usuários notarão uma mudança no ambiente do FD, pois renomearemos o link “ Turbonomic ” para “**Cloudability Premium - Otimização de Cargas de Trabalho”.** Essa alteração foi feita para ajudar a evitar confusão quanto à propriedade do produto e, juntamente com essa mudança de link, também fizemos alterações na experiência da interface do usuário do Turbonomic Rightsizing Engine.

## Melhorias na experiência do usuário nos painéis do Cloudability - 28 de abril de 2026

Hoje, estamos lançando várias melhorias na experiência do usuário nos painéis do Cloudability, que tornam a visualização e a criação de painéis mais fáceis e intuitivas. A lista de melhorias inclui:

- **Manter a configuração dos filtros do widget** ao alternar entre tipos de widget. Ao alterar o tipo de widget (por exemplo, de um gráfico para uma tabela), a interface agora manterá a configuração dos filtros, de modo que não seja necessário recriá-la separadamente para cada tipo de widget.
- **A linha “Outros” nos widgets de tabela agora é exibida separadamente dos demais valores,** para diferenciá-la claramente dos resultados reais.
- **Agora, os filtros baseados em data podem ser configurados por meio de um calendário de fácil uso**. Com essa mudança, os usuários não precisarão mais digitar os valores dos filtros de formato de data. Em vez disso, os usuários poderão selecionar uma data usando um seletor de calendário integrado.
- **Copiar e colar filtros** da/para a área de transferência. Agora, os usuários poderão transferir facilmente uma configuração de filtros entre diferentes widgets e salvar um conjunto de filtros para reutilizá-lo posteriormente.
- **Exportar o gráfico como uma imagem.png.** Agora, os gráficos podem ser exportados e salvos como imagens no formato PNG.
- **Pesquisar e filtrar em um widget de tabela**. Agora, todos os widgets de tabela podem ser filtrados por meio de um único campo de pesquisa de texto, que se aplica a todas as colunas visíveis.
- **Exportar como PDF**. Agora, todo o painel pode ser exportado em formato PDF para facilitar a colaboração com outros usuários.

## Inscreva-se para receber relatórios com intervalo de datas de comparação - 28 de abril de 2026

Esta versão traz uma melhoria na funcionalidade de assinatura do Relatórios d Cloudability. Com essa mudança, os usuários poderão se inscrever para receber relatórios que utilizam a funcionalidade “Comparar datas”, da mesma forma que atualmente podem se inscrever para receber relatórios com uma única data.

## Cloudability O COIN Explorer do Painel de Otimização oferece suporte à formatação condicional - 20 de abril de 2026

Cloudability agora oferece suporte à formatação condicional no COIN Explorer, disponível no Painel de Otimização. Na seção de preferências de ajuste de tamanho, os usuários podem definir limites para a formatação condicional da pontuação COIN. As configurações incluem um limite verde/amarelo, bem como um limite amarelo/vermelho.

O COIN (Índice de Otimização de Custos) oferece uma métrica padronizada para que as organizações analisem oportunidades de otimização no contexto dos gastos nessa área de seus negócios, permitindo que saibam onde concentrar esforços e definir prioridades. Muitas organizações chegam ao ponto de tratá-lo como um ranking para comparar a eficiência das equipes em toda a organização.

Juntamente com este lançamento, foram feitas várias atualizações no painel de otimização relacionadas ao COIN e às economias alcançadas, a fim de melhorar a precisão.

## Executar ações geradas pelo mecanismo d Turbonomic e e gerenciar políticas a partir da interface do usuário d Cloudability e - 17 de abril de 2026

Cloudability agora oferece suporte para permitir a execução de ações de otimização geradas pelo mecanismo Turbonomic na interface do usuário Cloudability, além da capacidade de gerenciar as políticas que alimentam o mecanismo de otimização Turbonomic e definir políticas de automação a partir da interface do usuário Cloudability. Turbonomic As ações geradas pelo mecanismo de controle de carga de trabalho ( VM ), de disco e de carga de trabalho agora podem ser executadas na página "Rightsizing" > "Avançado" > "Detalhes da ação".

Esta versão permite que os usuários gerenciem grupos, programações, fluxos de trabalho e políticas de automação na página “Preferências de Rightsizing > Avançado” da interface do usuário do Cloudability. A partir desta versão, os usuários com as permissões adequadas podem gerenciar essas configurações pela interface do usuário do Cloudability.

Nota:

É importante garantir que todas as contas na nuvem tenham suas credenciais atualizadas, a fim de assegurar que o conjunto de permissões exigido pelo mecanismo do Turbonomic seja implementado, permitindo visualizar o conjunto completo de ações de otimização geradas e apresentadas na página Rightsizing > Avançado

## Suporte para as recomendações de níveis do Google Cloud Storage - 14 de abril de 2026

Cloudability agora oferece suporte às recomendações de camadas do Google Cloud Storage. Cloudability Os usuários agora podem otimizar os custos do GCS recebendo recomendações para configurações de classe de armazenamento no nível do bucket, incluindo as opções Standard, Nearline, Coldline, Archive e Autoclass. Para cada bucket, o serviço “ Cloudability ” analisa o uso do armazenamento, os padrões de acesso e os custos operacionais ao longo de um período mínimo de 30 dias para identificar configurações incorretas das classes de armazenamento.

Essas recomendações seguem o mesmo formato das recomendações existentes de otimização de camadas do AWS S3 e estarão visíveis na página Rightsizing Explorer. Os clientes que tenham o Faturamento por Nível de Recurso ativado para o serviço " GCP " passarão automaticamente a receber essas recomendações.

Nota:

Os clientes devem conceder permissões de " storage.buckets.list " para que todos os elementos desse recurso funcionem conforme o esperado.

## GCP O ajuste de recursos de computação agora inclui custos de licença - 14 de abril de 2026

Cloudability aprimorou as recomendações de otimização de recursos de computação do GCP para incluir os custos de licenças de sistema operacional e de software nos cálculos de economia. Cloudability Os usuários agora podem receber recomendações de ajuste de recursos mais precisas, que levam em conta o custo total de operação de instâncias d GCP, incluindo licenças do Windows Server, do SQL Server, do Red Hat Enterprise Linux, do SUSE, do Linux Enterprise e do Ubuntu Pro.

Anteriormente, as recomendações de ajuste de recursos do GCP levavam em conta apenas os custos de computação (CPU, memória e armazenamento), o que poderia resultar em estimativas de economia incompletas para instâncias que executavam sistemas operacionais ou softwares licenciados. Com essa melhoria, as recomendações agora calculam tanto os custos de computação quanto os de licença para as instâncias de origem e os destinos recomendados, garantindo que os requisitos de licença e o número mínimo de núcleos sejam respeitados ao sugerir tipos de instância alternativos.

Essas recomendações aprimoradas estarão visíveis na página do Rightsizing Explorer e manterão o mesmo formato das recomendações de computação existentes no GCP. Os clientes com instâncias do ` GCP ` que executam sistemas operacionais licenciados verão automaticamente estimativas de economia mais precisas, que refletem o custo total de propriedade.

## Melhorias nas permissões de visualização exclusiva dos mapas de negócios - 14 de abril de 2026

Lançamos uma melhoria nas permissões de apenas visualização na área de Mapeamentos de Negócios. Com essa mudança, os usuários com acesso somente para visualização não verão mais os botões de ação (Editar, Excluir, Criar, etc.) em dimensões de negócios, dimensões hierárquicas e métricas de negócios. Além disso, unificamos a experiência de visualização em todas as áreas do Business Mappings. Os usuários com permissão apenas para visualização agora podem acessar de forma consistente os detalhes em dimensões de negócios, dimensões hierárquicas e métricas de negócios.

## Possibilidade de renomear a dimensão de negócios hierárquica - 9 de abril de 2026

Lançamos a funcionalidade que permite renomear dimensões de negócios hierárquicas nos mapeamentos de negócios. Com essa mudança, os usuários agora podem editar o nome de suas dimensões hierárquicas de negócios diretamente na interface, o que oferece maior flexibilidade na organização de suas estruturas.

## Cloudability A Rightsizing estabelece limites de economia para o programa “ Block Storage ” - 7 de abril de 2026

Cloudability O Rightsizing adicionou suporte a uma funcionalidade ampliada nas preferências do Rightsizing para fornecer um valor mínimo de economia para o " Block Storage " dentro das "Recomendações Básicas" do " Cloudability ". Esse limite (definido para recomendações de 30 dias e rateado para recomendações de 10 dias) permite que as organizações definam o valor mínimo de economia para suas recomendações de armazenamento em bloco ( AWS EBS, Azure Disk e GCP Persistent Disk) e filtrem todas as recomendações que não atendam a esse limite.

Esta versão permite que as organizações se concentrem nas recomendações mais impactantes, de forma semelhante à funcionalidade existente que foi criada para as recomendações de ajuste de recursos de computação

## Cloudability Suporte à governança para o servidor d GitHub Enterprise - 7 de abril de 2026

A adição do suporte **ao servidor** GitHub Enterprise amplia a governança do Cloudability para ambientes auto-hospedados e altamente regulamentados, permitindo que as empresas incorporem **as verificações de políticas**, **estimativas de custos** e **recomendações** do FinOps diretamente em seus fluxos de trabalho existentes do GitHub-based no local. Essa melhoria permite que as equipes de plataforma e de desenvolvimento de software ( FinOps ) apliquem as mesmas medidas de segurança e fluxos de trabalho de aprovação que utilizam no GitHub.com aos repositórios hospedados em sua própria infraestrutura, alinhando os controles de custo e conformidade com as estruturas de governança existentes para o **GitHub Enterprise**.

## Novas permissões do serviço “ Turbonomic ” para AWS e Azure – 6 de abril de 2026

Esta versão introduz novas permissões Turbonomic em Cloudability Premium e faz parte da atualização trimestral de permissões.

Consulte [a seção de referência sobre permissões](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=azure-permissions-reference-microsoft "(Abre em uma nova guia ou janela)") de visita para saber mais.

Observação: essas permissões são de natureza adicional e não afetam o funcionamento das contas e permissões credenciadas existentes. No entanto, será necessário renovar as credenciais para adicionar essas novas permissões

## Cloudability x Integração do CMDB da ServiceNow com o Business Dimensions - 1º de abril de 2026

Hoje, estamos lançando **a integração do CMDB** do Cloudability com o ServiceNow para o Business Dimensions.

A integração CMDB do Cloudability com o ServiceNow permite a sincronização automatizada entre o CMDB do ServiceNow e os mapeamentos de negócios do IBM Cloudability, possibilitando que as organizações utilizem o ServiceNow como fonte única de verdade para a estrutura de negócios e a lógica de alocação de custos no Cloudability.

Essa integração elimina a necessidade de atualizações manuais ou por API nos mapeamentos de negócios do Cloudability, refletindo automaticamente as alterações do CMDB do ServiceNow no Cloudability. A integração só pode ser instalada em versões certificadas do ServiceNow; versões não compatíveis impedirão totalmente a instalação.

**Principais destaques:**

- **Mapeamento automatizado de negócios:** Os mapeamentos de negócios no Cloudability são criados e mantidos automaticamente com base nos dados do CMDB d ServiceNow.
- **Governança centralizada:** O CMDB da ServiceNow atua como fonte oficial dos dados organizacionais, de aplicativos e de centros de custo utilizados para a alocação de custos na nuvem.
- **Sincronização quase em tempo real:** as atualizações no CMDB do ServiceNow são refletidas automaticamente no Cloudability sem intervenção manual.
- **Aplicativo nativo da ServiceNow :** A integração é fornecida como um aplicativo certificado disponível na ServiceNow Store.

ServiceNow A integração está disponível na loja “ ServiceNow ” no link a seguir: [https://store.servicenow.com/store/app/c3864d3d4784fe1482f632c4f16d43c8](https://store.servicenow.com/store/app/c3864d3d4784fe1482f632c4f16d43c8 "(Abre em uma nova guia ou janela)")

## Credenciais de fornecedores - Possibilidade de arquivar contas sem credenciais - 1º de abril de 2026

Esta versão introduz a possibilidade de arquivar **contas sem credenciais** diretamente na tela "**Credenciais de fornecedores** ".

Anteriormente, as contas sem credenciais precisavam ser credenciadas antes de poderem ser arquivadas. Com esta atualização, as contas que se encontram sem credenciais agora podem ser arquivadas diretamente usando o **menu** **de reticências (** **⋯)**, eliminando a necessidade de credenciamento.

Agora, as ações gerais de arquivamento estão disponíveis diretamente na tela "Credenciais do fornecedor" para todas as contas, independentemente do status.

## Detecção de anomalias - Feedback sobre anomalias - 30 de março de 2026

Lançamos **o Anomaly Feedback.** A partir de hoje, você pode enviar um feedback rápido sobre as anomalias detectadas usando simplesmente um **“curtir” ou um “não curtir** ”. Isso nos ajuda a entender se as anomalias sinalizadas são realmente úteis. Anteriormente, não havia uma forma direta ou estruturada de compartilhar feedback, o que limitava nossa capacidade de aprimorar a qualidade da detecção com base nas contribuições reais dos usuários.

## Importação em massa no WLP - 30 de março de 2026

Esta versão apresenta uma melhoria significativa no recurso de importação em massa do Planejamento de Carga de Trabalho (WLP). Isso permite que os clientes enviem um arquivo estruturado com até 500 recursos em uma única operação, abrangendo todos os tipos de serviço, regiões e provedores de serviços em nuvem.

Esse recurso ajuda os clientes a planejar cargas de trabalho com mais eficiência, eliminando a necessidade de adicionar recursos manualmente ou em pequenos lotes. Agora, os usuários podem importar até 500 recursos de uma só vez, receber recomendações instantaneamente e acelerar seu processo de planejamento de nuvem.

## Credenciais de fornecedores - Melhorias na experiência do usuário do painel de detalhes - 24 de março de 2026

Esta versão traz várias melhorias de usabilidade ao painel de detalhes **“Credenciais do fornecedor – Permissões”**, facilitando aos administradores a revisão e o gerenciamento de permissões em grande escala.

- As permissões estão agora **melhor organizadas em seções claramente definidas**, o que melhora a legibilidade e ajuda os usuários a compreender rapidamente como as permissões de cada recurso estão agrupadas.
- Para simplificar ainda mais a análise de permissões, adicionamos **filtros rápidos** que permitem aos administradores alternar instantaneamente entre permissões **ativadas** e **desativadas** — facilitando muito a identificação do que não está ativado.
- Também foi introduzida **uma** nova barra de pesquisa, que permite realizar pesquisas rápidas nas seções de permissões e recursos, o que é especialmente útil ao trabalhar com um grande conjunto de permissões.
- Por fim, os administradores agora podem **baixar o status das permissões no nível da conta**, o que permite a análise offline e facilita as auditorias ao gerenciar configurações complexas de permissões.

## Exportar o status das contas nas credenciais de fornecedores - 19 de março de 2026

Esta versão adiciona suporte para exportar o status das credenciais do fornecedor em formato CSV. Esse recurso ajuda nossos clientes a verificar rapidamente o status das contas quando há um grande número delas.

Cada uma das fontes de dados autenticadas com status de conta pode ser exportada no formato CSV. Cada fonte de dados terá sua própria exportação.

A exportação contém os detalhes exibidos na página principal de credenciais do fornecedor para cada conta.

## Snowflake Informações sobre custos de armazém e suporte a etiquetas - 19 de março de 2026

Cloudability agora oferece maior visibilidade dos custos **do serviço de computação em nuvem** ( Snowflake ) com **detalhes por armazém**, incluindo custos de serviços de computação e de nuvem, além de **tags por conta e por armazém** para melhorar a precisão da alocação e dos relatórios. Essas melhorias permitem que as equipes de plataforma de dados e de engenharia d FinOps, em a entender os gastos com o Snowflake a em um nível muito mais detalhado.

Com esta atualização, as equipes podem atribuir custos com maior precisão e identificar os principais fatores de custo usando os painéis e as dimensões de negócios do Cloudability. Anteriormente, o Cloudability oferecia visibilidade apenas no nível do serviço, o que significava que os clientes não podiam ver o custo de armazéns específicos nem utilizar as etiquetas d Snowflake para a alocação de custos. Cloudability agora oferece insights mais detalhados diretamente nos fluxos de trabalho existentes, permitindo uma gestão de custos mais eficaz e uma tomada de decisão mais fundamentada.

**Como funciona?**

- **Para clientes que já têm acesso a essa funcionalidade:** não é necessário realizar nenhuma ação.
- **Para clientes que já utilizam credenciais do Snowflake no Cloudability :**
- As organizações que ainda não renovaram sua certificação deverão fazê-lo para ativar essas melhorias. O processo continua o mesmo: basta seguir as etapas descritas em nossa [Central de Ajuda](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-standard/saas?topic=cloudability-connect-snowflake "(Abre em uma nova guia ou janela)") e executar o modelo atualizado fornecido na interface do usuário.
- **Para clientes que ainda não conhecem o site Snowflake em Cloudability :**
- Conclua o processo padrão de credenciamento descrito no [Connect Snowflake](../admin/connect-snowflake.html)

Observação: informações adicionais sobre os pré-requisitos para o suporte a tags estão disponíveis nas instruções do Connect Snowflake.

## Relatórios salvos do Inventário de Recursos: Melhoria no tratamento do intervalo de datas - 17 de março de 2026

Anteriormente, ao abrir um relatório salvo do Inventário de Recursos (RIS) com um intervalo de datas não contínuo e que excedesse o período de três meses permitido, o relatório não era carregado e exibia uma mensagem de erro.

Com esta atualização, esses relatórios são carregados com sucesso, em vez de apresentarem falhas. Se o intervalo de datas salvo exceder o limite permitido, o Cloudability o reajusta automaticamente para o intervalo padrão de 7 dias e exibe uma notificação em destaque informando aos usuários que o intervalo de datas foi ajustado.

Essa melhoria garante que os relatórios salvos continuem acessíveis mesmo quando os intervalos de datas armazenados ultrapassarem o limite permitido.

## Painéis 2.0 - 16 de março de 2026

Hoje, estamos lançando **o Dashboards 2.0** — uma grande reformulação da interface do usuário de toda a experiência do Dashboards em Cloudability. Esta atualização tem como objetivo modernizar a tecnologia utilizada nos painéis, disponibilizar novas funcionalidades nos painéis e acelerar o desenvolvimento de recursos futuros. Os painéis 2.0 resolvem várias questões de usabilidade e otimizam o design geral da estrutura dos painéis.

**O que esperar?**

- Não há diferenças funcionais entre o Dashboards 2.0 e a versão anterior do Dashboards. Todas as funcionalidades permanecerão as mesmas.
- Haverá pequenas diferenças visuais que não afetam o funcionamento do produto.

**O recurso "Painéis" v2 já está disponível em todas as regiões.**

## Suporte para OCI no Inventário de Recursos - 16 de março de 2026

Temos o prazer de anunciar o suporte à **Infraestrutura em Nuvem d Oracle (OCI)** no recurso Inventário de Recursos. Com esta versão, agora você pode visualizar dados de custo, utilização e metadados no nível dos recursos para os serviços OCI Compute (Máquina Virtual) na mesma interface unificada que você já utiliza para outros provedores de hiperescala.

O suporte ao serviço OCI Compute inclui todos os recursos atualmente disponíveis no Inventário de Recursos. Para ativar esse recurso na sua organização do Cloudability, entre em contato com seu TAM, CSM ou representante de conta do Apptio. Dentro de 3 a 4 dias úteis após a ativação, os dados completos do inventário da OCI para recursos de computação estarão disponíveis em Cloudability.

Para obter mais detalhes, consulte [o Inventário de Recursos da OCI](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-standard/saas?topic=inventory-oci-resource "(Abre em uma nova guia ou janela)").

## Cloudability Adiciona suporte para relatórios dinâmicos do COIN - 6 de março de 2026

Cloudability Adicionou uma nova guia ao Painel de Otimização, permitindo que os usuários relatem oportunidades de otimização de recursos e contextualizem essas oportunidades com os gastos subjacentes na forma de uma Pontuação COIN (Índice de Otimização de Custos).

As pontuações COIN podem ser utilizadas para compreender melhor e contextualizar oportunidades, bem como para normalizar oportunidades de otimização entre diferentes equipes e organizações, servindo como um quadro de líderes ou uma forma de medir a eficiência. No recém-lançado COIN Explorer, os usuários podem adicionar ou remover campos para entender as pontuações COIN na granularidade desejada, bem como exportar esses dados conforme necessário.

As organizações podem escolher se desejam utilizar seu conjunto de recomendações básicas ou avançadas para preencher o painel de otimização, incluindo o COIN Explorer.

## Cloudability O Rightsizing adiciona suporte para a métrica de bytes de memória disponíveis do Azure – 4 de março de 2026

Hoje, disponibilizamos métricas de memória aprimoradas para recomendações de redimensionamento de computação do Azure. Cloudability agora utiliza [a métrica padrão de Bytes de Memória Disponível do Azure](https://learn.microsoft.com/en-us/azure/azure-monitor/essentials/metrics-supported#microsoftcomputevirtualmachines "(Abre em uma nova guia ou janela)") como alternativa quando os dados personalizados de utilização de memória não estão disponíveis. Essa melhoria garante que mais instâncias do Azure recebam recomendações abrangentes de redimensionamento sem exigir que os clientes configurem métricas personalizadas.

Anteriormente, instâncias do Azure sem métricas de memória personalizadas não podiam receber recomendações de redimensionamento baseadas na memória, limitando as oportunidades de otimização. Com esta versão, o Cloudability calcula automaticamente a utilização da memória a partir da métrica de bytes de memória disponível integrada no Azure, ampliando a cobertura das recomendações de redimensionamento em todos os seus recursos de computação do Azure.

Essa melhoria pode resultar em recomendações atualizadas e estimativas de economia para instâncias do Azure que anteriormente não possuíam dados de memória. Não é necessária nenhuma ação por parte dos clientes — a melhoria se aplica automaticamente a todas as recomendações de computação do Azure. Os clientes que já possuem métricas de memória personalizadas configuradas não verão nenhuma alteração em suas recomendações.

Para obter mais informações, consulte a [documentação de ajuda sobre recomendações de ajuste de capacidade](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=recommendations-rightsizing "(Abre em uma nova guia ou janela)").

## Cloudability Compromissos adicionam suporte para Instâncias Reservadas do Azure App Service – 23 de fevereiro de 2026

Hoje, disponibilizamos suporte para [Instâncias Reservadas App Service Azure](https://learn.microsoft.com/en-us/azure/cost-management-billing/reservations/prepay-app-service "(Abre em uma nova guia ou janela)"). O [décimo segundo](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=discount-commitment-types-in-cloudability "(Abre em uma nova guia ou janela)") tipo de compromisso do Azure suportado, Azure App Service, o “Reserved Stances”, oferece um desconto em recursos de computação em troca de um compromisso de um ou três anos com o uso por hora. Esse tipo de compromisso é classificado como compromisso baseado em recursos e, como tal, requer a seleção de parâmetros de uso específicos: nível, instância e região. Com esta versão, oferecemos suporte a esse tipo de compromisso no portfólio de compromissos e nas recomendações.

Para obter mais informações, visite a documentação de ajuda do gerenciamento de compromissos.

## Recomendações avançadas suportadas no Painel de Otimização – 23 de fevereiro de 2026

Cloudability Premium introduziu o suporte para Recomendações Avançadas (desenvolvido pela Turbonomic ) no Painel de Otimização. Agora, os usuários que utilizam as Recomendações Avançadas e aproveitam o poder e a flexibilidade das políticas personalizáveis podem ver essas ações recomendadas nos campos de relatórios do painel de otimização e nos cálculos COIN.

Os usuários podem selecionar na página Preferências de dimensionamento > Painel para mostrar recomendações básicas ou avançadas.

## Nomes de mapeamento de negócios fáceis de usar em exportações de dados - 19 de fevereiro de 2026

Com esta versão, os Painéis e Relatórios do Cloudability lançaram uma nova funcionalidade que irá retornar os nomes intuitivos das Métricas de Negócio, Dimensões de Negócio, Grupos de Contas e Etiquetas e Rótulos ao exportar dados do CSV a partir de um Relatório, Painel ou Exploração. Anteriormente, as métricas e dimensões de negócios eram exportadas usando um ID de coluna (por exemplo, “ category12 ”), em vez do rótulo fácil de usar. O comportamento **padrão** das exportações baseadas em API **NÃO será alterado**. No entanto, os usuários poderão adicionar uma opção "useDimensionNames=true" na solicitação para ativar esse recurso ao usar a API. As integrações API existentes NÃO serão afetadas, e os usuários poderão usar os nomes fáceis de usar dos Mapeamentos de Negócios, se desejarem, adicionando o sinalizador às suas solicitações API.

## Cloudability Alertas de anomalias ignorados - 19 de fevereiro de 2026

Hoje lançamos os Alertas de Ignorar Anomalias. A partir de hoje, os usuários podem ignorar temporariamente os alertas de anomalia diretamente na página de configuração de alertas para reduzir o ruído durante eventos de custo esperados e garantir que apenas alertas significativos e acionáveis sejam exibidos.

Os principais recursos incluem:

1. Ignorar alertas no nível de alerta de anomalia individual
2. Suporte à funcionalidade de ignorar alertas compartilhados
3. Selecione a duração predefinida para ignorar (7, 14 ou 30 dias)
4. Defina um intervalo de datas personalizado para ignorar alertas.
5. Edite a duração da ignorar (aumente ou diminua conforme necessário)
6. Agendar ignorar para um período futuro
7. Ignore alertas em massa usando a opção Ignorar alertas de anomalia em massa
8. Retomar automaticamente os alertas assim que o período de ignorar terminar

## Cloudability Compromissos Anuncia Apoio ao Novo Programa CUD de Gastos do GCP – 16 de fevereiro de 2026

Hoje, a IBM Cloudability anuncia o apoio ao novo programa CUD da GCP.

*Segundo plano*

No início de 2025, a GCP anunciou mudanças significativas na forma como seus compromissos baseados em gastos seriam faturados, [afetando 13 dos seus 17 tipos de compromisso](https://docs.cloud.google.com/docs/cuds-multiprice#affected-cuds "(Abre em uma nova guia ou janela)").

Em 15 de julho de 2025, GCP possibilitou a migração antecipada para o novo programa CUDs baseado em gastos. Entre julho de 2025 e o início de fevereiro de 2026, os usuários poderão optar voluntariamente pelo novo modelo de cobrança. Durante a primeira semana de fevereiro, a GCP iniciou a migração forçada dos clientes, concluindo o processo na sexta-feira, 6 de fevereiro. Uma breve visão geral do programa está disponível aqui: [*Faturamento mais simples, economia mais clara: um guia da FinOps sobre os CUDs atualizados com base nos gastos*](https://cloud.google.com/blog/topics/cost-management/a-finops-professionals-guide-to-updated-spend-based-cuds "(Abre em uma nova guia ou janela)").

Tínhamos recomendado que os usuários adiassem a migração, pois se tratava de uma mudança significativa nos relatórios, no portfólio de compromissos e nas recomendações de compromissos.

*Suporte para o novo paradigma de faturamento*

Com este anúncio, o novo paradigma de faturamento agora é compatível com as funcionalidades de relatórios e compromissos. A carteira de compromissos e as recomendações foram restauradas para quase a paridade com o modelo de faturamento anterior. Para relatórios, oferecemos uma experiência aprimorada em comparação com o que existia anteriormente.

Em um nível elevado, os relatórios sobre custos e desperdícios de compromissos são agora mais diretos e seguem o paradigma já estabelecido para AWS e Azure. Além disso, agora podemos relatar esses dados por nível de CUD. No paradigma anterior, isso não era possível e representava um ponto fraco comum para usuários que buscavam aplicar uma lógica granular de chargeback ou showback.

Essas alterações estão em produção para todos os usuários. Para usuários que migraram voluntariamente antes da migração forçada em fevereiro, pode ser necessário recuperar os dados do mês anterior. Para obter mais informações, consulte [o Guia Complementar para GCP CUD](../product/supplemental_guide_to_gcp_s_spend_cud_program.html)

## Cloudability Suporte para a Fundiçã Azure (Atualização da marca) – 13 de fevereiro de 2026

Com esta versão, atualizamos a dimensão Nome do serviço em Cloudability para nos alinharmos com a mudança de marca da Microsoft de Azure Cognitive Services para Azure Foundry.

O nome de serviço existente “Serviços Cognitivos Azure ” será agora representado por dois nomes de serviço distintos:

Tabela 1. O que está mudando

| Antes | Depois |
| --- | --- |
| Azure Serviços cognitivos | Azure Modelos de fundição Azure |
|  | Azure Ferramentas para fundição |

Essa mudança reflete a nova estrutura da marca Foundry da Microsoft, que separa:

- **Modelos Foundry** – Mecanismos de inferência central ( Azure OpenAI, Phi, DeepSeek, Llama)
- **Ferramentas de fundição** – Recursos de IA pré-construídos (fala, linguagem, inteligência de documentos)

**Impacto**

- Todos os novos dados refletirão automaticamente os nomes de serviço atualizados
- Os dados históricos refletirão os novos nomes após o reprocessamento

## Visualizar visibilidade de atribuições para grupos de usuários e IDs Entra – 11 de fevereiro de 2026

Melhoramos o gerenciamento de grupos adicionando visibilidade sobre onde **os Grupos de Usuários e os Grupos de IDs Entra** são usados nas Visualizações. Anteriormente, se um grupo fosse usado na atribuição de visualizações, o sistema bloqueava sua exclusão e os administradores não tinham uma maneira fácil de identificar quais visualizações estavam usando o grupo. Isso muitas vezes exigia a verificação manual de várias visualizações.

Com essa melhoria, os administradores agora podem ver uma **lista somente leitura de todas as Visualizações** nas quais um grupo está atribuído, diretamente da página de definição do Grupo de usuários ou Grupo de IDs do Entra. A lista exibe os nomes das exibições e indica claramente quando um grupo não é usado em nenhuma exibição, ajudando a otimizar a limpeza do grupo e reduzir o esforço manual.

Para obter mais informações, consulte a documentação de ajuda [“Gerenciar grupos de usuários”](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=groups-manage-user "(Abre em uma nova guia ou janela)") e “[Gerenciar grupos do Entra ID](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=groups-manage-entra-id "(Abre em uma nova guia ou janela)") ”.

## Agendamento de sincronização automática para grupos Entra ID – 5 de fevereiro de 2026

Hoje, adicionamos **o agendamento de sincronização automática para grupos Entra ID** para melhorar a usabilidade e reduzir o esforço administrativo. Anteriormente, os administradores do Cloudability precisavam sincronizar manualmente os grupos Entra ID usando a ação “Sincronizar grupo Entra ID”, o que podia resultar em atualizações perdidas, já que as associações aos grupos Entra ID mudam com frequência.

Com essa melhoria, os administradores do Cloudability agora podem configurar **uma programação de sincronização automática diária, semanal ou mensal** usando critérios de filtro definidos. Os grupos Entra ID são sincronizados automaticamente com base na programação e nos critérios selecionados, garantindo que o Cloudability permaneça consistentemente alinhado com o Entra ID, sem intervenção manual.

Para obter mais informações, acesse a documentação de ajuda [sobre como gerenciar grupos do Entra ID](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=groups-manage-entra-id "(Abre em uma nova guia ou janela)").

## Cloudability O Painel de Otimização adiciona uma base de custo efetiva para recomendações de recursos - 2 de fevereiro de 2026

Hoje, o Cloudability adicionou a base de custo efetivo como uma opção para as recomendações exibidas no Painel de Otimização (Beta). A base de custo efetivo permite um cálculo mais significativo do COIN, comparando o custo amortizado dos serviços com a economia de custos efetiva calculada pelas recomendações de redimensionamento d Cloudability. Essa preferência pode ser encontrada na seção Preferências de redimensionamento > Painel, juntamente com outras preferências e configurações que afetam o Painel de otimização.

## Cloudability Atualização dos compromissos relativos ao próximo suporte para o novo programa Spend CUD da GCP - 30 de janeiro de 2026

[No dia 16 de janeiro, divulgamos um comunicado inicial](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=cloudability-whats-new-in-essentials#topic__commitment-gcp-cud-cldy-essentials "(Abre em uma nova guia ou janela)") sobre a migração obrigatória d GCP para o Novo Programa de CUD de Despesas. As informações a seguir são uma atualização do que podemos compartilhar neste momento.

**Quando será a migração?**

- Caso você não tenha migrado voluntariamente, a GCP migrará seus clientes para o novo modelo de cobrança na próxima semana: de 2 a 5 de fevereiro de 2026.

**Quando o Cloudability oferecerá suporte ao novo programa?**

- Planejamos lançar suporte iterativo à medida que ganharmos confiança em nosso lançamento. Cloudability Os relatórios, a carteira de compromissos e as recomendações de compromissos provavelmente serão divulgados de forma gradual.
- Esperamos lançar o suporte durante a semana de 9 a 13 de fevereiro de 2026. Esperamos que os clientes possam contar com todas as funcionalidades a partir de segunda-feira, 16 de fevereiro.
- Não é necessária nenhuma ação da sua parte — esperamos oferecer suporte ao novo programa automaticamente quando a migração ocorrer.

**O que preciso fazer?**

- Para os clientes que já migraram, precisamos recuperar os dados desde o mês em que você optou voluntariamente pelo novo programa. Solicitamos que você entre em contato com suas equipes de conta para fornecer os dados desse mês, a fim de nos preparar para o lançamento do nosso backend.
- Para os clientes que passarão pela migração obrigatória na próxima semana, talvez seja necessário recuperar os dados de fevereiro para ter o histórico completo. Forneceremos uma atualização na próxima semana.
- Observe que, para ambas as coortes, daremos suporte ao novo programa após o lançamento de nossa infraestrutura. Essa nova busca é um requisito único e só é necessária para os meses entre o lançamento do suporte de back-end e a ocorrência da migração.

Continuaremos a comunicar o progresso por meio deste centro de ajuda e notificações no aplicativo. Para quaisquer outras dúvidas ou questões, entre em contato com sua equipe de contas.

## Compromisso de suporte para Azure Banco de dados para MySQL Capacidade reservada – 23 de janeiro de 2026

Hoje, disponibilizamos suporte para [a Capacidade Reservada do Banco de Dados Azure para MySQL](https://learn.microsoft.com/en-us/azure/cost-management-billing/reservations/understand-reservation-charges-mysql "(Abre em uma nova guia ou janela)"). O [décimo primeiro](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=discount-commitment-types-in-cloudability "(Abre em uma nova guia ou janela)") tipo de compromisso do Azure suportado, o Azure Database para compromissos do MySQL, oferece um desconto em recursos de computação em troca de um compromisso de um ou três anos com o uso por hora. Esse tipo de compromisso é categorizado como compromissos baseados em recursos e, como tal, requer parâmetros de uso específicos de seleção: Opção de implantação, Instância e Região. Com esta versão, oferecemos suporte a esse tipo de compromisso no portfólio de compromissos e nas recomendações.

Para obter mais informações, visite a documentação de ajuda do gerenciamento de compromissos.

## Cloudability Suporte ao redimensionamento para conjuntos de escalonamento de máquinas virtuais do Azure - 22 de janeiro de 2026

Cloudability adicionou suporte para conjuntos de escalonamento de máquinas virtuais do Azure no Rightsizing. Cloudability Os usuários agora podem receber recomendações para ajustar seu comportamento de dimensionamento, modificando os tipos de instâncias usadas no ScaleSet para obter um melhor resultado de custo sem afetar o desempenho do aplicativo.

Os clientes podem precisar atualizar suas permissões para aproveitar esta versão, incluindo a permissão de gerenciamento:Reader ou as três permissões a seguir:

1. Microsoft.Compute/virtualMachineScaleSets/read
2. Microsoft.Compute/virtualMachineScaleSets/virtualMachines/read
3. Microsoft.Compute/virtualMachineScaleSets/extensions/read

Antes desta versão, os usuários com recomendações de computação d Azure s podem ter visto recomendações de instâncias individuais para instâncias que faziam parte de conjuntos de escala. Essas instâncias agora serão tratadas como parte do conjunto de escala, em vez de individualmente, portanto, alguns clientes poderão ver suas recomendações para instâncias de computação do Azure mudarem com esta versão, a fim de evitar contagem dupla.

Essas recomendações também ficarão visíveis na página Rightsizing Explorer e podem ser vinculadas a tickets de ROI de redimensionamento, assim como outros tipos de recomendações.

## Contêineres avançados com tecnologia Kubecost – 22 de janeiro de 2026

O Advanced Containers powered by Kubecost é um complemento pago para o Cloudability que fornece acesso ao conjunto completo de recursos do Kubecost diretamente na experiência do Cloudability.

O Advanced Containers amplia os insights existentes sobre contêineres do Cloudability com recursos avançados de visibilidade, otimização e automação de custos do Kubernetes.

Com os Contêineres Avançados, você pode:

- Acesse todo o poder do Kubecost, incluindo a alocação granular de custos do Kubernetes até o nível de pod e contêiner.
- Monitore e otimize as cargas de trabalho da GPU, incluindo visibilidade dos custos da GPU e insights sobre o dimensionamento adequado.
- Habilite a otimização automatizada do E Kubernetes, incluindo o redimensionamento prático e automatizado da CPU e da memória.
- Veja os custos em tempo real do Kubernetes, em vez de gastos com contêineres atrasados ou processados em lote.
- Monitore e aloque custos para clusters locais do Kubernetes, além de ambientes hospedados na nuvem.

O Advanced Containers está disponível como um complemento pago para o Cloudability e requer a implantação do agente Kubecost nos clusters Kubernetes monitorados.

Para obter instruções de configuração e detalhes adicionais, consulte a documentação do Cloudability Advanced Containers.

## AWS - Suporte para o formato CUR ( 2.0 ) Parquet – 20 de janeiro de 2026

Esta versão adiciona suporte para AWS CUR 2.0 no formato parquet, o que ajudará os clientes a configurar qualquer um dos seguintes AWS CUR 2.0 formatos de arquivo e compactação, dando-lhes mais flexibilidade na escolha dos formatos de compactação

• Texto/csv – gzip

• Parquet - parquet

## Novas permissões de Turbonomic para AWS, Azure e GCP – 19 de janeiro de 2026

Esta versão introduz novas permissões Turbonomic em Cloudability Premium e faz parte da atualização trimestral de permissões.

Consulte [a seção de referência sobre permissões](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=azure-permissions-reference-microsoft "(Abre em uma nova guia ou janela)") de visita para saber mais.

Observação: essas permissões são de natureza adicional e não afetam o funcionamento das contas e permissões credenciadas existentes. No entanto, será necessário renovar as credenciais para adicionar essas novas permissões

## Cloudability A Commitments anuncia o próximo suporte para o novo programa Spend CUD da GCP - 16 de janeiro de 2026

Google Cloud Platform ( GCP ) alterou a data obrigatória de migração para o [Novo Programa CUD de Despesas,](https://docs.cloud.google.com/docs/cuds-multiprice#how-to-opt-in "(Abre em uma nova guia ou janela)") passando do dia 26 de janeiro para um período de vários dias: de 2 a 5 de fevereiro de 2026.

*O que posso esperar durante a migração?*

- Durante o dia da migração, GCP informou que os usuários não poderão adquirir novos CUDs por um curto período, enquanto a migração para o novo programa de faturamento é concluída.
- Quando Cloudability começar a oferecer suporte ao programa Spend CUD, será necessário pelo menos um dia, mas não mais do que 48 horas para que nossos sistemas sejam atualizados.
- Não é necessária nenhuma ação da sua parte — esperamos oferecer suporte ao novo programa automaticamente quando a sua migração ocorrer

*Como posso saber a data da minha migração?*

GCP enviou um Anúncio de Serviço Obrigatório (MSA) em 11 de dezembro de 2025 com sua data de migração específica. Você também pode encontrar essa data na página Visão geral do faturamento no Console do GCP. Observe que Cloudability não tem acesso às datas de migração individuais dos clientes.

*Você já migrou para o novo programa Spend CUD?*   
 Se você optou pelo novo programa Spend CUD antecipadamente, pedimos desculpas pela demora no suporte. A funcionalidade completa será restaurada quando a janela de migração formal começar no início de fevereiro. Para quaisquer outras dúvidas ou questões, entre em contato com sua equipe de contas.

## Cloudability A governança está agora disponível para o público em geral – 15 de janeiro de 2026

Esse novo recurso traz insights proativos sobre custos e aplicação de políticas diretamente para o fluxo de trabalho de engenharia, garantindo que as mudanças na infraestrutura sejam econômicas e estejam em conformidade *antes* de serem implementadas.

Cloudability A governança agora está disponível **para engenheiros** do DevOps, **administradores de plataforma** e **equipes** de FinOps que gerenciam **recursos** do AWS e **us** am o Terraform — seja **por** meio do Terraform Community, **HCP Terraform** ou **Terraform Enterprise —** para sua solução de infraestrutura como código. Esse recurso foi projetado para equipes que hospedam seus repositórios de código **no** GitHub.com, incluindo o **GitHub Enterprise Cloud**.

Anteriormente, as práticas do FinOps eram frequentemente introduzidas tarde demais no ciclo de vida do desenvolvimento, levando a um desalinhamento entre Finanças e Engenharia. Esse atraso exigiu um retrabalho dispendioso, pois as equipes dependiam de revisões manuais ou auditorias pós-implantação para detectar ineficiências de custo e violações de políticas, resultando em gastos excessivos, riscos de conformidade e tarefas de correção inesperadas para os engenheiros.

Cloudability A governança se integra ao GitHub e ao Terraform para trazer a aplicação da política FinOps e a visibilidade dos custos para o pipeline de CI/CD. Os principais recursos incluem:

- **Estimativa de custos pré-implantação** : estimativas de custos em tempo real do AWS, incluindo preços personalizados e descontos EA, diretamente nos fluxos de trabalho do GitHub e do Terraform.

- **Obtenha uma seleção de recursos com custo otimizado** : recomendações para alternativas mais econômicas de EC2 e RDS com configurações semelhantes.

- **Aplicação de políticas em nível d IaC** : aplique tags obrigatórias, bloqueie recursos legados e defina limites de orçamento.

- **Monitoramento de conformidade** : painel centralizado para acompanhar a adesão às políticas de FinOps.

- **Gerenciamento de RP** : identifique e analise solicitações de pull não conformes com fluxos de trabalho de aprovação integrados.

- **Execute a integração de tarefas com o HCP Terraform** : integre perfeitamente a governança do Cloudability como **uma** tarefa de execução nos espaços de trabalho do HCP Terraform. Isso permite que as verificações de política sejam acionadas automaticamente durante a fase de planejamento de uma execução do Terraform, permitindo a aplicação consultiva ou obrigatória antes que a infraestrutura seja provisionada.

Esse recurso muda o gerenciamento de custos da nuvem de reativo para proativo, ajudando as equipes a evitar gastos excessivos e violações de políticas antes que a infraestrutura seja implantada.

Para obter mais informações sobre o recurso, consulte [a documentação Cloudability Governance](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=preview-governance-getting-started "(Abre em uma nova guia ou janela)").

## Suporte para base de custos eficaz no Rightsizing Explorer - 14 de janeiro de 2026

Cloudability adicionou suporte para base de custo efetiva no Rightsizing Explorer. Cloudability Os usuários agora podem visualizar recomendações de redimensionamento por custo sob demanda ou efetivo ao analisar oportunidades de redimensionamento no Explorer.

## Cloudability A Rightsizing adiciona suporte para endereços ElasticIP não vinculados ao AWS - 9 de janeiro de 2026

Cloudability adicionou AWS ElasticIP aborda o suporte em Rightsizing. Cloudability Os usuários agora podem receber recomendações para encerrar endereços ElasticIP não vinculados como parte de suas iniciativas mais amplas de otimização de carga de trabalho e recursos.

Não são necessárias novas permissões para essas recomendações, os clientes podem começar a ver essas recomendações preenchidas imediatamente. Essas recomendações também ficarão visíveis na página Rightsizing Explorer e podem ser vinculadas a tickets de ROI de redimensionamento, assim como outros tipos de recomendações.
