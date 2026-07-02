---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Planejamento: O que há de novo em 2020"
breadcrumb: []
source_path: "it-planning/release-notes/whats-new-2020.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planejamento: O que há de novo em 2020

## 2.86 - 28 de dezembro de 2020

Novas funcionalidades
:   Mensagens mais detalhadas na página de status da CTI
:   Os usuários agora recebem mensagens mais detalhadas e úteis ao importar e exportar operações no CTI. As mensagens de erro incluem detalhes necessários para depurar e resolver o problema.

Pequenos aprimoramentos
:   Nenhum

## 2.85 - 7 de dezembro a 18 de dezembro de 2020

Somente versão de manutenção
:   Esta versão contém apenas correções de bugs e manutenção para atender aos requisitos operacionais.

## 2.86 - 28 de dezembro de 2020

Novas funcionalidades
:   Renomeação de colunas
:   Os administradores agora podem alterar os nomes das colunas que os usuários veem durante a entrada do item de linha do orçamento. Antes desta versão, só era possível alterar os nomes das colunas para dimensões personalizadas ou colunas de lista; agora é possível fazer isso também para as dimensões do sistema. Para renomear colunas, basta editar a definição da tabela de itens de linha desejada em Dados de referência. O editor de tabelas agora suporta a renomeação de todas as colunas do tipo Lookup e String.

    ![](../../resources/images/it%20planning_images/release-notes/column-renaming.png)

    Figura 1: Edição das definições de coluna da tabela de itens de linha nos dados de referência.

    A renomeação de colunas não requer uma operação de Update Reference para que um plano receba a alteração. Depois de renomeado, os usuários verão o novo nome nos cabeçalhos das colunas da tabela de itens de linha.

    ![](../../resources/images/it%20planning_images/release-notes/colrename-after.png)

    Figura 2: Colunas do sistema renomeadas na Tabela de itens de linha.

    Observação: Renomear uma coluna simplesmente altera o nome de exibição usado na tabela de itens, na caixa de diálogo mostrar/ocultar colunas, na caixa de diálogo de filtro e nos seletores de agrupamento na análise da página Resumo. Ele não altera o "nome de código" subjacente usado nas operações de importação/exportação ou CTI

Amortização manual de contratos
:   Agora, oferecemos suporte à capacidade de importar, inserir e editar manualmente os valores de despesas amortizadas por período para um contrato. Para facilitar isso, adicionamos um método de amortização manual e a capacidade de alterar (substituir) o método de amortização definido pelo tipo de contrato. Como antes, a seleção de um Tipo de contrato preencherá automaticamente o campo Amortização do contrato com o método definido no Tipo de contrato, mas esse campo agora pode ser alterado. Se o método de amortização for definido como Manual, os valores de despesas gerados se tornarão editáveis.

    ![](../../resources/images/it%20planning_images/release-notes/manual-amort.png)

    Figura 3: Método de amortização padrão do tipo de contrato de substituição.

    Um ícone de "redemoinho" será exibido quando o método de amortização padrão do Tipo de contrato for modificado; clicar nele reverterá para o método definido pelo Tipo de contrato e forçará um novo cálculo dos valores de amortização de despesas com base no Valor do contrato atual, na Data de início/fim e em outros campos relevantes (Amortizar, Estender, etc.).

    ![](../../resources/images/it%20planning_images/release-notes/manual-amort-2.png)

    Figura 4: O método de amortização manual permite a modificação direta dos valores das despesas.

    OBSERVAÇÃO: enquanto estiver no modo de amortização manual, quaisquer edições feitas nos parâmetros do contrato (como valor, data de início/fim, extensão etc.) não terão impacto nos valores de despesas por período.

    Agora também é possível importar itens de linha de contrato com valores de despesas por período, em vez de fazer com que o site Planning calcule os valores para você. Para isso, é necessário importar os itens de linha com o Método de amortização do contrato definido como Amortização manual. Se o Tipo de contrato estiver usando um método de amortização diferente, o campo Método de amortização padrão do contrato substituído deverá ser definido como VERDADEIRO.

    ![](../../resources/images/it%20planning_images/release-notes/import-template.png)

    Figura 5: O método de amortização manual pode ser usado para importar diretamente os valores de despesas do contrato (por período).

    Por fim, agora é possível importar itens de linha do contrato como itens de linha externos. As partidas individuais externas são tratadas como originárias de um sistema externo e somente leitura em Planning. Use isso em conjunto com a amortização manual do contrato para trazer valores de despesas periódicas do contrato que foram calculados por outro sistema.

    ![](../../resources/images/it%20planning_images/release-notes/external-line-items.png)

    Figura 6: Importação de itens de linha de contrato externo.

Agrupamento de dimensões e descrições em Apptio BI
:   Agora você pode exibir a lista de dimensões agrupadas pelo tipo de dimensão ao configurar visualizações. Além disso, você pode passar o mouse sobre o ícone de ajuda ao lado do nome da dimensão para ver uma descrição da dimensão.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1%20(3).png)

    Figura 7: Agrupamento de dimensões em Apptio BI

    VEJA TAMBÉM:

    Guia do usuário: [Planning dados no Apptio BI](../planning/it-planning-data-self-servic-reporting.html "Apptio BI permite que os usuários criem e compartilhem seus próprios relatórios personalizados usando dados de vários aplicativos, inclusive o Planning.")

Pequenos aprimoramentos
:   Nenhum

## 2.83 - 9 de novembro a 20 de novembro de 2020

Novas funcionalidades
:   Suporte ao Apex Shell

    O ITP agora é executado no novo shell Apex. Os usuários podem alternar entre o novo painel de navegação à esquerda do shell ou a navegação no estilo da barra de menus atual por meio do menu Perfil do usuário.

    Para obter mais informações sobre o Apex, consulte [Apex Design System: Atualização de navegação](https://community.apptio.com/docs/DOC-13878 "(Abre em uma nova guia ou janela)").

Pequenos aprimoramentos
:   Somente atualizações de manutenção do sistema

## 2.82 - 2 de novembro de 2020

Novas funcionalidades
:   Suporte ao estilo Apex
:   Fizemos pequenas alterações no estilo de nossa interface do usuário para nos alinharmos melhor com a aparência do Apex. O Apex é o novo UX comum em todo o site Apptio que será introduzido ainda este ano. Basicamente, mudamos as fontes e as cores para dar aos nossos aplicativos uma aparência mais limpa e moderna. Também modificamos o estilo do cabeçalho do plano (a área logo abaixo dos menus do aplicativo e o início do conteúdo da página) para separá-lo de forma limpa da navegação do aplicativo e proporcionar uma aparência mais nítida, como você pode ver nas imagens abaixo.

    Novo visual e sensação do aplicativo

    ![](../../resources/images/it%20planning_images/release-notes/apex1.png)

    Veja a seguir uma visão mais detalhada das alterações no estilo do cabeçalho do plano. Não há alterações funcionais: tudo continua funcionando da mesma forma, apenas com uma aparência um pouco diferente e melhor.

    Plano anterior Estilo de cabeçalho

    ![](../../resources/images/it%20planning_images/release-notes/apex2.png)

    Novo estilo de cabeçalho de plano

    ![](../../resources/images/it%20planning_images/release-notes/apex5.png)

Dimensões em nível de departamento em Apptio BI
:   Adicionamos novas dimensões (Nível 1 e Nível 2) às fontes de dados Planning Apptio BI. O Nível 1 e o Nível 2 referem-se ao nível superior e ao nível superior seguinte do roll-up de departamento associado ao objeto de custo (departamento) de um item de linha. O Nível 1 é a primeira lista de departamentos que aparece no menu suspenso "All Departments" (Todos os departamentos) em Planning; o Nível 2 é a próxima lista de departamentos que aparece abaixo dos departamentos do Nível 1. Essas dimensões dão suporte a relatórios de nível executivo, fornecendo a agregação de valores de itens planejados até os níveis de departamento do executivo e do gerente sênior.

    ![](../../resources/images/it%20planning_images/release-notes/apex4.png)

    Figura 1: Valores de Nível 1 e Nível 2 na lista suspensa "All Departments" (Todos os departamentos) do site Planning.

    ![](../../resources/images/it%20planning_images/release-notes/apex6.png)

    Figura 2: As dimensões de Nível 1 e Nível 2 podem ser encontradas na configuração de visualização do site Apptio BI, na lista suspensa "Add Dimensions" (Adicionar dimensões)

Pequenos aprimoramentos
:   Nenhum

## 2.81 - 28 de setembro a 9 de outubro de 2020

Novas funcionalidades
:   Oculte dados confidenciais de trabalho dos usuários
:   Agora é possível identificar colunas de trabalho confidenciais e ocultar esses dados de trabalho confidenciais dos usuários no. Primeiro, o administrador identificará as colunas da guia Despesas trabalhistas que são confidenciais e precisam ser ocultadas dos usuários. Em seguida, os usuários que não deveriam ter acesso a dados confidenciais de trabalho podem ter o acesso revogado a esses dados confidenciais de trabalho. Por padrão, os usuários terão acesso aos dados confidenciais do trabalho.

    OBSERVAÇÃO: Após a atualização do locatário do Planning , os usuários existentes continuarão a ter acesso a dados confidenciais de trabalho. Para revogar o acesso de determinados usuários aos dados confidenciais de mão de obra, revogue o acesso do usuário diretamente das permissões do objeto de custo.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1%20(2).png)

    Figura 1: Configurar dados trabalhistas confidenciais

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_3%20(1).png)

    Figura 2: Conceder acesso a dados trabalhistas confidenciais

    VEJA TAMBÉM: Guia do usuário: [Ocultar acesso a dados trabalhistas confidenciais em Planning](https://community.apptio.com/docs/DOC-13724 "(Abre em uma nova guia ou janela)")

Listas de seleção de dependentes
:   As listas de opções dependentes permitem filtrar a lista de valores exibidos em uma lista de opções com base em outros valores no item de linha. Por exemplo, a lista de fornecedores pode ser filtrada pela seleção da classe de ativos atual para mostrar apenas os fornecedores de hardware ou software. As listas de opções dependentes tornam mais fácil para os administradores restringir o número de opções disponíveis para o usuário durante a entrada de dados de itens de linha, melhorando a qualidade dos dados e proporcionando uma melhor experiência de entrada para os usuários.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1%20(2).png)

    Figura 3: A tabela com lista de opções dependente (à direita) é usada para filtrar os resultados, facilitando a escolha

Pequenos aprimoramentos
:   Nenhum

## 2.80 - 28 de setembro a 9 de outubro de 2020

Novas funcionalidades
:   Nenhum

Pequenos aprimoramentos
:   Somente atualizações de manutenção do sistema

## 2.79 - 14 de setembro a 25 de setembro de 2020

Novas funcionalidades
:   Suporte a instâncias compartilhadas de CT em CTI
:   Agora você pode conectar várias instâncias do ITP a uma única instância compartilhada do CT - por exemplo, uma sandbox e um ambiente principal do ITP - usando o Token Auth como método de autenticação.

    Para obter mais informações sobre o processo de configuração, consulte [Integrar com transparência de custos](../planning/integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.") e painel de integração de CT.

Pequenos aprimoramentos
:   Nenhum

## 2.78 - 31 de agosto a 11 de setembro de 2020

Novas funcionalidades
:   Integração aprimorada do Costing Standard (CTI)
:   Aprimoramos a experiência de integração do Costing Standard para oferecer gerenciamento centralizado e importação e exportação com um clique com o Costing Standard. A página de configurações de CTI existente foi substituída por uma página de menu que centraliza todas as tarefas de CTI em um único local, eliminando a complexidade e o tédio do processo de troca de dados com Costing Standard.

    Ao acessar o CTI, você verá um novo painel com as seguintes opções:

    - Configure (Configurar ) - configure e modifique suas configurações de integração.
    - Import Actuals - importação em massa de conjuntos de dados de Actuals do CT
    - Importar dados de referência - importação em massa de conjuntos de dados de referência do CT
    - Publicar - dados do plano de exportação em massa para o CT
    - Status - visualize o status das solicitações de importação e exportação de dados

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_5.png)

    Observação: ainda é possível importar e exportar para o CT diretamente dos dados de referência individuais e das tabelas de partidas individuais planejadas por meio das ações de tabela Importar do CT e Exportar para o CT. A nova experiência de CTI simplesmente oferece um local central para realizar operações de importação e exportação em massa.

    Para obter mais informações sobre o processo de configuração, consulte [Integrar com transparência de custos](../planning/integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.") e painel de integração de CT.

Pequenos aprimoramentos
:   Nenhum

## 2.77 - 14 de agosto de 2020

Novas funcionalidades
:   Nenhum

Pequenos aprimoramentos
:   Atualizações de manutenção do sistema
:   Esta versão inclui apenas manutenção do sistema e correções de bugs.
:   Corrigido nesta versão:

    - As taxas de mão de obra externa agora são editáveis. Os usuários agora podem editar as taxas de mão de obra para itens de linha na tabela Projeto > Atividade > Externa.
    - Adicionamos o botão Atualizar dados de referência à barra de cabeçalho no Gerenciamento de despesas. Anteriormente, essa operação só estava disponível no menu Actions (Ações )

## 2.76 - 31 de julho de 2020

Novas funcionalidades
:   Planning dados em Apptio BI
:   Agora você pode criar e compartilhar relatórios personalizados em Apptio BI usando dados de planos de Planning. Você pode criar e visualizar relatórios em Apptio BI que usam os dados mais recentes do plano em tempo real. Seus relatórios podem apresentar várias visualizações, inclusive visualizações de diferentes fontes de dados. Por exemplo, um único relatório pode conter visualizações dos sites Costing Standard e Planning.

    As despesas do departamento estão disponíveis como fontes de dados Planning Financials, Labor, Contracts ou Assets em Apptio BI. Depois de selecionar uma fonte de dados, você pode selecionar qualquer plano ativo no campo Nome do plano para usar em uma visualização. As dimensões disponíveis para relatórios são as mesmas dimensões disponíveis na guia Despesas do departamento em Planning, incluindo dimensões personalizadas. Além dos intervalos de datas existentes no site Apptio BI, você também pode selecionar o intervalo de datas para o próximo ano, 2 anos futuros e até 6 anos futuros para usar em sua visualização.

    OBSERVAÇÃO: após o upgrade do locatário Planning , se o seu ambiente já tiver Apptio BI, as fontes de dados do ITP estarão disponíveis em Apptio BI dentro de uma hora. Consulte o cronograma completo de implantação aqui. As permissões existentes no nível do objeto de custo Planning serão aplicadas em Apptio BI.

    OBSERVAÇÃO: no momento, esse recurso não está disponível para locatários em execução em GovCloud ou IRAP.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1.png)

Importação de depreciação de ativos existentes
:   Adicionamos um novo método de depreciação manual, o que significa que agora você pode importar e editar valores de depreciação de ativos. Também adicionamos suporte a itens de linha de ativos externos para que você possa importar detalhes de ativos (e valores de depreciação) de um sistema externo para que os proprietários de orçamento possam visualizar, mas não editar, os itens de linha importados.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_3.png)

Pequenos aprimoramentos
:   Nenhum

## 2.75 - 13 de julho de 2020

Novas funcionalidades
:   Nenhum

Pequenos aprimoramentos
:   Somente atualizações de manutenção do sistema

## ITP Apptio BI L1, L2 Dimension - 11 de fevereiro de 2020

◆ Aplica-se a: Planning, Planning Foundation, Project Financial Planning, e/ou Service Demand Planning conforme indicado abaixo.

Nesta versão:

- [Dimensões de nível 1 e nível 2 do departamento em Apptio BI](whats-new-2020.html)
- [Mantenha-se informado sobre as atualizações de produtos](whats-new-2020.html)

## Dimensões de nível 1 e nível 2 do departamento em Apptio BI

Agora você pode selecionar duas novas dimensões (Nível 1 e Nível 2) nas fontes de dados Planning em Apptio BI. O Nível 1 e o Nível 2 são o nível superior e o próximo nível superior de roll-up de departamento associado ao objeto de custo do item de linha. O Nível 1 é a primeira lista de departamentos que aparece na lista suspensa "All Departments" (Todos os departamentos) em Planning ao selecionar o departamento para visualizar o plano. O Nível 2 é a segunda lista de departamentos que apareceria sob o Nível 1 na lista suspensa "Todos os departamentos". Isso permitirá que o usuário crie uma visualização que agregue o plano para os níveis de departamento do executivo e do gerente sênior, a fim de produzir relatórios executivos.

![](../../resources/images/it%20planning_images/itp-ssr-l1-l2-dimension-1_700x355.png)

Figura 1: Valores de Nível 1 e Nível 2 na lista suspensa "All Departments" (Todos os departamentos) do site Planning. 1 indica o valor do Nível 1, enquanto 2 indica o valor do Nível 2.

![](../../resources/images/it%20planning_images/itp-ssr-l1-l2-dimension-2_700x502.png)

Figura 2: As dimensões de Nível 1 e Nível 2 podem ser encontradas na configuração de visualização do site Apptio BI, na lista suspensa "Add Dimensions" (Adicionar dimensões).

VEJA TAMBÉM:

- [Use os dados do Planning em Apptio BI](https://community.apptio.com/docs/DOC-13547 "(Abre em uma nova guia ou janela)")
- [Planning dados expostos a Apptio BI](https://community.apptio.com/docs/DOC-13513 "(Abre em uma nova guia ou janela)")

## Mantenha-se informado sobre as atualizações de produtos

Para ser notificado quando esta página for atualizada, clique no menu Ações (engrenagem) no canto superior direito desta tela e, em seguida, clique em Seguir. Um link para o tópico atualizado aparecerá em sua [caixa de entrada da comunidade Apptio](https://community.apptio.com/inbox "(Abre em uma nova guia ou janela)"). Você também pode ver todos os detalhes históricos das versões do produto; consulte Planning and Financial Management: [What's New (Cumulative) and Upcoming Releases (Novidades (Cumulativas) e Próximas Versões](https://community.apptio.com/docs/DOC-1302 "(Abre em uma nova guia ou janela)") ).

MAIS RECURSOS:

- Consulte também [Planning Programação de manutenção semanal](https://community.ibm.com/community/user/viewdocument/maintenance-schedule-update?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Abre em uma nova guia ou janela)").
- Veja se os aplicativos Apptio Planning têm algum problema conhecido atualmente em [Apptio Known Issues](https://community.ibm.com/community/user/viewdocument/introducing-known-issues-it-planni?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Abre em uma nova guia ou janela)").
