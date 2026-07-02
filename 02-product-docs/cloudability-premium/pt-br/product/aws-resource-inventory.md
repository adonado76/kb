---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "AWS Inventário de recursos"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Inventário de recurso"
source_path: "product/aws-resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Inventário de recursos

AWS O recurso Inventário de Recursos do Cloudability permite que você produza uma lista oficial dos recursos em nuvem do AWS que existiam e foram cobrados durante um período específico de relatório. Você tem a flexibilidade de criar essa lista a partir de recursos que abrangem várias contas e escolher entre diferentes medidas (dimensões e métricas) para exibir os detalhes relevantes para elas. Essas informações, disponíveis para cada recurso de nuvem, unificam faturamento, utilização e metadados descritivos para oferecer uma visão mais abrangente do inventário.

## Introdução

AWS O recurso de relatório Resource Inventory deve estar ativado em sua Cloudability Org. Você deve entrar em contato com o seu TAM/CSM/ponto de contato da conta em Apptio para fazer isso. Depois de ativado, aguarde de 2 a 3 dias úteis para que os dados comecem a aparecer em seus relatórios de inventário. Para obter os dados completos do inventário do AWS Lambda, você deve habilitar **o Lambda Insights** no console do AWS.

## Medidas de relatório de inventário

- As medidas são categorizadas como colunas gerais ou colunas de tags. Você pode incluir até 20 colunas em um relatório individual.
- Para cada serviço do site AWS, há suporte para um conjunto específico de medidas.
- Você pode filtrar seus respectivos relatórios de inventário usando qualquer uma das medidas disponíveis nesse recurso.

## KPIs clicáveis para filtragem rápida

Para cada serviço (por exemplo: EC2, EBS ), os KPIs serão exibidos na parte superior do relatório para fornecer a você as principais informações resumidas, como Instâncias inativas e Instâncias não marcadas. Você pode clicar e filtrar o relatório de inventário com base nesses KPIs para detalhar os dados específicos do relatório que está procurando.

## Janelas de data de relatório de inventário

- Selecione o período no seletor de datas para visualizar os dados de inventário de cada serviço.

  O intervalo máximo permitido para a seleção é de 31 dias.

  Os dados do inventário de recursos são preenchidos até o início do mês atual e estão disponíveis em uma janela contínua de três meses.
- Acesse os dados de inventário de recursos do mês atual e dos dois meses anteriores sempre que necessário.

## Filtragem estatística usando o filtro de exibição

A partir dos dados de inventário gerados para um serviço e um período de tempo específicos, você pode optar por exibir um subconjunto desses dados, seja o número x superior ou a porcentagem x de recursos com base em sua métrica de custo ou utilização preferida.

Por exemplo: O inventário de recursos exibe 1.000 registros para o serviço EC2 por um período de sete dias. Você pode filtrar ainda mais essa exibição escolhendo visualizar apenas os 25% principais desses recursos, com base no Custo (Total). A aplicação desse filtro retornaria os 250 principais recursos com base no custo (total), ordenados do maior para o menor.

## Exportação de relatórios

Clique em Exportar na grade do relatório para exportar as colunas de inventário selecionadas com o(s) filtro(s) aplicado(s). No entanto, para exportar os dados completos do inventário para o mês e o serviço selecionados para todas as colunas compatíveis, clique no botão Exportar, à direita do menu suspenso Filtros na barra de ferramentas da guia.

## Salvando relatórios de inventário de recursos

É possível salvar um relatório com suas seleções de data, serviço e filtro e compartilhá-lo com outros usuários da organização, concedendo-lhes permissões de "Somente visualização" ou "Edição". No canto superior direito da barra de ferramentas na IU do Inventário de Recursos, você pode ver uma elipse com o ícone de três pontos, clicando nele para abrir o menu Ações do relatório com essas opções.

- **Salvar como relatório:** Com essa opção, você pode salvar uma cópia do seu relatório. Essa opção é útil se alguém tiver compartilhado um relatório com você com acesso "View Only" e você quiser fazer alterações nesse relatório fazendo sua própria cópia dele. Outro caso de uso do Save As Report é para o relatório padrão. O relatório padrão não pode ser modificado e você precisará selecionar a opção "Save As Report" (Salvar como relatório) para salvar as alterações feitas no relatório padrão.
- **Salvar relatório:** Essa opção é usada para salvar quaisquer alterações feitas no relatório que você criou ou compartilhou com você com uma permissão "Editar"
- **Compartilhar relatório:** Com essa opção, você pode compartilhar seus relatórios com outros usuários da sua organização, concedendo-lhes permissões de "View Only" (Somente visualização) ou "Edit" (Edição).
- **Excluir relatório:** Você pode excluir seu relatório clicando em Excluir relatório.
- **Tratamento do intervalo de datas em relatórios salvos:** Os relatórios salvos com intervalos de datas não contínuos e fora do intervalo permitido (superior a 3 meses) serão carregados com o intervalo de datas redefinido para o padrão de 7 dias. Também será exibida uma mensagem de aviso ao usuário informando que o intervalo de datas foi reiniciado. Esse comportamento garante que os relatórios salvos continuem acessíveis mesmo quando os intervalos de datas armazenados ultrapassarem o limite permitido.

Nota:

- O número máximo de relatórios que serão exibidos no menu suspenso Relatórios salvos é 100.
- Quando um relatório for compartilhado com um usuário, nenhuma notificação por e-mail será enviada.
- O Resource Inventory suporta um máximo de dados de 3 meses, ou seja, do mês até a data + dos últimos 2 meses. Portanto, os dados acabariam expirando nos relatórios quando ultrapassassem esse período de retenção.

## Utilização do inventário de recursos

1. Para acessar o AWS Resource Inventory, navegue até Insights > Resource Inventory.
2. Selecione o serviço no menu suspenso Serviços para o qual você deseja visualizar o inventário de recursos.
3. Selecione o intervalo de datas para o qual você deseja visualizar os dados do inventário de recursos. Você pode optar por visualizar até 31 dias de dados, no máximo. Por padrão, os dados exibidos são classificados por Custo (Total) em ordem decrescente.
4. Clique nos KPIs com uma barra azul à esquerda para filtrar seus relatórios com base neles (por exemplo, Newly Launched ).
5. Clique em configurações de tabela no canto superior direito da tabela Detalhes do inventário de recursos para configurar as medidas e as tags que você deseja exibir como colunas na tabela.
6. Clique em Filters (Filtros ) para classificar o relatório de inventário.
7. Selecione Exibir acima da tabela Detalhes do inventário de recursos. Isso especifica a porcentagem superior ou inferior de linhas a serem exibidas na tabela e também classifica a tabela por sua métrica de custo ou utilização preferida em ordem decrescente.
8. Clique em Exportar para exportar as colunas mostradas na tabela, filtradas por suas configurações de filtro. Para exportar todos os dados de inventário do mês e do serviço selecionados com colunas compatíveis, clique no botão Exportar à direita do menu suspenso de filtros na barra de ferramentas da guia.

Nota:

Os recursos, como Data de lançamento, Estado e Tamanho, às vezes são exibidos como Não disponíveis no relatório Inventário de recursos. Isso significa que o site Cloudability não conseguiu obter dados para essas medidas específicas devido a um dos seguintes motivos:

- Talvez você não tenha feito credenciamento avançado para a conta à qual o(s) recurso(s) específico(s) pertence(m).
- A vida útil do(s) recurso(s) pode ter sido muito curta para capturar os dados para essas medidas.
- As métricas de utilização desses recursos podem ser exibidas como "0" (zero) no relatório.

Nota:

As métricas de utilização desses recursos podem ser exibidas como "0" (zero) no relatório.

## Família de uso de recursos no inventário de recursos

O Resource Inventory usa o ID do recurso como identificador exclusivo para exibir os recursos. Ao contrário dos relatórios do site Cloudability, ele não é compatível com as dimensões da Família de Uso. Mesmo que a mesma ID de recurso seja consumida em diferentes famílias de uso, o inventário de recursos exibirá a ID de recurso apenas uma vez no relatório.

## Definições de KPI

| KPI | Descrição |
| --- | --- |
| EC2 | |
| Total de instâncias | Número total de instâncias do EC2 em seu inventário para o período selecionado. |
| Instâncias recém-lançadas | Número de instâncias do EC2 que foram lançadas no período selecionado. |
| Instâncias inativas | Número de instâncias de EC2 que não estão no estado "Running" (Em execução). |
| Custo (total) | Custo (Total) para as instâncias de EC2 para o período selecionado. |
| Instâncias sem tags | Número de instâncias de EC2 que não têm uma tag. |
| EBS | |
| Total de recursos | Número total de recursos do EBS em seu inventário para o período selecionado. |
| Total de capturas instantâneas | Número total de snapshots EBS em seu inventário para o período selecionado. |
| Novos volumes criados | Número de volumes EBS que foram criados no período selecionado. |
| Volumes inativos | Número de volumes EBS que estão no estado "Available" (Disponível). |
| Custo (total) | Custo (total) para os recursos do EBS (volumes e instantâneos). |
| Volumes sem tags | Número de volumes do site EBS que não têm uma tag. |
| Volumes não anexados | Número de volumes de EBS que não estão anexados a nenhuma instância de EC2. |
| Lambda | |
| Total de funções Lambda | Número total de funções Lambda em seu inventário para o período selecionado. |
| Computar funções Lambda | Número de Funções Lambda para o período selecionado que se enquadram na família de uso "Instance Usage" (Uso da instância) |
| Custo (total) | Custo (total) das funções Lambda para o período selecionado. |
| Funções não identificadas | Número de funções Lambda que não têm uma tag. |
| S3 | |
| Total de recursos | Número total de S3 baldes em seu inventário para o período selecionado. |
| Buckets inativos | Número de S3 baldes que não têm nenhum objeto neles. |
| Buckets sem tags | Número de S3 buckets que não têm uma tag |
| Custo (total) | Custo (Total) para os S3 baldes. |
| RDS | |
| Total de recursos | Número total de recursos do RDS em seu inventário para o período selecionado. |
| Total de capturas instantâneas | Número total de snapshots RDS em seu inventário para o período selecionado. |
| Recursos sem tags | Número de recursos do site RDS que não têm uma tag |
| Custo (total) | Custo (Total) para os recursos do RDS. |
| Redshift | |
| Total de recursos | Número total de recursos Redshift em seu inventário para o período selecionado. |
| Total de capturas instantâneas | Número total de instantâneos do Redshift no seu inventário para o período selecionado. |
| Novos recursos criados | Número de recursos Redshift criados no período selecionado. |
| Recursos sem tags | Número de recursos Redshift que não possuem uma tag. |
| Custo (total) | Custo (total) dos recursos do Redshift. |

**Tópico principal:** [Inventário de recursos](../product/resource-inventory.html)
