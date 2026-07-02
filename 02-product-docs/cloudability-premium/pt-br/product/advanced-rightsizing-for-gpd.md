---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "GCP Google Disco persistente (GPD)"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto avançado"
source_path: "product/advanced-rightsizing-for-gpd.html"
images:
  - "images/advanced-rightsizing-for-gpd-details.png"
  - "images/advanced-rightsizing-for-gpd.png"
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Google Disco persistente (GPD)

Você pode usar o painel de controle do Advanced Rightsizing para visualizar as recomendações de otimização de recursos para um disco persistente (GPD) d Google. O painel mostra recomendações de otimização para poupanças e investimentos, alimentadas por um motor de otimização de poupanças e investimentos ( Turbonomic ). Você pode visualizar as recomendações em várias contas do GCP a partir de um único painel.

[Redimensionamento avançado no Cloudability Premium](advanced-rightsizing-powered-by-turbonomic.html)

Antes de começar

Para visualizar o painel do Azure Disk, certifique-se de que você conectou Cloudability às contas corretas do GCP.

Observação: você precisa garantir que todas as credenciais de fornecedores existentes tenham as permissões relevantes exigidas pelo Turbonomic concedidas, sem as quais o mecanismo Turbonomic pode não ser capaz de gerar o conjunto correto de ações. Se você era um cliente Cloudability antes da atualização para Cloudability Premium, ainda precisa renovar todas as credenciais de fornecedor para conceder um conjunto adicional de permissões.

Acesse o painel do Disco do Azure

Para acessar o painel do GPD, abra a página inicial do Cloudability e, no menu de navegação à esquerda, selecione Otimizar > Redimensionamento > Avançado. Na página Rightsizing, selecione a guia “ GCP ” e, em seguida, selecione a subguia “GPD ”.

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-for-gpd.png)

Personalizar o painel

Você pode definir as seguintes opções para personalizar seu painel.

Nota:

Apenas a base de custo sob demanda é suportada para GPD.

A base de custo sob demanda fornece uma comparação direta entre o recurso listado na coluna **Nível** e o recurso recomendado na coluna **Novo nível,** com base exclusivamente no preço sob demanda. Não inclui nenhum impacto potencial dos descontos por uso comprometido.

Selecione a conta

Por padrão, o painel exibe recomendações para todas as contas. Para visualizar recomendações para uma conta específica, selecione o nome da conta no menu suspenso Conta.

Aplicar filtros

Você pode adicionar filtros para incluir ou excluir dados com base em uma ou mais condições.

Adicionar um filtro

Para adicionar um filtro:

1. Selecione Adicionar filtro na barra de ferramentas.
2. No menu Adicionar filtro, escolha uma dimensão.
3. Selecione um operador para fornecer uma condição lógica.
4. Escolha um valor para refinar seu filtro.
5. Selecione Adicionar filtro para aplicar o novo filtro à página.

Aplicar filtros com links

Você também pode adicionar filtros selecionando os valores em azul com hiperlink na tabela principal. A regra de filtro é aplicada automaticamente ao campo Filtros. Você pode selecionar apenas um valor ou parâmetro de cada coluna por vez.

Remover um filtro

Para remover um filtro:

1. Selecione o ícone do filtro ![ícone do filtro](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
2. Selecione o X ao lado do filtro que deseja remover.

Indicadores-chave de desempenho

Você pode visualizar os seguintes Indicadores-chave de desempenho (KPIs) no seu painel do Advanced Rightsizing:

- Despesa total : mostra o total atual de despesas alocadas
- Economia potencial : mostra a economia potencial total estimada que pode ser alcançada para todas as recomendações de otimização com impacto de custo menor do que o custo atual
- Investimentos necessários : mostra o total estimado de investimentos potenciais em todas as recomendações de otimização com impacto de custo superior ao custo atual

Tabela de recomendações de redimensionamento

O painel contém uma tabela de recomendações de redimensionamento, que fornece uma visão geral dos recursos do GPD para os quais foram identificadas recomendações de otimização. A tabela inclui as seguintes colunas:

Nota:

Por padrão, os dados são classificados pela coluna Impacto no custo. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- Status: Status indicando a prontidão para a execução da ação
- Nome do recurso : O nome do recurso GPD
- Nome da conta : O nome da conta
- Não disruptivo: Indicação se a ação apresentada é não disruptiva
- Reversível : Indicação se a ação apresentada é reversível ou não
- Anexo VM : GCE VM, ao qual este GPD está anexado
- Nível : O nível de armazenamento GPD atual
- Tamanho do disco : tamanho atual do disco GPD
- IOPS : IOPS GPD atual
- **Custo** : O custo atual de armazenamento do GPD
- Novo nível : o nível de armazenamento GPD recomendado
- Novo tamanho do disco : tamanho de armazenamento GPD recomendado
- Novos IOPS : Os IOPS GPD recomendados
- Categoria da ação : A categoria da ação recomendada. Os atualmente suportados são “Desempenho” ou “Economia”
- Ação : A ação recomendada. A tabela abaixo lista várias ações suportadas
- Impacto nos custos : Impacto nos custos da implementação desta ação

| Recomendação | Descrição |
| --- | --- |
| Escala | Redimensione para o tipo de recurso especificado na coluna Nova camada. Isso pode ser uma ação de “aumento” ou “redução” com base nas políticas configuradas |
| Excluir | Exclua seu recurso |

Recomendações de otimização de exportação para um arquivo Excel

Para exportar as ações recomendadas para um arquivo Excel, selecione Exportar. Observe que o arquivo Excel incluirá várias colunas adicionais, como região, sistema operacional, preço unitário e outras.

Detalhes da recomendação

Para visualizar os detalhes da ação recomendada para um recurso específico, selecione Exibir detalhes no menu Mais opções (três pontos).

A figura a seguir mostra um exemplo de painel de detalhes de ação.

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-for-gpd-details.png)

**Tópico principal:** [Redimensionamento avançado](../product/advanced-rightsizing-powered-by-turbonomic.html)
