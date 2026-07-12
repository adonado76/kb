---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Apptio abordagem de marcação recomendada para serviços de nuvem pública IaaS/PaaS"
breadcrumb: []
source_path: "cost-transparency/user-guide/rectaggingapproachpubliccloud-7892.html"
images:
  - "resources/images/ct_images/7892_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Apptio abordagem de marcação recomendada para serviços de nuvem pública IaaS/PaaS

A marcação em um ambiente de nuvem pública é uma maneira vital de aplicar informações mais informativas aos seus recursos de nuvem. Sem informações de marcação, as faturas do provedor de nuvem incluirão informações sobre os serviços do provedor e, possivelmente, apenas as contas responsáveis pela implementação dos recursos. Ao marcar informações, você pode obter informações mais descritivas sobre os recursos, como o aplicativo que consome esse recurso, o ambiente suportado pelo recurso e o indivíduo que possui o recurso. Todos são exemplos de informações geralmente associadas a tags de recursos.

- Aplica-se a: Apptio Costing Standard ou Apptio Cloud Cost Management em execução em TBM Studio v12.3.3 ou posterior.

Apptio o objeto do provedor de serviços de nuvem Costing Standard inclui alguns atributos predefinidos que provavelmente são candidatos a serem preenchidos com tags. A lista desses atributos é a seguinte:

- Consumidor

  Observação: Dependendo de como as empresas estão organizadas, o Consumer, em muitos casos, pode ser preenchido por um atributo sem tag, como uma conta vinculada para Amazon Web Services ( AWS ) ou uma conta para Microsoft Azure.
- Aplicativo
- Meio ambiente
- Propósito
- Centro de custos
- Proprietário do sistema
- Projeto

Apptio recomenda que as empresas configurem tags para capturar informações associadas a pelo menos alguns dos atributos listados acima usando os meios apropriados para o provedor. Entre em contato com seu provedor e com os proprietários da infraestrutura de nuvem para obter mais informações sobre a configuração de tags. Os links a seguir estão associados a provedores populares:

- [AWS](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-what-is.html "(Abre em uma nova guia ou janela)")
- [Azure](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/tag-resources?tabs=json "(Abre em uma nova guia ou janela)")
- [Google Cloud](https://cloud.google.com/compute/docs/labeling-resources "(Abre em uma nova guia ou janela)")

Esses atributos podem então ser usados como dimensões em sua análise e/ou como dimensões pelas quais os custos são alocados. A imagem a seguir mostra o uso do atributo Application (Aplicativo) como um valor pivotável para examinar seus custos de nuvem por aplicativo de consumo.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7892_1.png)![Uso do atributo Application (Aplicativo) como um valor be central]()

Além disso, o atributo Application (Aplicativo) costuma ser um meio pelo qual os custos devem ser alocados ao aplicativo apropriado para gerar um TCO do aplicativo que inclua os gastos públicos do IaaS/PaaS.
