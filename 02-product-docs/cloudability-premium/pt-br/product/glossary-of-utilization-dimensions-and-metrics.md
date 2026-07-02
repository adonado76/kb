---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Glossário de dimensões e métricas de utilização"
breadcrumb:
  - "Cloudability Premium"
  - "Referência de dados"
source_path: "product/glossary-of-utilization-dimensions-and-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Glossário de dimensões e métricas de utilização

Cloudability as ferramentas de geração de relatórios da Web permitem que você analise os dados de utilização para descobrir exatamente como sua infraestrutura está sendo usada. Divididas em duas seções, as dimensões e métricas disponíveis em seus relatórios são identificadas abaixo.

1. [Dimensões de utilização](#utilization_dimensions "(Abre em uma nova guia ou janela)")
2. [Métricas de utilização](#utilization_metrics "(Abre em uma nova guia ou janela)")

**Dimensões de utilização**

- ID da conta : O número de 12 dígitos AWS usado para identificar uma conta. Para a análise de custos das contas de faturamento consolidadas, isso se refere a uma conta vinculada.
- Nome da conta : O nome associado a uma conta AWS. Para a análise de custos das contas de faturamento consolidadas, isso se refere a uma conta vinculada.
- AMI : essa dimensão filtra os dados que você solicita para todas as instâncias que executam essa AMI (Amazon Machine Image) EC2. Disponível para instâncias com o Monitoramento detalhado ativado.
- Arquitetura : A arquitetura básica do hardware da instância (por exemplo, x86, x86\_64, i386 ).
- Zona de disponibilidade : uma combinação da região e da zona em que uma instância existe ou em que ocorreu uma cobrança de uso (por exemplo, us-east-1a ).
- Velocidade do clock da CPU : a velocidade básica do clock dos processadores na instância (GHz).
- Current State : O estado atual da instância EC2 (por exemplo, em execução, parada). Consulte o [Guia do usuário do ciclo de vida da instância AWS](http://docs.aws.amazon.com/awsec2/latest/userguide/ec2-instance-lifecycle.html "(Abre em uma nova guia ou janela)") para obter informações adicionais.
- Data : A data do calendário (por exemplo, AAAA-MM-DD).
- Day : O dia do mês.
- Dia da semana : O dia da semana (por exemplo, segunda-feira).
- Days Alive (Dias ativos ): o número total de dias desde que a instância foi inicialmente iniciada.
- Nome DNS : O nome DNS público associado a uma instância específica do EC2 (por exemplo, ec2-54-205-210-122.compute-1.amazonaws.com ).
- Hour : A hora numérica do dia (por exemplo, 1pm => 13).
- Categoria da instância : a categoria da instância (por exemplo, finalidade geral, otimizada para computação etc.).
- ID da instância : a ID associada a uma instância específica do site AWS.
- Nome da instância : O nome de uma instância específica do site EC2.
- Tipo de instância : O tamanho de uma instância (por exemplo, m1.medium ). Para obter mais informações, consulte [Dimensões e métricas usadas com frequência](frequently-used-dimensions-and-metrics.html).
- Endereço IP : O endereço IP associado a uma instância específica do EC2.
- **Última execução** : A data da última execução do recurso.
- Data de lançamento : A data de lançamento de uma instância específica (por exemplo, 2014-01-22).
- Dia de lançamento : O dia de lançamento de uma instância específica (por exemplo, segunda-feira).
- Dia da semana de lançamento : O dia da semana em que uma determinada instância foi lançada (por exemplo, segunda-feira).
- Mês de lançamento : O mês numérico em que uma instância foi lançada (por exemplo, 1 => janeiro).
- Hora de lançamento : o valor de data e hora que descreve quando uma instância foi lançada (por exemplo, 2000-01-01T22:46:34Z ).
- Semana de lançamento : a semana do ano em que uma instância foi lançada (ou seja, 52 indicaria a última semana em um ano civil).
- Ano de lançamento : O ano em que uma instância foi lançada.
- Month : O mês numérico do calendário (por exemplo, 2014-1-15 => 12).
- SO : O sistema operacional de uma instância (por exemplo, Linux ).
- Nome DNS privado : as instâncias do Amazon EC2 precisam de endereços IP para se comunicar. Os endereços IP públicos permitem a comunicação pela Internet.
- IP privado : as instâncias do Amazon EC2 precisam de endereços IP para se comunicar. Os endereços IP privados permitem a comunicação.
- Arquitetura do processador : A arquitetura da CPU.
- Região : Região na qual existe uma instância ou ocorreu uma cobrança de uso (por exemplo, Leste dos EUA).
- IDs de grupos de segurança : um grupo de segurança atua como um firewall que controla o tráfego de uma ou mais instâncias. Cada grupo de segurança é identificado por um ID exclusivo (por exemplo, sg-xxxxxxxxxx).
- Nomes de grupos de segurança : um grupo de segurança atua como um firewall que controla o tráfego de uma ou mais instâncias. Cada grupo de segurança requer um nome exclusivo (limite de 255 caracteres).
- Tipo de armazenamento : Nenhum conteúdo foi fornecido para esta entrada ainda
- ID da sub-rede : A ID da sub-rede associada a uma instância de EC2. Se houver um ID de sub-rede listado, a instância está em uma VPC.
- Virtualização : o ambiente virtualizado, se houver, em execução em uma determinada instância.
- Semana : A semana numérica do calendário.
- Ano : O ano civil (por exemplo, 2014).
- Zona : Zona de disponibilidade na qual existe uma instância ou ocorreu uma cobrança de uso (por exemplo, 1a ).

**Métricas de utilização**

- Avg CPU Utilization (Utilização média da CPU ): a porcentagem de unidades de computação EC2 alocadas que estão em uso no momento na instância. Essa métrica identifica a capacidade de processamento necessária para executar um aplicativo em uma instância selecionada.
- Avg Estimated Cost : O custo médio estimado de uma instância com base no período selecionado (horas de utilização: custo médio estimado por hora da instância).
- Custo médio por hora: O custo médio por hora com base nas taxas básicas estabelecidas pelo site AWS.
- Avg Hourly Cost Per Instance : O custo médio por hora por instância com base nas taxas básicas estabelecidas por AWS.
- Utilização média de memória: A porcentagem média de memória alocada por aplicativos e pelo sistema operacional para uma instância. Essa métrica exclui a memória em cache e os buffers.
- Avg Running Instances Per Hour : O número médio de instâncias em execução por hora. Para obter mais informações, consulte [Dimensões e métricas usadas com frequência](frequently-used-dimensions-and-metrics.html).
- Bandwidth In (Largura de banda em ): O número de bytes recebidos em todas as interfaces de rede pela instância. Essa métrica identifica o volume de tráfego de rede de entrada para um aplicativo em uma única instância.
- Bandwidth Out (Largura de banda de saída ): O número de bytes enviados em todas as interfaces de rede por instância. Essa métrica identifica o volume de tráfego de rede de saída para um aplicativo em uma única instância.
- Burst Balance : Fornece informações sobre a porcentagem de créditos de E/S (para gp2 ) ou créditos de throughput (para st1 e sc1 ) restantes no intervalo de burst. Usado somente com volumes de SSD de uso geral ( gp2 ), HDD otimizado para taxa de transferência ( st1 ) e HDD frio ( sc1 ).
- Custo (estimado sob demanda) : o custo estimado com base nos valores encontrados no arquivo de alocação de custos do site AWS.
- CPU Total (linha azul) : a porcentagem normalizada da utilização máxima da CPU na hora indicada, com base na contagem máxima de instâncias para todo o ASG na janela de tempo de 10 ou 30 dias. Exemplo: Se houver cinco instâncias em um ASG e todas as cinco instâncias estiverem utilizando 100% de sua CPU, o **total da CPU** será 100%. Se uma instância estiver utilizando 100% de sua CPU e as outras quatro instâncias estiverem utilizando 0% de suas CPUs, o **total da CPU** será de 20%.
- **Utilização da CPU (máx.)** : A porcentagem máxima de utilização da CPU atingida na hora. Para EC2, essa é a porcentagem máxima de unidades de computação EC2 alocadas em uso para uma instância. Quando agregado, ele informa o pico em todas as instâncias e em todo o período de tempo.
- Acesso ao disco : total de bytes lidos e gravados em todos os discos efêmeros disponíveis para a instância (se a sua instância usar o Amazon EBS, consulte [Amazon EBS Metrics](http://docs.aws.amazon.com/amazoncloudwatch/latest/developerguide/ebs-metricscollected.html "(Abre em uma nova guia ou janela)") ).
- E/S de disco : operações de leitura e gravação concluídas de todos os discos efêmeros disponíveis para a instância.
- Acesso de leitura de disco : Total de bytes lidos de todos os discos efêmeros disponíveis para a instância.
- E/S de leitura de disco : operações de leitura concluídas de todos os discos efêmeros disponíveis para a instância.
- Acesso de gravação em disco : total de bytes gravados em todos os discos efêmeros disponíveis para a instância.
- E/S de gravação em disco : operações de gravação concluídas em todos os discos efêmeros disponíveis para a instância.
- Total da GPU ( **%**) : - O Total da GPU (%) é tratado da mesma forma que o Total da CPU (%). (Consulte [Ajuste de tamanho para o ASG do AWS EC2](rightsizing-for-aws-autoscaling-groups.html) )
- **Total de memória da GPU (%)** : o Total de memória da GPU (%) é tratado da mesma forma que o Total de memória da CPU (%). (Consulte [Ajuste de tamanho para o ASG do AWS EC2](rightsizing-for-aws-autoscaling-groups.html) )
- **Utilização de memória da GPU** : Porcentagem de tempo em um período de amostra em que a memória estava sendo gravada ou lida.

  Nota:

  Para obter bons resultados com as métricas de GPU, certifique-se de ter configurado [as métricas mínimas de GPU](https://docs.aws.amazon.com/dlami/latest/devguide/tutorial-gpu-monitoring-gpumon.html "(Abre em uma nova guia ou janela)") como pré-requisito.
- **Utilização da GPU** : porcentagem de tempo em um período de amostra em que um ou mais kernels na GPU estavam em execução.
- Horas desde o lançamento : o número de horas decorridas desde o lançamento inicial de uma instância.
- **Contagem de instâncias: Total da CPU (linha vermelha)** : o número total de instâncias em execução para esse ASG na hora indicada.
- **Contagem de instâncias: Network Max (linha vermelha)** : o número total de instâncias em execução para esse ASG na hora indicada.
- **Contagem de instâncias: Memory Total (linha vermelha)** : o número total de instâncias em execução para esse ASG na hora indicada.
- Instâncias iniciadas : o número total de instâncias iniciadas em um determinado período de tempo.
- Memória : A quantidade de memória disponível para a instância.
- **Total de memória (linha azul)** : a porcentagem normalizada da utilização máxima de memória na hora indicada, com base na contagem máxima de instâncias para todo o ASG na janela de tempo de 10 ou 30 dias. Exemplo: Se houver cinco instâncias em um ASG e todas as cinco instâncias estiverem utilizando 100% de sua memória, então o **total de memória** será 100%. Se uma instância estiver utilizando 100% de sua memória e as outras quatro instâncias estiverem utilizando 0% de sua memória, o **total de memória** será de 20%.
- **Máximo da rede (linha azul)** : o número total de bits por segundo utilizados com base na contagem máxima de instâncias para todo o ASG na hora indicada.
- **Recomendado: CPU Total (linha tracejada amarela)** : a porcentagem normalizada recomendada de alocação de utilização da CPU para todo o ASG na hora indicada.
- **Recomendado: Memory Total (linha tracejada amarela)** : a porcentagem normalizada recomendada de alocação de utilização de memória para todo o ASG na hora indicada.
- **Recomendado: Total da rede (linha tracejada amarela)** : a alocação de rede recomendada para todo o ASG na hora indicada.
- **Contagem de instâncias recomendadas: CPU Total (linha amarela, exibida ao passar o mouse)** : o número total de instâncias recomendadas para esse ASG na hora indicada.
- **Contagem de instâncias recomendadas: Total de memória (linha amarela, exibida ao passar o mouse)** : o número total de instâncias recomendadas para esse ASG na hora indicada.
- Armazenamento : A quantidade de armazenamento disponível para a instância. Esse número não incluirá o site EBS.
- Dispositivos de armazenamento : o número total de dispositivos de armazenamento associados a uma instância em um determinado período de tempo.
- **Contagem de instâncias recomendadas (linha amarela, exibida ao passar o mouse)** : o número total de instâncias recomendadas para esse ASG na hora indicada.
- Total Bandwidth (Largura de banda total ): Total de bytes transferidos por uma instância específica.
- Contagem de instâncias exclusivas: o número total de instâncias exclusivas em um estado de execução durante um determinado período de tempo.
- Horas de utilização : o número total de horas de uso em uma instância em um período de tempo específico.
- Volume Consumed Read Write Ops (Operações de leitura e gravação consumidas): A quantidade total de operações de leitura e gravação (normalizadas para 256K unidades de capacidade) consumidas em um período de tempo específico. Usado somente com volumes SSD de IOPS provisionados.
- Porcentagem de rendimento do volume : a porcentagem de operações de E/S por segundo (IOPS) fornecidas do total de IOPS provisionado para um volume do Amazon EBS. Usado somente com volumes SSD de IOPS provisionados.

  Nota:

  Essa métrica não é compatível com volumes habilitados para vários anexos.
