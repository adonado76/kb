---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Máquinas virtuais (VMs) da OCI"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/rightsizing-for-oci-vms.html"
images:
  - "images/edit-icon.jpg"
  - "images/oci-vm-dashboard.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Máquinas virtuais (VMs) da OCI

Você pode usar o painel Rightsizing para visualizar as recomendações de otimização de recursos para os recursos de máquinas virtuais ( VM ) da Infraestrutura em Nuvem do Oracle (OCI). O painel mostra as recomendações de rightsizing e de inatividade (encerramento).

[Rightsizing em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Antes de começar

Para visualizar o painel do OCI VM, certifique-se de ter conectado Cloudability às instâncias corretas do OCI. Você precisa validar as credenciais para os contratos de locação pai e filho.

[Conecte-se Oracle Cloud](../admin/connect-oracle-cloud.html)

Acesse o painel do OCI “ VM ”

Para acessar o painel de controle da máquina virtual da OCI, abra a página inicial Cloudability e, no menu de navegação esquerdo, selecione Optimize > Rightsizing. Na página “Rightsizing”, selecione a guia “OCI ” e, em seguida, selecione a subguia “ VM ”.

![Captura de tela do painel do OCI](../../../../03-media/cloudability-premium/images/oci-vm-dashboard.jpg)

Personalizar o painel de controle

Você pode definir as seguintes opções para personalizar seu painel.

Atualmente, todos os custos das VMs são mostrados apenas usando a base de custos sob demanda.

Selecionar conta

Por padrão, o painel mostra recomendações para todas as contas/locações. Para visualizar as recomendações de uma conta específica, selecione o nome da conta no menu suspenso Conta.

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

1. Selecione o ícone de filtro ![Ícone de notas](../../../../03-media/cloudability-premium/images/edit-icon.jpg).
2. Selecione X ao lado do filtro que você deseja remover.

Aplicar opções

Você também pode definir opções em nível de página para incluir ou excluir determinadas recomendações.

Indicadores-chave de desempenho

Você pode visualizar os seguintes indicadores-chave de desempenho (KPIs) no painel do Rightsizing:

- Total de despesas : Mostra o total de despesas alocadas atuais.
- Economia ociosa estimada : Mostra a economia total estimada para todas as recomendações de encerramento.
- Economia estimada do Rightsize : Mostra a economia potencial total estimada que pode ser obtida com todas as recomendações do Rightsize.
- Despesas otimizadas estimadas : Mostra o total estimado de despesas após a aplicação das recomendações.

Tabela de recomendações de dimensionamento

O painel contém uma tabela de recomendações de ajuste de capacidade, que oferece uma visão geral dos seus recursos do VM. A tabela inclui as seguintes colunas:

Nota:

Por padrão, os dados são classificados pela coluna Economia de custos. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- ID do recurso : O ID do recurso VM.
- Nome do recurso : O nome do recurso “ VM ”.
- Nome da conta : O nome da conta do VM.
- Fonte dos dados : A fonte de dados “ VM ”
- Inativo : O tempo gasto abaixo de 2% da CPU em uma escala de 1 a 100.
- Custo : O custo total do recurso “ VM ” para a linha do tempo selecionada.
- Atual : O tipo de recurso atual VM.
- Novidade : O tipo de recurso mais recomendado do VM
- Ação : Recomendação para o recurso. A recomendação pode ser uma das seguintes.

  | Recomendação | Descrição |
  | --- | --- |
  | Tamanho do direito | Redimensione para o tipo de recurso especificado na coluna Novo. |
  | Encerrar | Encerre seu recurso porque ele está predominantemente ocioso. |
  | Nenhuma ação | Nenhuma ação é recomendada por padrão, mas recomendações adicionais com níveis de risco mais altos podem estar disponíveis no painel Detalhes. |
- Economia de custos : O valor estimado da economia de custos em 10 ou 30 dias.

Exportar recomendações para um arquivo Excel

Para exportar as recomendações para um arquivo Excel, selecione Exportar. Observe que o arquivo do Excel incluirá várias colunas e dados adicionais.

Detalhes da recomendação

Para exibir os detalhes da recomendação de um determinado recurso, selecione View Details (Exibir detalhes ) no menu More Options (Mais opções) (3 pontos).

Para ver as descrições das dimensões e métricas de custo, consulte [Glossário de dimensões e métricas de custo](glossary-of-cost-dimensions-and-metrics.html).

Para ver detalhes sobre a dimensão e as métricas de utilização, consulte [Glossário de dimensões e métricas de utilização](glossary-of-utilization-dimensions-and-metrics.html).

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
