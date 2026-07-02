---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "pt-br"
doc_type: "apptio-cost-management"
title: "Configuração de benchmarking de custos"
breadcrumb:
  - "Costing Essentials"
  - "Configuração"
source_path: "apptio-cost-management/admin/setup-be.html"
images:
  - "resources/images/acm_images/bm-1.jpg"
  - "resources/images/acm_images/bm-10.jpg"
  - "resources/images/acm_images/bm-2.jpg"
  - "resources/images/acm_images/bm-3.jpg"
  - "resources/images/acm_images/bm-4.jpg"
  - "resources/images/acm_images/bm-5.jpg"
  - "resources/images/acm_images/bm-6.jpg"
  - "resources/images/acm_images/bm-6a.jpg"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Configuração de benchmarking de custos

Pré-Requisito

O COE ou qualquer pessoa com acesso equivalente precisa fazer login em um produto ITBMX (Interactive Benchmarking) geral e atualizar o perfil da empresa do cliente (receita, gastos em OpEx etc.).

1. Faça login na ITBMX

   ![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-1.jpg)
2. Clique no ícone de roda dentada (configurações) na seção superior direita da tela e selecione "Configuration" (Configuração).

   ![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-2.jpg)
3. Na seção "Organization Profile" (Perfil da organização), insira "Organization Revenue" (Receita da organização), "Organization OpEx’ " (Organização ) e "Number of Employees" (Número de funcionários) sec1on com os números desejados.

   ![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-3.jpg)

   Observação: Certifique-se de que os números inseridos nas três seções sejam válidos com a marca "verde" antes de continuar.
4. Clique no menu suspenso "Benchmarks" no canto superior esquerdo da tela.

   ![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-4.jpg)
5. Role para baixo até a parte inferior da tela e clique no botão "Download Benchmarks as CSV".

   ![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-5.jpg)
6. Clique no botão "Download" na caixa de mensagem "Download Benchmarks" e verifique se o arquivo '.csv' foi baixado.

   ![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-6a.jpg)

   ![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-6.jpg)
7. Volte para a instância de cliente desejada e navegue até TBM Studio.

   Upload e configuração de dados
8. Em TBM Studio, carregue o arquivo '.csv' baixado no projeto. Faça as transformações necessárias, se for o caso.
9. Mapeie o conjunto de dados carregado para o Feed de Benchmarking.

   ![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-10.jpg)
