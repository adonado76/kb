---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Custos de contêineres alocados por fornecedor"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Alocação de custos de contêineres"
source_path: "product/container-costs-by-vendor.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Custos de contêineres alocados por fornecedor

Ao alocar o custo com base na utilização, o recurso de alocação de custos de contêineres contabiliza as seguintes informações, dependendo do fornecedor.

AWS (EKS/autogerenciado)

Para AWS, incluímos o custo de todos os nós (instâncias de EC2 ) que estavam presentes no cluster durante o tempo consultado, bem como todos os volumes de EBS anexados.

GCP (GKE)

No caso de " GKE ", incluímos o custo de quaisquer itens de faturamento que apresentem as duas características a seguir:

O rótulo do cluster é fundamental: gke-cluster

O valor é um nome de cluster para o qual o site Cloudability está coletando dados de utilização

Isso também pressupõe um mapeamento de tags configurado em Cloudability para essa chave de rótulo. Normalmente, isso inclui, no mínimo, os custos do Compute Engine d GCP.

Azure (AKS)

Para Azure, incluímos todos os recursos do Grupo de Recursos identificados na lista de nós presentes no cluster durante o tempo consultado. Normalmente, isso inclui o Azure Compute.

Oracle Nuvem (OKE)

Para a OCI, alocamos os custos com base em seus IDs de recursos, que são combinados com itens de linha de faturamento específicos com base nas métricas que eles suportam. Isso garante que os custos de cada contêiner sejam refletidos com precisão de acordo com o seu uso. Você pode descobrir quais instâncias suportam quais métricas visitando [Oracle 's compute pricing](https://www.oracle.com/cloud/compute/pricing/ "(Abre em uma nova guia ou janela)"). Esse recurso ajuda a explicar as variações nos custos, por exemplo, por que alguns nós acumulam taxas de sistema de arquivos enquanto outros não, com base nos custos suportados por métrica de cada tipo de nó.

Red Hat OpenShift Serviço em AWS

Cloudability o Container Cost Insights da Container foi ampliado para oferecer suporte ao site ROSA semelhante ao EKS. O processo de configuração para importar dados do ROSA para o Cloudability segue as mesmas etapas básicas da configuração do K8s – você baixa um arquivo YAML do agente Cloudability, que é então utilizado no seu cluster para [provisionar o agente de métricas](k8s-cluster-provisioning.html#k8s-cluster-provisioning__deploythemetricsagent).

Configurações compatíveis com o site Kubernetes

Como o orquestrador de contêineres mais popular que existe, há muitas maneiras diferentes de implementar Kubernetes e OpenShift. Nós nos esforçamos para oferecer suporte a todas as versões certificadas pelo CNCF e manteremos essa matriz atualizada à medida que implementarmos o suporte para configurações adicionais.

**Tópico pai:** [Alocação de custos de contêineres](../product/k8s-cost-allocation.html)
