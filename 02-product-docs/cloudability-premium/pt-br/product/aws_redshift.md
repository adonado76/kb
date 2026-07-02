---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Amazon Redshift"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/aws_redshift.html"
images:
  - "images/Redshift-Rightsizing-Details.jpg"
  - "images/Redshift-Rightsizing.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Amazon Redshift

Você pode usar o painel “Rightsizing” para visualizar informações sobre a otimização de recursos para clusters d Amazon Redshift. O painel exibe métricas de utilização e identifica clusters com oportunidades potenciais de economia. Você pode visualizar métricas de várias contas a partir de um único painel.

[Reestruturação em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Antes de começar

Para visualizar o painel do Amazon Redshift, certifique-se de ter conectado o Cloudability às contas corretas do AWS.

[Conexão com o AWS - Guia de integração do cliente](../admin/aws-credentialing-standard-enterprise-home.html)

Acesse o painel do Amazon Redshift

Para acessar o painel do Amazon Redshift, abra a página inicial Cloudability e, no menu de navegação à esquerda, selecione Otimizar > Redimensionamento. Na página “Rightsizing”, selecione a guia “ AWS ” e, em seguida, selecione a subguia “ Redshift ”.

![](../../../../03-media/cloudability-premium/images/Redshift-Rightsizing.jpg)

Personalize o painel

Você pode definir as seguintes opções para personalizar seu painel.

Selecionar conta

Por padrão, o painel exibe informações sobre todas as contas. Para visualizar as informações de uma conta específica, selecione o nome da conta no menu suspenso Conta.

Especificar cronograma

Você pode optar por analisar os gastos dos últimos 10 dias ou dos últimos 30 dias. Por padrão, a opção Linha do tempo está definida para 10 dias. Para a maioria dos usuários, 10 dias é o período recomendado, pois reflete as tendências de desempenho mais recentes e permite prever com maior precisão o uso futuro dos recursos.

Aplicar filtros

Você pode adicionar filtros para incluir ou excluir dados com base em uma ou mais condições. Para adicionar um filtro, selecione “Adicionar filtro” na barra de ferramentas e configure a dimensão, o operador e o valor.

Redshift tabela de insights

O painel contém uma tabela de insights, que oferece uma visão geral dos clusters d Redshift s com oportunidades de otimização. A tabela inclui as seguintes colunas:

Nota:

Por padrão, os dados são classificados pela coluna Pontuação de Prioridade para ajudar você a identificar os grupos com maior potencial de economia. Para alterar a ordem de classificação, selecione o nome da coluna.

- Pontuação de prioridade : A classificação de prioridade de otimização (0–100), em que 100 representa a oportunidade de economia com maior potencial.
- Nome do recurso : O nome do cluster do Redshift.
- Comentário : Notas ou anotações fornecidas pelo usuário para o cluster.
- Última visualização : A data mais recente em que o aglomerado foi detectado.
- Classe : A classificação do tipo de nó do cluster.
- Nome da conta : O nome da conta “ AWS ”.
- Número de nós : O número de nós no cluster.
- Inatividade : A porcentagem de tempo em que a CPU ficou abaixo de 2% durante o período selecionado. Porcentagens mais altas de inatividade indicam que o cluster raramente está ativo.
- CPU : A porcentagem média de utilização da CPU do cluster durante o período selecionado. Uma média baixa de uso da CPU, com picos mínimos, sugere que o cluster possa estar com capacidade excedente.
- Armazenamento : A porcentagem do espaço em disco alocado que está em uso. Uma utilização de armazenamento próxima de zero pode indicar que o cluster contém poucos dados ou nenhum dado.
- Utilização : A pontuação combinada de utilização da CPU e do armazenamento. Pontuações mais baixas indicam menor uso e maior potencial de otimização.
- Custo : O custo total do cluster para o período selecionado.

Avaliar oportunidades de otimização

O painel “ Redshift ” fornece métricas de utilização para ajudá-lo a identificar clusters com potencial de economia. Por padrão, a tabela é ordenada pela Pontuação de Prioridade mais alta, a fim de dar destaque aos agrupamentos com maiores oportunidades de otimização. Ao contrário de alguns outros tipos de serviço, a página de insights do Redshift concentra-se atualmente em recomendações de utilização, em vez de ações prescritivas explícitas. Analise as métricas e os gráficos de utilização para determinar a ação adequada.

Exportar análises para um arquivo do Excel

Para exportar os dados para um arquivo do Excel, selecione Exportar. O arquivo do Excel inclui várias colunas adicionais, como região, configuração do nó e detalhamento de custos.

Detalhes da recomendação

Para visualizar os detalhes de utilização de um cluster específico, selecione “Exibir detalhes” no menu “Mais opções” (três pontos). O painel de detalhes exibe gráficos de utilização da CPU e do armazenamento para a linha do tempo selecionada.

![](../../../../03-media/cloudability-premium/images/Redshift-Rightsizing-Details.jpg)

Para consultar as descrições das dimensões e métricas de custo, consulte o [Glossário de dimensões e métricas de custo](glossary-of-cost-dimensions-and-metrics.html).

Para visualizar detalhes sobre a dimensão de utilização e as métricas, consulte o [Glossário de dimensões e métricas de utilização](glossary-of-utilization-dimensions-and-metrics.html).

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
