---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "AWS ElasticIP"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/aws_elasticip.html"
images:
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS ElasticIP

Você pode usar as recomendações do site Cloudability para identificar endereços Amazon Web Services ( AWS ) ElasticIP que não estejam vinculados a nenhum domínio. () O painel apresenta recomendações para encerrar endereços ElasticIP identificados como não vinculados a uma instância e não utilizados. Você pode visualizar as recomendações de várias contas a partir de um único painel.

[Reestruturação em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

## Antes de começar

Para visualizar o painel do AWS EC2 EBS, certifique-se de ter conectado o Cloudability às contas corretas do AWS.

[Conexão com o AWS - Guia de integração do cliente](../admin/aws-credentialing-standard-enterprise-home.dita "(Abre em uma nova guia ou janela)")

## Acessando as recomendações de IPs elásticos d AWS

Para acessar o painel “ AWS EC2 ” ( EBS ), abra a página inicial do Cloudability e, no menu de navegação à esquerda, **selec** ione “Optimize” > “**Rightsizing** ”. Na **página “Rightsizing** ”, selecione a guia “ **AWS** ” e, em seguida, selecione **a** subguia “Elastic IP”.

## Entendendo suas recomendações

Observação: Apenas a base de custo sob demanda é compatível com endereços do tipo “ ElasticIP ”.

A base de custo “On-Demand” oferece uma comparação direta entre a instância listada na **coluna** “Atual” e a instância recomendada na **col** una “Nova”, com base exclusivamente **no** **preço “On-Demand** ”. Como os endereços do tipo “ ElasticIP ” não oferecem compromissos, apenas a base de custo “On Demand” está disponível, a qual não inclui nenhum impacto potencial decorrente de Instâncias Reservadas (RIs) ou Planos de Economia (SPs). Observe que os preços sob demanda refletirão quaisquer acordos de preços personalizados que você tenha configurado no Cloudability.

**Selecionar conta**

Por padrão, o painel exibe recomendações para todas as contas. Para visualizar as recomendações para uma conta específica, selecione o nome da conta no menu suspenso “Conta”.

**Especificar cronograma**

Você pode optar por analisar os gastos dos últimos **10 dias** ou dos últimos 30 dias. Por padrão, **a** opção “Linha do tempo” está definida para 10 dias. Para uma recomendação de inatividade do ElasticIP, recomenda-se encerrar o recurso caso ele permaneça desvinculado durante pelo menos a última metade do período de análise retrospectiva.

**Aplicar filtros**

Você pode adicionar filtros para incluir ou excluir dados com base em uma ou mais condições.

**Adicionar um filtro**

Para adicionar um filtro:

1. **Sel** ecione “Adicionar filtro” na barra de ferramentas.
2. No **menu “Adicionar** filtro”, escolha **uma** “Dimensão”.
3. Selecione um **operador** para definir uma condição lógica.
4. Escolha um valor para refinar seu filtro.
5. **Sel** ecione “Adicionar filtro” para aplicar o novo filtro à página.

**Aplicar filtros com links**

Você também pode adicionar filtros selecionando os valores em azul com hiperlink na tabela principal. A regra de filtro é aplicada automaticamente ao **campo** “Filtros”. Você pode selecionar apenas um valor ou parâmetro de cada coluna por vez.

**Remover um filtro**

Para remover um filtro:

1. Selecione o ícone do filtro. ![](../../../../03-media/cloudability-premium/images/edit-icon.jpg)
2. Selecione o X ao lado do filtro que você deseja remover.

## Indicadores-chave de desempenho

Você pode visualizar os seguintes Indicadores-chave de Desempenho (KPIs) no seu painel do Rightsizing:

- **Total** **Spend** : Mostra o gasto total atual com os recursos do ElasticIP, acompanhado de recomendações
- **Economia estimada com o** **IdleSavings** : Mostra a economia total estimada para todas as recomendações de “Terminate”.
- **Econom** **ia estimada com o Rightsizing**  : Mostra a economia potencial total estimada que pode ser alcançada com todas as recomendações do Rightsize. Como os endereços IP elásticos suportam apenas recomendações de terminação, espera-se que esse valor seja 0.
- **Estimativa** **de gastos otimizados** : mostra o total estimado de gastos após a aplicação das recomendações. Como os endereços IP elásticos suportam apenas recomendações de terminação, espera-se que esse valor seja 0.

## Tabela de recomendações para o redimensionamento

O painel contém uma tabela de recomendações de ajuste de capacidade, que oferece uma visão geral dos seus recursos do AWS ElasticIP. A tabela inclui as seguintes colunas:

Observação: Por padrão, os dados são classificados pela coluna “Economia de custos”. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- **Res** **ourceID** : O ID do volume.
- **Res** **ourceName** : O nome do volume.
- **N** **ome da conta**  : O nome da conta do AWS.
- **Inatividade** : A porcentagem de horas com zero IOPS.
- **Estado** : O estado pode ser “Anexado”, “Não anexado” ou “Excluído”.
- **Custo** : O custo total do volume.
- **Tipo** : O tipo de volume.
- **Tamanho** : O tamanho do volume ( GiB ).
- **New** **Type** : O tipo de volume mais recomendado.
- **New** **Type** : O tipo de volume mais recomendado.
- **New** **Size** : O tamanho de volume mais recomendado (em GiB ).
- **Ação** : Recomendação para o recurso; atualmente, apenas recomendações de encerramento estão disponíveis para endereços ElasticIP.

**Econom** **ia de custos**  : O valor estimado da economia de custos em 10 ou 30 dias.

**Exportar recomendações para um arquivo do Excel**

Para exportar as recomendações para um arquivo do Excel, selecione “Exportar”. Observe que o arquivo do Excel incluirá várias colunas adicionais, como região, sistema operacional, preço unitário e outras.

**Detalhes da recomendação**

Para visualizar os detalhes da recomendação de um recurso específico, selecione “Ver detalhes” no menu “Mais opções” (três pontos).

O painel de detalhes do “ EBS ” exibe as seguintes informações:

- **Última** **data de faturamento** : A última data para a qual há dados de custo disponíveis.
- **Data** **da última conexão** : A última data em que o volume estava conectado.
- **Último** **ID de instância anexada** : O ID da última instância à qual o volume foi anexado.
- **Tipo** : O tipo de volume.
- **Tamanho** : O tamanho do volume.
- **Capacidade de processamento** : O volume máximo de processamento.
- **IOPS** : O número máximo de IOPS do volume.
- **Risco (em relação às recomendações)** : Caracteriza a probabilidade de atingir os limites de capacidade para uma determinada recomendação.
- **M** **étricas de utilização** : As métricas de utilização exibidas para os volumes do EBS baseiam-se nos seguintes parâmetros.

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
