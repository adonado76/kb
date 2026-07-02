---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Configuração opcional"
breadcrumb: []
source_path: "cost-transparency/configuration/optionalconfig.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configuração opcional

Os itens a seguir são opcionais. Configure uma ou mais das seguintes funções, conforme necessário.

- [Insira os custos estimados não relacionados ao provedor](estmatednonprov.html "Os custos estimados de não fornecedores inseridos manualmente são principalmente para os novos clientes somente do Cloud Cost Management que não iluminaram os reais com seu GL no Costing Standard. Para quem tem o cálculo de custo padrão, a melhor opção é direcionar os custos não relacionados ao fornecedor a partir dos reais no modelo de custo padrão. Há um link entre os dois modelos (modelo CT Cost e modelo CCM Cloud Invoice) para permitir que você faça isso por meio do objeto IT Resource Towers.")
- [Identificar serviços compartilhados](idsharedservices.html "Uma parte dos seus custos de nuvem pode ser atribuída a serviços de infraestrutura de nuvem pública compartilhados entre os departamentos que criam aplicativos na nuvem pública. Um bom exemplo é o Suporte Empresarial, cujos custos podem ser uma grande quantia fixa que precisa ser alocada aos serviços em nuvem que são consumidos diretamente pelas equipes e departamentos da sua organização. Os custos desses serviços de infraestrutura compartilhada podem ser alocados para os serviços que são consumidos diretamente, garantindo que os custos para os departamentos de aplicativos contabilizem todos os custos incorridos com o uso de provedores de nuvem pública.")
- [Mapeie o AWS Marketplace para ATUM](mapawstoatum.html "Se você consumir serviços do AWS Marketplace, deverá ingerir e modelar essas contas da mesma forma que suas contas de serviço do AWS. AWS cria um arquivo de faturamento separado do AWS Marketplace para cada relatório de faturamento que você configurar para ser criado em suas preferências de faturamento.")
- Várias moedas:
  - Para novos clientes, atualize o Azure EA Detailed Bill Master Data.CurrencyCode com o código da moeda da fatura.
  - Para clientes existentes, siga estas instruções: [Configurar o Cloud Cost Management para várias moedas](multicurrency.html "Você pode ativar o suporte a várias moedas para os produtos do Apptio Cloud.").
- [Relatórios diários/hora - Extensão ou alteração](clouddailyhourlyreports.html "Os relatórios diários/horários são criados em um formato de dados que permite armazenamento e consultas rápidos e eficientes em conjuntos de dados de volume muito alto (como contas de nuvem muito granulares, como o Relatório de custo e uso do AWS ). Como resultado, a extensão do esquema dos conjuntos de dados envolvidos e a modificação dos relatórios criados com base nesses conjuntos de dados exigem alguma configuração")
