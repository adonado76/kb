---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Cloudability Incorporando uma nova instância do Turbonomic"
breadcrumb:
  - "Cloudability Premium"
  - "Turbonomic Integração"
source_path: "product/turbonomic-integration-cloudability-production.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cloudability Incorporando uma nova instância do Turbonomic

## Visão geral

Em um ambiente de produção, qualquer configuração é feita automaticamente com a ajuda do PPO. A única ação manual necessária é configurar as permissões para os usuários no Frontdoor. Isso deve ser feito pelo usuário administrador do cliente.

Esta seção abordará a diferença na configuração das funções e dos escopos dos usuários entre instâncias do Turbonomic que não utilizam o Frontdoor e instâncias do Turbonomic habilitadas para o Frontdoor, bem como a descrição das próprias permissões disponíveis no ambiente de produção.

Em uma instância do Cloudability Premium Turbonomic, os usuários são criados automaticamente durante seu primeiro login no site Turbonomic, com base em sua configuração no Frontdoor. A configuração do Frontdoor é usada para definir funções de usuário no Turbonomic (que se baseiam nas permissões do Frontdoor), mas não há como configurar os escopos do Turbonomic a partir do Frontdoor. A atribuição inicial do escopo do usuário ocorre apenas quando o usuário faz login pela primeira vez (e a conta do usuário é criada automaticamente no Turbonomic ). Vale ressaltar que, uma vez que a conta do usuário já exista em Turbonomic, a alteração das permissões no Frontdoor não afetará o escopo desse usuário. Para configurar um escopo mais detalhado, serão necessárias etapas adicionais por parte do administrador do cliente (no site Turbonomic ).

## Escopos no ` Turbonomic `

Os escopos no Turbonomic funcionam de maneira semelhante às Visualizações no Cloudability, mas vale a pena observar que eles não são sincronizados entre Cloudability e Turbonomic, e precisam ser configurados separadamente em cada aplicativo. Isso ocorre apenas na fase inicial da integração entre os dois, quando o cliente tem acesso direto ao aplicativo Turbonomic. Em versões futuras da nossa integração, o cliente não poderá mais fazer login diretamente em Turbonomic e não precisará mais configurar esses escopos — o Cloudability cuidará de todas as ações necessárias para conceder acesso aos recursos especificados para o usuário.

## Permissões de frontdoor

Aqui você encontra uma lista de todas as permissões disponíveis na instância de produção do Frontdoor, que podem ser utilizadas para a autorização d Turbonomic.

| Nome da permissão | Descrição |
| --- | --- |
| ScopedAutomatorFullAccess | Os usuários com essa permissão podem utilizar todos os recursos do Turbonomic (incluindo Plan, Park e Place), mas não podem configurar a instalação do Turbonomic nem criar políticas. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). |
| ScopedDeployerFullAccess | Os usuários com essa permissão podem visualizar todos os gráficos e dados do Turbonomic, usar o Place para reservar cargas de trabalho e criar políticas e modelos de alocação. No entanto, os usuários não podem executar planos ou executar ações recomendadas. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). |
| ScopedAdvisorFullAccess | Os usuários com essa permissão podem visualizar todos os gráficos e dados do Turbonomic e executar planos. No entanto, os usuários não podem usar o Place para reservar cargas de trabalho, criar políticas ou executar qualquer ação recomendada. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). |
| ScopedObserverFullAccess | Os usuários com essa permissão podem visualizar o ambiente, incluindo a Home Page e os Dashboards. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). |
| ScopedOperationalObserverFullAccess | Os usuários com essa permissão podem visualizar o ambiente, incluindo a página inicial, os painéis, os grupos e as políticas. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). |
| ScopedSharedAdvisorFullAccess | Os usuários com essa permissão podem visualizar a Home Page e os Dashboards, mas só podem ver VMs e aplicativos. Os usuários não podem executar ações do tipo “ Turbonomic ”. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). |
| ScopedSharedObserverFullAccess | Os usuários com essa permissão podem visualizar a Home Page e os Dashboards personalizados, mas só podem ver VMs e aplicativos. Os usuários não podem visualizar os painéis executivos nem executar ações do “ Turbonomic ”. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). |
| SiteAdminFullAccess | Os usuários com essa permissão podem utilizar todos os recursos do Turbonomic e modificar as configurações específicas do site para configurar a instalação do Turbonomic. Os usuários também podem administrar grupos, políticas, fluxos de trabalho, modelos, faturamento/custos e configuração de destino, mas não e-mail, licenças, atualizações e manutenção. Os usuários com essa função podem definir o escopo em outras contas. |
| AutomatorFullAccess | Os usuários com essa permissão podem utilizar todos os recursos do Turbonomic (incluindo Plan, Park e Place), mas não podem configurar a instalação do Turbonomic nem criar políticas. |
| DeployerFullAccess | Os usuários com essa permissão podem visualizar todos os gráficos e dados do Turbonomic, usar o Place para reservar cargas de trabalho e criar políticas e modelos de alocação. No entanto, os usuários não podem executar planos ou executar ações recomendadas. |
| AdvisorFullAccess | Os usuários com essa permissão podem visualizar todos os gráficos e dados do Turbonomic e executar planos. No entanto, os usuários não podem usar o Place para reservar cargas de trabalho, criar políticas ou executar qualquer ação recomendada. |
| ObserverFullAccess | Os usuários com essa permissão podem visualizar o ambiente, incluindo a Home Page e os Dashboards. |
| OperationalObserverFullAccess | Os usuários com essa permissão podem visualizar o ambiente, incluindo a página inicial, os painéis, os grupos e as políticas. |

As permissões da função “Frontdoor” acima correspondem diretamente às funções integradas do Turbonomic. Por exemplo, uma permissão da função “Frontdoor” em **ObserverFullAccess** concederá a função **“Observer”** aos usuários em Turbonomic. Observe que a maioria das permissões listadas acima tem duas variantes, e a diferença entre elas se baseia no fato de o usuário ser atribuído a um escopo vazio (sem acesso a nenhum recurso) ou a um escopo completo (acesso a todos os recursos). Além dos escopos, essas duas permissões concederão a mesma função no Turbonomic (ou seja, **ScopedObserverFullAccess** e **ObserverFullAccess** concederão a função **“Observador”** a um usuário no Turbonomic ). Observe que algumas permissões **não** suportam o escopo, pois concedem acesso a todos os recursos independentemente (por exemplo, **SiteAdminFullAccess** ).

No caso de várias permissões serem aplicadas ao mesmo usuário no Frontdoor, o Turbonomic escolherá a permissão com o menor nível de privilégios.

## Aplicação de escopos aos usuários no Turbonomic

A um usuário no Turbonomic é atribuída uma função e um escopo adequados durante seu primeiro login (com base nas permissões iniciais da função “Frontdoor”). Vale a pena observar que um usuário não existe em Turbonomic (antes do primeiro login) e, portanto, não pode ser pré-configurado com um escopo granular.

Para aplicar escopos completos ao usuário, siga as etapas abaixo.

1. Um administrador aplica a permissão de **ObserverFullAccess** permissão de função ao usuário no Frontdoor.
2. O usuário faz login pela primeira vez na instância do Turbonomic – nesse momento, um novo usuário é criado automaticamente no Turbonomic com base nas permissões da função no Frontdoor.
3. O usuário agora pode acessar Turbonomic com a função **de Observador** e terá acesso a todos os recursos.

Para aplicar um escopo limitado ao usuário, siga as etapas abaixo.

1. Um administrador aplica a permissão **ScopedObserverFullAccess** permissão de função ao usuário no Frontdoor
2. O usuário faz login pela primeira vez na instância do Turbonomic – nesse momento, um novo usuário é criado automaticamente no Turbonomic com base nas permissões da função no Frontdoor
3. Agora, o usuário pode acessar Turbonomic com a função **“Scoped Observer”,** mas não tem acesso a nenhum recurso.
4. Um administrador faz login em Turbonomic e configura um escopo para esse usuário, com o respectivo acesso aos recursos.
5. Quando o usuário fizer login novamente, ele poderá acessar Turbonomic com a função **“Scoped Observer”** e terá um escopo adequado atribuído a ele.

## Atualização de funções de usuário no Turbonomic

Para alterar a função de um usuário no site Turbonomic, o administrador precisa atualizar as permissões atribuídas a esse usuário no Frontdoor. A cada login, o Turbonomic verificará as funções atualmente atribuídas ao usuário no Frontdoor e atualizará sua configuração, se necessário. Esse processo não afetará os escopos, pois a verificação dos escopos é realizada apenas durante o primeiro login em Turbonomic.

Caso as funções sejam atualizadas diretamente no Turbonomic, a configuração do Frontdoor substituirá a função do usuário no próximo login.

**NOTA** : Quando os usuários são adicionados ao Turbonomic no Cloudability Premium, eles não são removidos automaticamente ao terem seu acesso revogado no Frontdoor. Caso isso ocorra (por exemplo: durante o cancelamento do cadastro de um usuário), será necessário remover manualmente o usuário do site Turbonomic. É importante observar, do ponto de vista da segurança, que, quando um usuário é removido do Frontdoor, ele não poderá mais acessar Turbonomic (já que o acesso é controlado pelo Frontdoor).
