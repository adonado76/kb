---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "notas de versão 2023"
breadcrumb:
  - "Planning"
  - "Notas sobre a liberação"
source_path: "it-planning/release-notes/whats-new-2023.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# notas de versão 2023

## 3.60 - 25 de dezembro de 2023

A partir de segunda-feira, 25/12/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.60. Apptio está lançando os seguintes recursos nessa versão secundária.

- Criação de plano assíncrono (Beta) : O processo de criação de planos agora é assíncrono. Os usuários podem iniciar o processo de criação do plano e continuar a usar o aplicativo Planning para realizar outras tarefas. Quando o plano for criado, o usuário será notificado. *Na versão beta, esse recurso estará disponível apenas nos ambientes sandbox (não principais).* Para saber mais, consulte [Criação de plano assíncrono.](../planning/create-budget-plan.html)
- Automated Data Management : As configurações de conexão são definidas automaticamente quando a integração do ADM é ativada no Company Profile. Para obter mais informações, consulte [Pré-requisitos](../planning/adm/adm_prerequisites.html).
- Confirmação de exclusão de linha de despesas - Uma caixa de diálogo de confirmação será exibida antes da exclusão de um item de linha de despesas. Este recurso está disponível em Despesas > Nova visualização. Para saber mais, consulte [Excluindo itens de linha](../planning/working-with-apex-line-items.html "Este tópico explica como gerenciar itens de linha do Apex no aplicativo, incluindo adição, inserção, duplicação, importação, exportação e exclusão de itens de linha.").

## 3.59 - 11 de dezembro de 2023

A partir de segunda-feira, 11/12/2023, os principais locatários de produção começam a fazer upgrade para a versão 3.59. Apptio está lançando os seguintes recursos nessa versão secundária.

## Comparação de planos sobre mão de obra

Agora é possível comparar os dados trabalhistas entre dois planos usando a nova visualização de despesas. Para saber mais, consulte [Comparar o número de funcionários](../planning/analyze-labor-headcount.html)

## Dados de atividade de trabalho FTE em Apptio BI

Agora é possível criar relatórios Apptio BI para Atividade de Trabalho usando FTE como unidade de quantidade, além de Horas como unidade de quantidade atualmente suportada. Para saber mais, consulte [os dados sobre a atividade laboral em tempo integral](../planning/ssr/fte-labor-activity-data.html "Atualmente, os dados disponíveis no site Apptio BI suportam apenas dados de horas, mas para o IIP o planejamento da atividade de trabalho é ativado usando tanto a unidade de horas quanto a de FTE. Esse recurso permite que os usuários criem relatórios de alocação usando FTE para que possam analisar o relatório de alocação usando a capacidade, os detalhes de utilização e os dados de alocação mensal por recurso.").

## 3.58 - 27 de novembro de 2023

A partir de segunda-feira, 27/11/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.58. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.

## 3.57 - 13 de novembro de 2023

A partir de segunda-feira, 13/11/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.57. Nesta versão secundária, o site Apptio oferecerá suporte à importação automatizada de reais da Transparência de custos para o Gerenciamento de despesas por meio do site Data Management automatizado.

## Importação automatizada de dados reais

Agora será possível importar automaticamente os dados reais da Transparência de custos para o Gerenciamento de despesas usando o site automatizado Data Management. Para saber mais sobre ApptioOne Planejamento e Integração Data Management Automatizada, consulte [Visão Geral do ADM.](../planning/adm/adm_overview.html "O Costing & Planning está integrado ao serviço da plataforma Automated Data Management, que permite o compartilhamento automatizado de dados do Costing & Planning Cost (Costing Standard) para o Costing & Planning Plan (Planning), além de permitir a importação de dados planejados sob demanda do Costing Standard para um plano específico.")

Para saber mais sobre como importar dados reais com o Automated Data Management, visite [Importar dados reais](../planning/adm/adm_import_actuals.html "A importação de dados reais traz dados históricos de gastos do Apptio Cálculo de custos para Apptio o Planejamento, onde podem ser usados para previsões, análises de variação e comparações de planos.").

## 3.56 - 30 de outubro de 2023

A partir de segunda-feira, 30/10/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.56. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.

## 3.55 - 16 de outubro de 2023

A partir de segunda-feira, 16/10/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.55. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.

## 3.54 - 3 de outubro de 2023

A partir de segunda-feira, 10/03/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.54. Apptio está lançando os seguintes recursos nessa versão secundária.

## Identificador único externo para linhas de despesas

As linhas de despesas agora suportam o External Unique Code. Os usuários podem definir um código exclusivo para cada linha de despesa.

Ao atualizar as despesas existentes:

- O código do item de linha tem precedência sobre o código externo se ambos estiverem presentes.
- Se o código do item de linha estiver faltando, o código externo será usado para atualizar as despesas existentes.
- Caso o código do item de linha corresponda às linhas existentes e às linhas importadas, mas o código externo seja diferente, a operação será tratada como uma atualização do código externo.

Para ativar o recurso, navegue até Company Profile > Settings e clique em Enable External Code e Save Changes.

Para saber mais, consulte [Identificador Externo Único](../planning/external-unique-identifier.html "Quando você importa ou atualiza dados de despesas (por exemplo, mão de obra, atividade de mão de obra, contratos, ativos) de sistemas externos (sistemas de RH, bancos de dados de fornecedores, etc.), Você precisa de um identificador consistente e exclusivo para corresponder as linhas do seu plano aos registros no sistema de origem.").

## Integrated Investment Planning Recursos

## Atualizar dados da lista de projetos

Na versão ApptioOne Plan 3.54, simplificamos o processo de atualização da lista de projetos usando os projetos de Reference Data > Projects. Use a opção Atualizar dados do projeto no menu Projetos > Ações de lista para atualizar os projetos na Lista de projetos com Dados de referência > Projetos.

![imagem](../../resources/images/it%20planning_images/proj-list-data.png)

Para saber mais, visite a seção [Upgrade Reference Data](../planning/iip/project-list-document.html) in Plan.

## Selecione Grupos de projetos no menu suspenso Projetos

Agora é possível selecionar Grupo(s) de Projeto(s) no menu suspenso Projetos. A seleção de um grupo de projetos selecionará automaticamente todas as entidades filhas, seja um ou mais grupos de projetos ou um ou mais projetos.

![imagem](../../resources/images/it%20planning_images/pg-projects.png)

Observação: Caso você tenha uma hierarquia de projetos em que o Grupo de projetos não tenha nenhum projeto secundário, esses grupos de projetos não serão exibidos no menu suspenso Projetos no momento. Por exemplo, considere a hierarquia do projeto abaixo. Nesse caso, o Grupo de Projetos 1 não é mostrado no menu suspenso de projetos, mas o Projeto Group2, o Projeto Group3 e o Grupo de Projetos 4 são mostrados. Essa é uma limitação da versão 3.54. Estamos trabalhando para melhorá-la e mostrar todos os grupos de projetos.

Projetos Group1

- Projeto Group2
  - Project1
  - Project2
- Projeto Group3
  - Project3
  - Project4
  - Projeto Group4
    - Project5

## Resumo de atividades trabalhistas

Agora é possível visualizar os atributos relacionados de um recurso, como fornecedor, local, código externo, função etc. em Despesas > Atividade de trabalho.

Para resumir os dados de atividade de mão de obra por atributos relevantes de recursos de mão de obra, como Fornecedor, Local, Função, ative os atributos necessários na caixa de diálogo Mostrar/Ocultar colunas....

![imagem](../../resources/images/it%20planning_images/3.54-labor.png)

## 3.53 - 18 de setembro de 2023

A partir de segunda-feira, 18/09/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.53. Apptio está lançando o suporte para o tipo de custo no Spend Management.

## Tipo de custo no gerenciamento de despesas

Os clientes que usam o site Integrated Investment Planning agora podem ver o Tipo de custo como uma coluna pronta para uso no Gerenciamento de despesas. Isso ajudará a identificar as despesas reais como de construção ou execução. Agora será possível extrair dados reais como construção ou execução em planos de previsão. Se o valor não for fornecido, o valor padrão Run será aplicado aos valores reais carregados.

![imagem](../../resources/images/it%20planning_images/release-notes/3.53-rn_987x238.png)

## 3.52 - 4 de setembro de 2023

A partir de segunda-feira, 04/09/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.52. Apptio está lançando o suporte para salvar a comparação ano a ano (YTD) no atalho de comparação.

## Salvar a comparação ano a ano (YTD) no atalho de comparação

As comparações de planos criadas usando o Comparison Shortcut também suportam e salvam a comparação ano a ano (YTD) para os planos de previsão. Para saber mais, consulte [Comparar versões ou planos.](../planning/compare-versions-plans.html "Você pode comparar os dados financeiros entre dois períodos ou versões do mesmo plano, ou entre dois planos diferentes. Essas comparações revelam diferenças entre períodos de tempo e itens de linha para ajudá-lo a entender as mudanças e variações.")

## 3.51 - 21 de agosto de 2023

A partir de segunda-feira, 21/08/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.51. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.
:   Criação de plano assíncrono - Devido a um problema de produção observado recentemente, desativamos temporariamente o recurso de criação de plano assíncrono. A criação do plano será executada como uma solicitação síncrona, como anteriormente, até que o recurso seja reativado. O recurso voltará a ser ativado na versão ApptioOne 3.54.

## 3.50 - 7 de agosto de 2023

A partir de segunda-feira, 07/08/2023, os principais locatários de produção começam a fazer upgrade para a versão 3.50. Apptio está lançando o suporte para Soft Plan Delete nesta versão secundária.

## Plano de exclusão suave

O processo de exclusão do plano agora ocorre em duas etapas.

- Soft Delete (Exclusão suave ) - O plano é removido da interface do usuário assim que um administrador clica no botão Delete (Excluir) na página Plans (Planos). O plano excluído não estará mais acessível aos usuários.
- Hard Delete (Exclusão definitiva ) - Os dados do plano são excluídos automaticamente, dois dias após a exclusão definitiva.

Os administradores não precisam mais esperar pelo longo processo de exclusão de planos; exclua um plano rapidamente e depois prossiga com outras tarefas. Caso você exclua acidentalmente algum plano, há um período de dois dias para restaurar os dados do plano registrando um tíquete de suporte em Apptio.

► Saiba mais sobre: [Gerenciar planos](../planning/manage-plans.html "Com a página Plans, você pode gerenciar seus planos de forma fácil e intuitiva.")

## 3.49 - 24 de julho de 2023

A partir de segunda-feira, 24/07/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.49. Apptio está lançando o suporte à criação de planos assíncronos e ao controle de acesso no nível do projeto (Beta) nesta versão secundária.

## Controle de acesso em nível de projeto (Beta)

- Somente IIP: Conceder permissões a usuários, como gerentes de projeto/produto, com base em cada projeto. (Independente do orçamento do departamento).
- Somente IIP: Esses usuários podem visualizar as despesas de um ou mais projetos usando o filtro de hierarquia de projetos.

► Saiba mais sobre [:Controle de acesso em nível de projeto](../planning/iip/project-level-access-control.html)

## Criação de plano assíncrono

O processo de criação de planos agora é assíncrono. Os usuários podem iniciar o processo de criação do plano e continuar a usar o aplicativo Planning para realizar outras tarefas. Quando o plano for criado, o usuário será notificado.

► Saiba mais: [Criação de planos assíncronos](../planning/create-budget-plan.html)

## 3.48 - 10 de julho de 2023

A partir de segunda-feira, 10/07/2023, os principais locatários de produção começam a atualizar para a versão 3.48. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.

## 3.47 - 26 de junho de 2023

A partir de segunda-feira, 26/06/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.47. Apptio está lançando o suporte para adicionar e excluir automaticamente dimensões personalizadas em Automated Data Management > Entity Mapping nesta versão secundária.

## Automatizado Data Management

Esse recurso é aplicável se o Data Management automatizado estiver ativado.

O Costing & Planning está integrado ao serviço da plataforma Automated Data Management, que permite o compartilhamento automatizado de dados do Costing & Planning Cost (Costing Standard) para o Costing & Planning Plan (Planning) e oferece a capacidade de importar dados do plano sob demanda do Costing Standard para um plano específico. Para saber mais, consulte [Visão geral do ADM](../planning/adm/adm_overview.html "O Costing & Planning está integrado ao serviço da plataforma Automated Data Management, que permite o compartilhamento automatizado de dados do Costing & Planning Cost (Costing Standard) para o Costing & Planning Plan (Planning), além de permitir a importação de dados planejados sob demanda do Costing Standard para um plano específico.").

- Adicionar automaticamente o mapeamento de entidades em Automated Data Management quando uma nova dimensão personalizada for criada no ITP
- Excluir automaticamente o mapeamento de entidades no Automated Data Management quando uma dimensão personalizada for excluída no ITP

► Saiba mais sobre: [Mapeamento de entidades de dimensões personalizadas](../planning/adm/custom-dimension-entitiy-metric.html)

## 3.46 - 12 de junho de 2023

A partir de segunda-feira, 12/06/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.46. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.

## 3.45 - 29 de maio de 2023

A partir de segunda-feira, 29/05/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.45. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.

## 3.44 - 15 de maio de 2023

A partir de segunda-feira, 15/05/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.44. Apptio está lançando o suporte para intervalos de datas personalizados com fontes de dados Planning nesta versão secundária.

## Intervalos de datas personalizados para os relatórios do site Apptio BI

ApptioOne As fontes de dados de planejamento em Apptio BI agora suportam os seguintes períodos personalizados para visualizações:

- Mês
- Trimestre
- Metade
- Ano

Esses períodos personalizados são fornecidos além dos intervalos de datas existentes. Você também pode usar a opção Rolling and Compare com esses períodos personalizados. Para obter mais detalhes, acesse [Intervalos de datas personalizados](../planning/ssr/custom-date-ranges.html "Os clientes do Costing & Planning agora podem criar relatórios de vários anos usando intervalos de datas personalizados.").

## 3.43 - 2 de maio de 2023

A partir de segunda-feira, 02/05/2023, os principais locatários de produção começam a fazer upgrade para a versão 3.43. Apptio está lançando a ocultação aprimorada de dados confidenciais nesta versão secundária.

## Ocultação aprimorada de dados confidenciais

Se você tiver uma estrutura organizacional em que há usuários que gerenciam o número de funcionários e os dados financeiros de seus respectivos departamentos ou grupos de departamentos, será necessário fornecer a eles permissões de edição para os respectivos departamentos ou grupos de departamentos. Mas, ao mesmo tempo, se quiser que esses usuários possam visualizar as finanças ou o número de funcionários da mão de obra em uma hierarquia de departamento mais alta, excluindo os dados confidenciais para visibilidade e conhecimento, você terá necessidades muito específicas para gerenciar os dados confidenciais da mão de obra para esse caso de uso.

Por exemplo,

![imagem](../../resources/images/it%20planning_images/release-notes/esdh-example.png)

No exemplo acima, o usuário CCO2 recebeu acesso de Editor no departamento APPDEV. Como as permissões são distribuídas em cascata de cima para baixo na hierarquia de objetos de custo, o site CCO2 obterá automaticamente o acesso de Editor na hierarquia de objetos de custo filho para o APPDEV, independentemente de o acesso específico ser ou não fornecido ao usuário CCO2.

Observe que o usuário CCO2 não recebe o acesso Can View Sensitive Columns no nível APPDEV. Mas o usuário CCO2 tem acesso ao Can View Sensitive Columns no APPDEV L3, uma hierarquia de objetos de custo filho no APPDEV.

Com as novas alterações na versão ApptioOne Planning 3.43, introduzimos um comportamento de cascata de permissão diferente para as permissões de dados confidenciais. O que permite controlar as permissões em nível granular.

No exemplo acima, como o usuário CCO2 não tem permissão para visualizar colunas confidenciais no nível do APPDEV, a mesma permissão será aplicada em cascata na hierarquia de departamentos até encontrar um objeto de custo/departamento, grupo ou folha, em que a permissão para visualizar colunas confidenciais seja fornecida. Se ele encontrar uma, essa permissão terá precedência sobre a permissão de nível superior.

Devido a essa alteração, agora é possível fornecer ao usuário CCO2 acesso para visualizar colunas confidenciais no APPDEV L3, mesmo que CCO2 não tenha permissão para visualizar colunas confidenciais em um objeto de custo de nível superior APPDEV.

Você também notará que o usuário CCO2 recebeu acesso explícito para visualizar colunas confidenciais nos objetos de custo de folha APP-BO e APP-SALES, mas não há nenhuma permissão explícita de Can View Sensitive Columns concedida em APP-LOB. Mas, independentemente disso, o site CCO2 poderá visualizar colunas confidenciais no APP-LOB porque a permissão do objeto de custo de nível superior APPDEV L3 será transferida em cascata para os objetos de custo filhos de nível inferior. Em resumo, não é necessário dar permissão explícita para visualizar colunas confidenciais em todos os objetos de custo de folha do APPDEV L3. Se a permissão para visualizar colunas confidenciais for fornecida no APPDEV L3, ela será transferida em cascata para os objetos de custo de nível inferior no APPDEV L3.

Confira as capturas de tela abaixo para entender a diferença entre o comportamento antigo e o novo ao lidar com permissões de dados confidenciais.

## Comportamento anterior (antes do ApptioOne Plan 3.43 )

![imagem](../../resources/images/it%20planning_images/release-notes/esdh-prev.png)

## Novo comportamento (após a versão do ApptioOne Plan 3.43 )

![imagem](../../resources/images/it%20planning_images/release-notes/esdh-current.png)

O exemplo acima é específico para as permissões Can View Sensitive Columns, mas as mesmas regras também se aplicam à permissão Can View Sensitive Financials.

OBSERVAÇÃO: As permissões de dados não confidenciais (Editor, Owner e View Only) funcionam da mesma forma que antes. A alteração é específica apenas para permissões de dados confidenciais.

## 3.42 - 19 de abril de 2023

A partir de segunda-feira, 19/04/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.42. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.

## 3.41 - 12 de abril de 2023

A partir de segunda-feira, 12/04/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.41. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.

## 3.40 - 20 de março de 2023

A partir de segunda-feira, 20/03/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.40. Esta versão secundária anuncia o lançamento do recurso Lista de projetos.

## Lista de projetos

Os clientes que usam o site Integrated Investment Planning agora podem visualizar todos os projetos ou investimentos junto com seus atributos em uma exibição de lista no nível do plano. Usando a visualização de lista, os usuários administrativos agora podem adicionar, editar ou excluir projetos em um nível de plano.

![imagem](../../resources/images/it%20planning_images/project-list.png)

![imagem](../../resources/images/it%20planning_images/project-list-view.png)

► Saiba mais: [Lista de projetos](../planning/iip/project-list-document.html)

## 3.39 - 20 de fevereiro de 2023

A partir de segunda-feira, 20/02/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.39. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.

## 3.38 - 6 de fevereiro de 2023

A partir de segunda-feira, 06/02/2023, os principais locatários de produção começam a atualizar para a versão 3.38. Esta versão contém apenas atualizações de manutenção.

Somente versão de manutenção
:   Esta versão contém atualizações de manutenção do sistema.

## 3.37 - 23 de janeiro de 2023

A partir de segunda-feira, 23/12/2023, os principais locatários de produção começarão a fazer upgrade para a versão 3.37. Essa versão secundária lança a capacidade de ativar/desativar a guia Expenses Labor Activity e aprimoramentos na New Expenses View.

## Ativar/desativar a ficha Atividade de trabalho

Os clientes que usam [Integrated Investment Planning](../planning/iip/gs-integrated-investment-planning.html) agora podem ativar ou desativar a guia Labor Activity (Atividade de trabalho) na página Expenses (Despesas) usando as configurações na página Company Profile (Perfil da empresa).

## Página de despesas Nova visualização

Página Despesas A nova visualização foi atualizada para mostrar as subguias All, Opex e Capex na guia Despesas > Resumo. A operação de atualização de dados de referência também é suportada agora a partir da Nova visualização.

Para ativar a "Nova visualização" em Despesas, consulte [Ativar a tabela de itens de linha do Apex.](../planning/enable-apex-line-item-table.html)
