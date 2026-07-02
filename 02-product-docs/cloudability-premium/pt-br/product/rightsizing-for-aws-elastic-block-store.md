---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "AWS EBS"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/rightsizing-for-aws-elastic-block-store.html"
images:
  - "images/ebs-details-final.jpg"
  - "images/ebs-final.jpg"
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS EBS

Você pode usar o painel Rightsizing para visualizar as recomendações de otimização de recursos para Amazon Web Services ( AWS ) Elastic Block Store ( EBS ). O painel mostra as recomendações de rightsizing e de inatividade (encerramento). Você pode visualizar as recomendações em várias contas a partir de um único painel.

[Rightsizing em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Antes de começar

Para visualizar o painel AWS EC2 EBS, certifique-se de que conectou Cloudability às contas AWS corretas.

[Conexão com AWS - Guia de integração do cliente](../admin/aws-credentialing-standard-enterprise-home.html)

Acesse o painel AWS EC2 EBS

Para acessar o painel AWS EC2 EBS, abra a página inicial Cloudability e, no menu de navegação à esquerda, selecione Otimizar > Redimensionamento. Na página Rightsizing, selecione a guia AWS e, em seguida, selecione a subguia EBS.

![Captura de tela do painel do AWS EBS ec2](../../../../03-media/cloudability-premium/images/ebs-final.jpg)

Personalizar o painel de controle

Você pode definir as seguintes opções para personalizar seu painel.

Nota:

Somente a base de custo sob demanda é compatível com EBS.

A base de custo On-Demand fornece uma comparação direta entre a instância listada na coluna Current (Atual ) e a instância recomendada na coluna New (Nova ) com base exclusivamente no preço On-Demand. Ele não inclui nenhum impacto potencial de instâncias reservadas (RIs) ou planos de economia (SPs). Observe que os preços sob demanda refletirão quaisquer acordos de preços personalizados que você tenha configurado em Cloudability.

Selecionar conta

Por padrão, o painel mostra recomendações para todas as contas. Para visualizar as recomendações de uma conta específica, selecione o nome da conta no menu suspenso Conta.

Especificar o cronograma

Você pode optar por revisar as despesas dos últimos 10 dias ou dos últimos 30 dias. Por padrão, a opção Linha do tempo é definida como 10 dias. Para a maioria dos usuários, 10 dias é o período de tempo recomendado porque captura as tendências de desempenho mais recentes e é mais preditivo do uso futuro de recursos.

Aplicar filtros

Você pode adicionar filtros para incluir ou excluir dados com base em uma ou mais condições.

Adicionar um filtro

Para adicionar um filtro:

1. Selecione Add Filter (Adicionar filtro ) na barra de ferramentas.
2. No menu Add Filter (Adicionar filtro ), escolha uma Dimensão.
3. Selecione um operador para fornecer uma condição lógica.
4. Escolha um valor para refinar seu filtro.
5. Selecione Add Filter (Adicionar filtro ) para aplicar o novo filtro à página.

Aplicar filtros com links

Você também pode adicionar filtros selecionando os valores azuis com hiperlink na tabela principal. A regra de filtro é aplicada automaticamente ao campo Filtros. Você pode selecionar apenas um valor ou parâmetro de cada coluna por vez.

Remover um filtro

Para remover um filtro:

1. Selecione o ícone de filtro ![Ícone de notas](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
2. Selecione X ao lado do filtro que você deseja remover.

Indicadores-chave de desempenho

Você pode visualizar os seguintes indicadores-chave de desempenho (KPIs) no painel do Rightsizing:

- Total de despesas : Mostra o total de despesas alocadas atuais.
- Economia ociosa estimada : Mostra a economia total estimada para todas as recomendações de encerramento.
- Economia estimada com o Rightsizing : Mostra a economia potencial total estimada que pode ser obtida com todas as recomendações do Rightsize.
- Despesas otimizadas estim adas : mostra o total estimado de despesas após a aplicação das recomendações.

Tabela de recomendações de dimensionamento

O painel contém uma tabela de recomendações de dimensionamento de direitos, que fornece uma visão geral de seus recursos EC2 EBS. A tabela inclui as seguintes colunas:

Nota:

Por padrão, os dados são classificados pela coluna Economia de custos. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- ID do recurso : a ID do volume.
- Nome do recurso : o nome do volume.
- Nome da conta : O nome da conta AWS.
- Inativo : A porcentagem de horas com zero IOPS.
- Estado : O estado pode ser Attached (anexado ), Unattached (não anexado ) ou Deleted (excluído ).
- Custo : O custo total do volume.
- Tipo :O tipo de volume.
- Tamanho : O tamanho do volume (em GiB ).
- Novo tipo : O tipo de volume mais recomendado.
- Novo tipo : O tipo de volume mais recomendado.
- New Size (Novo tamanho ): O tamanho de volume mais recomendado (em GiB ).
- Ação : Recomendação para o recurso. A recomendação pode ser uma das seguintes.

| Recomendação | Descrição |
| --- | --- |
| Tamanho do direito | Redimensione para o tipo de recurso especificado na coluna Novo. |
| Encerrar | Encerre seu recurso porque ele está predominantemente ocioso. |
| Nenhuma ação | Nenhuma ação é recomendada por padrão, mas recomendações adicionais com níveis de risco mais altos podem estar disponíveis no painel Detalhes. |

Economia de custos : O valor estimado de economia de custos em 10 ou 30 dias.

Exportar recomendações para um arquivo Excel

Para exportar as recomendações para um arquivo Excel, selecione Exportar. Observe que o arquivo do Excel incluirá várias colunas adicionais, como região, sistema operacional, preço unitário e outras.

Detalhes da recomendação

Para exibir os detalhes da recomendação de um determinado recurso, selecione View Details (Exibir detalhes ) no menu More Options (Mais opções) (3 pontos).

A figura a seguir mostra um exemplo de painel de detalhes de recomendação.

![Ícone de notas](../../../../03-media/cloudability-premium/images/ebs-details-final.jpg)

O painel de detalhes do EBS mostra as seguintes informações:

- Última data de faturamento : A última data para a qual os dados de custo estão disponíveis.
- Last Attached Date : A última data em que o estado do volume foi anexado.
- Última ID anexada : a última ID de instância à qual o volume foi anexado.
- Type : O tipo de volume.
- Tamanho : O tamanho do volume.
- Taxa de transferência : A taxa de transferência máxima do volume.
- IOPS : O volume máximo de IOPS.
- Risco (sob recomendações) : caracteriza a probabilidade de atingir os limites de capacidade para uma determinada recomendação.
- Métricas de utilização : as métricas de utilização exibidas para os volumes do site EBS baseiam-se nos seguintes parâmetros.

| Parâmetro | Descrição |
| --- | --- |
| Taxa de transferência (MB/S) | Throughput Max (linha azul) : O máximo de MB/S de throughput utilizado na hora indicada.  Capacidade (linha vermelha) : A capacidade de throughput em MB/S na hora indicada.  Recomendado (linha tracejada amarela) : A capacidade de throughput recomendada em MB/S na hora indicada. |
| IOPS (contagem) | IOPS Max (linha azul) : o máximo de IOPS utilizado na hora indicada.  Capacidade (linha vermelha) : A capacidade de IOPS na hora indicada.  Recomendado (linha tracejada amarela) : a capacidade de IOPS recomendada na hora indicada. |

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
