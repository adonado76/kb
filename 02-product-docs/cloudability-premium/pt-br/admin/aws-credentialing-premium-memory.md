---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conexão com AWS - Obtenção de métricas de memória para instâncias de EC2 (Windows e Linux )"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conexão com AWS - Guia de integração do cliente"
source_path: "admin/aws-credentialing-premium-memory.html"
images:
  - "images/clip_image001_-662737569.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conexão com AWS - Obtenção de métricas de memória para instâncias de EC2 (Windows e Linux )

O mecanismo de dimensionamento de direitos do Cloudability avalia a utilização de recursos subjacentes para cada instância do EC2 e recomenda tipos de instâncias que são bem compatíveis com cada perfil de utilização. O objetivo final é manter seus custos baixos e, ao mesmo tempo, estar atento aos riscos operacionais.

Para obter as recomendações mais precisas, há quatro métricas de utilização que precisam ser avaliadas: CPU, IOPS de disco (no caso de instâncias que têm discos locais), largura de banda de rede e utilização de memória. Por uma série de motivos muito bons, adotamos a abordagem de extrair esses dados diretamente do site CloudWatch. O principal motivo é que as métricas no nível do hipervisor são salvas em CloudWatch por padrão para cada instância, sem que você faça nada. Isso deixa a utilização de memória como a única métrica que exige um pouco mais de esforço de sua parte para ser publicada em CloudWatch. Isso é feito usando o que o site AWS chama de Custom Metrics, sobre o qual você pode ler [aqui](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Famazoncloudwatch%2Flatest%2Fmonitoring%2Fpublishingmetrics.html "(Abre em uma nova guia ou janela)").

A boa notícia é que o site AWS criou formatos padrão para a publicação de dados de memória e adotamos uma abordagem simplificada para ingerir esses dados. Exigimos que apenas uma métrica personalizada seja publicada usando o [agente unificado atual.](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Famazoncloudwatch%2Flatest%2Fmonitoring%2Finstall-cloudwatch-agent.html "(Abre em uma nova guia ou janela)")

**Etapas para a integração**

**AWS Agente unificado**

Esse é o método preferido para dados de memória. Cloudability suporta o local padrão e as convenções de nomenclatura que o agente unificado usa ao gravar métricas personalizadas no Cloudwatch. Esses detalhes são:

- **nome da métrica** : "mem\_used\_percent" (para Linux )
- **metric-name** : "Mbytes disponíveis" (para Windows)
- **namespace** : CWAgent
- **dimensions** : InstanceId (é importante adicionar apenas essa dimensão)
- **unidade** : porcentagem

**Instruções**

AWS fornece várias opções para instalar o agente, que podem ser encontradas em [https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-on-EC2-Instance.html](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Famazoncloudwatch%2Flatest%2Fmonitoring%2Finstall-cloudwatch-agent-on-ec2-instance.html "(Abre em uma nova guia ou janela)"). O agente unificado oferece recursos para publicar muitos tipos de métricas personalizadas.

A seguir, um exemplo de uma configuração mínima **Linux** para publicar apenas as informações de memória:

```
{   
						"metrics": {
						"metrics_collected": {
						"mem": {
						"measurement": [
						"mem_used_percent"
						],
						"resources": [
						"*"
						]
						}
						},  
						"append_dimensions": {
						"InstanceId": "${aws:InstanceId}"
						} 
						}
				}
```

A seguir, um exemplo de uma configuração mínima **do Windows** para publicar apenas as informações de memória:

```
{  
						"metrics": { 
						"metrics_collected": { 
						"Memory": { 
						"measurement": [ 
						{"name": "Available Mbytes", "unit":"Megabytes"} 
						], 
						"resources": [ 
						"*" 
						] 
						} 
						},  
						"append_dimensions": { 
						"InstanceId": "${aws:InstanceId}" 
						} 
						} 
						} 
				
```

Observação: Se a métrica **“Mbytes disponíveis”** não estiver disponível, será utilizada a métrica antiga **“% de bytes comprometidos em uso”,** caso esteja disponível. Por exemplo, {"name": "% Committed Bytes In Use", "unit":"Percent"}

Observação: Quando a métrica personalizada for publicada, é importante que ela contenha apenas a dimensão “ InstanceId ”. Isso ocorre porque, conforme descrito em [https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch\_concepts.html#dimension-combinations](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Famazoncloudwatch%2Flatest%2Fmonitoring%2Fcloudwatch_concepts.html%23dimension-combinations "(Abre em uma nova guia ou janela)") por AWS, cada combinação de dimensões constitui uma métrica totalmente independente, que deve ser consultada com todos os dados dimensionais.

Se você quiser publicar várias dimensões, poderá usar a palavra-chave aggregation\_dimensions, conforme mostrado no **Linux** exemplo abaixo. A dimensão extra, nesse caso, é AutoScalingGroupName. Neste exemplo, você terá três métricas de memória publicadas, cada uma com uma combinação de dimensão diferente 1) apenas InstanceID 2) apenas AutoScalingGroupName 3) InstanceID e AutoScalingGroupName.

O seguinte é um **Linux** exemplo:

```
{   
						"metrics": {
						"metrics_collected": {
						"mem": {
						"measurement": [
						"mem_used_percent"
						],
						"resources": [
						"*"
						]
						}
						},  
						"append_dimensions": {
						"InstanceId": "${aws:InstanceId}"
						} 
						}
				}
```

**Perl Agente baseado em**

Observe que o AWS descontinuou o agente baseado em perl, mas ele continua disponível para download. Cloudability continuará a oferecer suporte a esse método, mas recomendamos que você mude para o agente unificado mais recente, se possível.

Conforme mencionado acima, é necessária apenas uma métrica personalizada. A métrica baseada em perl tem a seguinte aparência:

- **nome da métrica** : MemoryUtilization
- **namespace** : System/ Linux ou Windows/Default
- **dimensions** : InstanceId (é importante adicionar apenas essa dimensão)
- **unidade** : porcentagem

**Instruções**

Instale os scripts de monitoramento perl CloudWatch conforme descrito nesta página da Web AWS. Nesta página, você encontrará instruções para instalar os pacotes pré-requisitos em máquinas que executam a AMI do Amazon Linux e outros sistemas operacionais populares, como o Red Hat.

Esta é a configuração do crontab que usamos em Cloudability para as máquinas Linux :

`* * * * * ~/aws-scripts-mon/mon-put-instance-data.pl --mem-util
--from-cron`

Isso publicará exatamente o que o site Cloudability exige e nada mais. Você deve poder confirmar que a métrica de memória é relatada em intervalos de 5 minutos.

**Outras opções** : Outras opções incluem a criação de seu próprio agente que se integra ao SDK do AWS. [Aqui](https://www.ibm.com/links?url=https%3A%2F%2Fgithub.com%2Fa3linux%2Fgo-aws-mon "(Abre em uma nova guia ou janela)") está um exemplo utilizando o site Golang, com o qual alguns de nossos clientes obtiveram bons resultados.

**Como confirmar o sucesso**

Normalmente, dentro de 24 horas após a configuração de sua instância EC2, essas informações de memória estarão disponíveis no Cloudability rightsizing.

Aqui está um exemplo dos dados de memória resultantes quando visualizados no console do AWS Cloudwatch. Isso pode ser útil para fins de depuração.

![aws](../../../../03-media/cloudability-premium/images/clip_image001_-662737569.jpg)

Observação: Esses são dados de exemplo do agente baseado em perl. Os dados do agente unificado terão aparência semelhante, mas com o namespace e o nome da métrica relevantes.

Ter esses dados de memória em CloudWatch trará benefícios que vão muito além de Cloudability e é altamente recomendável seguir esse caminho. Por exemplo, você pode usar os dados da memória para acionar eventos de dimensionamento automático ou disparar alarmes. Depois de descobrir qual método funciona para você, seria uma boa ideia incluí-lo em sua configuração.

**Obtenção de recomendações com base em dados da GPU O** Cloudability permite que os usuários visualizem recomendações com base em dados da GPU provenientes de instâncias d AWS EC2.

Cloudability ingere dados de processamento de GPU e de utilização de memória de suas instâncias do AWS. Isso permitirá que o site Cloudability faça recomendações de dimensionamento que também considerem esses dados. Por exemplo, se você não estiver usando GPUs, poderá ser recomendado que mude para um tipo de instância que inclua GPUs para economizar dinheiro.

Cloudability oferece duas opções para coletar dados de GPU:

**Opção 1: Usar o agente AWS CloudWatch (somente Linux )**

Para começar a coletar os dados de utilização da GPU por meio do agente AWS CloudWatch, você deve primeiro configurar seu agente para fornecer esses dados: [https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch-Agent-NVIDIA-GPU.html](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Famazoncloudwatch%2Flatest%2Fmonitoring%2Fcloudwatch-agent-nvidia-gpu.html "(Abre em uma nova guia ou janela)")

A seguir, um exemplo de uma configuração mínima do site Linux para publicar apenas as informações de memória e GPU:

```
{   
						"metrics": {
						"metrics_collected": {
						"mem": {
						"measurement": [
						"mem_used_percent"
						]       
						},
						"nvidia_gpu": {
						"measurement": [
						"utilization_gpu",
						"utilization_memory"
						]
						}    
						},  
						"append_dimensions": {
						"InstanceId": "${aws:InstanceId}"
						} 
						}
				}
```

**Opção 2: usar o agente de monitoramento de GPU ( Linux e Windows)**

Para começar a ingerir os dados de utilização da GPU, você deve usar o agente de monitoramento da GPU.

Antes de começar

Seu arquivo ` VM ` deve conter o seguinte:

- GPU ativada
- Drivers da Nvidia instalados
- Python 2.7 ou superior instalado

**Etapas para a integração**

**Instruções para Linux VMs**

Execute o script Python :

1. Instale Python 2.7 ou superior se ainda não estiver disponível e torne-a a versão padrão de Python.
2. Instale o pip >= 20.3.4 se ele ainda não estiver disponível.
3. Como sua instância já está sendo executada na AMI habilitada para GPU, você precisa criar uma função IAM que conceda à sua instância a permissão para enviar métricas para o Amazon CloudWatch. Crie uma função de serviço EC2 que permita a seguinte política:

   ```
   { "Version": "2012-10-17", "Statement": [ { "Action": [ "cloudwatch:PutMetricData", ], "Effect": "Allow", "Resource": "*" } ] }
   ```
4. Baixe o script personalizado do gpumon em [https://community.apptio.com/viewdocument/custom-gpumon-python-script-to-coll](https://www.ibm.com/links?url=https%3A%2F%2Fcommunity.apptio.com%2Fviewdocument%2Fcustom-gpumon-python-script-to-coll%3Fcommunitykey%3Df67c7e7c-be1c-4053-9845-2376da697342%26tab%3Dlibrarydocuments "(Abre em uma nova guia ou janela)") e coloque-o na pasta VM.
5. Instale todas as dependências.

   Para Python 2.7:

   `sudo pip2.7 install Nvidia-ml-py
   boto3`

   Para Python 3 ou superior:
6. Executa o comando fornecido em segundo plano:

   `python gpumon.py <Region> <log file
   path>`

   Por exemplo, nohup python gpumon.py < AWS -Region> <caminho do arquivo de registro> &

**Instale e execute o agente do Datadog**

1. Siga o documento fornecido para configurar o agente do Datadog em [https://docs.datadoghq.com/integrations/nvml/](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.datadoghq.com%2Fintegrations%2Fnvml%2F "(Abre em uma nova guia ou janela)").

Execute o seguinte comando de instalação da integração do Agent em vez do comando fornecido na documentação do Datadog :

`sudo -u dd-agent datadog-agent integration install -t
datadog-nvml==<INTEGRATION_VERSION>`

**Instruções para VMs do Windows**

1. Instale o site Python 2.7 ou superior.
2. Como sua instância já está sendo executada na AMI habilitada para GPU, você precisa criar uma função IAM que conceda à sua instância a permissão para enviar métricas para o Amazon CloudWatch. Crie uma função de serviço EC2 que permita a seguinte política:
3. Configure o caminho de Python para as variáveis de ambiente do Windows.
4. Baixe o script personalizado do gpumon Python em [https://community.apptio.com/viewdocument/custom-gpumon-python-script-to-coll](https://www.ibm.com/links?url=https%3A%2F%2Fcommunity.apptio.com%2Fviewdocument%2Fcustom-gpumon-python-script-to-coll%3Fcommunitykey%3Df67c7e7c-be1c-4053-9845-2376da697342%26tab%3Dlibrarydocuments "(Abre em uma nova guia ou janela)") e atualize o caminho do arquivo de log de acordo com o diretório de arquivos do Windows.
5. Execute o comando no modo de administrador para instalar todas as dependências.

   Para Python 2.7:

   `pip2.7 install Nvidia-ml-py boto3`

   Para Python 3 e superior:

   `pip install Nvidia-ml-py boto3`
6. Execute o script para coletar os dados de utilização da GPU e enviá-los para o Cloud Watch usando o seguinte comando no modo de administrador:

   `python gpumon.py <AWS-Region> <log file
   path>.`

**Instale e execute o agente do Datadog**

1. Instale o agente do Datadog no seu Windows VM.
2. Defina o caminho ( **C:\Program Files\ Datadog \ Datadog Agent\bin** ) nas variáveis de ambiente do Windows.
3. Execute este comando:

   `agent integration install -t
   datadog-nvml==<INTEGRATION_VERSION>`
4. Instale o pip no Windows no caminho indicado do executável Python, que é utilizado pelo Datadog ( **C:\Program Files\ Datadog \ DatadogAgent\embedded3** )
5. No prompt de comando no modo de administrador, acesse o caminho **C:\Program Files\ Datadog \ Datadog Agent\embedded3\Scripts** e, em seguida, execute o comando a seguir para instalar o pacote.

   `pip3 install grpcio pynvml`
6. Edite o arquivo **nvml.d/conf.yaml** no diretório **conf.d/** na raiz do diretório de configuração do seu Agent para começar a coletar os dados de desempenho do NVML. Consulte a amostra **nvml.d/conf.yaml** para ver todas as opções de configuração disponíveis.
7. Reinicie o agente.

**Tópico principal:** [Conexão com AWS - Guia de integração do cliente](../admin/aws-credentialing-premium-home.html)
