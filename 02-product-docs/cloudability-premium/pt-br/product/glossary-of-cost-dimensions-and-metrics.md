---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Glossário de dimensões e métricas de custo"
breadcrumb:
  - "Cloudability Premium"
  - "Referência de dados"
source_path: "product/glossary-of-cost-dimensions-and-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Glossário de dimensões e métricas de custo

Cloudability permitem que você analise seus dados de custo e uso para descobrir exatamente para onde seu dinheiro está indo. As dimensões e métricas disponíveis em seus relatórios estão identificadas abaixo.

## Dimensões de custo e uso

- ID da conta : O identificador exclusivo relacionado a uma conta do AWS, uma assinatura do Azure, um projeto do GCP ou uma locação OCI.
- Nome da conta : O nome dado pelo cliente que está associado a cada conta do AWS, assinatura do Azure, projeto do GCP ou locação OCI.
- ATUM Torre : Representa uma visão de TI de alto nível das funções tecnológicas da sua organização, fornecendo uma ampla categorização de custos. Exemplos de valores incluem Rede, Plataforma, Usuário Final e Aplicação.
- ATUM Sub-Torre : Oferece uma categorização mais detalhada em cada torre, por exemplo, dividindo a Plataforma em Middleware e Banco de Dados.
- ATUM Tipo de serviço : representa uma visão geral de alto nível dos seus gastos com a nuvem. Esta é a categorização de nível superior em serviços com valores como Serviços de Plataforma, Serviços de Entrega e Serviços ao Usuário Final.
- ATUM Categoria de serviço : oferece uma categorização mais detalhada em cada tipo de serviço, por exemplo, dividindo os serviços de entrega em operações, segurança e conformidade e suporte.
- ATUM Nome do serviço : esta é a categorização mais detalhada relacionada aos serviços, por exemplo, dividir a categoria de serviços de operações em gerenciamento de eventos, gerenciamento de serviços de TI e implantação e administração.
- Zona de disponibilidade : uma combinação da região e da zona em que um recurso existe. Por exemplo, us-east-1a.
- **Azure Nome do pedido de reserva** : O nome ou a descrição do produto ou serviço que foi pedido ou consumido, atualmente suportado apenas pelo site Azure.
- Nome do cluster : O "Nome do cluster" do Kubernetes ao qual pertencem os itens de custo subjacentes — como custos de VM, armazenamento e rede. O valor corresponde ao nome definido pelo seu administrador ao provisionar o cluster no site Cloudability.
- Nome do cluster : essa é uma dimensão específica do contêiner e não é suportada no momento.
- Compute Usage Type (Tipo de uso de computação ): dimensão útil definida em Cloudability para entender o tipo de computação de alguns serviços AWS, como EC2 e RDS. Essa dimensão pode ajudar o usuário a entender rapidamente a região e a categoria (como Spot, Dedicated Host, Mirror Usage) da computação.
- Data : A data do calendário - formatada como "Seg DD, AAAA" (9 de agosto de 2022).
- Day : O dia numérico do calendário (por exemplo, "Aug 9, 2022" => 9).
- Dia da semana : O dia da semana (por exemplo, segunda-feira).
- Mecanismo : O mecanismo de banco de dados ou de cache (por exemplo, Oracle, SQL Server, MySQL ou Redis ).
- Categoria da instância : A categoria de um servidor de base de dados ( VM ) ou de uma base de dados à qual uma instância pertence. As categorias comuns incluem Finalidade geral, Otimizado para computação e Otimizado para memória.
- Família da instância : a família de instâncias do ` VM ` ou do banco de dados à qual uma instância pertence. Normalmente, isso formará o prefixo da definição completa do tipo de instância. Para AWS, a família inclui o tipo e a geração (por exemplo, m6a, c6i, t3 ); para Azure, trata-se da série (por exemplo, A, B, D); e para GCP, trata-se do “tipo de série” (por exemplo, padrão, highmem). No momento, não há dados disponíveis para a OCI.
- Tamanho da instância : O tamanho de um VM e ou banco de dados. Isso está correlacionado aos principais atributos de recursos, como o número de CPUs e a memória disponível. Valores de exemplo: large, xlarge, 2xlarge para AWS; 2,4,8 para Azure; n1-8-vcpu, n1-16-vcpu para GCP. No momento, não há dados disponíveis para a OCI.
- Tipo de instância: O identificador completo do tipo de instância do ` VM ` ou do banco de dados, indicando tanto a família quanto o tamanho. Esse valor forma um componente completo da SKU do produto (usado junto com a localização e o sistema operacional). Por exemplo, c6g.large para AWS, Standard\_D2\_v3 para Azure e standard.c2-8-vcpu para GCP. No momento, não há dados disponíveis para a OCI.
- Data da fatura : a data da fatura para qualquer item de custo, conforme fornecido pelo fornecedor da nuvem. Isso é informado no formato "Seg DD, AAAA". O consumo de nuvem durante o mês geralmente recebe uma data de fatura no primeiro dia do mês.
- ID da fatura: O ID da fatura que corresponde a qualquer item de custo cobrado, conforme fornecido por AWS. Para o mês atual, em que o custo ainda não foi faturado, você verá um valor de "Estimado". Atualmente, não há dados disponíveis para Azure, GCP e OCI.
- Descrição do item : o texto mais descritivo disponível de cada fornecedor de nuvem detalhando cada item de custo. Para as últimas exportações detalhadas de faturamento, isso corresponde a "LineItemDescription" para AWS, "ProductName" + "additionalInfo" para Azure e “ sku.description ” para GCP e “product/Description” para OCI.
- Lease Type (Tipo de arrendamento ): O modo de pagamento dos itens de custo informados, com padrão "On-Demand" (Sob demanda). Os valores válidos são: On-Demand, Savings Plan, Reserved e Spot. Essa é uma dimensão de relatório definida por Cloudability para dar suporte à categorização de custos em várias nuvens.
- Mês (categoria) : O mês em que qualquer item de custo foi incorrido, formatado como "Seg". Exemplos "Jun", "Jul", "Aug". Isso é útil para examinar os custos por mês de qualquer ano (por exemplo, mostrar os custos que ocorreram em julho de qualquer ano).
- Mês (ano) : O mês e o ano de qualquer item de custo (formatado como Mês AAAA), útil para a classificação cronológica adequada. Exemplos: Julho de 2021, setembro de 2022.
- Namespace : O Kubernetes "Namespace" atribuído aos itens de custo subjacentes que pertencem a um cluster Kubernetes. O valor do custo alocado a cada valor do Namespace é calculado pelo site Cloudability por meio da análise da utilização de recursos do contêiner. Os recursos individuais da nuvem, como as instâncias do EC2, geralmente são divididos em vários Namespaces devido à sua natureza multilocatária.
- Namespace : Esta é uma dimensão específica do contêiner e não é suportada no momento.
- Sistema operacional : o sistema operacional das VMs, conforme informado pelos fornecedores de nuvem para fins de faturamento. Valores de exemplo: Linux, Windows, Red Hat Enterprise Linux.
- Operação : Essa dimensão mostra a ação específica realizada em um recurso. Por exemplo, se a rede estiver transferindo dados para dentro ou para fora de uma instância do VM. Quando combinado com o ID do recurso, isso ajuda os clientes a entender a origem e as ações que contribuíram para o custo. Para as exportações de faturamento detalhadas mais recentes, isso corresponde a “Operação” para AWS, "meterName" para Azure, "skuItem.categoryResourceGroup" para GCP e “cost/productSku” para OCI.
- **Número da peça** : Identificador usado para obter preços específicos de medidores, atualmente suportado apenas para Azure e OCI.
- ID da conta do pagador : O identificador exclusivo relacionado à conta de gerenciamento AWS, ao contrato EA/MCA Azure ou à conta de faturamento GCP. AWS As contas de membros, as assinaturas Azure, os projetos GCP e as locações OCI são normalmente consolidados nessas "contas de pagador".
- Nome da conta do pagador : O nome relacionado à conta de gerenciamento AWS, ao contrato EA/MCA Azure ou à conta de cobrança GCP ou à locação raiz OCI. Dependendo de sua situação, esse valor pode voltar para a ID de faturamento exclusiva.
- Nome do produto : O nome oficial do produto fornecido pelo fornecedor (por exemplo, Amazon Elastic Compute Cloud, GCP Cloud Storage, Microsoft.Compute ou OCI Compute).
- Região : a região em que um recurso existe ou uma cobrança de uso ocorreu, por exemplo: us-east-1 para AWS, US East para Azure e us-east1 para GCP e us-ashburn-1 para OCI.
- Classe de reserva : A oferta de compromisso vinculada a qualquer item de custo. Os valores de exemplo incluem instâncias reservadas "padrão" e "conversível", “EC2InstanceSavingsPlans” e “ComputeSavingsPlans” para planos de poupança.
- ID da reserva : a ID exclusiva do compromisso (como instância reservada e plano de economia) vinculada a qualquer item de custo, conforme fornecido pelo fornecedor da nuvem. Isso é particularmente útil para entender exatamente quais compromissos foram consumidos por um subconjunto de uso ou por um VM específico.
- **Nome da** reserva: O nome da instância da reserva adquirida.
- ID do recurso : esse é um identificador exclusivo usado pelo fornecedor para distinguir os recursos reais que são usados. Por exemplo, isso seria o ID da instância do VM, o nome do bucket de armazenamento ou o ID do volume de dados. Para GCP, atualmente usamos o ID do SKU para preencher o ID do recurso.
- **Vendedor** : O vendedor oficial de serviços. O uso dessa dimensão permite que você separe as cobranças do marketplace de seus outros custos de nuvem.
- Nome do serviço : Uma dimensão criada pela Cloudability que padroniza as convenções de nomenclatura de produtos para AWS, Azure, GCP e OCI:
  - AWS EBS torna-se seu próprio produto de nível superior.
  - Dados unificados que estavam misturados em vários produtos:
    - AWS rastreia o Cloudwatch parcialmente como um produto e como EC2. Isso separa o Cloudwatch em seu próprio serviço
    - AWS rastreia o Glacier parcialmente como um produto e em S3. Isso consolida todos os arquivos Glacier e S3
    - AWS tem um serviço de importação e exportação, bem como um serviço Snowball. O nome do serviço os consolida.
  - Em alguns casos, os dados dos sites AWS e Azure mostram vários produtos para os mesmos serviços:
    - AWS tem vários nomes para o Support. Isso consolida todos eles em um único item de linha AWS Support.
    - AWS tem muitos encargos administrativos listados como produtos de nível superior, como Amazon Partner Network, re:Invent Tickets, etc. Eles são consolidados em um único item administrativo AWS.
    - Azure tem computação, Microsoft.Compute e máquinas virtuais. Todos eles são iguais e consolidados em Azure Compute.
  - Em alguns casos, AWS e GCP são bastante semelhantes no que diz respeito aos nomes dos seus serviços:
    - GCP usa termos como Google Compute Engine e Google App Engine ( AWS EC2 ), Google Cloud SQL, Google Cloud Firestore e Google Cloud Bigtable ( AWS RDS e DynamoDB ).
  - AWS os arquivos de faturamento têm esquemas de nomes inconsistentes para os produtos. Por exemplo, o uso de acrônimos em vez de nomes completos (Amazon vs. AWS ). O nome do serviço segue um padrão de prefixo único.
    - AWS é o prefixo de todos os Amazon Web Services. Isso é seguido pelo nome que é visto no menu do console AWS (por exemplo, EC2, S3, RDS, Kinesis, Lambda, etc.).
    - Azure é o prefixo de todos os serviços Microsoft Azure.
  - Essa é uma dimensão de relatório definida por Cloudability para dar suporte à categorização de custos em várias nuvens.
- Tenancy : dimensão específica do AWS que identifica o tenancy das instâncias do EC2. Três valores válidos são compartilhado, host e dedicado. "compartilhado" é o valor padrão.
- Tipo de transação : O tipo de transação para qualquer item de custo. Os valores válidos são Uso, Cobrança recorrente (por exemplo, cobranças de suporte corporativo, instâncias reservadas não utilizadas), Única (por exemplo, compras antecipadas de instâncias reservadas), Imposto e Crédito. Essa é uma dimensão de relatório definida por Cloudability para dar suporte à categorização de custos em várias nuvens.
- Tipo de uso : Especifica os detalhes operacionais do item de linha de uso.
  - Por exemplo. USW1-BoxUsage:m2.2xlarge descreve o uso da caixa de instância EC2 High-Memory Double ExtraLarge da Amazon na região oeste dos EUA (Oregon).
- Família de uso : essa é uma dimensão padronizada definida por Cloudability para categorizar os tipos de alto nível de uso da nuvem entre os provedores. Os valores de exemplo incluem uso de instância, transferência de dados, armazenamento, solicitação de API, rede, uso de balanceador de carga, suporte e operação do sistema. Usada em conjunto com a dimensão de relatório Nome do serviço, a Família de uso pode ajudar os usuários a entender rapidamente o que está impulsionando seus gastos com a nuvem.
- Fornecedor : o fornecedor de nuvem associado ao item de custo. Os valores válidos são Amazon, Azure, GCP e OCI.
- Semana (ano) : A semana e o ano de qualquer item de custo (formatado como AAAA-WW), útil para a classificação cronológica adequada. Exemplos: 2021-06, 2022-52.
- **Semana (categoria)** : A semana em que qualquer item de custo foi incorrido, formatada como "WW". Exemplos "01", "15", "52". Isso é útil para examinar os custos por semana de qualquer ano (como mostrar os custos que ocorreram na semana 1 de qualquer ano).
- **Ano** : O ano civil em que qualquer item de custo ocorreu, formatado como AAAA (por exemplo, 2022).
- Zone (Zona ): esse campo é específico para AWS e corresponde à letra de uma zona específica na qual existe uma instância ou ocorreu uma cobrança de uso em uma Availability Zone (Zona de disponibilidade). Por exemplo, a Zona AWS "a" corresponde às Zonas de Disponibilidade " eu-west-1a " ou " ap-southeast-2a " etc. Este campo não é utilizado para Azure, GCP e OCI.

## Métricas de custo e uso

- Custo (lista) : essa métrica representa o custo dos itens que os clientes cobram na tarifa pública sob demanda. Isso significa que quaisquer compromissos (instâncias reservadas e planos de economia), preços de instâncias pontuais e preços personalizados (normalmente descontos empresariais) não são considerados nessa métrica. A métrica é derivada da combinação de dados disponíveis nos arquivos de faturamento detalhados do fornecedor e em suas planilhas de preços baseadas em API, e está atualmente implementada para todos os serviços do AWS. Para Azure, a métrica "Custo (lista)" é compatível com serviços sob demanda. Além disso, o uso de sua instância de compromisso nos tipos de arrendamento "Reserved" e "Savings Plan" é compatível com serviços selecionados - atualmente, somente Azure Compute e Azure Database.

- Custo (Total) : Essa é a métrica de custo padrão em Cloudability. É uma métrica de "caixa" e representa simplesmente o valor faturado associado a qualquer item de custo, conforme relatado pelo fornecedor de nuvem. Para AWS, isso corresponde à coluna lineItem/UnblendedCost do arquivo CUR; para Azure, à coluna CostInBillingCurrency da exportação de faturamento padrão; e para GCP, ao atributo de custo da tabela BigQuery; e para OCI, à coluna cost/myCost no relatório de custos.
  - **Como as porções "usadas" dos custos são alocadas para os RIs:**   
     Quando AWS não aloca a parte "usada" dos RIs aos recursos para UnblendedCost, Cloudability a aloca aos recursos que se beneficiaram dos RIs. Caso contrário, os encargos seriam alocados à conta na qual o RI foi comprado. Você pode alocar alocações de showback ou chargeback melhores devido a esse aprimoramento, o que aumentará a transparência do uso real.
- Custo (Total Blended) : Essa métrica de custo é específica para AWS e corresponde à coluna lineItem/BlendedCost do arquivo CUR. Essa métrica "combina" o impacto das instâncias reservadas e dos planos de economia. Isso pode levar a números inesperados. Portanto, recomenda-se usar o Custo (Total) ou o Custo (Amortizado).
- Custo (amortizado) : em contraste com o custo (total), que é uma métrica de "caixa", o custo (amortizado) é uma métrica de custo de "acumulação", representando o custo consumido durante qualquer período. Essa métrica é útil para garantir que os compromissos, como instâncias reservadas e planos de economia (incluindo pagamentos antecipados), sejam alocados para o tempo e o local em que são consumidos. Para os itens do site AWS, o site Cloudability se baseia em uma combinação de colunas no CUR para exibir esse valor. Para Azure, é usada a coluna CostInBillingCurrency da exportação do faturamento amortizado.   
   **Observação:** os itens de linha do compromisso inicial são exibidos como US$ 0 nessa métrica.
- Custo (ajustado) : Criado a partir da métrica Custo (total), essa métrica ajusta os valores para permitir quaisquer regras de preços personalizadas. Essa métrica é comumente usada com os dados do site AWS para que os descontos corporativos possam ser levados em conta de forma consistente no nível do item de linha de uso, em vez de aparecerem em massa no final do mês. Essa métrica aparece apenas para os clientes do site Cloudability que ativaram o módulo de preços personalizados.
- Custo (amortizado ajustado) : Criado a partir da métrica Custo (amortizado), essa métrica ajusta os valores para permitir quaisquer regras de preços personalizadas. Essa métrica é mais comumente usada com os dados do site AWS para que os descontos corporativos possam ser levados em conta de forma consistente no nível do item de linha de uso, em vez de aparecerem em massa no final do mês. Essa métrica aparece apenas para os clientes do site Cloudability que ativaram o módulo de preços personalizados.
- Ajuste de custo : O valor pelo qual o custo foi ajustado.

Nota:

**Isso não está disponível a menos que o Custom Pricing esteja ativado.**

- **Transferência de dados ( GiB ) : Quantidade de dados transferidos em um determinado período de tempo.**
- **GiB Horas : um gibibyte-hora refere-se ao número de gibibibytes armazenados em uma plataforma de nuvem em um determinado período de uma hora.**

- GiB Meses : Refere-se ao número de gibibytes de um recurso para AWS, Azure, GCP e OCI em um determinado período mensal.
- Solicitações de E/S : Descreve o número de solicitações de dados de um serviço de banco de dados.
- Meses de IOPS : as operações de entrada e saída de armazenamento por segundo associadas aos serviços de armazenamento.
- Horas sob demanda : A quantidade de horas de computação sob demanda usadas durante o período do relatório. Para obter mais informações, consulte [Dimensões e métricas usadas com frequência](frequently-used-dimensions-and-metrics.html).
- Taxa (combinada) : para contas de faturamento consolidado, a taxa efetiva do item de linha calculada como uma média do custo de instâncias idênticas operando naquela hora na mesma zona de disponibilidade.
- Taxa (não combinada) : o custo por hora de um item de linha. Isso é resumido nas horas de um dia. Para obter informações adicionais, consulte [Emerge](http://blog.cloudability.com/what-you-need-to-know-about-blended-rates-on-aws/ "(Abre em uma nova guia ou janela)").
- Solicitações : o número de recursos de computação usados nas unidades especificadas por cada serviço. Por exemplo, seu serviço pode determinar o preço de acordo com a quantidade de armazenamento, o número de solicitações ou o horário de funcionamento. Para obter mais informações sobre como o uso é calculado, clique em [Preços do AWS](http://aws.amazon.com/pricing/ "(Abre em uma nova guia ou janela)").
- Taxa de cobertura reservada : a porcentagem do total de horas de uso durante o período em que as instâncias reservadas foram aplicadas. Para obter mais informações, consulte [Dimensões e métricas usadas com frequência](frequently-used-dimensions-and-metrics.html).
- Horas reservadas : O número de horas de computação reservadas usadas durante o período do relatório. Para obter mais informações, consulte [Dimensões e métricas usadas com frequência](frequently-used-dimensions-and-metrics.html).
- Contagem de recursos : essa nova métrica indica a contagem de recursos exclusivos em um determinado período de tempo. Isso permite que os clientes entendam o número de ativos que eles controlam e como eles oscilam e fluem ao longo do tempo.
- Horas de uso : o número de recursos de computação usados nas unidades especificadas por cada serviço. Por exemplo, seu serviço pode determinar o preço de acordo com a quantidade de armazenamento, o número de solicitações ou o horário de funcionamento.
- Quantidade de uso : A quantidade consumida para o item de custo. A unidade está vinculada à SKU específica e à forma como ela é carregada. Por exemplo, esse número representará o número de horas de instância consumidas para VMs, GiB-months para armazenamento e GiB para dados transferidos. Para despesas em AWS e Azure, essa métrica complementa as métricas de taxa (não combinada) e custo (total) quando usadas juntas em um relatório para explicar o valor cobrado pelo fornecedor de nuvem.

## Métricas de sustentabilidade

- Emissões estimadas de carbono ( MTCO2e ) : esta métrica captura as emissões estimadas de carbono em toneladas métricas de equivalentes de dióxido de carbono.
- **Potência consumida ( kWh )** : Potência consumida em quilowatts-hora.
- **Emissões de carbono operacionais** **( MTCO2e )** — Esta métrica representa as emissões de carbono geradas durante a operação diária dos serviços em nuvem. Isso se deve principalmente à eletricidade utilizada para alimentar e refrigerar os centros de dados durante a execução das cargas de trabalho.
- **Emissões de carbono incorporadas** **( MTCO2e )** — Esta métrica representa a parcela das emissões de carbono associadas à produção e ao ciclo de vida da infraestrutura em nuvem. No contexto da nuvem, isso é estimado através da alocação de uma parcela das emissões totais incorporadas dos servidores físicos e equipamentos, com base no seu uso específico.
