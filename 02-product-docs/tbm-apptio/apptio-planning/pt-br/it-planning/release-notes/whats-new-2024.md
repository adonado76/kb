---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "notas de versão de 2024"
breadcrumb:
  - "Planning"
  - "Notas sobre a liberação"
source_path: "it-planning/release-notes/whats-new-2024.html"
images:
  - "resources/images/it_planning_images/3.71-1.jpg"
  - "resources/images/it_planning_images/3.71-2.jpg"
  - "resources/images/it_planning_images/3.72-1.jpg"
  - "resources/images/it_planning_images/3.72-3.jpg"
  - "resources/images/it_planning_images/3.72-5.jpg"
  - "resources/images/it_planning_images/3.73-rn.jpg"
  - "resources/images/it_planning_images/3.74-1.jpg"
  - "resources/images/it_planning_images/3.80-1.jpg"
  - "resources/images/it_planning_images/3.80-2.jpg"
  - "resources/images/it_planning_images/3.80-4.jpg"
  - "resources/images/it_planning_images/3.80-5.jpg"
  - "resources/images/it_planning_images/3.803.jpg"
  - "resources/images/it_planning_images/fcs-1.jpg"
  - "resources/images/it_planning_images/fcs-2.jpg"
  - "resources/images/it_planning_images/finalize-plan.jpg"
  - "resources/images/it_planning_images/fixed-cal1.jpg"
  - "resources/images/it_planning_images/release-notes/3.75-1.jpg"
  - "resources/images/it_planning_images/release-notes/3.75-2.jpg"
  - "resources/images/it_planning_images/release-notes/3.78_rn.jpg"
  - "resources/images/it_planning_images/release-notes/3.81.jpg"
  - "resources/images/it_planning_images/release-notes/3.82-1.jpg"
  - "resources/images/it_planning_images/release-notes/3.82.jpg"
  - "resources/images/it_planning_images/release-notes/3.83.jpg"
  - "resources/images/it_planning_images/release-notes/apptio-bi-ba.jpg"
  - "resources/images/it_planning_images/release-notes/dash-after.jpg"
  - "resources/images/it_planning_images/release-notes/left-navigate-ba.jpg"
  - "resources/images/it_planning_images/release-notes/name-after.jpg"
  - "resources/images/it_planning_images/release-notes/name-before.jpg"
  - "resources/images/it_planning_images/release-notes/summary-after.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# notas de versão de 2024

## 3.83 - 23 de dezembro de 2024

Esta versão introduz o recurso Variable Labor Compensation Adjustments (Ajustes de remuneração variável de mão de obra), proporcionando maior flexibilidade na modelagem dos custos de mão de obra. Com essa funcionalidade, você pode:

Ajustes de remuneração variável de mão de obra

- Aplique ajustes percentuais aos salários-base mensalmente, permitindo um planejamento preciso da remuneração.
- Defina ciclos de remuneração padrão e aumentos de mérito por função para agilizar os ajustes salariais em sua força de trabalho.
- Modelar mudanças dinâmicas em aumentos de mérito, ajustes de mercado ou atualizações de políticas orientadas por remuneração.

  ![plano de remuneração do trabalho](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.83.jpg)

  Para obter mais informações, consulte [Configuração de ajustes de remuneração de mão de obra](../planning/plan-labor-compensation.html "Os ajustes de remuneração de mão de obra permitem que as organizações modelem aumentos (ou reduções) de remuneração ao longo do tempo no site Apptio Planning. Esse recurso oferece uma forma estruturada de contabilizar os ajustes salariais planejados, como aumentos por mérito, ajustes de mercado, promoções ou mudanças no custo de vida.").

Correções de bugs

- Foi resolvido um problema em que a importação de dados de atividade de trabalho não preenchia o centro de custos de recursos.
- Foi resolvido um problema em que os campos não eram exibidos na guia Contratos na visualização Nova Despesa.
- Foi corrigido um problema em que as linhas da dimensão Projetos ficavam impossíveis de serem pesquisadas quando a contagem de registros ultrapassava 10.000.
- Foi corrigido um problema em que a renomeação de um atributo de projeto registrava incorretamente dois eventos no Histórico de alterações em vez de um único evento.
- Aprimorou o registro de eventos Criar plano para incluir detalhes que indicam se a opção Copiar códigos de itens de linha foi selecionada (Verdadeiro) ou não (Falso).
- Foi corrigido um problema em que o Histórico de alterações não registrava eventos de falha quando uma ação Criar plano falhava. O Change History agora captura e exibe corretamente os registros de tentativas de criação de planos com falha.

## 3.82 - 2 de dezembro de 2024

Selecione o período de origem para a importação do plano em Apptio Costing

Os proprietários de centros de custo agora podem selecionar o período de origem ao importar dados de linha de base do plano do site Apptio Costing. Anteriormente, o sistema usava como padrão o período mais recente.

![substituir todos os dados](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.82.jpg)

Total do contrato KPI

Nos planos de previsão, o KPI Total do contrato agora exibe o Total do contrato (real mais previsão) e o Total do contrato de previsão para o período selecionado.

Total do contrato : Valor total do contrato para períodos históricos e de previsão.

Total da previsão : Valor total do contrato somente para períodos de previsão.

![Contratos](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.82-1.jpg)

Registro de log aprimorado para análise de variância

Essa atualização introduz o registro detalhado das atividades de análise de variação, proporcionando maior transparência e rastreabilidade das principais ações:

Criação de nova análise de variância : Agora são gerados logs quando uma nova análise de variância é criada, capturando informações como o nome do plano e as configurações de variância.

Adição/modificação de explicações de análise de desvio : quaisquer adições ou modificações nas explicações de análise de desvio são registradas, incluindo detalhes como texto antes e depois, objeto de custo, conta e plano associado.

Correções de bugs

- Foi resolvido um problema em que a opção "Is Existing Employee" não estava presente na tabela Expenses > Labor na Legacy View quando a opção Streamlined Labor estava ativada.
- Foi resolvido um problema em que a funcionalidade de importação e exportação não funcionava para listas personalizadas que continham o caractere '/' no nome.
- Correção de um problema em que a exportação de dados planejados contendo símbolos "&" ou "," resultava em um arquivo com formatação incorreta.
- Foi corrigido um problema em que as dimensões marcadas como obrigatórias não estavam sendo aplicadas como necessárias.
- Correção de um problema em que períodos fiscais nulos estavam sendo enviados na solicitação pull de entidade para o ADM, fazendo com que o ADM importasse por padrão os planos do período fiscal do calendário atual em vez do período fiscal selecionado.
- Foi corrigido um problema em que os usuários com permissões "Can View Sensitive Data" e "Can View Sensitive Financials" não conseguiam publicar dados confidenciais de mão de obra em Apptio Costing.
- Foi resolvido um problema em que a alternância entre a visualização herdada e a nova visualização falhava se mais de 20 layouts privados estivessem presentes. - Foi corrigido um problema na nova exibição em que os filtros eram redefinidos após a seleção, impedindo que os usuários aplicassem filtros com êxito.
- Foi resolvido um problema em que, se o SDP ou PFP não estivesse ativado, o Tipo de transação apareceria incorretamente no menu Agrupar por na guia Resumo.

## 3.81 - 18 de novembro de 2024

Formato de data e número específico do usuário

O Planning agora se integra às configurações de localidade do usuário do Frontdoor, ajustando automaticamente os formatos de data e número para corresponder à localidade configurada de cada usuário. Esse aprimoramento permite que os usuários personalizem como as datas e os números são exibidos, criando uma experiência mais personalizada. Cada país ou região segue padrões e convenções diferentes para representar números. As variações podem incluir os símbolos usados para separação decimal, formatos de agrupamento, exibição de moeda e a ordem do ano, mês e dia nas datas.

O que esperar

- A partir da versão 3.81, o Planning exibirá datas e formatos de números com base nas configurações de localidade do usuário definidas no Frontdoor, em vez das configurações de localidade do navegador.
- A localidade padrão no Frontdoor é en\_US, portanto, se os usuários não tiverem definido uma localidade preferida, as datas e os números aparecerão no formato en\_US.
- Essa alteração se aplica apenas à visualização e à inserção de datas e números no aplicativo. Para arquivos de importação/exportação, as configurações de localidade do Frontdoor não são aplicadas; os usuários devem especificar os formatos de data e número nas opções de formatação da caixa de diálogo de importação/exportação.

  ![campo de localização preferencial](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.81.jpg)

  Para obter mais informações, consulte [Configurar formato de data e número](../planning/config-date-num-format.html).

Correções de bugs

- O menu suspenso Comparison Plan (Plano de comparação) na caixa de diálogo Add Comparison (Adicionar comparação) ou Compare Shortcut (Comparar atalho) agora exibe os nomes dos planos em ordem alfabética, tornando mais rápida e fácil a localização do plano desejado para comparação.
- Foi corrigido um problema em que a funcionalidade de importação e exportação não funcionava para listas personalizadas que continham o caractere '/' no nome.
- Foi corrigido um problema com a classificação na coluna "User Name" (Nome do usuário) na tabela Configuration > Cost Object Permissions (Configuração > Permissões de objetos de custo).
- Foi corrigido um problema em que o modelo de exportação do projeto fornecia cabeçalhos incorretos para importação nos dados de referência do projeto.
- Foi corrigido um problema em ambientes PFP que impedia atualizações de dados de referência devido à limpeza incompleta de dimensões personalizadas nas tabelas Allocation e Demand.

## 3.80 - 4 de novembro de 2024

Períodos de comparação personalizados para configuração de desvio

Os proprietários de processos orçamentários agora podem selecionar um período de comparação personalizado ao configurar a análise de variação para comparar o real com o planejado. Para melhorar a clareza, os nomes das colunas de valores reais também foram atualizados para incluir "valores reais", como "Sept FY24 Actuals"

Esta é uma versão inicial destinada a dar suporte a aprimoramentos futuros, que permitirão comparações entre planos em qualquer intervalo de tempo, como uma variação de um ano inteiro.

![novo período de comparação](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.80-1.jpg)

![data final e inicial da comparação](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.80-2.jpg)

Interface do usuário de despesas

Os botões de importação e exportação de dados de despesas foram realocados para o menu de opções acima da tabela de despesas, criando uma interface de usuário mais limpa. Agora é possível acessar essas funções diretamente nesse menu.

![finanças de importação e exportação](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.803.jpg)

Aprimoramento da visão do trabalho

A guia Trabalho na nova visualização de despesas foi atualizada com uma subguia "Todos", reunindo recursos de trabalho planejados e existentes em uma visualização unificada para fácil referência.

A subguia "Todos" inclui uma coluna de mão de obra existente para indicar claramente se uma linha de mão de obra é planejada ou existente. Os usuários podem mudar os recursos de mão de obra entre Planejado e Existente editando a caixa de seleção na coluna Mão de obra existente.

![caixa de seleção de mão de obra existente](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.80-4.jpg)

Aprimoramento da visualização de ativos

A guia Assets (Ativos) na Expenses New View (Nova visualização de despesas) agora apresenta uma subguia "All" (Todos), combinando ativos planejados e existentes em uma única visualização unificada para facilitar o gerenciamento.

Na subguia "All" (Todos), uma coluna Existing Asset (Ativo existente) indica claramente se cada linha de ativo é planejada ou existente. Os usuários podem mover ativos entre Planejados e Existentes ajustando a caixa de seleção na coluna Ativo Existente.

![aprimoramento da visualização de ativos](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.80-5.jpg)

Correções de bugs

- Foi corrigido um problema no site Integrated Investment Planning (IIP) em que a atualização de projetos na lista de projetos usando a dimensão do projeto nos dados de referência causava erros se um atributo personalizado da lista nos dados de referência do projeto contivesse valores nulos.
- Também foi resolvido um problema no gráfico de tendência Summary > Headcount, que anteriormente exibia a linha do tempo do ano duas vezes ao longo do eixo x.

## Apptio Transição da comunidade para IBM TechXchange - 1º de novembro de 2024

Atualmente, a comunidade Apptio fez a transição completa para IBM TechXchange.

Use e marque [esta nova página inicial](https://community.ibm.com/community/user/apptio/home "(Abre em uma nova guia ou janela)") para os grupos de tópicos do Apptio.

- Acesse o grupo de tópicos relevante para suas necessidades; alguns dos grupos de tópicos com os quais você está familiarizado foram combinados em novos grupos de tópicos.

  Os seguintes grupos de tópicos estão disponíveis:
- [Apptio](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=4100dfb8-fc23-4203-83c7-019253cf7c0b "(Abre em uma nova guia ou janela)") : Costing Essentials, Costing Standard (CT-Foundation), Apptio Planning (ITP/ITFMF), Faturamento (Billing Standard), Benchmarking (Benchmarking), ServiceNow Integração

  - [Notas de lançamento de planejamento](https://community.ibm.com/community/user/apptio/viewdocument/apptio-planning-whats-new-cumula?communitykey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Abre em uma nova guia ou janela)")
  - [TBM Studio notas de versão de aplicativos e aplicativos](https://community.ibm.com/community/user/apptio/viewdocument/tbm-studio-and-applications-r12-rel?communitykey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(Abre em uma nova guia ou janela)")
- [Cloudability](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=15c0e07d-35c0-49de-a84b-019253d13376 "(Abre em uma nova guia ou janela)") : Soluções em nuvem para planejamento financeiro, Cloudability TotalCost, Apptio Turbonomic Integração
- [Processo-alvo](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=55a3712d-1835-4ec2-bcd7-603e88cd9dd2 "(Abre em uma nova guia ou janela)")
- [Plataforma](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8 "(Abre em uma nova guia ou janela)") : Apptio BI, ATUM, Automated Data Management, DataLink, Frontdoor, TBM Studio
- [Apptio para todos](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=2e85ed45-9b8a-486c-bd55-019253d466eb "(Abre em uma nova guia ou janela)")
- Quando estiver em seu grupo de tópicos, leia e contribua com todo o conteúdo habitual, como links rápidos, discussões, perguntas e blogs.
- Confira [estes recursos](https://community.ibm.com/community/user/participate/resources "(Abre em uma nova guia ou janela)") sobre como navegar e utilizar a comunidade.
- Comece a enviar solicitações de aprimoramentos em [IBM Ideas](https://login.ibm.com/idaas/mtfim/sps/idaas/login?client_id=nwnjmzc5njetmzlkyi00&target=https%3a%2f%2flogin.ibm.com%2foidc%2fendpoint%2fdefault%2fauthorize%3fqsid%3dc75ff073-50e8-4426-8979-7e4b6b992e80%26client_id%3dnwnjmzc5njetmzlkyi00 "(Abre em uma nova guia ou janela)").

  - IBM usa um portal de ideias unificado em [ideas.ibm.com](https://ideas.ibm.com/ "(Abre em uma nova guia ou janela)") para que você possa levantar ideias sobre todos os produtos. A partir de hoje, essa lista foi ampliada para incluir os produtos recentemente adquiridos da Apptio. As ideias enviadas antes da aquisição serão disponibilizadas para as equipes de produtos e poderão ser adicionadas ao portal em uma data futura para garantir a continuidade.

Entre em contato com a equipe da comunidade em nosso novo e-mail, [support@communitysite.ibm.com](mailto:support@communitysite.ibm.com "(Abre em uma nova guia ou janela)") com qualquer dúvida ou necessidade.

## 3.79 - 21 de outubro de 2024

Somente versão de manutenção

Esta versão contém atualizações de manutenção do sistema e correções de bugs.

Correções de bugs

- Foi solucionado o problema em que a atualização dos valores reais fazia com que os valores reais gerados na página do Ledger fossem excluídos para os clientes do site Project Financial Planning .
- Foi resolvido o problema na funcionalidade Atualizar valores reais para ambientes Project Financial Planning (PFP) quando os valores reais são excluídos do Gerenciamento de despesas e o usuário deseja remover os valores reais do plano de previsão usando o recurso Atualizar valores reais.
- Foi resolvido o problema na funcionalidade Atualizar dados reais quando a configuração Gerar custos em períodos reais está ativada em Project Financial Planning (PFP) > Atividade de trabalho.

## 3.78 - 7 de outubro de 2024

Sincronizar layouts herdados

Os usuários agora podem transferir seus layouts de tabela de despesas da visualização antiga para a nova visualização com um único clique, eliminando a migração manual e economizando tempo.

Para sincronizar layouts, basta clicar no ícone Layouts na Nova visualização e selecionar "Sync Legacy Layouts" Isso copiará automaticamente seus layouts da visualização herdada para a nova visualização. Observe que será necessário sincronizar os layouts de cada guia da tabela de despesas individualmente para concluir a migração da visualização herdada para a nova visualização.

![sincronizar layouts legados](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.78_rn.jpg)

Correções de bugs

- Foi resolvido um problema em que os uploads de dados ficavam incompletos ao usar a configuração de localidade japonesa.
- Foi solucionado um problema em que a atualização dos valores reais fazia com que os valores reais gerados na página Ledger fossem excluídos para os clientes do site Project Financial Planning .
- Foi resolvido um problema em que a página não era carregada após a aplicação de comparações e filtros e o salvamento das configurações em um layout na Nova página de despesas.
- Foi resolvido um problema em que os usuários administradores não conseguiam ver as colunas marcadas como confidenciais depois de atribuir permissões de objeto de custo com restrições de visualização.

## 3.77 - 23 de setembro de 2024

Somente versão de manutenção

Esta versão contém atualizações de manutenção do sistema e correções de bugs.

Correções de bugs

- Foi resolvido um problema em que a guia Contratos não era carregada quando acessada na Nova visualização.
- Foi resolvido um problema em que a classificação de uma coluna na tabela Permissões de objetos de custo fazia com que a página fosse exibida em branco.

## 3.76 - 9 de setembro de 2024

Integração do serviço de calendário fiscal

Apptio Planning agora está integrado ao Serviço de Calendário Fiscal (FCS), um serviço de plataforma centralizado no site Apptio. O FCS foi projetado para gerenciar calendários fiscais em todos os produtos Apptio, permitindo que os clientes definam seu calendário fiscal uma vez e o apliquem em todos os produtos assinados. Essa integração simplifica o gerenciamento do calendário fiscal com uma interface amigável que facilita a visualização, a edição e a atualização das configurações do calendário.

Observação: se estiver usando uma variante 445 ou um calendário de 13 períodos, você gerenciará suas definições de calendário por meio do Serviço de Calendário Fiscal. Os tipos de calendário só podem ser definidos durante a configuração inicial.

Como acessar o Serviço de Calendário Fiscal

O FCS é acessível a usuários com função de administrador. O FCS está disponível como um novo aplicativo em seu ambiente Frontdoor.

![calendário fiscal](../../../../../03-media/apptio-planning/resources/images/it_planning_images/fcs-1.jpg)

![configuração do calendário fiscal](../../../../../03-media/apptio-planning/resources/images/it_planning_images/fcs-2.jpg)

Para obter mais informações, consulte [Serviços de calendário fiscal](../../fiscal-calendar-services/home.html).

Correções de bugs

- Agora você pode criar layouts para subguias na guia Despesas, como Trabalho existente ou Planejamento, na Nova visualização.
- Foi resolvido um problema com a exportação de dados do Plano para Apptio Costing (Cost Transparency) ao usar o formato "Publish Months for all Fiscal Years as columns in a single row". A exportação de dados do plano agora segue corretamente as definições de formato de exportação configuradas.
- Foi corrigido um problema no Update Actuals em que os valores reais do projeto não estavam sendo distribuídos corretamente durante o processo de atualização.

## 3.75 - 26 de agosto de 2024

A partir de segunda-feira, 26 de agosto de 2024, os principais locatários de produção começarão a fazer o upgrade para a versão 3.75. Apptio lançará o seguinte recurso nesta versão.

Programar a publicação de dados planejados para Apptio Costing

Os usuários administradores agora podem criar programações diárias, semanais e mensais, bem como selecionar um horário para executar a programação usando a integração automatizada Data Management para publicar os dados do plano de Apptio Planning para Apptio Costing (transparência de custos). Além disso, os usuários também podem especificar um período em Apptio Costing para o qual os dados devem ser publicados.

Esse aprimoramento elimina a necessidade de publicação manual de dados e agiliza o processo de integração de dados entre o Planning e o Costing. O Data Management automatizado (ADM) será atualizado em 4 de setembro de 2024, para permitir a programação da publicação dos dados do plano no Apptio Costing.

Para obter mais informações, consulte [Programar a publicação de dados planejados](../planning/adm/adm-sch-pub-plan-to-costing.html "Os usuários administradores agora podem criar cronogramas diários, semanais e mensais, bem como selecionar um horário para executar o cronograma usando a integração automatizada Data Management para publicar os dados do plano de Apptio Planning para Apptio Costing (transparência de custos). Além disso, os usuários também podem especificar um período em Apptio Costing para o qual os dados devem ser publicados.").

![adicionar cronograma](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.75-1.jpg)

![adicionar cronograma](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.75-2.jpg)

Correções de bugs

- Descobriu-se que o recurso "Update Actuals" tinha um bug em que os dados reais não estavam sendo atualizados conforme o esperado, apesar de a operação ter sido bem-sucedida.
- Resolvemos um problema em que os totais da linha de resumo para Remuneração base (guia Trabalho), Valor do contrato (guia Contrato) e Preço de compra (guia Ativo) exibiam valores incorretos quando a opção de várias moedas estava ativada. Anteriormente, os totais eram imprecisos devido à conversão incorreta da moeda. A lógica de cálculo foi atualizada para garantir que, com a opção de várias moedas ativada, os totais da linha de resumo da Compensação básica, do Valor do contrato e do Preço de compra agora sejam calculados corretamente usando a Taxa do plano média para a moeda selecionada. A taxa média do plano é determinada pela média de todas as taxas do plano para uma moeda específica durante a duração do plano.
- Foi resolvido um problema em que a atualização de dados reais com várias moedas ativadas resultava em um erro. O problema ocorria quando os itens de linha reais continham várias transações em moedas diferentes para o mesmo "Objeto de custo", "Centro de custo" e "Conta"
- Foi corrigido o problema em que os dados de mês, trimestre e ano não eram visíveis em Despesas > Nova visualização. Se você ainda não conseguir ver essas colunas, siga estas etapas: Clique no botão Layout e selecione "Redefinir colunas para o layout padrão" Isso deve exibir todas as colunas de período (meses, trimestres e ano). Quando as colunas estiverem visíveis, vá para Layout > Layout público > Layout padrão e clique em "Salvar" para salvar as alterações no layout padrão.

## 3.74 - 12 de agosto de 2024

A partir de segunda-feira, 12 de agosto de 2024, os principais locatários de produção começarão a fazer o upgrade para a versão 3.74. Apptio lançará o seguinte recurso nesta versão.

Exclusão seletiva das regras de alocação de mão de obra do cálculo da carga total de trabalho

Na versão de planejamento 3.74, introduzimos um novo recurso que permite que os usuários administradores excluam regras específicas de alocação de mão de obra do cálculo de mão de obra totalmente onerada na guia Mão de obra. Esse aprimoramento garante que essas regras ainda gerem itens de linha financeira na guia Resumo, mas não afetem os totais do ano fiscal exibidos na guia Trabalho.

Anteriormente, na versão de planejamento 3.71, aprimoramos a capacidade do proprietário do orçamento de visualizar o custo de mão de obra totalmente onerado diretamente na coluna Expenses > Labor > FY Total, eliminando a necessidade de navegar até a seção Expenses > Summary. Para obter mais detalhes, acesse as notas de versão do site 3.71.

Para acomodar as organizações que preferem não incluir determinadas regras de alocação de mão de obra no FY Total mostrado na guia Expenses > Labor, as seguintes atualizações foram introduzidas nesta versão:

- Uma nova coluna, "Excluir do cálculo de mão de obra", foi adicionada à tabela Regras de alocação de mão de obra.
- Os usuários administradores podem selecionar a exclusão de uma regra diretamente na interface da tabela.
- Por padrão, as regras são incluídas no cálculo do total do FY de mão de obra. Para excluir uma regra, marque a caixa de seleção correspondente.
- Quando uma regra é marcada para exclusão, ela não afeta o FY Total exibido na guia Trabalho, mas continua a gerar um item de linha financeira na guia Resumo.

  ![excluir do cálculo da mão de obra](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.74-1.jpg)

  Para obter mais informações, consulte [as Regras de Alocação de](../planning/manage-labor-allocation-rules.html) Mão de Obra.

Correções de bugs

- Os proprietários de orçamento agora verão o "Custo totalmente onerado" para o ano fiscal exibido corretamente como a soma de todos os custos gerados de períodos reais e os custos gerados de períodos de previsão. Anteriormente, a ausência de dados reais de mão de obra fazia com que a coluna Ano fiscal totalmente onerado exibisse valores significativamente menores do que o valor da Remuneração base nos planos de previsão. Com essa correção, os períodos reais são calculados usando as Regras de alocação de mão de obra e incluídos nos valores de "Custo de mão de obra" totalmente onerados na guia Mão de obra; no entanto, os dados financeiros não são gerados para períodos históricos na guia Resumo.

## 3.73 - 29 de julho de 2024

A partir de segunda-feira, 29 de julho de 2024, os principais locatários de produção começarão a fazer o upgrade para a versão 3.73. Apptio lançará o seguinte recurso nesta versão.

Despesas em tela cheia ModeTable Layouts na nova visualização de despesas

A tabela de despesas na nova visualização agora oferece recursos aprimorados de personalização, incluindo a capacidade de personalizar a estrutura da coluna, o agrupamento, os filtros e salvar as alterações como um layout. Os usuários individuais podem criar até 50 layouts privados, enquanto os usuários administradores podem criar até 50 layouts públicos. Isso representa um aumento em relação ao limite anterior de 30 layouts em configurações públicas e privadas no Expenses Legacy View.

Em uma versão futura, ainda este ano, os usuários também poderão sincronizar os layouts existentes do Expenses Legacy View com o New View, garantindo a continuidade e a facilidade de transição.

![layout padrão](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.73-rn.jpg)

Para obter mais informações, consulte [Layouts de tabela](../planning/customize-save-share-apx.html).

Correções de bugs

- Foi solucionado um bug que impedia a atualização dos valores de comparação ao navegar para um departamento específico a partir da página Status com uma comparação ativa.
- Foi corrigido um erro que fazia com que o uso do método de alinhamento "Matching Fiscal Years" para adicionar uma comparação fizesse com que os valores de comparação fossem exibidos em branco.
- Correção de um problema em que a mensagem de erro para adicionar um código de projeto duplicado era exibida incorretamente como "Erro do servidor, tente novamente"

## 3.72 - 15 de julho de 2024

A partir de segunda-feira, 15 de julho de 2024, os principais locatários de produção começarão a fazer o upgrade para a versão 3.72. Apptio lançará os seguintes recursos nesta versão.

Despesas no modo de tela cheia

A tabela de despesas agora suporta o modo de tela cheia. Essa configuração permite que os usuários maximizem o espaço da tela para visualizar e editar com eficiência as linhas de despesas. Observe que a experiência da tabela New View é necessária para ativar o modo de tela cheia.

![imagem](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.72-1.jpg)

Para obter mais informações, consulte [Trabalhando com itens da linha Apex](../planning/working-with-apex-line-items.html "Este tópico explica como gerenciar itens de linha do Apex no aplicativo, incluindo adição, inserção, duplicação, importação, exportação e exclusão de itens de linha.").

Delegação de contratos

Os usuários agora podem delegar despesas de contrato a um centro de custo diferente a partir de uma data especificada. Esse aprimoramento permite a alocação precisa das despesas ao centro de custo apropriado. Para projetos com várias fases (por exemplo, construção/execução), delegar despesas a centros de custo específicos ajuda a acompanhar o desempenho financeiro de cada fase do projeto de forma eficaz.

![painel de imagens](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.72-3.jpg)

Para obter mais informações, consulte [Custos de projetos delegados](../planning/iip/delete-project-costs.html).

Calendário de trabalho mensal fixo

Integrated
Investment Planning agora suporta um calendário de trabalho mensal fixo, que permite aos usuários definir um número total fixo de horas de trabalho por mês. Esse recurso permite a conversão de alocações de atividades de mão de obra FTE em alocações de atividades de mão de obra por hora.

![adicionar configuração de calendário](../../../../../03-media/apptio-planning/resources/images/it_planning_images/fixed-cal1.jpg)

![configuração do calendário](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.72-5.jpg)

Para mais informações, consulte o [Calendário de Trabalho](../planning/configure-working-days.html "O calendário de trabalho define quantos dias e horas de trabalho são usados para o planejamento de mão de obra, o que influencia a conversão de equivalentes de tempo integral (FTE), a amortização de custos de mão de obra e os cálculos de despesas mensais.").

Correções de bugs

- Anteriormente, quando os valores reais estavam vazios na página Gerenciamento de despesas e um usuário tentava atualizar os valores reais no plano para todos os meses com valores reais vazios, as linhas do plano de previsão não eram excluídas como esperado. Esse problema já foi corrigido.
- Correção de um problema de aparência e resolução com o logotipo Apptio em mensagens automáticas usadas para informar os usuários sobre atualizações do fluxo de trabalho do Plano.
- Implementou uma correção para garantir que, quando as Regras de alocação de mão de obra e Remuneração base não estiverem presentes, as colunas de total do ano fiscal na guia Mão de obra sejam exibidas corretamente

## 3.71 - 2 de julho de 2024

A partir de terça-feira, 02/07/2024, os principais locatários de produção começam a fazer upgrade para a versão 3.71. Apptio está lançando o seguinte recurso nesta versão secundária.

Visualizar Custo de mão de obra totalmente onerado

Os responsáveis pelo orçamento agora podem visualizar facilmente o custo total da mão de obra diretamente nas colunas Expenses > Labor > FY total, eliminando a necessidade de navegar até a seção Expenses > Summary para obter essas informações. Anteriormente, essa coluna exibia apenas a Remuneração base x Quantidade.

Por exemplo, na guia Trabalho, você pode ver uma linha de trabalho com um FY24 total de US$ 196.888. Esse valor representa o custo de mão de obra totalmente onerado, calculado com base nas regras de alocação de mão de obra configuradas.

![custo total da mão de obra](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.71-1.jpg)

O custo de mão de obra totalmente onerado é a soma das contas do razão geral geradas a partir das Regras de alocação de mão de obra na guia Resumo. Como mostrado, o total de FY24 na guia Resumo corresponde ao total de FY24 na guia Trabalho.

![resumo](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.71-2.jpg)

## 3.70 - 17 de junho de 2024

A partir de segunda-feira, 17/06/2024, os principais locatários de produção começarão a fazer upgrade para a versão 3.70. Apptio está lançando os seguintes recursos nesta versão secundária.

- Seleção do centro de custos de recursos : Agora é possível reconhecer facilmente o centro de custos bloqueado no menu suspenso Centro de custos de recursos em Despesas Nova visualização > Atividade de trabalho. Uma mensagem de validação é exibida quando o centro de custo bloqueado é selecionado para alocar recursos de mão de obra a um projeto. Para saber mais, veja [aqui](../planning/iip/allocate-labor-project.html).
- Finalizar plano : Uma nova opção "Finalize Plan" (Finalizar plano) foi adicionada ao menu de ação New Expense (Nova despesa).

  ![finalizar o plano](../../../../../03-media/apptio-planning/resources/images/it_planning_images/finalize-plan.jpg)

## 3.69 - 26 de maio de 2024

A partir de segunda-feira, 26/05/2024, os principais locatários de produção começarão a fazer upgrade para a versão 3.69. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção

Esta versão contém atualizações de manutenção do sistema.

## 3.68 - 22 de abril de 2024

A partir de segunda-feira, 22/04/2024, os principais locatários de produção começarão a fazer upgrade para a versão 3.68. Apptio está lançando os seguintes recursos nesta versão secundária.

- Mostrar/ocultar colunas de período - Agora você pode ativar o agrupamento em Despesas > Nova visualização. Esse recurso permite que você mostre/oculte as colunas Mês, Trimestre e Ano. Para saber mais, consulte [Trabalhando com colunas Apex](../planning/working-with-apex-columns.html "Quando um administrador ou proprietário de processo orçamentário ativa o recurso Apex Line Item Table, os usuários com função não administrativa podem alterar a visualização da tabela entre Classic View e New View.").
- Alinhamento do exercício da análise de desvio - Agora é possível alinhar o exercício do plano de comparação na análise de desvio para corresponder ao exercício do plano de origem. Para saber mais, consulte [Analisar variação orçamentária](../planning/analyze-budget-variance.html "O recurso Variance Analysis ajuda a comparar um plano de previsão atual com uma linha de base (orçamento ou previsão anterior), identificar diferenças significativas e criar uma trilha de comentários que explique os fatores por trás das variações.").

## 3.67 - 8 de abril de 2024

A partir de segunda-feira, 08/04/2024, os principais locatários de produção começarão a fazer upgrade para a versão 3.67. Apptio está lançando os seguintes recursos nesta versão secundária.

- Análise de alocação de atividades de mão de obra - Agora é possível configurar limites de alocação excessiva e insuficiente para o planejamento de atividades de mão de obra em nível de recursos. Isso permite que os usuários analisem a demanda de mão de obra em relação à capacidade de mão de obra e tomem decisões informadas sobre a utilização, a realocação, a contratação e o equilíbrio entre trabalho e recursos. Para saber mais, consulte [Ativar/desativar atividade trabalhista.](../planning/iip/enable-disable-labor-activity.html)
- Atualizar dados reais - Agora é possível atualizar os dados reais em um plano de previsão existente, esteja ele no estado Novo ou Aberto. Isso elimina a necessidade de recriar o plano de previsão para atualizar os dados reais, resultando em economia de tempo e maior eficiência no ciclo de previsão mensal. Para saber mais, consulte “[Atualizar dados reais](../planning/update-actuals-data.html) ”.

## 3.66 - 26 de março de 2024

A partir de segunda-feira, 26/03/2024, os principais locatários de produção começarão a fazer upgrade para a versão 3.66. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção

Esta versão contém atualizações de manutenção do sistema.

## 3.65 - 11 de março de 2024

A partir de segunda-feira, 11/03/2024, os principais locatários de produção começam a fazer upgrade para a versão 3.65 Apptio está lançando os seguintes recursos nessa versão secundária.

## 3.64 - 26 de fevereiro de 2024

A partir de segunda-feira, 26/02/2024, os principais locatários de produção começarão a fazer upgrade para a versão 3.64. Apptio está lançando os seguintes recursos nesta versão secundária.

- Análise de variação : Esse recurso é usado para sinalizar a variação de despesas causada por despesas relatadas em um plano, mas ausentes em outro plano. Para saber mais, consulte “[Analisar variação orçamentária](../planning/analyze-budget-variance.html "O recurso Variance Analysis ajuda a comparar um plano de previsão atual com uma linha de base (orçamento ou previsão anterior), identificar diferenças significativas e criar uma trilha de comentários que explique os fatores por trás das variações.") ”.
- Evitar a alocação excessiva : Esse recurso garante que os recursos de mão de obra não sejam alocados em excesso a projetos ou investimentos durante o Planejamento de Atividades de Mão de Obra, aumentando assim a eficiência do gerenciamento de recursos. Para saber mais, consulte [Análise de alocação excessiva/subalocada de atividade de trabalho](../planning/iip/manage-over-under-allocation.html).
- Modo denso : Agora você pode ativar o Dense Mode em Expenses > New View. Esse recurso aplica as últimas alterações de estilo à tabela, otimizando o uso do espaço e permitindo a acomodação do máximo de linhas. Para saber mais, consulte [Trabalhando com tabelas Apex](../planning/working-with-apex-table.html "Quando um administrador ou proprietário de processo orçamentário ativa o recurso Apex Line Item Table, os usuários com função não administrativa podem alterar a visualização da tabela entre Classic View e New View. Este tópico fornece instruções sobre o gerenciamento de tabelas do Apex, incluindo a alteração de visualizações, a seleção de intervalos de datas e o ajuste de opções de tabela.").
- Criação de plano assíncrono (GA) : A criação de planos assíncronos será ativada em todos os ambientes principais a partir de 4 de março de 2024. O processo de criação de planos agora é assíncrono. Os usuários podem iniciar o processo de criação do plano e continuar a usar o aplicativo Planning para realizar outras tarefas. Quando o plano for criado, o usuário será notificado. Para saber mais, consulte [Criação de plano assíncrono.](../planning/create-budget-plan.html)

## 3.63 - 12 de fevereiro de 2024

A partir de segunda-feira, 12/02/2024, os principais locatários de produção começarão a fazer upgrade para a versão 3.63. Apptio lança o Bulk Delete Expenses nessa versão secundária.

Excluir despesas em massa

Agora é possível selecionar várias linhas de despesas e excluí-las com um único clique usando Expenses > New View (Despesas > Nova visualização ).

Para obter mais informações, consulte [“Exclusão em massa de despesas”](../planning/working-with-apex-line-items.html "Este tópico explica como gerenciar itens de linha do Apex no aplicativo, incluindo adição, inserção, duplicação, importação, exportação e exclusão de itens de linha.")

## 3.62 - 29 de janeiro de 2024

A partir de segunda-feira, 29/01/2024, os principais locatários de produção começarão a fazer upgrade para a versão 3.62. Nesta versão secundária, o produto "Planejamento de TI" é renomeado para "Planejamento". Essa alteração não afeta nenhuma funcionalidade existente.

Algumas das alterações de UX para alinhar com a nova nomenclatura do produto são mostradas abaixo:

Aplicativo de porta de entrada tile/switcher

![nome antes](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/name-before.jpg)

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/name-after.jpg)

Painel de navegação esquerdo

![nome após](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/left-navigate-ba.jpg)

Apptio BI nome da coleção de relatórios

![aplicativo](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/apptio-bi-ba.jpg)

Gráficos de resumo e de painel

O dashboard e os gráficos de resumo foram renomeados para Spend Breakdown, Spend Waterfall, Spend Tends e Spend Variances, respectivamente.

![após o resumo](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/summary-after.jpg)

![variações de gastos](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/dash-after.jpg)

## 3.61 - 15 de janeiro de 2024

A partir de segunda-feira, 15/01/2024, os principais locatários de produção começarão a fazer upgrade para a versão 3.61. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção

Esta versão contém atualizações de manutenção do sistema.
