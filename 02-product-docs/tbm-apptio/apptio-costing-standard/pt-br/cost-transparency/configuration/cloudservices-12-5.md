---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Configuração da nuvem para o cálculo de custos padrão 12.1 por meio de 12.5x"
breadcrumb: []
source_path: "cost-transparency/configuration/cloudservices-12-5.html"
images:
  - "resources/images/ct_images/6820_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configuração da nuvem para o cálculo de custos padrão 12.1 por meio de 12.5x

Use o componente CTF - Cloud Service Provider para importar dados de uso de serviços da Web. O componente é opcional.

## Introdução

Se você estiver usando Amazon Web Services ( AWS ), Microsoft Azure, SoftLayer, ou CenturyLink,, poderá importar dados de uso dos relatórios mensais de uso e faturamento. Os dados são usados nos relatórios CTF e nos relatórios de aplicativos e serviços. Os dados podem ajudá-lo a comparar o custo dos serviços em nuvem com os serviços internos. Para usar os dados dos webservices, você deve instalar o componente CTF - Cloud Service Provider.

## Dois procedimentos de configuração diferentes

Há dois procedimentos de configuração diferentes:

- [Amazon Web Services configuração](aws.html "Para configurar o aplicativo para Amazon Web Services, você deve instalar os componentes CTF-Cloud Service e CTF- Amazon Web Services.")
- [Microsoft Azure e configuração de outros provedores](azure.html "Para configurar o aplicativo para Microsoft Azure ou outros provedores, você deve instalar o componente CTF-Cloud Service.")

Cada procedimento é documentado separadamente.

## Vinculado a fornecedores

Para que o custo da nuvem seja calculado corretamente, os dados do fornecedor devem ser inseridos no aplicativo Costing Standard . Os dados do fornecedor identificam os custos provenientes dos serviços da Web e os alocam aos serviços em nuvem. O modelo apresentado abaixo mostra essa relação.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6820_1.png)

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
