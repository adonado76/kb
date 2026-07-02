---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Agente de métricas do Common Kubernetes - Mensagens de erro"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "product/k8s-metrics-agent.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Agente de métricas do Common Kubernetes - Mensagens de erro

**Visão geral**

Durante a operação, o Agente de Métricas do Cloudability pode registrar mensagens de erro específicas. Este artigo explica como analisar os registros de mensagens de erro, quais são as mensagens de erro mais comuns e quais são as possíveis soluções.

**Análise dos registros de mensagens de erro**

Para visualizar os registros de mensagens de erro de um pod específico do Metrics Agent, é necessário obter o nome do pod antes de solicitar o registro de mensagens de erro.

1. Na linha de comando, execute o comando a seguir para visualizar uma lista de todos os pods do Metrics Agent disponíveis em um cluster. `kubectl get pods -n cloudability`
2. Execute o comando a seguir para visualizar o log de mensagens de erro de um pod específico do Metrics Agent. Substitua <pod-name> pelo nome do pod do Metrics Agent identificado na etapa anterior. `kubectl logs <pod-name> -n cloudability`

`Exported metric sample <cluster_UID>_<timestamp> to cloudability`

**Mensagens de erro**

| Mensagem de erro | Solução |
| --- | --- |
| Aviso: erro não fatal: ocorreu um erro do agente ao recuperar diagnósticos de tempo de execução: <mensagem detalhada> | Pode ser necessário atualizar a função RBAC no namespace Cloudability. Refaça o provisionamento do agente de métricas para este cluster, conforme detalhado em [Kubernetes cluster provisioning](k8s-cluster-provisioning.html). |
| Erro ao enviar métricas: Erro ao recuperar o URI de upload: 403 | A chave da API do Cloudability atualmente em uso não é válida. A chave da API pode estar incorreta ou pode ter expirado.  Se a chave da API tiver expirado, ela precisa ser reativada antes de se proceder ao reabastecimento do agente de métricas, conforme detalhado em [Kubernetes cluster provisioning](k8s-cluster-provisioning.html). Entre em contato com o suporte para reativar as chaves de API expiradas.  Se a chave da API estiver incorreta, gere-a novamente seguindo as etapas de provisionamento descritas em [Kubernetes cluster provisioning.](k8s-cluster-provisioning.html) |
| Erro ao enviar métricas: Erro ao recuperar o URI de envio: <mensagem detalhada> | Problemas de transporte de rede podem estar impedindo que o agente entre em contato com a API de coleta de métricas.  Esse erro pode ser causado por configurações de segurança do cluster ou por proxies configurados nos contêineres do cliente Kubernetes. Essas configurações são gerenciadas pelos administradores do cluster. Entre em contato com os administradores do cluster do Kubernetes para confirmar se o Metrics Agent consegue estabelecer uma conexão com: [https://metrics-collector.cloudability.com](https://metrics-collector.cloudability.com/ "(Abre em uma nova guia ou janela)") |
| Aviso: erro não fatal: Ocorreu um erro do agente ao recuperar as métricas de origem do nó: Não foi possível recuperar as métricas do nó. Verifique as funções RBAC: | Pode ser necessário atualizar a função RBAC no namespace Cloudability. Refaça o provisionamento do agente de métricas para este cluster, conforme detalhado em [Kubernetes cluster provisioning](k8s-cluster-provisioning.html). |
| Nó Fargate encontrado no cluster; conexão direta com o nó desativada. | Não é possível estabelecer conexão direta com um nó do AWS Fargate; portanto, quando um nó do Fargate é detectado no cluster, o agente passa a utilizar o kube-proxy para todas as conexões com os nós do cluster.  Atualmente, a alocação de tarefas do EKS Fargate não é suportada pelo painel de controle do recurso de contêineres. Entre em contato com seu gerente técnico de contas para obter instruções sobre como acessar as informações do EKS Fargate por meio do recurso de relatórios. |

Para obter suporte direto em relação a problemas com o Agente de Métricas do Cloudability, [entre em contato com o Suporte](https://support.cloudability.com/hc/en-us/requests/new "(Abre em uma nova guia ou janela)").
