---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Aproveitar ao máximo as dimensões e métricas populares dentro de Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Referência de dados"
source_path: "product/frequently-used-dimensions-and-metrics.html"
images:
  - "images/making_the_most_2016-11-03_09-18-07.jpg"
  - "images/making_the_most_8_image04.jpg"
  - "images/making_the_most__2016-11-03_09-12-37.jpg"
  - "images/making_the_most__cursor_and_account_copyg.jpg"
  - "images/making_the_most__image00.jpg"
  - "images/making_the_most_image01.jpg"
  - "images/making_the_most_image06.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Aproveitar ao máximo as dimensões e métricas populares dentro de Cloudability

Há um grande número de dimensões e métricas disponíveis nos relatórios do site Cloudability. Listamos abaixo alguns dos mais populares e úteis. Para obter uma lista completa, consulte nosso [Glossário de dimensões e métricas](glossary-of-cost-dimensions-and-metrics.html).

Nome do serviço (vs. nome do produto)

![Captura de tela: serviço x produto](../../../../03-media/cloudability-premium/images/making_the_most__2016-11-03_09-12-37.jpg)

Cloudability criou o Service Name para padronizar as convenções de nomes mistos para o campo Product Name de AWS e Azure :

- AWS EBS torna-se seu próprio produto de nível superior.
- Dados unificados que estavam misturados em vários produtos:
- AWS rastreia o Cloudwatch parcialmente como um produto e, como EC2;, separa o Cloudwatch em seu próprio serviço.
- AWS rastreia o Glacier parcialmente como um produto e, em S3;, consolida todos os produtos Glacier e S3.
- AWS tem um serviço de importação e exportação, bem como um serviço Snowball; o Service Name consolida esses serviços.
- Em alguns casos, os dados dos sites AWS e Azure mostram vários produtos para os mesmos serviços:
  - AWS tem vários nomes para Suporte, isso consolida todos eles em um único item de linha AWS Support.
  - AWS tem muitos encargos administrativos listados como produtos de nível superior, como: Rede de parceiros da Amazon, ingressos para o re:Invent, etc. Eles são consolidados em um único item administrativo AWS.
  - Azure tem computação, Microsoft.Compute e máquinas virtuais; todos eles são iguais e consolidados em Azure Compute.
- AWS os arquivos de faturamento têm esquemas de nomenclatura inconsistentes para os produtos, às vezes Amazon versus AWS; acrônimos versus nomes escritos. O nome do serviço segue um único padrão de um prefixo de AWS seguido pelo nome que é visto no menu do console AWS : EC2, S3, RDS, Kinesis, Lambda, etc. Da mesma forma, Azure é o prefixo de todos os serviços Microsoft Azure.

Todos os relatórios salvos devem usar Service Name.

Família de uso (vs. tipo de uso)

![Captura de tela comparativa entre a família usag e o produto](../../../../03-media/cloudability-premium/images/making_the_most_2016-11-03_09-18-07.jpg)

O Tipo de uso é uma dimensão muito granular que expõe detalhes operacionais específicos de cada item de linha. Essa dimensão pode fornecer uma grande quantidade de utilidade quando combinada com contains e não contém parâmetros de filtro.

Os valores típicos a serem retornados são BoxUsage:c3.xlarge para indicar o uso sob demanda, ou HeavyUsage:m2.4xlarge para indicar o uso pesado/reservado, ou EBS:VolumeP-IOPS.piops para indicar o uso de IOPS provisionado.

Um tipo de uso desconhecido é representativo de coisas como a taxa de inscrição de uma compra de RI.

A Família de Uso, por sua vez, é uma dimensão padronizada criada por Cloudability para consolidar valores semelhantes de Tipo de Uso em uma única família de alto nível, por exemplo, Uso de Instância, Transferência de Dados, Armazenamento ou Solicitação de API. É um ótimo lugar para começar a dividir seus gastos além de Contas e Serviços.

Descrição do item

![captura de tela da descrição do item](../../../../03-media/cloudability-premium/images/making_the_most_8_image04.jpg)

A Descrição do item é uma dimensão ainda mais granular que pode expor ainda mais detalhes operacionais de cada item de linha. Essa dimensão também pode fornecer uma grande quantidade de utilidade quando combinada com contains e não contém parâmetros de filtro.

Os valores típicos que podem ser retornados são $ 0.105 por hora de instância do On Demand Linux c3.large para indicar uso sob demanda, ou $ 0.070 por GB — nos próximos 100 TB/mês de transferência de dados de saída para indicar transferência de dados, ou 0.5589 por hora por Linux /UNIX, i2.4xlarge instance para indicar horas de uso de RI, ou 0.0290 por GB – a partir dos próximos 450 TB/mês de armazenamento utilizado para indicar custos de S3, ou 0.850 por Redshift Dense Storage Extra Large ( DW1.XL ) Compute Node-hour (ou fração de hora) para indicar custos de Redshift.

Descrição de um item Cobrança de inscrição para assinatura: ####, planId: ### (onde ### são números reais) é representativo das cobranças de registro de uma compra do RI. Isso permite que você crie um filtro para o item description\_does not contain\_sign up para ver seus custos de computação sem a taxa inicial incluída.

Tipo de transação

![Captura de tela do tipo de transação](../../../../03-media/cloudability-premium/images/making_the_most__cursor_and_account_copyg.jpg)

Essa dimensão foi criada pelo site Cloudability para separar discretamente cobranças recorrentes, como suporte do AWS e taxas mensais do RI, cobranças únicas, como pagamentos de inscrição no RI, créditos, impostos e custos de uso. Isso pode ser extremamente útil para determinar a eficiência e o desperdício de seu RI, além de ajudar a mostrar como os custos combinados e não combinados podem variar por item de linha, mesmo quando atingem o mesmo total no final do mês.

Tipo de uso de computação

![captura de tela do tipo de uso do Compute](../../../../03-media/cloudability-premium/images/making_the_most_image06.jpg)

Essa dimensão detalha claramente quais instâncias estão sendo executadas sob demanda, spot, reservadas, um nó RDS, etc. A execução de um relatório do Cost Analytics com o tipo de uso de computação e a descrição do item como as únicas dimensões apresentará uma visão detalhada completa.

Para ver apenas seus custos de computação, adicione um filtro para compute usage type\_not equals\_other, pois o outro tipo de uso representa custos como transferência de dados, mapeamento de IP elástico, meses de alarme, horas de leitura/gravação, armazenamento em GB, LoadBalancer GB processados, horas de shard, PIOPS, armazenamento magnético e outros.

- Para visualizar seus custos do Redshift, adicione um filtro para “compute usage type\_equals\_node ”.
- Para ver seus ElastiCache custos, adicione um filtro para compute usage type\_equals\_node usage.
- Para ver seus RDS custos, adicione um filtro para compute usage type\_equals\_instance usage.
- Para ver seus custos de RI pesado, adicione um filtro para compute usage type\_equals\_heavy usage.
- Para ver seus custos On-Demand, adicione um filtro para compute usage type\_equals\_box usage.

Horas sob demanda, horas reservadas, taxa de cobertura reservada

![captura de tela do horário](../../../../03-media/cloudability-premium/images/making_the_most__image00.jpg)

Essas métricas são valiosas para determinar exatamente quais contas, serviços, tags ou recursos aproveitaram suas instâncias reservadas. O relatório de faturamento detalhado é preenchido com a resolução por hora em todos esses parâmetros, permitindo que nossa plataforma de análise agrupe qualquer dimensão e mostre como ela aproveitou as horas de RI em qualquer período de relatório escolhido.

Adicionar um filtro para taxa de cobertura reservada\_maior que\_X% (onde X% é um número sem o símbolo de porcentagem) é uma ótima maneira de ver quais áreas de sua infraestrutura poderiam se beneficiar de uma cobertura adicional de RI.

Tipo de instância

![captura de tela do tipo de instância](../../../../03-media/cloudability-premium/images/making_the_most_image01.jpg)

Essa dimensão combina as dimensões Instance Family e Instance Size e apresenta o identificador completo da instância, por exemplo, c3.large.

No Cost Analytics, para ver apenas seus custos de computação, adicione um filtro para instance type\_not equals\_none, pois o tipo de instância none representa transferência de dados, mapeamento de IP elástico, meses de alarme, horas de leitura/gravação, armazenamento em GB, LoadBalancer GB processado, horas de shard, PIOPS, armazenamento magnético, solicitações GET/PUT/POST/COPY/LIST e outros.

No Usage Analytics, essa dimensão retornará apenas suas instâncias de EC2.

�

Instâncias em execução e média de instâncias em execução por hora

![Captura de tela das instâncias em execução](../../../../03-media/cloudability-premium/images/making_the_most_image01.jpg)

A métrica Instâncias em execução é uma contagem de todos os IDs de instância exclusivos que estavam em execução em um ponto durante a janela do relatório. Essa não é necessariamente uma contagem das instâncias que estão ativas ou em execução no momento em que o relatório é executado. Em vez disso, é a soma dos IDs de instância exclusivos que estavam em execução.

A média de instâncias em execução por hora é uma média do número de instâncias que estavam ativas a cada hora da janela do relatório.
