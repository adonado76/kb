---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Conectar IBM Cloud"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "product/apptio_help_center_ibm_cloud.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar IBM Cloud

Você pode conectar suas contas IBM Cloud a Cloudability para permitir a ingestão de dados de custo e uso. Cloudability suporta a ingestão de dados de contas Enterprise e Standard. Uma **conta padrão IBM Cloud** é simplesmente uma conta única e independente para uma organização ou usuário, com seu próprio faturamento e gerenciamento de acesso. Uma **[conta corporativa](https://cloud.ibm.com/docs/enterprise-management?topic=enterprise-management-what-is-enterprise "(Abre em uma nova guia ou janela)")** é uma conta principal de nível superior que funciona como um hub central para gerenciar uma hierarquia de várias contas secundárias individuais e grupos de contas.

Nota:

Leva de 4 a 24 horas para que seus dados iniciais de custo e uso apareçam em Cloudability. Isso depende do tempo que o site IBM Cloud leva para gerar seus primeiros relatórios de faturamento.

**Duas maneiras de se conectar**

Há dois métodos para conectar suas contas IBM Cloud a Cloudability :

1. Cloudability método: É fornecido um script do Terraform para o gerenciamento de credenciais, que se baseia em chaves de API.
2. Método de aplicativo de Arquitetura Implantável (DA): O IBM Cloud oferece suporte a um aplicativo de Arquitetura Implantável (DA) chamado “ IBM Cloudability Enablement”, com o qual você pode autenticar sua conta do IBM Cloud no Cloudability. Esse é o método preferencial para credenciar contas d IBM Cloud, pois o aplicativo ajuda a agilizar o processo.

- **[Configure as credenciais de IBM Cloud usando o método Cloudability](../product/setup_ibm_cloud_credentials_using_cldy_method.html)**
- **[Configure as credenciais IBM Cloud usando o aplicativo de arquitetura implantável (DA)](../product/setup_ibm_cloud_credentials_using_da_method.html)**
