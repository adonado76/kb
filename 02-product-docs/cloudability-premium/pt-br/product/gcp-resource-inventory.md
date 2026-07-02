---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "GCP Inventário de recursos"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Inventário de recurso"
source_path: "product/gcp-resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Inventário de recursos

GCP O recurso Inventário de Recursos do Cloudability permite que você produza uma lista confiável dos recursos em nuvem do GCP que existiam e foram cobrados durante um período específico de relatório. Você tem a flexibilidade de criar essa lista a partir de recursos que abrangem várias contas e escolher entre diferentes medidas (dimensões e métricas) para exibir os detalhes relevantes para elas. Essas informações, disponíveis para cada recurso de nuvem, unificam o faturamento, a utilização e os metadados descritivos para oferecer uma visão mais abrangente do inventário.

## Introdução

GCP O recurso de relatórios de inventário de recursos deve estar ativado para sua organização Cloudability. Você deve entrar em contato com seu TAM/CSM/ponto de contato da conta em Apptio para fazer isso. Depois de ativado, aguarde de 2 a 3 dias úteis para que os dados comecem a aparecer em seus relatórios de inventário.

Medidas de relatório de inventário

- As medidas são categorizadas como dimensões, métricas e tags (as tags incluem as dimensões de tag do Cloudability, grupos de contas e mapeamentos de negócios). Você pode incluir até 20 colunas em um relatório individual.
- Para cada serviço GCP, é oferecido suporte a um conjunto específico de medidas.
- Você pode filtrar seus respectivos relatórios de inventário usando qualquer uma das medidas disponíveis nesse recurso.

KPIs clicáveis para filtragem rápida

Para cada serviço, os KPIs serão exibidos na parte superior do relatório para fornecer a você as principais informações resumidas, como Recursos recém-lançados e Instâncias não marcadas. Você pode clicar e filtrar o relatório de inventário com base nesses KPIs para detalhar os dados específicos do relatório que está procurando.

Janelas de data de relatório de inventário

Você pode selecionar o período no seletor de datas para o qual deseja visualizar os dados de inventário de cada serviço. O intervalo máximo permitido para a seleção é de 31 dias. Ao ativar esse recurso, os dados do inventário de recursos serão preenchidos novamente até o início do mês atual. Com o passar do tempo, os dados de inventário estarão disponíveis em uma janela contínua de três meses. A qualquer momento, você poderá acessar os dados de inventário de recursos do mês atual e dos dois meses anteriores.

Filtragem estatística usando o filtro de exibição

A partir dos dados de inventário gerados para um serviço e um período de tempo específicos, agora você pode optar por exibir um subconjunto desses dados, seja o número x superior ou a porcentagem x de recursos com base na sua métrica de custo ou utilização preferida.

Por exemplo: O inventário de recursos exibe 1.000 registros para o serviço de computação por um período de sete dias. Você pode filtrar ainda mais essa exibição escolhendo visualizar apenas os 25% principais desses recursos, com base no Custo (Total). A aplicação desse filtro retornaria os 250 principais recursos com base no custo (total), ordenados do maior para o menor.

Exportação de relatórios

clicar em Exportar no canto superior direito da tabela de relatórios exportará todas as colunas de inventário selecionadas com qualquer filtro aplicado. No entanto, para exportar os dados completos do inventário para o mês e o serviço selecionados com todas as colunas compatíveis, clique no botão Exportar no canto superior direito do menu suspenso de filtros na barra de ferramentas da guia.

Salvando relatórios de inventário de recursos

É possível salvar um relatório com suas seleções de data, serviço e filtro e compartilhar esse relatório com outros usuários da organização, concedendo-lhes permissões "View Only" (Somente visualização) ou "Edit" (Editar). No canto superior direito da barra de ferramentas na IU do Inventário de Recursos, você pode ver uma elipse com o ícone de três pontos, clicando nele para abrir o menu Ações do relatório com essas opções.

- **Salvar como relatório:** Com essa opção, você pode salvar uma cópia do seu relatório. Essa opção é útil se alguém tiver compartilhado um relatório com você com acesso "View Only" e você quiser fazer alterações nesse relatório fazendo sua própria cópia dele. Outro caso de uso do Save As Report é para o relatório padrão. O relatório padrão não pode ser modificado e você precisará selecionar a opção "Save As Report" (Salvar como relatório) para salvar as alterações feitas no relatório padrão.
- **Salvar relatório:** Essa opção é usada para salvar quaisquer alterações feitas no relatório que você criou ou compartilhou com você com uma permissão "Editar"
- **Compartilhar relatório:** Com essa opção, você pode compartilhar seus relatórios com outros usuários da sua organização, concedendo-lhes permissões de "View Only" (Somente visualização) ou "Edit" (Edição).
- **Excluir relatório:** Você pode excluir seu relatório clicando em Excluir relatório.
- **Tratamento do intervalo de datas em relatórios salvos:** Os relatórios salvos com intervalos de datas não contínuos e fora do intervalo permitido (superior a 3 meses) serão carregados com o intervalo de datas redefinido para o padrão de 7 dias. Também será exibida uma mensagem de aviso ao usuário informando que o intervalo de datas foi reiniciado. Esse comportamento garante que os relatórios salvos continuem acessíveis mesmo quando os intervalos de datas armazenados ultrapassarem o limite permitido.

Nota:

- O número máximo de relatórios que serão exibidos no menu suspenso Relatórios salvos é 100.
- Quando um relatório for compartilhado com um usuário, nenhuma notificação por e-mail será enviada.
- O Resource Inventory suporta um máximo de dados de 3 meses, ou seja, do mês até a data + dos últimos 2 meses. Portanto, os dados acabariam expirando nos relatórios quando ultrapassassem esse período de retenção.

Utilização do inventário de recursos

1. Para acessar o Inventário de Recursos d GCP, navegue até Insights > Inventário de Recursos e clique na guia GCP.

1. Selecione o serviço no menu suspenso Serviços para o qual você deseja visualizar o inventário de recursos.
2. Selecione o intervalo de datas para o qual você deseja visualizar os dados do inventário de recursos. Você pode optar por visualizar até 31 dias de dados, no máximo. Por padrão, os dados exibidos serão classificados por Custo (Total) em ordem decrescente.
3. Clique em qualquer um dos KPIs com a barra azul à esquerda para filtrar seus relatórios com base nesse KPI específico.
4. Clique no botão de configurações da tabela no canto superior direito da tabela de inventário de recursos para configurar as medidas e as tags que você deseja exibir como colunas na tabela.

As medidas e tags selecionadas são exibidas como colunas na tabela.

1. Clique em Filters (Filtros ) para aplicar qualquer filtro ao relatório de inventário.
2. Use o menu suspenso Exibir acima da tabela Detalhes do inventário de recursos para especificar a porcentagem superior ou inferior das linhas a serem exibidas na tabela e para classificar a tabela de forma decrescente pela métrica de custo ou utilização preferida.
3. Clique no botão Export (Exportar ) no canto superior direito da tabela Resource Inventory Details (Detalhes do inventário de recursos) para exportar todas as colunas exibidas na tabela filtradas por suas configurações de filtro. Para exportar todos os dados de inventário do mês e do serviço selecionados com todas as colunas compatíveis, clique no botão Exportar, à direita do menu suspenso Filtros na barra de ferramentas da guia.

Medidas de recursos mostrando "Não disponível

Para alguns recursos, você pode descobrir que algumas medidas, como Data de lançamento, Estado e Tamanho, entre outras, aparecem como Não disponível no relatório Inventário de recursos. Isso significa que o site Cloudability não conseguiu obter dados para essas medidas específicas devido a um dos seguintes motivos:

- Talvez você não tenha feito credenciamento avançado para a conta à qual o(s) recurso(s) específico(s) pertence(m).
- A vida útil do(s) recurso(s) pode ter sido muito curta para capturar os dados para essas medidas.
- As métricas de utilização desses recursos podem ser exibidas como "0" (zero) no relatório.

| GCP Calcular | |
| --- | --- |
| Total de recursos | Número total de recursos em seu inventário para o período selecionado. |
| Total de instâncias | Número total de instâncias de computação, excluindo snapshots. |
| Recursos recém-lançados | Número de recursos que foram lançados no período selecionado. |
| Custo (total) | Custo (total) para as instâncias. |
| GCP Disco persistente | |
| Volumes totais | Número total de volumes em seu inventário para o período selecionado. |
| Volumes recém-lançados | Número de volumes que foram lançados no período selecionado. |
| Custo (total) | Custo (Total) para todos os volumes. |
| Volumes sem tags | Número de volumes que não têm pelo menos uma única etiqueta. |
| Volumes não anexados | Número de volumes que não estão anexados a nenhuma instância de computação. |

**Tópico principal:** [Inventário de recursos](../product/resource-inventory.html)
