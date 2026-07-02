---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Como o gerenciamento de compromissos difere entre os provedores de serviços em nuvem"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Otimização de custos da nuvem em Cloudability"
source_path: "product/commitment_management_across_providers.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Como o gerenciamento de compromissos difere entre os provedores de serviços em nuvem

## Propósito

O objetivo deste documento é apresentar como os descontos baseados em compromisso funcionam entre os diferentes provedores de serviços de nuvem (CSPs).

## Introdução aos tipos de compromisso

Todos os modelos de preços com desconto baseados em compromisso buscam o mesmo objetivo: trocar a previsibilidade de uso e o bloqueio do fornecedor por um preço com desconto. Cada provedor oferece uma maneira de pagar menos do que sob demanda se você estiver disposto a se comprometer, geralmente com uma pegada de recursos e um nível de gastos específicos. Os detalhes variam, mas as questões práticas são universais, *Que taxa de desconto estou recebendo? Quanto gasto estou comprometido e por quanto tempo? Como o desconto é aplicado e informado? Como posso medir o desempenho?*

Primeiro, definiremos algumas terminologias para simplificar esta discussão.

**Compromisso -** Compromisso é o nosso termo abreviado, independente de fornecedor, usado para descrever esses descontos em Cloudability.

**Tipo de compromisso -** um tipo de compromisso é o termo Cloudability escolhido para descrever as diferentes versões desses contratos. (Tipo) é explicitamente usado para diferenciar o modelo de preços do nome do serviço subjacente. Como você aprenderá em breve, alguns serviços, especialmente os de computação, têm vários tipos de compromisso aplicáveis. Notavelmente, essa definição está [definida no FOCUS](https://focus.finops.org/focus-columns/#commitment-discount-type "(Abre em uma nova guia ou janela)"). Concordamos e aceitamos essa definição

**Compromissos baseados em recursos -** Em todas as nuvens, surgem dois padrões. Primeiro, os compromissos baseados em recursos oferecem um desconto em troca de um compromisso com uma determinada quantidade de uso de um produto ou serviço.

**Compromissos baseados em despesas** - Esses compromissos oferecem um desconto em troca de um compromisso com um determinado valor de despesas em um produto ou serviço. Os compromissos baseados em gastos diferem dos compromissos baseados em recursos, pois abrangem um conjunto mais amplo de uso, mas exigem atenção cuidadosa à utilização para que você não compre mais compromissos do que o seu mix de carga de trabalho pode consumir.os compromissos baseados em recursos têm o benefício de um desconto maior com uma matemática de equilíbrio mais clara, enquanto a contrapartida é um alinhamento mais rígido com os atributos de uso.

**Categoria de compromisso** - vamos nos referir ao fato de um tipo de compromisso poder ser classificado como recurso ou despesa como a categoria de compromisso.notavelmente, essa definição também está [definida no FOCUS](https://focus.finops.org/focus-columns/#commitment-discount-category "(Abre em uma nova guia ou janela)"). Concordamos e aceitamos essa definição.

Os CSPs têm nomes formais para cada tipo de compromisso. Aqui, tentaremos explicar de forma geral como os nomes dos compromissos variam de acordo com o fornecedor

**Instância reservada - RI ( AWS, Azure ) -** Oferece um desconto em troca do compromisso de usar uma quantidade específica de um produto ou serviço definido. Comumente usado para serviços em que o uso subjacente é definido como uma instância de computação. Por exemplo, a terminologia mudará para nó reservado para AWS Redshift, pois o uso subjacente é definido em nós. Independentemente disso, nessas situações, esse conceito funciona de forma semelhante.

Observe que as instâncias reservadas são comumente abreviadas como RIs.

**Plano de economia - SP ( AWS, Azure ) -** Oferece um desconto em troca do compromisso de gastar um valor específico (geralmente expresso em $/hora) em serviços elegíveis. Este tipo de compromisso é específico para AWS e Azure e aplicável apenas a gastos com computação. Para Azure, os Planos de Poupança são explicitamente separados em uma seção diferente das outras reservas nas páginas de compras em seu console.

Observe que os Planos de Poupança são comumente abreviados como SPs.

**Reservas ( Azure ) -** Termo genérico do Azure para compromissos em vários serviços.

**Plano de pré-compra - PPP ( Azure ) -** Uma opção de compromisso de gastos do Azure que utiliza créditos fungíveis que não expiram a cada hora, aplicados em todos os serviços elegíveis.

Observe que os Planos de Compra são comumente abreviados como PPPs.

**Desconto por uso comprometido - CUD** **( GCP ) -** Termo genérico da GCP para compromissos em vários serviços.

**Gastar CUDs** **( GCP ) -** Variante de compromisso baseada em gastos da GCE. É funcionalmente semelhante a um Plano de Poupança AWS / Azure. Google Compute Engine A variante CUD de gastos do GCE é especificamente referida como GCE Flex-CUD, enquanto que o recurso CUD é simplesmente um GCE CUD. GCP é único em comparação com AWS e Azure, pois prioriza compromissos para serviços fora da computação.

## Introdução às opções de compra

Em seguida, há várias opções diferentes que definem como um compromisso é estruturado e implementado.

**Prazo ( AWS,** **Azure, GCP ) -** Um termo universal usado para descrever a duração do compromisso, normalmente de 1 ou 3 anos, com casos especiais em que pode ser de apenas 1 mês ou até 6 anos.

**Opção de pagamento ( AWS, GCP ) -** O termo AWS é usado para descrever como um compromisso é cobrado. AWS tem três opções para muitos de seus compromissos: sem pagamento antecipado (semelhante ao plano mensal d Azure ), pagamento antecipado parcial (onde metade do custo é cobrada antecipadamente) e pagamento antecipado. Tal como Azure, estas opções de pagamento oferecem descontos diferentes. Conforme mencionado em Cloudability, utilizamos o termo independente do fornecedor, Opção de Pagamento. Este termo não está explicitamente definido em GCP, uma vez que os seus compromissos são todos sem adiantamento. No entanto, para representar essas informações de maneira uniforme, atribuímos esse parâmetro a GCP.

**Frequência de cobrança ( Azure ) -** O termo que Azure usa para descrever como um compromisso é cobrado. Azure tem duas opções para muitos de seus compromissos: mensal e adiantado. Essas frequências de cobrança têm descontos diferentes. Em Cloudability, usamos o termo independente de fornecedor, Payment Option, para Azure.

**Região ( AWS, Azure, GCP ) -** Um termo universal entre os fornecedores, que define onde os recursos físicos estão localizados, afetando assim o agrupamento, o potencial de utilização e a flexibilidade. A região é relevante para a maioria dos tipos de compromisso, exceto para os planos de poupança AWS e Azure.

**Zona de disponibilidade** **( AWS ) -** Uma zona de disponibilidade (AZ) é um ou mais data centers discretos com energia, resfriamento e rede independentes, vinculados dentro da região por conectividade de baixa latência. Alguns compromissos do AWS podem ser adquiridos por AZ em vez de por região. No caso de compromissos baseados na zona de disponibilidade, os descontos são inerentemente menores, pois o contrato oferece menos previsibilidade ao fornecedor.

## Introdução à estrutura da conta

Além dessas opções básicas de pagamento, é fundamental entender como a estrutura da conta ditará a forma como um compromisso será realizado.

**Conta do pagador -** termo agnóstico do fornecedor do Cloudability para descrever a conta principal que está sofrendo cobranças.

**Conta vinculada -** Cloudability é um termo independente de fornecedor para descrever a conta secundária que está sofrendo cobranças. As contas vinculadas têm uma relação de muitos para um com as contas de pagadores.

Unidades **Organizacionais** **- UO** **( AWS ) -** Um contêiner semelhante a uma pasta que você usa dentro do AWS Organizations para agrupar várias contas AWS em uma hierarquia comum (Raiz → UOs → Contas). As UOs não possuem recursos nem incorrem em cobranças - elas existem para organizar contas e aplicar a governança em escala. Essas unidades podem ser aninhadas e operar acima do nível em que um compromisso é adquirido.

**Conta de gerenciamento ( AWS ) -** Semelhante à conta Cloudability Payer, essa conta AWS representa o local onde os usuários podem criar políticas e delegar contas de membros. A conta de gerenciamento não precisa estar diretamente sob a raiz, ela pode ser colocada em qualquer lugar da organização.

Conta **de membro** **( AWS ) -** Semelhante a uma conta vinculada, esta conta AWS é onde os recursos residem e os custos são gerados.

**Conta** **de faturamento** **( Azure ) -** A conta que define o modelo de faturamento (EA, MCA, CSP/MPA). Assim como AWS OUs, essa construção está acima do escopo de relevância para um compromisso.

**Perfil de faturamento ( Azure ) -** Um perfil de faturamento representa uma fatura e as informações de faturamento relacionadas, como métodos de pagamento e endereço de faturamento. É semelhante a uma conta de pagador em Cloudability.

**Assinatura ( Azure ) -** No Azure, uma assinatura é um contêiner de recursos que também funciona como unidade de faturamento. O uso gerado pelos recursos em uma assinatura é faturado por meio de qualquer modelo de conta de faturamento em que você esteja (EA, MCA, CSP/MPA).

**Assinatura de faturamento** **( Azure ) -** Com base na definição de assinatura, uma assinatura de faturamento Azure é a assinatura por meio da qual o uso é consolidado em sua fatura. É semelhante a uma conta vinculada em Cloudability.

**Escopo ( Azure ) -** No momento da compra, um escopo de compromissos pode abranger uma assinatura ou várias assinaturas. Quando compartilhado, o desconto é aplicado a assinaturas qualificadas em seu contexto de faturamento.

- Quando a assinatura é única, o desconto da reserva é aplicado aos recursos correspondentes na assinatura selecionada.
- Quando se trata de um único grupo de recursos, o desconto da reserva é aplicado somente aos recursos correspondentes no grupo de recursos selecionado.
- Para os clientes do Contrato Enterprise, o contexto de faturamento são todas as assinaturas no registro do EA.
- Para clientes Pay-As-You-Go, o contexto de faturamento são todas as assinaturas elegíveis criadas pelo administrador da conta.
- Para o Contrato de Cliente da Microsoft, o contexto de faturamento é o perfil de faturamento.

**Conta de cobrança ( GCP ) -** Conta do pagador da GCP onde os recursos residem e os custos são gerados.

**Projeto ( GCP ) -** Conta vinculada do GCP onde os recursos são armazenados e os custos são gerados.

## Introdução à flexibilidade do tamanho da instância

**Sobre a flexibilidade do tamanho da instância para o Rls do RDS**

As instâncias reservadas (RIs) do Amazon RDS agora se beneficiam da [flexibilidade de tamanho de instância](https://www.ibm.com/links?url=https%3A%2F%2Faws.amazon.com%2Fabout-aws%2Fwhats-new%2F2017%2F10%2Famazon-rds-reserved-instances-offer-instance-size-flexibility%2F "(Abre em uma nova guia ou janela)") (ISF) da mesma forma que a ISF se aplica às instâncias do EC2. Atualizamos o mecanismo que alimenta nosso RI Planner para acomodar a mudança em nossas recomendações para instâncias RDS. Comprar com o benefício ISF reduzirá suas despesas administrativas e proporcionará a máxima economia.

**O que é a ISF?**

O ISF é um recurso das RI ( RDS ) que permite que a economia de uma RI se aplique a qualquer tamanho de instância dentro de uma família. Você obtém automaticamente esse benefício ao adquirir um RI na mesma região do Amazon Web Services ( AWS ) (para configurações Single-AZ e Multi-AZ), mecanismo de banco de dados e família de instâncias. O ISF está disponível para os seguintes mecanismos de banco de dados: Amazon Aurora, MariaDB, MySQL, PostgreSQL, Oracle (edição Bring Your Own License).

**Como funciona o ISF?**

A ISF gerencia suas reservas em um sistema baseado em pontos, no qual uma escala determina as unidades atribuídas a cada tamanho dentro de uma família. Quando você executa uma instância, por exemplo, db.m3.large, qualquer ISF RI dentro da família db.m3 pode ser aplicado à instância, e o número de pontos que seu RI tem em relação aos pontos para o tamanho da instância executada determina quanto ou quantos RI são consumidos por essa hora de instância. Os números de unidades normalizadas por tamanho de instância de banco de dados são:

**ISF no RI Planner**

Em nosso RI Planner, na guia “ RDS ” (Planejamento de fundos), levamos em consideração o ISF ao fazer recomendações. Ainda analisamos o uso por segundo da instância e levamos em consideração todo o seu inventário de RIs, incluindo RIs ISF e não ISF, antes de fazer uma recomendação. Para ISF RIs, como qualquer tamanho de RI pode ser aplicado a uma instância executada dentro de uma família, você não precisará mais adquirir vários tamanhos e, em vez disso, poderá adquirir para a família, banco de dados e região com base em unidades normalizadas. Na prática, você pode abstrair o conceito de compra para o seu perfil de tipo de instância e, em vez disso, apenas comprar pontos.

Há várias maneiras de conseguir isso, mas após muitos testes internos de cenários e discussões com nossos maiores clientes, estabelecemos um padrão eficaz que incorporamos ao planejador.

No esquema abaixo, o uso da amostra ao longo de um período de tempo ajuda a ilustrar como o ISF funciona. Para cada unidade de tempo, imagine que você está executando uma combinação de instâncias. [A meta de uma linha de água](https://www.ibm.com/links?url=https%3A%2F%2Fwww.apptio.com%2Fcase-study%2Fatlassian-leverages-apptio-cloudabilitys-big-data-analytics-engine-to-improve-reserved-instance-coverage%2F "(Abre em uma nova guia ou janela)") ainda é válida e, no caso de utilização de 100% de RI, recomendamos que você adquira 10 RIs grandes, pois esses são os menores tamanhos de instância disponíveis. Você tem uma compra de RI e, quando seu uso normalizado permanecer o mesmo ou aumentar, seus RIs continuarão sendo utilizados perfeitamente.

A página **Detalhes** do RI Planner mostra como aplicamos o ISF a uma instância do RDS.

**Nossa estratégia ISF ( RDS )**

A filosofia que adotamos com o ISF ( EC2 ) concentrou-se em reduzir suas despesas administrativas e, ao mesmo tempo, maximizar suas economias. Para o ISF ( RDS ) também, fazemos recomendações para o menor tamanho de instância possível e Single-AZ. Isso permite a cobertura máxima com o menor conjunto de parcelas RI. Observe que as parcelas serão grandes e talvez seja necessário [solicitar um aumento](https://www.ibm.com/links?url=https%3A%2F%2Fsignin.aws.amazon.com%2Fsignin%3Fredirect_uri%3Dhttps%253a%252f%252fconsole.aws.amazon.com%252fsupport%252fhome%253fstate%253dhashargs%252523case%25252fcreate%25253fissuetype%25253dservice-limit-increase%252526limittype%25253dservice-code-rds-instances%252526type%25253dservice_limit_increase%252526servicelimitincreasetype%25253drds-instances%2526isauthcode%253dtrue%26client_id%3Darn%253aaws%253aiam%253a%253a015428540659%253auser%252fsupportcenter%26forcemobileapp%3D0%26code_challenge%3Drqkdlstpj9sj50c95lgyoxfcdgnasohhi8yrhlwilo0%26code_challenge_method%3Dsha-256 "(Abre em uma nova guia ou janela)") do seu limite de compra RI à Amazon para acomodar a compra de uma grande quantidade de instâncias de tamanho pequeno.

Você se beneficiará de um ciclo de vida RI mais simplificado com a compra de grandes quantidades, em vez de, como no passado, ter que fazer várias compras de tamanhos diferentes por família. Essa estratégia também ajudará você a gerenciar melhor seu inventário se o uso diminuir, com a capacidade de vender um número muito mais granular de unidades RI para se adequar aos novos padrões de uso.

**O que é a ISF?**

O ISF é um recurso das RI ( RDS ) que permite que a economia de uma RI se aplique a qualquer tamanho de instância dentro de uma família. Você obtém automaticamente esse benefício ao adquirir um RI na mesma região do Amazon Web Services ( AWS ) (para configurações Single-AZ e Multi-AZ), mecanismo de banco de dados e família de instâncias. O ISF está disponível para os seguintes mecanismos de banco de dados: Amazon Aurora, MariaDB, MySQL, PostgreSQL, Oracle (edição Bring Your Own License).

**Como funciona o ISF?**

A ISF gerencia suas reservas em um sistema baseado em pontos, no qual uma escala determina as unidades atribuídas a cada tamanho dentro de uma família. Quando você executa uma instância, por exemplo, db.m3.large, qualquer ISF RI dentro da família db.m3 pode ser aplicado à instância, e o número de pontos que seu RI tem em relação aos pontos para o tamanho da instância executada determina quanto ou quantos RI são consumidos por essa hora de instância. Os números de unidades normalizadas por tamanho de instância de banco de dados são:

**ISF nas recomendações de compromisso**

Em nossas Recomendações de Compromisso, levamos em consideração o ISF ao fazer recomendações. Ainda analisamos o uso por segundo da instância e levamos em consideração todo o seu inventário de RIs, incluindo RIs ISF e não ISF, antes de fazer uma recomendação. Para ISF RIs, como qualquer tamanho de RI pode ser aplicado a uma instância executada dentro de uma família, você não precisará mais adquirir vários tamanhos e, em vez disso, poderá adquirir para a família, banco de dados e região com base em unidades normalizadas. Na prática, você pode abstrair o conceito de compra para o seu perfil de tipo de instância e, em vez disso, apenas comprar pontos.

Há várias maneiras de conseguir isso, mas após muitos testes internos de cenários e discussões com nossos maiores clientes, estabelecemos um padrão eficaz que incorporamos ao planejador.

No esquema abaixo, o uso da amostra ao longo de um período de tempo ajuda a ilustrar como o ISF funciona. Para cada unidade de tempo, imagine que você está executando uma combinação de instâncias. [A meta de uma linha de água](https://www.ibm.com/links?url=https%3A%2F%2Fwww.apptio.com%2Fcase-study%2Fatlassian-leverages-apptio-cloudabilitys-big-data-analytics-engine-to-improve-reserved-instance-coverage%2F "(Abre em uma nova guia ou janela)") ainda é válida e, no caso de utilização de 100% de RI, recomendamos que você adquira 10 RIs grandes, pois esses são os menores tamanhos de instância disponíveis. Você tem uma compra de RI e, quando seu uso normalizado permanecer o mesmo ou aumentar, seus RIs continuarão sendo utilizados perfeitamente.

A página Detalhes das recomendações de compromisso mostra como aplicamos o ISF a uma instância do RDS.

**Nossa estratégia ISF ( RDS )**

A filosofia que adotamos com o ISF ( EC2 ) concentrou-se em reduzir suas despesas administrativas e, ao mesmo tempo, maximizar suas economias. Para o ISF ( RDS ) também, fazemos recomendações para o menor tamanho de instância possível e Single-AZ. Isso permite a cobertura máxima com o menor conjunto de parcelas RI. Observe que as parcelas serão grandes e talvez seja necessário [solicitar um aumento](https://www.ibm.com/links?url=https%3A%2F%2Fsignin.aws.amazon.com%2Fsignin%3Fredirect_uri%3Dhttps%253a%252f%252fconsole.aws.amazon.com%252fsupport%252fhome%253fstate%253dhashargs%252523case%25252fcreate%25253fissuetype%25253dservice-limit-increase%252526limittype%25253dservice-code-rds-instances%252526type%25253dservice_limit_increase%252526servicelimitincreasetype%25253drds-instances%2526isauthcode%253dtrue%26client_id%3Darn%253aaws%253aiam%253a%253a015428540659%253auser%252fsupportcenter%26forcemobileapp%3D0%26code_challenge%3Drqkdlstpj9sj50c95lgyoxfcdgnasohhi8yrhlwilo0%26code_challenge_method%3Dsha-256 "(Abre em uma nova guia ou janela)") do seu limite de compra RI à Amazon para acomodar a compra de uma grande quantidade de instâncias de tamanho pequeno.

Você se beneficiará de um ciclo de vida RI mais simplificado com a compra de grandes quantidades, em vez de, como no passado, ter que fazer várias compras de tamanhos diferentes por família. Essa estratégia também ajudará você a gerenciar melhor seu inventário se o uso diminuir, com a capacidade de vender um número muito mais granular de unidades RI para se adequar aos novos padrões de uso.

## Diferenças gerais diversas

Há várias nuances que também são relevantes para serem destacadas aqui.

- Em AWS e Azure, os compromissos de recursos são adquiridos em termos do número de unidades de um tamanho predeterminado. Isso contrasta com GCP, onde os CUDs de recursos GCE são adquiridos em subquantidades discretas (memória vCPU,, SSD, GPU).
- AWS e Azure 's compromissos de gastos adquiridos em termos de custo do compromisso. GCP Os CUDs, por outro lado, são comprados pelo equivalente sob demanda. Observe que isso está mudando em janeiro de 2026.
- AWS e Azure incluem uma métrica de cobertura, em termos de horas de uso, no arquivo de cobrança. GCP notavelmente não inclui essa métrica.

Em seguida, começaremos a nos aprofundar em como o Cloudability ajuda a otimizar seus gastos com a nuvem.

**Tópico principal:** [Otimização de custos de nuvem em Cloudability](../product/cloud_cost_optimization.html)
