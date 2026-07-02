---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Apptio - AWS Política de IAM"
breadcrumb: []
source_path: "cost-transparency/configuration-additional/awsiampolicy.html"
images:
  - "resources/images/ct_images/8285_1.png"
  - "resources/images/ct_images/8285_2.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Apptio - AWS Política de IAM

- Aplica-se a: Apptio Costing Standard ou Apptio Cloud Cost Management em execução em TBM Studio v12.3.3 ou posterior.

O documento em anexo inclui a política de IAM baseada em JSON necessária ao configurar uma nova função em AWS.This. A política de IAM inclui várias permissões que permitem que Datalink (Classic) acesse dados no seu ambiente AWS que o CCM exige para fornecer análises sobre seu custo e consumo em AWS, bem como recomendações do Trusted Advisor. A figura a seguir destaca as várias seções da política de IAM.

Observação: Somente a primeira seção ( S3-related ) é necessária para os usuários do conector multicloud.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8285_1.png)

A API de suporte é a única opção de acesso aos dados do Trusted Advisor e requer a permissão de suporte para funcionar corretamente. A captura de tela abaixo da documentação do AWS ilustra a limitação e, para obter mais informações, consulte a documentação do AWS disponível aqui: [Primeiros passos com o suporte AWS](https://docs.aws.amazon.com/awssupport/latest/user/getting-started.html "(Abre em uma nova guia ou janela)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8285_2.png)

[Link para o arquivo de política](https://community.apptio.com/viewdocument/apptio-aws-iam-policy?CommunityKey=15f4e51d-d06f-4641-94c5-f2598d137d06&tab=librarydocuments "(Abre em uma nova guia ou janela)")
