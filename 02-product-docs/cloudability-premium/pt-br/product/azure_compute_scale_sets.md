---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Azure Conjuntos de escala de computação"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/azure_compute_scale_sets.html"
images:
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Azure Conjuntos de escala de computação

Você pode usar o painel Rightsizing para visualizar as recomendações de otimização de recursos para uma computação d Microsoft Azure gerenciada por meio de conjuntos de escala. O painel mostra recomendações de redimensionamento e inatividade (encerramento) para conjuntos de escala homogêneos e heterogêneos. Você pode visualizar as recomendações em várias contas a partir de um único painel.

[Reestruturação em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

## Antes de começar

Para visualizar o painel do Azure Compute, certifique-se de ter conectado o Cloudability às contas corretas do Azure.

[Conecte-se Microsoft Azure](../admin/azure-cm-setup.html)

## Acesse o Painel de Compute do Azure

Para acessar o painel do Azure Compute, abra a página inicial do Cloudability e, no menu de navegação à esquerda, **selec** ione Otimizar > Redimensionamento. Na **página** Rightsizing, selecione a **Azure** guia e, em seguida, selecione a subguia **Comp** **ute Scale Sets**.

**Personalizar o painel**

Você pode definir as seguintes opções para personalizar seu painel.

**Especifique a base de custo**

A base de custo determina como as recomendações são calculadas. A base de custo pode ser sob demanda ou efetiva. . A base de custo sob demanda é selecionada por padrão.

**Nota:**

Se sua organização ativou o Preço personalizado em Cloudability, as taxas personalizadas relevantes serão aplicadas aos cálculos da base de custo.

- **Sob demanda** : a base de custo sob demanda fornece uma comparação direta entre a instância listada na coluna Atual e a instância recomendada na coluna Nova, com base exclusivamente no Preço sob demanda. Não inclui nenhum impacto potencial de Instâncias Reservadas (RIs) ou Planos de Economia (SPs). Observe que os preços sob demanda refletirão quaisquer acordos de preços personalizados que você tenha configurado em Cloudability
- **Efetivo** : a base de custo efetivo leva em consideração o impacto histórico das instâncias reservadas (RIs) e dos planos de economia (SPs) para calcular o custo do tipo de instância atual durante o período do relatório. Assim como a métrica Custo (amortizado), ela inclui todos os custos iniciais e recorrentes associados.

  Em outras palavras, a base de custo efetivo mostra o custo efetivo de execução da sua instância atual. Os valores de custo para o novo tipo de instância recomendado são baseados nos preços sob demanda. Isso ocorre porque a nova configuração pode não se beneficiar de RIs ou SPs. Essa comparação é a opção mais conservadora. Mesmo que você inadvertidamente se afaste dos RIs ou SPs, sua nova taxa geral ainda será melhor. Como resultado, a economia total relatada usando essa metodologia às vezes será menor. Preços personalizados serão aplicados a esses valores, se aplicável.

**Nota:**

Use a base de custo sob demanda se você deseja remover a natureza imprevisível dos descontos baseados em compromissos da sua análise e maximizar o número de recomendações fornecidas a você. Use a base de custo efetivo se preferir basear suas recomendações no custo real histórico da execução de suas instâncias e adotar uma abordagem conservadora.

**Selecionar conta**

Por padrão, o painel exibe recomendações para todas as contas. Para visualizar as recomendações para uma conta específica, selecione o nome da conta no menu suspenso Conta.

**Especifique o cronograma**

Você pode optar por revisar os gastos dos últimos 10 dias ou dos últimos 30 dias. Por padrão, a opção Linha do tempo está definida para 10 dias. Para a maioria dos usuários, 10 dias é o período recomendado, pois captura as tendências de desempenho mais recentes e é mais preditivo do uso futuro de recursos.

**Aplicar opções**

Você também pode definir opções no nível da página para incluir ou excluir determinadas recomendações.

**Aplicar filtros**

Você pode adicionar filtros para incluir ou excluir dados com base em uma ou mais condições.

**Adicionar um filtro**

Para adicionar um filtro:

1. Selecione Adicionar filtro na barra de ferramentas.
2. No menu Adicionar filtro, escolha uma Dimensão.
3. Selecione um operador para fornecer uma condição lógica.
4. Escolha um valor para refinar seu filtro.
5. Selecione Adicionar filtro para aplicar o novo filtro à página.

**Aplicar filtros com links**

Você também pode adicionar filtros selecionando os valores em azul com hiperlink na tabela principal. A regra de filtro é aplicada automaticamente ao campo Filtros. Você pode selecionar apenas um valor ou parâmetro de cada coluna por vez.

**Remover um filtro**

Para remover um filtro:

1. Selecione o ícone do filtro![](../../../../03-media/cloudability-premium/images/edit-icon.jpg).
2. **Sel** ecione o X ao lado do filtro que deseja remover.

## Indicadores-chave de desempenho

Você pode visualizar os seguintes Indicadores-chave de desempenho (KPIs) no seu painel Rightsizing:

- **Despesa total** : mostra o total atual de despesas alocadas.
- **Economia estimada em modo inativo** : mostra a economia total estimada para todas as recomendações de encerramento.
- **Economia estimada com o Rightsize** : mostra a economia potencial total estimada que pode ser alcançada com todas as recomendações do Rightsize.
- **Despesa otimizada estimada** : mostra a despesa total estimada após a aplicação das recomendações.

## Tabela de recomendações de redimensionamento

O painel contém uma tabela de recomendações de redimensionamento, que fornece uma visão geral dos recursos de computação para os quais foram identificadas recomendações. A tabela inclui as seguintes colunas:

**Nota:**

Por padrão, os dados são classificados pela coluna “Economia de custos”. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- **Nome do recurso** : O nome do recurso ScaleSet.
- **Nome da conta** : O nome da conta onde os recursos estão sendo executados
- **Grupo de recursos** : O grupo de recursos de computação.
- **Fonte dos dados** : A fonte dos dados utilizada para os dados de utilização relevantes
- **Ocioso** : O tempo gasto abaixo de 2% da CPU em uma escala de 1 a 100.
- **Custo:** o custo total de todas as instâncias em execução no Compute.
- **Atual** : O tipo de instância de computação atual. Para conjuntos de escalas heterogêneos, o valor “Misto” preencherá o campo Atual
- **Novo** : o tipo de instância de computação mais recomendado.
- **Ação** : Recomendação para o recurso. A recomendação pode ser uma das seguintes

|  |  |
| --- | --- |
| **Recomendação** | **Descrição** |
| Dimensionamento correto | Redimensione para o tipo de recurso especificado na coluna Novo. |
| Finalizar | Encerre seu recurso porque ele está predominantemente ocioso. |
| Ajuste automático de escala | Configure o autoescalonamento para o recurso. |
| Sem ação | Por padrão, nenhuma ação é recomendada, mas recomendações adicionais com níveis de risco mais elevados podem estar disponíveis no painel Detalhes. |

Economia de custos: O valor estimado da economia de custos em 10 ou 30 dias.

**Exportar recomendações para um arquivo Excel**

Para exportar as recomendações para um arquivo Excel, selecione Exportar. Observe que o arquivo Excel incluirá várias colunas adicionais, como região, sistema operacional, preço unitário e outras.

**Detalhes da recomendação**

Para visualizar os detalhes da recomendação para um recurso específico, selecione Exibir detalhes no menu Mais opções (três pontos).

Para consultar as descrições das dimensões e métricas de custo, consulte [o Glossário de dimensões e métricas de custo](glossary-of-cost-dimensions-and-metrics.html).

Para visualizar os detalhes da dimensão e das métricas de utilização, consulte [o Glossário de dimensões e métricas de utilização](glossary-of-utilization-dimensions-and-metrics.html).

**Tópico principal:**

[Reestruturação em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
