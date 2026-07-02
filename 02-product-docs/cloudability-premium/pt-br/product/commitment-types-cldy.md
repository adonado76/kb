---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Tipos de compromisso em Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Otimização de custos da nuvem em Cloudability"
source_path: "product/commitment-types-cldy.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Tipos de compromisso em Cloudability

Os seguintes tipos de compromissos são suportados no Cloudability pelos três principais fornecedores de nuvem. As tabelas a seguir exibem os detalhes.

AWS Tipos de compromisso suportados

| Categoria | Tipo | Faturado | Comprado em | Escopo |
| --- | --- | --- | --- | --- |
| Recurso | EC2 Instância reservada | Hora extra para usar ou perder | Unidades | Tipo de instância, região, sistema operacional |
| RDS Instância reservada | Hora extra para usar ou perder | Unidades | Região, mecanismo de banco de dados |
| Abrir instância reservada de pesquisa | Hora extra para usar ou perder | Unidades | Tipo de instância, opção de pagamento, região |
| Redshift Nós reservados | Hora extra para usar ou perder | Nós | Tipo de nó, região |
| Nós reservados da Elasticache | Hora extra para usar ou perder | Nós | Tipo de nó, região, sistema operacional |
| Gastar | Plano de poupança de cálculo | Hora extra para usar ou perder | Custo por hora | Inscreva-se em EC2 em todas as instâncias de família, tamanho, AZ, região, sistema operacional ou locação, e também se inscreva no Fargate ou Lambda. |
| EC2 Plano de poupança | Hora extra para usar ou perder | Custo por hora | Família e região da instância |
| SageMaker Plano de poupança | Hora extra para usar ou perder | Custo por hora | Aplica-se independentemente da família, tamanho, AZ, região AWS ou componentes da instância. |

Azure Tipos de compromisso suportados

| Categoria | Tipo | Faturado | Comprado em | Escopo |
| --- | --- | --- | --- | --- |
| Recurso | Instância reservada de máquina virtual | Hora extra para usar ou perder | Quantidade | Tipo de instância, região, sistema operacional |
| SQL Database e Instância Reservada Gerenciada | Hora extra para usar ou perder | Quantidade | Nível de desempenho, região, tipo de implementação |
| Banco de dados para capacidade reservada do MySQL | Hora extra para usar ou perder | Instância | Opção de implantação, instância e região |
| Banco de dados para capacidade reservada d PostgreSQL | Hora extra para usar ou perder | Instância | Opção de implantação, instância e região |
| Azure Blob Storage Capacidade reservada | Hora extra para usar ou perder | Tamanho ( 100Tb, 1Pb ) | Nível de acesso, redundância, tamanho e região |
| Cosmos DB Capacidade reservada | Hora extra para usar ou perder | Unidades reservadas (RU/s) | Camada |
| Pools de SQL dedicados do Synapse Analytics | Hora extra para usar ou perder | Unidades de armazenamento de dados (DWUs) | Região |
| Cache para Redis Reservas | Hora extra para usar ou perder | Nós (análogo à capacidade total do cache) | Tipo de nó, região, sistema operacional |
| App Service Instanças reservadas | Hora extra para usar ou perder | Quantidade | Instância, camada, região |
| Gastar | Plano de poupança de cálculo | Hora extra para usar ou perder | Custo por hora | Tipo de escopo |
| Planos de pré-compra da Databricks | Créditos Fungíveis em todo o período | 1 DBU = $1 | Família e região da instância |
| Planos de pré-compra do Synapse Analytics | Créditos Fungíveis em todo o período | 1 SCU = $1 | Aplicável em 7 produtos |
| Taxa de transferência provisionada do Microsoft Foundry | Hora extra para usar ou perder | PTU, uma unidade normalizada de uso de largura de banda | Região, Tipo de implantação |

GCP Tipos de compromissos suportados

| Categoria | Tipo | Faturado | Comprado em | Escopo |
| --- | --- | --- | --- | --- |
| Recurso | CUDs do mecanismo de computação | Hora extra para usar ou perder | vCPU\*, Memória\*, disco SSD local, GPU | Tipo de máquina, região |
| Gastar | Flex-CUDs do mecanismo de computação | Hora extra para usar ou perder | Equivalente a uma hora sob demanda | Tipo de Máquina |
| CUDs de SQL na nuvem | Hora extra para usar ou perder | Equivalente a uma hora sob demanda | Família e região da instância |

Para solicitar suporte para um tipo adicional, por favor, [adicione](https://ideas.ibm.com/new-idea "(Abre em uma nova guia ou janela)") ou vote a favor de uma sugestão em nossa comunidade (Sugestões do IBM ) ou entre em contato com o representante da sua conta. Escolha Rate Optimization como a categoria para a ideia.

**Tópico principal:** [Otimização de custos da nuvem no Cloudability](../product/cloud_cost_optimization.html)
