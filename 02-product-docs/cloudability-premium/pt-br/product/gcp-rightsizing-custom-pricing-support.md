---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Configurando o suporte a preços personalizados para GCP"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conectar Google Cloud"
source_path: "product/gcp-rightsizing-custom-pricing-support.html"
images:
  - "images/gcp-standard-billing-1.jpg"
  - "images/gcp-standard-billing-2.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configurando o suporte a preços personalizados para GCP

O suporte a preços personalizados agora foi estendido ao GCP para o Cloudability, de modo que descontos contratuais e outros preços específicos para cada cliente sejam aplicados às recomendações de ajuste de capacidade do GCP e **ao Planejamento** de Cargas de Trabalho.

Siga as etapas abaixo para habilitar a exportação de dados de preços personalizados para contas do GCP.

1. Acesse a conta de cobrança do GCP.
2. Selecione **Billing** > **Billing export**.

   ![GCP captura de tela do faturamento padrão](../../../../03-media/cloudability-premium/images/gcp-standard-billing-1.jpg)
3. Em **Preços**, clique em “ **Habilitar exportação de preços** ”.
4. Selecione **Pricing > Edit Settings**.
5. Dependendo da sua escolha de **faturamento GCP** ( **Faturamento Padrão** ou **Faturamento Detalhado** ), você precisa garantir o seguinte:
   - Selecione **o nome do projeto** e **o nome do conjunto de dados** igual ao **selecionado** para " **Custo de uso padrão** " se estiver usando o **faturamento padrão**.

   ![Ícone de notas](../../../../03-media/cloudability-premium/images/gcp-standard-billing-2.jpg)

   - Selecione **o nome do projeto** e **o nome do conjunto de dados** igual ao **selecionado** para " **Custo de uso detalhado** " se estiver usando **o faturamento detalhado**.

**Tópico principal:** [Conectar Google Cloud](../admin/connect-google-cloud-premium.html)
