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
  - "Dimensionamento correto"
source_path: "product/rightsizing-for-aws-rds.html"
images:
  - "images/aws-rds-dashboard.jpg"
  - "images/edit-icon.jpg"
  - "images/rightsizing-aws-rds.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS RDS

Você pode usar o painel Rightsizing para visualizar as recomendações de otimização de recursos para Amazon Web Services ( AWS ) Relational Database Service ( RDS ). O painel mostra as recomendações de rightsizing e de inatividade (encerramento). Você pode visualizar as recomendações em várias contas a partir de um único painel.

[Rightsizing em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Antes de começar

Para visualizar o painel do AWS RDS, certifique-se de que conectou o Cloudability às contas corretas do AWS.

[Conexão com AWS - Guia de integração do cliente](../admin/aws-credentialing-standard-enterprise-home.html)

Acesse o painel do AWS RDS

Para acessar o painel do AWS RDS, abra a página inicial do Cloudability e, no menu de navegação à esquerda, selecione Otimizar > Redimensionamento. Na página Rightsizing, selecione a guia AWS e, em seguida, selecione a subguia RDS.

![AWS RDS captura de tela](../../../../03-media/cloudability-premium/images/aws-rds-dashboard.jpg)

Personalizar o painel de controle

Você pode definir as seguintes opções para personalizar seu painel.

Especificar a base de custos

A base de custo determina como as recomendações são calculadas. A base de custo pode ser On-Demand ou Effective. A base de custos On-Demand é selecionada por padrão.

Nota:

Se sua organização tiver ativado o Custom Pricing em Cloudability, as taxas personalizadas relevantes serão aplicadas aos cálculos da base de custo.

- Sob demanda : A base de custos sob demanda fornece uma comparação direta entre a instância listada na coluna Atual e a instância recomendada na coluna Nova com base exclusivamente no preço sob demanda. Ele não inclui nenhum impacto potencial de instâncias reservadas (RIs) ou planos de economia (SPs). Observe que os preços sob demanda refletirão quaisquer acordos de preços personalizados que você tenha configurado em Cloudability.
- Efetivo : A base de custo efetiva leva em conta o impacto histórico das instâncias reservadas (RIs) e dos planos de economia (SPs) para calcular o custo do tipo de instância atual durante o período do relatório. Assim como a métrica de custo (amortizado), ela inclui todos os custos iniciais e recorrentes associados.   
   Em outras palavras, a base de custo efetivo mostra o custo efetivo da execução de sua instância atual. Os valores de custo para o novo tipo de instância recomendado são baseados nos preços sob demanda. Isso ocorre porque a nova configuração pode não se beneficiar de RIs ou SPs. Essa comparação é a opção mais conservadora. Mesmo que você se afaste inadvertidamente dos RIs ou SPs, sua nova taxa geral ainda será melhor. Como resultado, a economia total relatada usando essa metodologia às vezes será menor. O preço personalizado será aplicado a esses valores, se aplicável.

Nota:

Use a base de custo On-Demand se estiver procurando remover a natureza imprevisível dos descontos baseados em compromisso de sua análise e maximizar o número de recomendações fornecidas a você. Use a base de custo efetivo se preferir basear suas recomendações no custo real histórico da execução de suas instâncias e adotar uma abordagem conservadora.

Selecionar conta

Por padrão, o painel mostra recomendações para todas as contas. Para visualizar as recomendações de uma conta específica, selecione o nome da conta no menu suspenso Conta.

Especificar o cronograma

Você pode optar por revisar as despesas dos últimos 10 dias ou dos últimos 30 dias. Por padrão, a opção Linha do tempo é definida como 10 dias. Para a maioria dos usuários, 10 dias é o período de tempo recomendado porque captura as tendências de desempenho mais recentes e é mais preditivo do uso futuro de recursos.

Aplicar filtros

Você pode adicionar filtros para incluir ou excluir dados com base em uma ou mais condições.

Adicionar um filtro

Para adicionar um filtro:

1. Selecione Add Filter (Adicionar filtro ) na barra de ferramentas.
2. No menu Add Filter (Adicionar filtro ), escolha uma Dimensão.
3. Selecione um operador para fornecer uma condição lógica.
4. Escolha um valor para refinar seu filtro.
5. Selecione Add Filter (Adicionar filtro ) para aplicar o novo filtro à página.

Aplicar filtros com links

Você também pode adicionar filtros selecionando os valores azuis com hiperlink na tabela principal. A regra de filtro é aplicada automaticamente ao campo Filtros. Você pode selecionar apenas um valor ou parâmetro de cada coluna por vez.

Remover um filtro

Para remover um filtro:

- Selecione o ícone de filtro ![ícone de edição](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
- Selecione X ao lado do filtro que você deseja remover.

Indicadores-chave de desempenho

Você pode visualizar os seguintes indicadores-chave de desempenho (KPIs) no painel do Rightsizing:

- Total de despesas : Mostra o total de despesas alocadas atuais.
- Economia ociosa estimada : Mostra a economia total estimada para todas as recomendações de encerramento.
- Economia estimada do Rightsize : Mostra a economia potencial total estimada que pode ser obtida com todas as recomendações do Rightsize.
- Despesas otimizadas estim adas : mostra o total estimado de despesas após a aplicação das recomendações.

Tabela de recomendações de dimensionamento

O painel contém uma tabela de recomendações de dimensionamento, que fornece uma visão geral dos recursos do RDS para os quais foram identificadas recomendações. A tabela inclui as seguintes colunas:

Nota:

Por padrão, os dados são classificados pela coluna Economia de custos. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- ID do cluster : A ID do cluster.
- Nome do recurso : O nome da instância.
- Mecanismo : o mecanismo do banco de dados.
- Função : A função do IAM.
- Nome da conta : O nome da conta AWS.
- Ocioso : Com base no número de conexões/sessões ativas do banco de dados em um determinado momento.
- Custo : O custo total da instância.
- Current : o tipo de instância atual.
- Novo : O tipo de instância mais recomendado.
- Ação : Recomendação para o recurso. A recomendação pode ser uma das seguintes.

| Recomendação | Descrição |
| --- | --- |
| Dimensionamento correto | Redimensione para o tipo de recurso especificado na coluna Novo. |
| Encerrar | Encerre seu recurso porque ele está predominantemente ocioso. |
| Nenhuma ação | Nenhuma ação é recomendada por padrão, mas recomendações adicionais com níveis de risco mais altos podem estar disponíveis no painel Detalhes. |

Economia de custos : O valor estimado de economia de custos em 10 ou 30 dias.

Exportar recomendações para um arquivo Excel

Para exportar as recomendações para um arquivo Excel, selecione Exportar. Observe que o arquivo do Excel incluirá várias colunas adicionais, como região, sistema operacional, preço unitário e outras.

Detalhes da recomendação

Para exibir os detalhes da recomendação de um determinado recurso, selecione View Details (Exibir detalhes ) no menu More Options (Mais opções) (3 pontos).

A figura a seguir mostra um exemplo de painel de detalhes de recomendação.

![AWS RDS detalhes da recomendação captura de tela](../../../../03-media/cloudability-premium/images/rightsizing-aws-rds.jpg)

Para ver as descrições das dimensões e métricas de custo, consulte [Glossário de dimensões e métricas de custo](glossary-of-cost-dimensions-and-metrics.html).

Para ver detalhes sobre a dimensão e as métricas de utilização, consulte [Glossário de dimensões e métricas de utilização](glossary-of-utilization-dimensions-and-metrics.html).

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
