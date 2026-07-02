---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Explorador avançado de redimensionamento"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto avançado"
source_path: "product/advanced-rightsizing-explorer.html"
images:
  - "images/advanced-rightsizing-explorer.png"
  - "images/download_button.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Explorador avançado de redimensionamento

## Painel do Explorer

O painel do Rightsizing Explorer permite agrupar, filtrar e navegar por todas as recomendações de otimização avançada, incluindo economias e investimentos, permitindo que você compreenda melhor suas oportunidades e concentre seus esforços para maximizar o desempenho e minimizar o desperdício.

Você pode alternar entre a visualização de poupanças ou investimentos no explorador.

Observação: você precisa garantir que todas as credenciais de fornecedores existentes tenham as permissões relevantes exigidas pelo Turbonomic concedidas, sem as quais o mecanismo Turbonomic pode não ser capaz de gerar o conjunto correto de ações. Se você era um cliente Cloudability antes da atualização para Cloudability Premium, ainda precisa renovar todas as credenciais de fornecedor para conceder um conjunto adicional de permissões.

O Advanced Rightsizing Explorer está em Otimizar > Rightsizing > Avançado > Explorer.

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-explorer.png)

Nota:

Turbonomic As políticas de configuração são aplicadas quando as ações de otimização são geradas. O Rightsizing Explorer trabalha com as ações de otimização após elas serem geradas. Devido ao agrupamento, o Cloudability recomenda que você ajuste seu valor mínimo de poupança para um valor mais baixo se estiver usando o Rightsizing Explorer.

Serviços oferecidos

Os serviços atualmente suportados são:

- AWS: EC2, EBS
- Azure : Computação, Disco
- GCP e: GCE, GPD

Navegue pelo Rightsizing Explorer

A maneira mais eficiente de usar o Advanced Rightsizing Explorer é filtrar primeiro, localizar e, em seguida, focar:

1. Aplique filtros para remover primeiro a maior quantidade de resultados, como Contas, Fornecedores, Serviços. Você pode selecionar nós Sankey para adicionar filtros rapidamente
2. Remova quaisquer dimensões desnecessárias do menu. Adicione dimensões adicionais, uma de cada vez, para aprofundar e descobrir tendências adicionais.
3. Selecione um nó para visualizar as recomendações individuais correspondentes aos atributos do nó.
4. Filtre ainda mais a tabela selecionando valores específicos nas colunas.

Dimensões

As dimensões são utilizadas no diagrama de Sankey para dividir e agrupar suas recomendações de otimização. Quando você adiciona uma dimensão ao diagrama de Sankey, ele cria um conjunto de nós com os valores dessa dimensão. O tamanho do nó corresponde ao valor total das economias ou investimentos resultantes de recomendações individuais com esse valor de dimensão.

Nota:

Apenas a base de custo sob demanda é suportada, pois a maioria dos serviços não oferece métodos de desconto.

As dimensões são definidas através da barra de menus na parte superior do diagrama de Sankey.

- Adicionar: Selecione Editar dimensões e use a caixa de seleção ao lado da dimensão necessária para adicionar. Para obter melhor desempenho, o Cloudability recomenda que você não adicione várias dimensões muito rapidamente, pois isso pode atingir o limite de taxa
- Remover: Selecione Editar dimensões e use a caixa de seleção ao lado da dimensão desejada ou selecione o botão Excluir ao lado da dimensão.
- Reordenar: A ordem das dimensões pode ser alterada no diagrama de Sankey, alterando a ordem no menu. Selecione e mantenha pressionados os pontos ao lado do nome da dimensão e, em seguida, arraste-o para a nova posição.

Saiba mais sobre [o Glossário de dimensões e métricas de custos](glossary-of-cost-dimensions-and-metrics.html)

Saiba mais sobre [o Glossário de dimensões e métricas de utilização](glossary-of-utilization-dimensions-and-metrics.html)

Recomendações **de otimização**

Ver recomendações

Quando você quiser se concentrar em um nó específico e ver as recomendações individuais para essa dimensão:

1. Selecione o nó no diagrama de Sankey
2. Selecione Exibir recomendações

   A tabela de recomendações é exibida abaixo do diagrama de Sankey, listando as recomendações para o nó selecionado.

   Para baixar uma cópia desses dados, selecione ![Ícone de notas](../../../../03-media/cloudability-premium/images/download_button.jpg)

Configure a tabela

- Para ordenar as colunas da tabela conforme necessário, selecione e mantenha pressionado o título da coluna e arraste-o para o local desejado.
- Para classificar os dados com base em uma coluna, selecione o cabeçalho da coluna.

Ver detalhes da recomendação

1. Selecione os três pontos à direita da recomendação
2. Selecione Exibir detalhes

Você pode visualizar os detalhes das recomendações.

## Perguntas frequentes sobre redimensionamento avançado

Com que frequência as recomendações de otimização são atualizadas?

Atualizamos as recomendações de otimização a cada hora. Você pode acessar recomendações para recursos 24 horas após a criação do recurso, desde que haja dados de utilização suficientes.

**Tópico principal:** [Redimensionamento avançado](../product/advanced-rightsizing-powered-by-turbonomic.html)
