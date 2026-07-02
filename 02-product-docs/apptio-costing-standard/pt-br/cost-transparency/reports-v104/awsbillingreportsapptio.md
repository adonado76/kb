---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Visão geral dos relatórios de faturamento do site AWS"
breadcrumb: []
source_path: "cost-transparency/reports-v104/awsbillingreportsapptio.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Visão geral dos relatórios de faturamento do site AWS

Aplica-se a: Costing Standard em TBM Studio 12.3.3 e posterior

AWS oferece várias fontes de dados de faturamento, cada uma com suas próprias características e usos. Para obter mais detalhes, consulte [Entendendo seu uso com relatórios de faturamento - AWS Billing and Cost Management.](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-reports.html "(Abre em uma nova guia ou janela)")

Embora o site Apptio seja compatível com dados de uma grande variedade de fontes, oferecemos integrações específicas para um subconjunto de relatórios de faturamento do site AWS. Atualmente, o Apptio criou integrações com os seguintes relatórios de faturamento:

- **Relatório de alocação de custos** - Essa conta mensal de grãos do site AWS inclui todos os detalhes de faturamento (produto AWS, quantidade de uso, custo, etc.) bem como as tags selecionadas para serem incluídas nas faturas. Apptio aproveita o Relatório de alocação de custos para gerar relatórios mensais de TCO para a nuvem pública.
- **Relatório detalhado de faturamento com recursos e etiquetas** - Essa fatura por hora do site AWS é semelhante ao relatório de alocação de custos e inclui detalhes de faturamento e etiquetas. Apptio aproveita o Relatório de Faturamento Detalhado com Recursos e Tags para gerar o relatório de Custos Diários no Cloud Cost Management, que você pode usar para ver os custos acumulados no mês até o dia atual, bem como a tendência diária e horária dos custos do AWS.

O relatório de faturamento detalhado com recursos e tags pode se tornar excessivamente grande ( 100M+ linhas por mês) porque combina detalhes por hora com os detalhes inerentes ao faturamento AWS. À medida que as despesas da sua organização em AWS aumentam, o tamanho dessa conta pode se tornar muito grande para ser trazido para Apptio como um arquivo.csv nativo.

A partir da versão Apptio 12.3.3 e Datalink (Classic), você verá uma nova opção de transformação automática do conector AWS que permite ingerir o Relatório de Faturamento Detalhado com a fatura de Recursos e Tags em um novo formato no qual o relatório de Custos Diários é criado. Esse novo formato, embora sirva como base para os relatórios diários no Cloud Cost Management, não está disponível no momento para transformações ou modelagem em TBM Studio. O relatório de alocação de custos ainda é a fonte para o faturamento mensal.

## E o relatório de custo e uso (CUR) do site AWS?

AWS tem um relatório de faturamento mais recente que é o padrão futuro para as contas do AWS. Apptio está trabalhando atualmente na integração com o CUR e tem planos de fornecer um conector baseado no CUR em uma versão futura.
