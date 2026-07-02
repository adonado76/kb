---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "AWS RDS"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto avançado"
source_path: "product/aws_rds.html"
images:
  - "images/aws-rds-dashboard.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS RDS

Você pode usar o painel “Advanced Rightsizing” para visualizar as recomendações de otimização de recursos para o Serviço de Banco de Dados Relacional do Amazon Web Services ( AWS ) ( RDS ). O painel exibe recomendações de otimização tanto para poupança quanto para investimentos, com base no mecanismo d Turbonomic. Você pode visualizar as recomendações de várias contas do AWS a partir de um único painel.

[Ajuste avançado de recursos no Cloudability Premium](advanced-rightsizing-powered-by-turbonomic.dita "(Abre em uma nova guia ou janela)")

**Antes de começar**

Para visualizar o painel do AWS RDS, certifique-se de ter conectado o Cloudability às contas corretas do AWS.

[Conectando-se ao AWS - Guia de integração do cliente](../admin/aws-credentialing-standard-enterprise-home.dita "(Abre em uma nova guia ou janela)")

Observação: É necessário garantir que todas as suas credenciais de fornecedor existentes tenham as permissões relevantes concedidas pelo Turbonomic; sem elas, o mecanismo Turbonomic pode não conseguir gerar o conjunto correto de ações. Se você já era cliente do Cloudability antes da atualização para o Cloudability Premium, ainda precisará atualizar todas as credenciais de cada fornecedor para conceder um conjunto adicional de permissões.

**Acesse o painel do AWS RDS**

Para acessar o painel do AWS RDS, abra a página inicial Cloudability e, no menu de navegação à esquerda, selecione Otimizar > Redimensionamento > Avançado. Na página “Rightsizing”, selecione a guia “ AWS ” e, em seguida, selecione “ RDS ” no menu suspenso. ![](../../../../03-media/cloudability-premium/images/aws-rds-dashboard.png)

**Especificar base de custo**

A Base de Custo determina como as recomendações são calculadas e como as economias ou os investimentos são projetados. A base de custo pode **ser** “Ajustada” ou **“Ajustada e amortizada”**, o que reflete os cálculos subjacentes dos custos dos recursos de origem e de destino.

**Ajustado** — calculado com base no custo de caixa de um determinado recurso, incluindo suas taxas privadas, quando disponíveis (onde o custo de compromisso é considerado como $0), e comparado ao custo de caixa projetado para o estado futuro e à cobertura esperada dos compromissos aplicáveis a esse recurso durante o período de análise retrospectiva. Esse cálculo é denominado “On Demand” na documentação “ Cloudability Premium : Workload Optimization UI” e “ Turbonomic ”.

**Amortizado ajustado** — calculado com base no custo amortizado de um determinado recurso e nos compromissos associados que se aplicaram a ele durante o período de análise retrospectiva (incluindo tarifas privadas, quando disponíveis). O custo futuro do Estado é calculado com base na forma como se espera que esses compromissos sejam aplicados, quais parcelas devem permanecer sob demanda e quais compromissos (se houver) serão liberados para serem aplicados em outras áreas. Esse cálculo é denominado “Efetivo” na interface de usuário do Cloudability Premium : Workload Optimization e na documentação disponível em Turbonomic.

**Indicadores-chave de desempenho**

Você pode visualizar os seguintes Indicadores-chave de Desempenho (KPIs) no seu painel do Advanced Rightsizing:

- **Gastos totais** : Mostra o total atual dos gastos alocados
- **Economia potencial** : mostra a estimativa da economia total potencial que pode ser alcançada com todas as recomendações de otimização cujo impacto nos custos seja menor do que o custo atual
- **Investimentos necessários** : Mostra o total estimado dos investimentos potenciais em todas as recomendações de otimização com impacto de custo maior do que o custo atual

Observação: No caso do serviço “ RDS ”, o custo é determinado pelo uso da instância.

**Tabela de recomendações para o redimensionamento**

O painel de controle contém uma tabela de recomendações de ajuste de capacidade, que oferece uma visão geral dos recursos do EDS para os quais foram identificadas recomendações. A tabela inclui as seguintes colunas:

Observação: Por padrão, os dados são classificados pela **col** una “Impacto no custo”. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- **Status:** Status que indica se a ação está pronta para ser executada
- **Nome do recurso** : O nome do recurso “ RDS ”
- **Nome da conta** : Nome da conta na qual o banco de dados do RDS está em execução
- **Não disruptivo:**  Indicação de que a ação apresentada não é disruptiva
- **Reversível**  : Indicação se a ação apresentada é reversível ou não
- **Tipo**  : O tipo atual da instância do ` RDS `
- **Custo**  : O custo atual da instância do RDS
- **Novo tipo de instância** : O tipo de instância recomendado para o RDS
- **Novo custo** : O custo projetado do novo tipo de instância “ RDS ” recomendado
- **Categoria** da ação : A categoria da ação recomendada. Os modos atualmente suportados são “Desempenho” ou “Economia”
- **Ação** : A ação recomendada. A tabela abaixo lista as diversas ações suportadas
- **Impacto nos custos** : Impacto nos custos decorrentes da implementação desta ação

|  |  |
| --- | --- |
| **Recomendação** | **Descrição** |
| **Escala** | Redimensione de acordo com o tipo de recurso especificado na **col** una “Novo tipo de instância”. Essa ação pode ser de “aumentar a escala” ou “diminuir a escala”, dependendo das políticas configuradas |
| **Desativar** | Encerre seu recurso, pois ele está predominantemente ocioso |

**Exportar recomendações de otimização para um arquivo do Excel**

Para exportar as ações recomendadas para um arquivo do Excel, **selec** ione “Exportar”. Observe que o arquivo do Excel incluirá várias colunas adicionais, como região, sistema operacional, preço unitário e outras.

**Detalhes da recomendação**

Para visualizar os detalhes da ação recomendada para um recurso específico, **selec** ione “Exibir detalhes” no menu “Mais opções” (três pontos).

Para consultar as descrições das dimensões e métricas de custo, consulte [o](glossary-of-cost-dimensions-and-metrics.dita "(Abre em uma nova guia ou janela)") Glossário de dimensões e métricas de custo

Para visualizar detalhes sobre a dimensão de utilização e as métricas, consulte [o](glossary-of-utilization-dimensions-and-metrics.dita "(Abre em uma nova guia ou janela)") Glossário de dimensões e métricas de utilização

**Tópico principal:** [Redimensionamento avançado](../product/advanced-rightsizing-powered-by-turbonomic.html)
