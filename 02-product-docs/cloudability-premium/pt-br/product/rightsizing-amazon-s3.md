---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "AWS S3"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/rightsizing-amazon-s3.html"
images:
  - "images/edit-icon.jpg"
  - "images/s3-rightsizing-details-pane.jpg"
  - "images/s3-rightsizing-recommendations-grid.jpg"
  - "images/s3-storage-classes.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS S3

Você pode usar o painel Rightsizing para visualizar as recomendações de otimização de recursos para Amazon Web Services ( AWS )Simple Storage Service ( S3 ). O painel mostra as recomendações de rightsizing e de inatividade (encerramento). Você pode visualizar as recomendações em várias contas a partir de um único painel.

[Rightsizing em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

AWS S3 visão geral

Amazon Web Services ( AWS ) S3 é um serviço de armazenamento organizado em torno de buckets. Os buckets são contêineres de nível superior. Você pode usar esses compartimentos para armazenar objetos individuais associados a uma classe de armazenamento e também organizar objetos individuais hierarquicamente em pastas.

Baldes

Você pode ter até mil buckets por conta. Em cada bucket, você pode armazenar até cinco terabytes de objetos individuais. Os custos são incorridos de acordo com a taxa da classe de armazenamento do objeto e fatorados pelo espaço de armazenamento alocado (GB por mês), duração, número de operações (leitura, gravação, listas, exclusão) e volume de dados transferidos (saída).

Classes de armazenamento

As classes de armazenamento são adaptadas com base nos padrões de acesso e nas necessidades de durabilidade, variando de armazenamento frequente a pouco frequente (arquivamento). Somente um objeto, e não um bucket, é associado a uma classe de armazenamento.

As classes de armazenamento do AWS S3 diferem em preço, desempenho, disponibilidade e requisitos mínimos de tamanho e duração. Dependendo da classe de armazenamento utilizada, podem ser incorridas taxas adicionais para monitoramento, transição de classe de armazenamento, exclusão antecipada e taxas de restauração.

Por padrão, os objetos S3 são criados na classe de armazenamento Standard de preço mais alto. Para otimizar manualmente objetos individuais, é necessário identificar as taxas de cada classe de armazenamento por região, coletar os padrões e as operações de acesso anteriores e, em seguida, avaliar cada uma das alternativas considerando todas as compensações.

![captura de tela das classes de armazenamento da amazon s3](../../../../03-media/cloudability-premium/images/s3-storage-classes.jpg)

Antes de começar

Para visualizar o painel do AWS S3, certifique-se de que conectou o Cloudability às contas corretas do AWS.

[Conexão com AWS - Guia de integração do cliente](../admin/aws-credentialing-standard-enterprise-home.html)

Acesse o painel do AWS S3

Para acessar o painel do AWS EC2, abra a página inicial do Cloudability e, no menu de navegação à esquerda, selecione Otimizar > Redimensionamento. Na página Rightsizing, selecione a guia AWS e, em seguida, selecione a subguia S3.

Nota:

Somente os compartimentos com custos incorridos maiores que zero serão exibidos.

![captura de tela do aws rightsizing](../../../../03-media/cloudability-premium/images/s3-rightsizing-recommendations-grid.jpg)

Todos os dias, o Cloudability analisa suas métricas de custo, uso e utilização do AWS S3 nos últimos 30 dias. O redimensionamento produz insights e recomendações de otimização em nível de balde. Os gastos são determinados por GB Months.

Observação: o redimensionamento oferece uma divisão de classes de armazenamento heterogêneas em um bucket.

Observação: Recursos ociosos ou volumes de armazenamento alocados que contêm dados insignificantes ou inexistentes também são exibidos no painel Rightsizing.

Personalizar o painel de controle

Você pode definir as seguintes opções para personalizar seu painel.

Nota:

Somente a base de custo sob demanda é compatível com S3.

A base de custos On-Demand fornece uma comparação direta entre a instância listada na coluna Current (Atual ) e a instância recomendada na coluna New (Nova ) com base exclusivamente no preço On-Demand. Ele não inclui nenhum impacto potencial de instâncias reservadas (RIs) ou planos de economia (SPs). Observe que os preços sob demanda refletirão quaisquer acordos de preços personalizados que você tenha configurado em Cloudability.

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

1. Selecione o ícone de filtro ![ícone de edição](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
2. Selecione X ao lado do filtro que você deseja remover.

Indicadores-chave de desempenho

Você pode visualizar os seguintes indicadores-chave de desempenho (KPIs) no painel do Rightsizing:

- Total de despesas : Mostra o total de despesas alocadas atuais.
- Economia estimada com o Rightsizing : Mostra a economia potencial total estimada que pode ser obtida com todas as recomendações do Rightsize.
- Despesas otimizadas estim adas : mostra o total estimado de despesas após a aplicação das recomendações.

Tabela de recomendações de dimensionamento

O painel contém uma tabela de recomendações de dimensionamento de direitos, que fornece uma visão geral de seus recursos S3. A tabela inclui as seguintes colunas:

Nota:

Por padrão, os dados são classificados pela coluna Economia de custos. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- Nome do bucket : O nome do bucket S3.
- Nome da conta : O nome da conta AWS.
- Tamanho : O tamanho de todos os objetos dentro do compartimento.
- Objetos : O número de objetos dentro do compartimento.
- Solicitações : O número de solicitações (leitura, gravação, lista) feitas por meio do console ou da API.
- Custo : O custo incorrido nos últimos 30 dias para os objetos dentro do balde.
- Current : a classe de armazenamento derivada do bucket. Quando 100% de todos os objetos estiverem na mesma classe de armazenamento, essa classe de armazenamento será exibida. Se um bucket consistir em objetos de várias classes de armazenamento, será exibido MIXED. Ao clicar nos detalhes, será exibida a distribuição relativa entre essas classes.
- Novo : A classe de armazenamento ideal recomendada para todos os objetos no bucket.
- Ação : Recomendação para o recurso. A recomendação pode ser uma das seguintes

| Recomendação | Descrição |
| --- | --- |
| Dimensionamento correto | Redimensione para o tipo de recurso especificado na coluna Novo. |
| Sem ação | Nenhuma ação é recomendada por padrão, mas recomendações adicionais com níveis de risco mais altos podem estar disponíveis no painel Detalhes. |

Economia de custos : O valor estimado de economia de custos em 10 ou 30 dias.

Exportar recomendações para um arquivo Excel

Para exportar as recomendações para um arquivo Excel, selecione Exportar. Observe que o arquivo do Excel incluirá várias colunas adicionais, como região, sistema operacional, preço unitário e outras.

Detalhes da recomendação

Para exibir os detalhes da recomendação de um determinado recurso, selecione View Details (Exibir detalhes ) no menu More Options (Mais opções) (3 pontos).

A figura a seguir mostra um exemplo de painel de detalhes de recomendação.

![captura de tela dos detalhes da recomendação](../../../../03-media/cloudability-premium/images/s3-rightsizing-details-pane.jpg)

O painel de detalhes do S3 mostra as seguintes informações:

Recomendações

Mostra uma ou mais recomendações, classificadas por economia de custos e risco (0-5).

- Economia: Porcentagem de economia estimada para o período de 10 ou 30 dias.
- Economia de custos : Valor estimado da economia.
- Classe de armazenamento : Classe de armazenamento recomendada.
- Ação : Ação recomendada.
- Risco : em uma escala de 0 a 5, o número de transições de classe de armazenamento de acesso frequente para infrequente.

Gráficos

- Tamanho do armazenamento (Bytes) : Exibe a quantidade do tamanho do armazenamento por classe de armazenamento. Os valores possíveis incluem os seguintes:
  - Standard
  - FA inteligente (Intelligent Tiering - Frequent Access)
  - Intelligent IA (Intelligent Tiering = Acesso pouco frequente)
  - Acesso não frequente
  - 1 (uma) zona
  - Glacier
  - Deep Archive
  - Redundância reduzida
- Solicitações (leitura/gravação/contagem) : Exibe as solicitações de leitura e gravação realizadas no bucket. Esse gráfico fornece informações valiosas sobre a categoria de uso do bucket, como principalmente leituras, leituras e gravações equilibradas ou orientadas para gravação.
- Número de objetos (contagem) : O gráfico mostra o número de objetos no intervalo durante o período de tempo.
- Dados transferidos (bytes) : Quantidade de saída para a Internet (ou dados transferidos entre regiões).
- Transições de dados (Bytes) : Quantidade de dados transferidos entre classes de armazenamento (exclui Standard).
- Exclusão antecipada (Bytes) : Quantidade de armazenamento que incorre em uma taxa de exclusão antecipada.

Tomada de providências com relação às recomendações

Classes de armazenamento

Para fazer a transição da classe de armazenamento de objetos em massa, você tem duas opções:

- Gerenciamento do ciclo de vida do objeto

  Você pode ativar uma regra de gerenciamento do ciclo de vida no nível do bucket para fazer a transição de todos os objetos contidos para a classe de armazenamento recomendada com base na data de criação do objeto.

  Para obter mais informações sobre o gerenciamento do ciclo de vida dos objetos, consulte “[Gerenciamento do ciclo de vida dos objetos](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html "(Abre em uma nova guia ou janela)") ”.
- S3 Operações em lote

  Se preferir uma rota programática, você pode aproveitar o site S3 Batch Operations para alterar a classe de armazenamento de todos os objetos ou de objetos selecionados em um ou mais buckets.

  Para obter mais informações sobre operações em lote, consulte [https://aws.amazon.com/blogs/aws/new-amazon-s3-batch-operations/](https://aws.amazon.com/blogs/aws/new-amazon-s3-batch-operations/ "(Abre em uma nova guia ou janela)").

Classificação inteligente por níveis

O Intelligent Tiering é um serviço de classe de armazenamento híbrido que monitora os padrões e atributos de acesso de cada objeto. Com base nesses dados, o serviço fará a transição automática de objetos entre a classe de armazenamento Standard e Infrequent Access por uma taxa de monitoramento por objeto, além das taxas específicas da classe de armazenamento.

O rightsizing em nível de bucket ajuda você a identificar quais buckets se beneficiarão desse serviço. Embora a maioria dos objetos seja criada na classe Standard inicialmente, à medida que os buckets do S3 são otimizados ao longo do tempo, recomendações adicionais de otimização incremental, como Infrequent Access ou até mesmo Glacier, podem ser recomendadas.

Para obter mais informações, consulte [https://aws.amazon.com/s3/storage-classes/](https://aws.amazon.com/s3/storage-classes/ "(Abre em uma nova guia ou janela)").

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
