---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Configurar um agente de monitoramento d GCP s para o dimensionamento adequado"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conectar Google Cloud"
source_path: "admin/gcp-memory-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configurar um agente de monitoramento d GCP s para o dimensionamento adequado

Para que o Cloudability possa utilizar métricas adicionais de utilização, como a memória, será necessário configurar o Agente de Monitoramento do GCP. Cloudability é compatível tanto com o Ops Agent quanto com o Legacy Monitoring Agent. As instruções a seguir detalham como configurar cada agente:

1. Pré-requisitos

   Para instalar o agente, certifique-se de que todas as condições estejam atendidas.

   [Instalação do Ops Agent em máquinas virtuais individuais](https://cloud.google.com/monitoring/agent/monitoring/installation#before_you_begin "(Abre em uma nova guia ou janela)")

   [Instalação do agente antigo do Cloud Monitoring em máquinas virtuais individuais](https://cloud.google.com/monitoring/agent/monitoring/installation#before_you_begin "(Abre em uma nova guia ou janela)")
2. Instale o agente usando a linha de comando

   Para instalar o agente pela linha de comando, siga as instruções a seguir.

   [Instalando o Ops Agent usando a linha de comando](https://cloud.google.com/monitoring/agent/monitoring/installation#joint-install "(Abre em uma nova guia ou janela)")

   [Instalando o agente Legacy usando a linha de comando](https://cloud.google.com/monitoring/agent/monitoring/installation#joint-install "(Abre em uma nova guia ou janela)")
3. Instale o agente usando o console do Google Cloud

   Você pode instalar o agente em uma ou mais máquinas virtuais do Compute Engine a partir do painel pré- VM ado “Monitoramento de instâncias do Compute Engine”.

   [Instalando o Ops Agent usando o Console do Google Cloud](https://cloud.google.com/monitoring/agent/monitoring/installation#gce-ui-install "(Abre em uma nova guia ou janela)")

   [Instalação do agente Legacy usando o Console do Google Cloud](https://cloud.google.com/monitoring/agent/monitoring/installation#gce-ui-install "(Abre em uma nova guia ou janela)")

**Tópico principal:** [Conectar-se Google Cloud](../admin/connect-google-cloud-premium.html)
