---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Estimativa de custos baseada em uso e configuração"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
source_path: "admin/governance-usage-and-configuration-based-cost-estimation.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Estimativa de custos baseada em uso e configuração

Cloudability A governança pode estimar os custos diretamente a partir da sua configuração do Terraform. Além das estimativas baseadas na configuração, você pode, opcionalmente, fornecer parâmetros de entrada baseados no uso para recursos específicos. Essas informações ajudam a gerar projeções de custos mais precisas e personalizadas com base no seu consumo previsto. Para serviços que exigem dados de uso — como o AWS Lambda, o SQS e outros —, será utilizado um valor padrão de uso quando não for fornecida nenhuma entrada personalizada. Se você fornecer seus próprios valores de uso esperado, eles sempre substituirão os padrões.

## Terraform/Terragrunt

**Ações da Comunidade Terraform/ GitHub**

Se você estiver usando o GitHub Actions ou o Terraform Community Edition:

- Cloudability A governança é acionada por uma ação do Github definida para o repositório. A entrada de uso esperada pode ser especificada por meio de um arquivo usage.json e especificada como uma entrada para a ação do Github IBM /ibm-cloudability-governance/actions/cost-estimation. Você pode ver um exemplo aqui: [https://github.com/IBM/ibm-cloudability-governance/blob/main/example-workflows/single-deployment/workflow.yaml#L95](https://github.com/IBM/ibm-cloudability-governance/blob/main/example-workflows/single-deployment/workflow.yaml#L95 "(Abre em uma nova guia ou janela)")

**HCP Terraform / Terraform Enterprise (TFE)**

Se você estiver usando o HCP Terraform / Terraform Enterprise:

- Cloudability A governança é acionada por uma **tarefa de execução** associada a um espaço de trabalho específico definido no HCP Terraform.

- Se houver um arquivo “ usage.json ” no **diretório de trabalho configurado** da área de trabalho, o Cloudability Governance detectará automaticamente e aplicará os valores de uso contidos nesse arquivo durante a estimativa de custos.

- O nome do arquivo deve corresponder ao nome “ usage.json ”.

Isso garante que as entradas baseadas no uso sejam aplicadas de forma consistente sempre que a estimativa de custos for realizada para essa área de trabalho.

**Exemplo de usage.json**

```
{
  "version": "0.1",
  "resource_usage": {
    "aws_instance.costguard_demo_ec2_1": {
      "os": "linux_unix"
    },
    "aws_instance.costguard_demo_ec2_2": {
      "term_type": "compute_savings_plan",
      "purchase_option": "partial_upfront",
      "lease_contract_length": "3yr"
    }
  }
}
```

| Chave | Descrição |
| --- | --- |
| Exemplo: “ aws\_instance.costguard\_demo\_ec2\_1 ” | Descrição do recurso |
| "sistemas operacionais" | Propriedade de recursos |
| "linux\_unix" | O valor que está sendo definido |

```
version: "0.1" # Version of the schema
resource_usage: # All resource usage values should be listed here
  # The resource is identified as <terraform_resource_name>.<resource_identifier>
  aws_instance.costguard_demo_ec2:
    # Each field represents a specific attribute and its expected usage
    # <attribute_field_name>:<expected_value>
    os: "linux_unix"
  aws_instance.costguard_demo_ec2_2:
    term_type: "compute_savings_plan"
    purchase_option: "partial_upfront"
    lease_contract_length: "3yr"
```

As estimativas são exibidas como comentários PR, fornecendo informações sobre os custos mensais com base nas entradas de uso.

## Tipos de serviços compatíveis com o AWS

1. EC2
2. EBS
3. EBS Resumo
4. ElasticMapReduce (EMR)
5. S3
6. RDS
7. ElasticCache
8. DynamoDB
9. Lambda
10. SNS
11. SQS
12. SecretManager
13. EventBridge
14. VPC
15. RedShift
16. Cloudwatch
17. Serviço de gerenciamento de chaves (KMS)
18. FSx
19. Serviço de migração de banco de dados
20. Sistema de arquivos elástico
21. Equilíbrio de Carga Elástico (ELB)
22. OpenSearch
23. Firewall de Aplicações Web (WAF)
24. Glue
25. ECS

## AWS Detalhes de uso por tipo de serviço

Recursos de computação

aws\_instância

```
count:
  desc: Number of instances to launch
term_type:
  values: ["compute_savings_plan", "ec2_savings_plan", "standard_reserved_instance", "convertible_reserved_instance"]
  desc: Type of pricing model
purchase_option:
  values: ["all_upfront", "partial_upfront", "no_upfront"]
  desc: Payment option for reserved instances
lease_contract_length:
  values: ["1yr", "3yr"] or ["1_year", "3_year"]
  desc: Duration of lease in years
```

aws\_launch\_template

```
count:
  desc: Number of instances to launch
term_type:
  values: "reserved" or "on_demand"
  desc: Type of pricing model
purchase_option:
  values: ["all_upfront", "partial_upfront", "no_upfront"]
  desc: Payment option for reserved instances
lease_contract_length:
  values: ["1yr", "3yr"] or ["1_year", "3_year"]
  desc: Duration of lease in years
```

Recursos do banco de dados

aws\_db\_instância

```
term_type:
  values: "reserved" or "on_demand"
  desc: Type of pricing model
purchase_option:
  values: ["all_upfront", "partial_upfront", "no_upfront"]
  desc: Payment option for reserved instances
lease_contract_length:
  values: "1" or "3"
  desc: Duration of lease in years
```

aws\_rds\_cluster

```
acu_per_hour:
  desc: Aurora Capacity Units per hour for Aurora Serverless V2
aurora_storage_gb:
  desc: Amount of Aurora storage in GB for Aurora Serverless V2
```

aws\_dynamodb\_table

```
storage_gb:
  desc: Amount of data stored in the table in GB
strongly_consistent_reads_per_month:
  desc: Number of strongly consistent read requests per month
eventually_consistent_reads_per_month:
  desc: Number of eventually consistent read requests per month
transaction_reads_per_month:
  desc: Number of transactional read requests per month
standard_writes_per_month:
  desc: Number of standard write requests per month
transaction_writes_per_month:
  desc: Number of transactional write requests per month
average_item_byte_size:
  desc: Average size of items stored in bytes
```

aws\_elasticache\_cluster, aws\_elasticache\_replication\_group

```
term_type:
  values: "reserved" or "on_demand"
  desc: Type of pricing model
purchase_option:
  values: ["all_upfront", "partial_upfront", "no_upfront", "heavy_utilization"]
  desc: Payment option for reserved instances
lease_contract_length:
  values: "1" or "3"
  desc: Duration of lease in years
```

aws\_redshift\_cluster

```
term_type:
  values: "on_demand", "reserved"
  desc: Type of pricing model
backup_storage_gb:
  desc: Backup storage beyond included amount in GB
spectrum_data_scanned_tb:
  desc: Amount of data scanned by Redshift Spectrum in TB
managed_storage_gb:
  desc: Amount of managed storage in GB
data_transfer_gb:
  desc: Amount of data transferred in GB
utilization_hours:
  desc: Number of hours the cluster is utilized per month
```

aws\_dms\_replication\_config

```
avg_dcu:
  desc: Average Data Capacity Units for DMS Serverless replication (default minimum is 1)
```

Recursos de armazenamento

aws\_ebs\_volume

```
count:
  desc: Number of volumes to create
iops:
  desc: Provisioned IOPS (only for io1, io2 volume types)
throughput:
  desc: Throughput in MiB/s (only for gp3 volume type)
```

aws\_ebs\_snapshot

```
count:
  desc: Number of snapshots
write_churn_rate:
  desc: Fraction of volume size written between snapshots (e.g. 0.01 = 1%)
snapshot_interval_days:
  desc: Number of days between snapshots
```

aws\_fsx\_lustre\_sistema\_de\_arquivos

```
compression_factor:
  desc: Data compression ratio for storage optimization
backup_storage_gb:
  desc: Amount of backup storage in GB
```

aws\_s3\_bucket

```
standard_storage:
  storage_gb:
    desc: Amount of data stored in standard storage class in GB
  rw_requests:
    desc: Number of read-write API requests per month for standard storage
  ro_requests:
    desc: Number of read-only API requests per month for standard storage
  select_data_returned_gb:
    desc: Amount of data returned by S3 Select in GB
  select_data_scanned_gb:
    desc: Amount of data scanned by S3 Select in GB
standard_ia_storage:
  storage_gb:
    desc: Amount of data stored in standard IA storage class in GB
  rw_requests:
    desc: Number of read-write API requests per month for standard IA storage
  ro_requests:
    desc: Number of read-only API requests per month for standard IA storage
  select_data_returned_gb:
    desc: Amount of data returned by S3 Select in GB
  select_data_scanned_gb:
    desc: Amount of data scanned by S3 Select in GB
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  retrieval_data_gb:
    desc: Amount of data retrieved in GB
glacier_da_storage:
  storage_gb:
    desc: Amount of data stored in Glacier Deep Archive in GB
  avg_object_size_mb:
    desc: Average object size in MB
  rw_requests:
    desc: Number of read-write API requests per month
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  restore_standard_requests:
    desc: Number of standard restore requests
  restore_bulk_requests:
    desc: Number of bulk restore requests
  data_standard_retrieval_gb:
    desc: Amount of data retrieved via standard retrieval in GB
  data_bulk_retrieval_gb:
    desc: Amount of data retrieved via bulk retrieval in GB
glacier_ir_storage:
  storage_gb:
    desc: Amount of data stored in Glacier Instant Retrieval in GB
  rw_requests:
    desc: Number of read-write API requests per month
  ro_requests:
    desc: Number of read-only API requests per month
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  retrieval_data_gb:
    desc: Amount of data retrieved in GB
  select_data_returned_gb:
    desc: Amount of data returned by S3 Select in GB
  select_data_scanned_gb:
    desc: Amount of data scanned by S3 Select in GB
glacier_fr_storage:
  storage_gb:
    desc: Amount of data stored in Glacier Flexible Retrieval in GB
  avg_object_size_mb:
    desc: Average object size in MB
  rw_requests:
    desc: Number of read-write API requests per month
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  restore_standard_requests:
    desc: Number of standard restore requests
  restore_bulk_requests:
    desc: Number of bulk restore requests
  restore_expedited_requests:
    desc: Number of expedited restore requests
  data_standard_retrieval_gb:
    desc: Amount of data retrieved via standard retrieval in GB
  data_bulk_retrieval_gb:
    desc: Amount of data retrieved via bulk retrieval in GB
  data_expedited_retrieval_gb:
    desc: Amount of data retrieved via expedited retrieval in GB
intelligent_tiering_storage:
  storage_gb:
    desc: Amount of data stored in Intelligent-Tiering in GB
  avg_object_size_mb:
    desc: Average object size in MB
  frequent_access_percent:
    desc: Percentage of data in frequent access tier
  infrequent_access_percent:
    desc: Percentage of data in infrequent access tier
  archive_instant_access_percent:
    desc: Percentage of data in archive instant access tier
  archive_access_percent:
    desc: Percentage of data in archive access tier
  deep_archive_access_percent:
    desc: Percentage of data in deep archive access tier
  rw_requests:
    desc: Number of read-write API requests per month
  ro_requests:
    desc: Number of read-only API requests per month
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  select_data_returned_gb:
    desc: Amount of data returned by S3 Select in GB
  select_data_scanned_gb:
    desc: Amount of data scanned by S3 Select in GB
one_zone_ia_storage:
  storage_gb:
    desc: Amount of data stored in One Zone-IA in GB
  rw_requests:
    desc: Number of read-write API requests per month
  ro_requests:
    desc: Number of read-only API requests per month
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  retrieval_data_gb:
    desc: Amount of data retrieved in GB
  select_data_returned_gb:
    desc: Amount of data returned by S3 Select in GB
  select_data_scanned_gb:
    desc: Amount of data scanned by S3 Select in GB
express_one_zone_storage:
  storage_gb:
    desc: Amount of data stored in Express One Zone in GB
  rw_requests:
    desc: Number of read-write API requests per month
  rw_request_size_gb:
    desc: Total size of read-write requests in GB
  ro_requests:
    desc: Number of read-only API requests per month
  ro_request_size_gb:
    desc: Total size of read-only requests in GB
```

aws\_efs\_file\_system

```
storage_gb:
  desc: Total storage capacity in GB
standard_storage_reads_gb:
  desc: GB read from standard storage per month (elastic throughput mode only)
standard_storage_writes_gb:
  desc: GB written to standard storage per month (elastic throughput mode only)
ia_storage_percent:
  desc: Percentage of total storage in Infrequent Access tier (0-100)
ia_tiering_gb:
  desc: GB moved to IA tier per month
ia_reads_gb:
  desc: GB read from IA tier per month
archive_storage_percent:
  desc: Percentage of total storage in Archive tier (Multi-AZ elastic only, 0-100)
archive_tiering_gb:
  desc: GB moved to Archive tier per month (Multi-AZ elastic only)
archive_reads_gb:
  desc: GB read from Archive tier per month (Multi-AZ elastic only)
```

Recursos de mensagens

tópico\_aws\_sns

```
monthly_requests:
  desc: Number of API requests per month
monthly_storage:
  desc: Amount of data stored for message archive in GB
```

assinatura\_de\_tópico\_aws\_sns

```
monthly_notifications:
  desc: Number of notifications delivered per month
```

fila\_aws\_sqs

```
monthly_requests:
  desc: Number of API requests per month
```

Recursos sem servidor

função\_aws\_lambda

```
monthly_requests:
  desc: Number of function invocations per month
request_duration_ms:
  desc: Average duration of each invocation in milliseconds
```

aws\_lambda\_provisioned\_concurrency\_config

```
monthly_requests:
  desc: Number of function invocations per month
request_duration_ms:
  desc: Average duration of each invocation in milliseconds
```

Recursos de Big Data

aws\_emrserverless\_application

```
job_runtime_hour:
  desc: Number of hours the EMR Serverless application runs
```

aws\_emrcontainers\_job\_template

```
job_runtime_hour:
  desc: Number of hours the EMR Containers job runs
job_vcpu:
  desc: Number of vCPUs allocated to the job
job_memory_gb:
  desc: Amount of memory allocated to the job in GB
```

aws\_emr\_cluster

```
core_node_utilization:
  desc: Percentage utilization of core nodes (0-100)
master_node_utilization:
  desc: Percentage utilization of master nodes (0-100)
```

aws\_emr\_instance\_fleet

```
instance_utilization:
  desc: Percentage utilization of instances in the fleet (0-100)
```

aws\_emr\_instance\_group

```
instance_utilization:
  desc: Percentage utilization of instances in the group (0-100)
```

aws\_opensearch\_domain

```
data_instances:
  term_type:
    values: "on_demand" or "reserved"
    desc: Pricing model for data instances
  purchase_option:
    values: ["all_upfront", "partial_upfront", "no_upfront"]
    desc: Payment option for reserved data instances
  lease_contract_length:
    values: ["1yr", "3yr"]
    desc: Duration of lease for reserved data instances
master_instances:
  term_type:
    values: "on_demand" or "reserved"
    desc: Pricing model for dedicated master instances
  purchase_option:
    values: ["all_upfront", "partial_upfront", "no_upfront"]
    desc: Payment option for reserved master instances
  lease_contract_length:
    values: ["1yr", "3yr"]
    desc: Duration of lease for reserved master instances
ultrawarm_instances:
  managed_storage_gb:
    desc: Amount of UltraWarm managed storage in GB
cold_storage:
  managed_storage_gb:
    desc: Amount of cold storage in GB
```

aws\_opensearchserverless\_collection

```
avg_index_ocu_count:
  desc: Average number of indexing OpenSearch Compute Units (OCUs)
avg_query_ocu_count:
  desc: Average number of search/query OpenSearch Compute Units (OCUs)
storage_gb_per_month:
  desc: Amount of data stored per month in GB
```

Recursos de processamento de eventos

aws\_esquemas\_esquema

```
ingestion_count:
  desc: Number of schema ingestion operations per month
```

tubos\_aws\_tubo

```
event_count:
  desc: Number of events processed through the pipe per month
```

aws\_cloudwatch\_event\_bus

```
event_count:
  desc: Number of events processed through the event bus per month
```

aws\_cloudwatch\_event\_archive

```
archive_processing:
  desc: Amount of data processed for archiving in GB
archive_storage:
  desc: Amount of archived data stored in GB
```

Recursos de monitoramento

aws\_cloudwatch\_alerta\_métrico

```
avg_metrics_retrieved:
  desc: Average number of metrics retrieved per alarm per month
```

Recursos de segurança

aws\_secretsmanager\_secret

```
average_duration_in_days:
  desc: Average number of days the secret is stored per month (prorated billing)
monthly_requests:
  desc: Number of API requests per month
```

chave\_aws\_kms

```
monthly_symmetric_requests:
  desc: Number of symmetric encryption/decryption requests per month
monthly_asymmetric_requests_except_rsa2048:
  desc: Number of asymmetric requests per month (excluding RSA 2048)
monthly_asymmetric_rsa2048_requests:
  desc: Number of RSA 2048 asymmetric requests per month
monthly_generatedatakeypair_ecc_requests:
  desc: Number of ECC key pair generation requests per month
monthly_generatedatakeypair_rsa_requests:
  desc: Number of RSA key pair generation requests per month
```

chave externa aws\_kms

```
monthly_symmetric_requests:
  desc: Number of symmetric encryption/decryption requests per month
monthly_asymmetric_requests_except_rsa2048:
  desc: Number of asymmetric requests per month (excluding RSA 2048)
monthly_asymmetric_rsa2048_requests:
  desc: Number of RSA 2048 asymmetric requests per month
monthly_generatedatakeypair_ecc_requests:
  desc: Number of ECC key pair generation requests per month
monthly_generatedatakeypair_rsa_requests:
  desc: Number of RSA key pair generation requests per month
```

aws\_kms\_chave\_réplica

```
monthly_symmetric_requests:
  desc: Number of symmetric encryption/decryption requests per month
monthly_asymmetric_requests_except_rsa2048:
  desc: Number of asymmetric requests per month (excluding RSA 2048)
monthly_asymmetric_rsa2048_requests:
  desc: Number of RSA 2048 asymmetric requests per month
monthly_generatedatakeypair_ecc_requests:
  desc: Number of ECC key pair generation requests per month
monthly_generatedatakeypair_rsa_requests:
  desc: Number of RSA key pair generation requests per month
```

aws\_kms\_replica\_chave\_externa

```
monthly_symmetric_requests:
  desc: Number of symmetric encryption/decryption requests per month
monthly_asymmetric_requests_except_rsa2048:
  desc: Number of asymmetric requests per month (excluding RSA 2048)
monthly_asymmetric_rsa2048_requests:
  desc: Number of RSA 2048 asymmetric requests per month
monthly_generatedatakeypair_ecc_requests:
  desc: Number of ECC key pair generation requests per month
monthly_generatedatakeypair_rsa_requests:
  desc: Number of RSA key pair generation requests per month
```

aws\_wafv2\_web\_acl

```
monthly_requests:
  desc: Number of web requests evaluated per month
request_sizing_weights:
  16KB:
    desc: Weight for requests up to 16KB body size (0-1)
  32KB:
    desc: Weight for requests up to 32KB body size (0-1)
  48KB:
    desc: Weight for requests up to 48KB body size (0-1)
  64KB:
    desc: Weight for requests up to 64KB body size (0-1)
shield_protected:
  values: true or false
  desc: Whether AWS Shield Advanced protection is enabled
```

Recursos de rede

conexão\_vpn\_aws

```
data_processing_month_gb:
  desc: Amount of data processed through VPN connection in GB per month
```

aws\_ec2\_transit\_gateway\_vpc\_attachment

```
data_processing_month_gb:
  desc: Amount of data processed through transit gateway in GB per month
```

aws\_ec2\_client\_vpn\_network\_association

```
active_users:
  desc: Number of concurrent VPN users
hrs_active_per_month:
  desc: Number of hours the VPN connection is active per month
```

aws\_vpc\_endpoint (gateway)

```
gateway_endpoint:
  endpoint_az_count:
    desc: Number of availability zones for the endpoint
  processed_bytes_per_hour_gb:
    desc: Amount of data processed per hour in GB
```

Recursos de balanceamento de carga

aws\_elb (Equilibrador de Carga Clássico)

```
data_gb:
  desc: Total GB of data processed by the Classic Load Balancer per month
```

aws\_lb (Equilibrador de Carga de Aplicações)

```
application:
  average_new_connections_per_second:
    desc: Average new connections per second
  average_connection_duration_seconds:
    desc: Average connection duration in seconds
  average_processed_bytes_per_hour_gb_ec2:
    desc: Average processed bytes per hour in GB for EC2 targets
  average_processed_bytes_per_hour_gb_lambda:
    desc: Average processed bytes per hour in GB for Lambda targets
  average_requests_per_second:
    desc: Average requests per second
  average_rules_processed:
    desc: Average number of rules processed per request
  on_outposts:
    values: true or false
    desc: Whether the ALB is deployed on AWS Outposts
  reserved_lcu_hours:
    desc: Reserved LCU capacity hours (billed in full)
```

aws\_lb (Equilibrador de Carga de Rede)

```
network:
  average_new_tcp_connections_per_second:
    desc: Average new TCP connections per second
  average_tcp_connection_duration_sec:
    desc: Average TCP connection duration in seconds
  average_processed_bytes_tcp_per_hour_gb:
    desc: Average processed bytes for TCP per hour in GB
  average_new_udp_flows_per_second:
    desc: Average new UDP flows per second
  average_udp_flow_duration_sec:
    desc: Average UDP flow duration in seconds
  average_processed_bytes_udp_per_hour_gb:
    desc: Average processed bytes for UDP per hour in GB
  average_new_tls_connections_per_second:
    desc: Average new TLS connections per second
  average_tls_connection_duration_sec:
    desc: Average TLS connection duration in seconds
  average_processed_bytes_tls_per_hour_gb:
    desc: Average processed bytes for TLS per hour in GB
  reserved_nlcu_hours:
    desc: Reserved NLCU capacity hours (billed in full)
```

aws\_lb (Gateway Load Balancer)

```
gateway:
  availability_zone_count:
    desc: Number of availability zones
  new_connections_per_second:
    desc: New connections per second
  average_connection_duration_seconds:
    desc: Average connection duration in seconds
  processed_bytes_per_hour_gb:
    desc: Processed bytes per hour in GB
  reserved_glcu_hours:
    desc: Reserved GLCU capacity hours (billed in full)
```

Recursos de contêineres

aws\_ecs\_service

```
external_instances:
  desc: Number of external instances
fargate_utilization:
  desc: Percentage utilization of Fargate tasks (0-100)
external_instances_utilization:
  desc: Percentage utilization of external instances (0-100)
managed_instances_utilization:
  desc: Percentage utilization of managed instances (0-100)
```

aws\_ecs\_capacity\_provider

```
managed_instance_type:
  desc: Instance type for managed capacity provider (e.g. t3.medium)
managed_instance_count:
  desc: Number of managed instances
managed_scaling_instance_count:
  desc: Number of instances for managed scaling
```

AWS Recursos sobre colas

aws\_glue\_job

```
job_runtime_min:
  desc: Duration of each job run in minutes
monthly_invocations:
  desc: Number of job invocations per month
default_max_capacity:
  desc: Default maximum DPU capacity for the job
```

aws\_glue\_crawler

```
no_of_dpus:
  desc: Number of DPUs allocated to the crawler
crawl_duration_min:
  desc: Duration of each crawl in minutes
monthly_invocations:
  desc: Number of crawl invocations per month
```

aws\_glue\_trigger

```
monthly_invocations:
  desc: Number of trigger invocations per month
```

aws\_glue\_catalog\_database, aws\_glue\_catalog\_table

```
catalog_object_count:
  desc: Number of objects stored in the Data Catalog
catalog_access_request_count:
  desc: Number of access requests to the Data Catalog per month
table_statistics_job:
  workers_count:
    desc: Number of DPU workers for table statistics jobs
  duration_min:
    desc: Duration of each statistics job in minutes
  monthly_invocations:
    desc: Number of statistics job invocations per month
table_optimization_job:
  workers_count:
    desc: Number of DPU workers for table optimization jobs
  duration_min:
    desc: Duration of each optimization job in minutes
  monthly_invocations:
    desc: Number of optimization job invocations per month
```

## Tipos de serviços compatíveis com o Azure

1. Linux Máquina virtual
2. Máquina virtual do Windows
3. Máquina virtual (versão antiga)
4. Linux Conjunto de máquinas virtuais em escala
5. Conjunto de escalonamento de máquinas virtuais do Windows
6. Conjunto de escalonamento de máquinas virtuais (versão antiga)
7. Kubernetes Cluster
8. Disco gerenciado
9. Application Insights
10. Área de trabalho do Log Analytics
11. CosmosDB (SQL, Mongo, Cassandra, Gremlin, Table)
12. Firewall
13. PostgreSQL Servidor flexível
14. MySQL Servidor flexível
15. Aplicativo Function (para Linux e e Windows)
16. Configuração de autoescala

## Azure Detalhes de uso por tipo de serviço

Recursos de computação

azurerm\_virtual\_machine, azurerm\_linux\_virtual\_machine, azurerm\_windows\_virtual\_machine

```
storage_transactions:
  desc: Number of monthly storage transactions for the VM's OS disk
```

azurerm\_monitor\_autoscale\_setting (para conjuntos de escalonamento de máquinas virtuais)

```
utilization:
  desc: Expected utilization factor between 0 and 1 (e.g. 0.5 = 50% of max capacity)
```

azurerm\_kubernetes\_cluster

```
utilization:
  desc: Expected utilization factor between 0 and 1 for autoscaling node pools (e.g. 0.5 = 50% between min and max node count)
```

Recursos de armazenamento

azurerm\_managed\_disk

```
storage_transactions:
  desc: Number of monthly storage transactions (applies to Standard HDD and Standard SSD)
```

Recursos do banco de dados

azurerm\_cosmosdb\_sql\_container, azurerm\_cosmosdb\_mongo\_collection, azurerm\_cosmosdb\_cassandra\_table, azurerm\_cosmosdb\_gremlin\_graph, azurerm\_cosmosdb\_table

```
storage_gb:
  desc: Amount of data stored in GB
throughput_serverless:
  desc: Throughput consumption for serverless mode (in RU/s units)
```

azurerm\_postgresql\_flexible\_server

```
backup_storage_gb:
  desc: Amount of backup storage in GB beyond included amount
commitment_type:
  values: "reserved"
  desc: Commitment pricing type
commitment_length:
  values: "1_year" or "3_year"
  desc: Duration of the reserved commitment
```

azurerm\_mysql\_flexible\_server

```
backup_storage_gb:
  desc: Amount of backup storage in GB beyond included amount
commitment_type:
  values: "reserved"
  desc: Commitment pricing type
commitment_length:
  values: "1_year" or "3_year"
  desc: Duration of the reserved commitment
```

Recursos de monitoramento

azurerm\_log\_analytics\_workspace

```
analytics_logs_gb:
  desc: Monthly ingestion volume for Analytics Logs in GB
basic_logs_gb:
  desc: Monthly ingestion volume for Basic Logs in GB
auxiliary_logs_gb:
  desc: Monthly ingestion volume for Auxiliary Logs in GB
platform_logs_gb:
  desc: Monthly ingestion volume for Platform Logs in GB
```

azurerm\_application\_insights

```
analytics_logs_gb:
  desc: Monthly data ingestion volume for Analytics Logs in GB
```

Recursos de rede

azurerm\_firewall

```
data_processed_gb:
  desc: Amount of data processed per month in GB (for AZFW_Hub SKU only)
```

Recursos sem servidor

azurerm\_linux\_function\_app, azurerm\_windows\_function\_app

```
tier:
  values: "Flex Consumption"
  desc: Function app hosting tier
memory_mb:
  desc: Memory allocation in MB
monthly_active_executions:
  desc: Number of active executions per month
monthly_active_exec_seconds:
  desc: Total active execution seconds per month
execution_time_ms:
  desc: Average execution time in milliseconds
monthly_executions:
  desc: Total number of executions per month
```

azurerm\_function\_app\_flex\_consumption

```
monthly_active_executions:
  desc: Number of active executions per month
monthly_active_exec_seconds:
  desc: Total active execution seconds per month
always_ready_baseline_sec:
  desc: Always-ready baseline seconds per month
always_ready_exec_sec:
  desc: Always-ready execution seconds per month
always_ready_exec_count:
  desc: Always-ready execution count per month
```
