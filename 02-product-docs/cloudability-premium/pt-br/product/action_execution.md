---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Execução da ação"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto avançado"
source_path: "product/action_execution.html"
images:
  - "images/advanced-rightsizing-for-aws-ec2-details-action.png"
  - "images/advanced-rightsizing-for-aws-ec2-listing.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Execução da ação

## Introdução

Depois que você tiver concluído a configuração das credenciais das suas contas na nuvem, o mecanismo do Turbonomic inicia a análise do seu ambiente. A análise holística realizada pelo mecanismo do Turbonomic identifica medidas que você pode adotar para otimizar suas implantações na nuvem, tanto em termos de desempenho quanto de custo. Essas ações de otimização realizadas pelo Turbonomic são exibidas na página “Rightsizing > Advanced” em Cloudability para que você possa analisá-las e tomar as medidas necessárias.

Para obter os melhores resultados dessas ações baseadas no Turbonomic, execute-as imediatamente e considere automatizar o maior número possível delas.

## Execução e automação de ações

Por padrão, o mecanismo do ` Turbonomic ` não executa ações automaticamente. Se você examinar as políticas padrão que vêm com o produto, perceberá que elas não permitem a automação de nenhuma ação. Turbonomic O mecanismo oferece a você controle total sobre a execução dessas ações e todas as decisões relacionadas à automação.

Seu objetivo deve ser avaliar todas as ações apresentadas na página “Rightsizing > Avançado” e, em seguida, executar aquelas que resultem em melhorias imediatas no desempenho, nos custos e na utilização de recursos. Com o tempo, você desenvolve e aprimora seu processo de gerenciamento de ações para atingir as metas de produtividade e responder às necessidades comerciais em constante mudança. Esse processo poderia levar às seguintes decisões importantes:

- Executar ação manualmente: Permita que o motor “ Turbonomic ” continue publicando determinadas ações para que você possa executá-las caso a caso.

  Por exemplo, certas ações podem exigir a aprovação de determinadas pessoas. Nesse caso, seria recomendável que um mot Turbonomic e enviasse essas ações para revisão e executasse apenas aquelas que fossem aprovadas.

  Essas ações deixam de ser exibidas depois que você as executa, caso você as desative ou automatize, ou se o ambiente mudar na próxima análise de mercado, de modo que as ações não sejam mais necessárias.
- Automatizar ações por meio de políticas de automação: as políticas de automação permitem que determinadas ações sejam executadas automaticamente, como aquelas que garantem o desempenho e/ou o controle de custos em recursos essenciais à operação.

  A automação simplifica sua tarefa, ao mesmo tempo em que garante que as cargas de trabalho continuem contando com recursos adequados para ter um desempenho ideal. Por isso, é importante que você estabeleça a meta de automatizar o maior número possível de ações. Isso exige avaliar quais ações podem ser automatizadas com segurança e em quais entidades.

## Execução de ações manuais

Se uma ação for executável, você poderá executá-la no painel “Detalhes da ação”. Selecione as ações relevantes nas quais você está interessado clicando em “Ver detalhes” na ação correspondente na página de lista de ações de otimização e, em seguida, clique em “Executar ação ”.

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-for-aws-ec2-listing.png)

O painel de detalhes da ação agora permite que você execute essa ação.

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-for-aws-ec2-details-action.png)

Quando você opta por executar uma ação, é solicitado que você confirme; em seguida, a execução da ação é iniciada. Neste momento, o botão “Executar ação” está desativado, com uma dica de texto indicando que a execução da ação está em andamento. Essa ação permanecerá nesse estado (ou seja, o botão “Executar ação” estará desativado na página de detalhes) até o próximo ciclo de atualização das ações (60 minutos).

Observação: você só poderá executar uma ação se tiver a permisi AutomatorFullAccess e atribuída a você no Frontdoor

Execução de ações — Pontos a serem considerados

- Algumas ações podem não ser executáveis. Por exemplo, a configuração de aceitação de ação em uma política pode ter sido definida como “Recomendar” ou a tecnologia subjacente à entidade pode não oferecer suporte à automação. Nesses casos, o botão “Executar ação” pode não estar ativado para uma ação na interface do usuário
- Algumas ações só podem ser executadas após o cumprimento de determinados pré-requisitos. Por exemplo, para suspender o Host A, VM\_01, o host deve primeiro ser transferido para o Host B. No entanto, o Host B tem capacidade apenas para um VM e, no momento, está hospedando VM\_02. Nesse caso, a suspensão do Host A está bloqueada por duas ações pré-requisitos: VM\_02, que deve ser transferida para outro host, e VM\_01, que deve ser transferida para o Host B. Para uma ação com pré-requisitos, o botão “Executar ação” fica desativado e o status indica que ela está bloqueada.

## Perguntas Frequentes

1. É possível executar todas as ações do Turbo?

   Não, nem todas as ações de otimização geradas pelo mecanismo Turbonomic são executáveis. Isso depende de como as políticas estão configuradas; a tecnologia subjacente à entidade deve suportar a execução, ou todos os pré-requisitos necessários para uma ação devem ser atendidos.
2. Como posso acompanhar o status de execução da ação na interface do usuário?

   O campo “status” na página de listagem de ações, bem como o painel de detalhes da ação, refletem o status atual da execução da ação. Observe que os valores de status em Cloudability não refletem imediatamente o status de execução da ação na interface do usuário de Cloudability. No entanto, os usuários podem acessar a interface do usuário do Turbonomic por meio do Frontdoor, localizar o recurso no contexto a partir da visualização da cadeia de suprimentos e verificar o status da ação no widget “Todas as ações ”
3. Eu executei uma ação. O que acontece agora?

   Quando você executa uma ação na interface do usuário d Cloudability, isso aciona a solicitação de execução da ação no mecanismo Turbonomic. O botão “Executar ação” na interface do usuário do Cloudability ficará desativado para impedir que este ou qualquer outro usuário em Cloudability execute a mesma ação novamente. Uma dica de texto indicará que a execução dessa ação está em andamento. Essa ação continuará listada na interface do usuário do Cloudability, tanto na página de listagem quanto nas páginas de detalhes da ação, que são visíveis aos usuários na interface do usuário do Cloudability, embora os usuários não possam executá-la. No entanto, o status da execução da ação no mecanismo d Turbonomic não é refletido na interface do usuário d Cloudability. Os usuários podem acompanhar a solicitação de execução na interface do usuário do Turbonomic por meio do widget “Todas as ações ”. Cloudability Atualiza as ações do Turbonomic a cada 60 minutos e, no próximo ciclo de atualização, essa ação poderá apresentar atualizações na interface do usuário do Cloudability com base no ciclo de avaliação do Turbonomic
4. Como faço para solucionar problemas no fluxo de execução da ação? Por onde começar?

   Pode levar alguns segundos ou minutos para que a execução de uma ação seja concluída no mecanismo do Turbonomic. Você pode verificar o status de execução da ação para o recurso em nuvem em questão na interface do usuário do Turbonomic. Acesse a página de recursos (na visualização da cadeia de suprimentos, você pode selecionar o tipo de entidade ou algo semelhante) e pesquise o nome ou o ID do recurso no contexto. Abra a guia “Visão geral”. O widget “Todas as ações” lista todas as ações executadas (bem-sucedidas ou com falha) ao longo do ciclo de vida do recurso em contexto e é exibido aqui.
5. Executei uma ação que foi bem-sucedida, mas ainda vejo a ação listada na interface do usuário. Como isso é possível?

   Mesmo que a execução da ação seja bem-sucedida, o mecanismo “ Turbonomic ” leva alguns minutos para atualizar esse status e sua cadeia de suprimentos interna. Assim que esse status for atualizado internamente em todos os serviços do mecanismo Turbonomic, a próxima execução de geração de ações no mecanismo Turbonomic garantirá que a ação não seja listada, uma vez que já foi executada (a menos que a política tenha sido atualizada nesse intervalo com limites diferentes). Como o Cloudability atualiza as ações de otimização geradas pelo mecanismo Turbonomic a cada 1 hora, leva de 1 a 2 horas para que a ação desapareça da página “Rightsizing”, mesmo após a ação ter sido executada com sucesso
6. Executei uma ação e ela falhou. O que acontece agora?

   Turbonomic O sistema leva alguns minutos para atualizar esse status e sincronizar sua cadeia de suprimentos interna. Assim que esse status for atualizado internamente em todos os serviços do Turbonomic, o próximo ciclo de análise do mecanismo Turbonomic gerará um conjunto de ações com base nas políticas configuradas, e essa ação reaparecerá na lista de ações da interface do usuário (a menos que a política tenha sido atualizada nesse intervalo com limites diferentes).

**Tópico principal:** [Redimensionamento avançado](../product/advanced-rightsizing-powered-by-turbonomic.html)
