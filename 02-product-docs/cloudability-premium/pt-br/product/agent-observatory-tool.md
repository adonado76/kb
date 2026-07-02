---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Ferramenta do Observatório de Agentes"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Alocação de custos de contêineres"
source_path: "product/agent-observatory-tool.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Ferramenta do Observatório de Agentes

## Visão geral

A Agent Observability Tool fornece monitoramento em tempo real dos agentes de métricas do Cloudability em um formato tabular em todos os seus clusters, permitindo que você rastreie a integridade do agente, detecte problemas e garanta relatórios de custos precisos.

Nota:

Atualmente, os dados estão disponíveis **apenas para os últimos 7 dias**.

Para acessar a Ferramenta de Observabilidade do Agente:

Navegue até **Insights** > **Contêineres** > **Monitor**.

A Agent Observability Tool exibe em uma tabela a lista de todos os clusters monitorados para agentes de métricas instalados.

| Coluna | Descrição |
| --- | --- |
| Nome do cluster | Nome do seu cluster. |
| Status do agente | Exibe o status como **Ativo** / **Inativo** para o agente de métricas. |
| Versão do agente | A versão do agente instalado. |
| Versão do cluster | A versão do Kubernetes / Openshift em execução no cluster. |
| Visto pela última vez | Registro de data e hora da última ingestão de dados bem-sucedida. |
| Tipo de cluster | Identifica o tipo de cluster (por exemplo, EKS, ROSA ). |
| Fornecedor | O provedor de serviços em nuvem para o cluster (por exemplo, AWS ). |

## Ações recomendadas

- Verifique se há agentes inativos: Filtre por status **Inactive** para encontrar clusters que não estejam relatando dados, investigue conexões, versões e problemas de configuração. Um cluster é marcado como **Inativo** se o valor de **Last Seen** for maior que 12 horas.
- Monitore as versões do agente: Certifique-se de que todos os clusters estejam executando a versão mais recente do agente para compatibilidade, novos recursos e melhorias de segurança.
- Revise os nomes de clusters duplicados: Se você vir um ícone de aviso, atualize os nomes exclusivos dos clusters para obter relatórios precisos.
- Acompanhe a atualização dos dados: Use a coluna **Last Seen** para garantir que os dados sejam recentes. Os agentes que não se apresentarem por mais de 24 horas devem ser revisados.

**Tópico pai:** [Alocação de custos de contêineres](../product/k8s-cost-allocation.html)
