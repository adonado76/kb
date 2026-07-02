---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Explorador de redimensionamento"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/rightsizing-explorer.html"
images:
  - "images/download_button.jpg"
  - "images/rightsizing-explorer-with-effective-cost.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Explorador de redimensionamento

O painel do Rightsizing Explorer permite agrupar, filtrar e navegar por todas as suas recomendações de rightsizing, possibilitando que você entenda melhor suas oportunidades e concentre seus esforços para maximizar os retornos.

O Rightsizing Explorer está em Otimizar > Rightsizing > Explorer e é a página padrão para Rightsizing.

![](../../../../03-media/cloudability-premium/images/rightsizing-explorer-with-effective-cost.jpg)

Nota:

As preferências de rightsizing são aplicadas quando as recomendações são geradas. O Rightsizing Explorer trabalha com as recomendações depois que elas são geradas. Devido ao agrupamento, Cloudability recomenda que você ajuste o valor mínimo de economia para uma configuração mais baixa se estiver usando o Rightsizing Explorer.

Serviços oferecidos

Os serviços suportados atualmente são:

- AWS : EC2, EBS, S3, RDS, Lambda

  Nota:Cloudability geram apenas recomendações de 30 dias para AWS S3. Quando um período 10day é selecionado no Rightsizing Explorer, são exibidas recomendações de 30 dias para S3.
- Azure : Computação, disco, SQL
- GCP e: GCE, GPD
- OCI: VM

Navegue pelo Rightsizing Explorer

A maneira mais eficiente de usar o Rightsizing Explorer é filtrar primeiro, localizar e depois focar:

1. Aplique filtros para remover primeiro a maior quantidade de resultados, como Contas, Fornecedores, Serviços. Você pode selecionar nós Sankey para adicionar filtros rapidamente
2. Remova todas as dimensões desnecessárias do menu. Acrescente dimensões adicionais, uma de cada vez, para se aprofundar e descobrir outras tendências.
3. Selecione um nó para visualizar as recomendações individuais que correspondem aos atributos do nó.
4. Filtre ainda mais a tabela selecionando valores específicos nas colunas.

Dimensões

As dimensões são usadas no diagrama Sankey para dividir e agrupar suas recomendações de dimensionamento. Quando você adiciona uma dimensão ao diagrama Sankey, ele cria um conjunto de nós com os valores dessa dimensão. O tamanho do nó corresponde à quantidade total de economia de recomendações individuais com esse valor de dimensões.

As dimensões são definidas por meio da barra de menus na parte superior do diagrama Sankey.

- Adicionar: selecione Editar dimensões e use a caixa de seleção ao lado da dimensão necessária para adicionar. Para fins de desempenho, o site Cloudability recomenda que você não adicione várias dimensões muito rapidamente, pois poderá atingir a limitação de taxa.
- Remover: Selecione Editar dimensões e use a caixa de seleção ao lado da dimensão necessária ou selecione o botão excluir ao lado da dimensão.
- Reordenar: A ordem das dimensões pode ser alterada no diagrama Sankey, alterando a ordem no menu. Selecione e mantenha pressionados os pontos próximos ao nome da dimensão e, em seguida, arraste-os para a nova posição.

Saiba mais sobre o [Glossário de dimensões e métricas de custo](glossary-of-cost-dimensions-and-metrics.html)

Saiba mais

[Glossário de dimensões e métricas de utilização](glossary-of-utilization-dimensions-and-metrics.html)

Recomendações

Ver recomendações

Quando você quiser se concentrar em um nó específico e ver as recomendações individuais para essa dimensão:

1. Selecione o nó no diagrama Sankey.
2. Selecione Exibir recomendações.

   A tabela de recomendações é mostrada abaixo do diagrama Sankey, listando as recomendações para o nó que você selecionou.

   Para baixar uma cópia desses dados, selecione ![Ícone de notas](../../../../03-media/cloudability-premium/images/download_button.jpg) .

Configure a tabela

- Para ordenar as colunas na tabela conforme necessário, selecione e mantenha pressionado o título da coluna e arraste-o para o local desejado.
- Para classificar os dados com base em uma coluna, selecione o cabeçalho da coluna.

Ver detalhes da recomendação

1. Selecione os três pontos à direita da recomendação
2. Selecione Abrir detalhes ou Criar tíquete.

Você pode visualizar os detalhes das recomendações e criar tíquetes para executá-las.

Caso de uso

Um cliente que usa muitas instâncias do Windows tem um grande número de recomendações de dimensionamento de disco. Todas elas são pequenas economias e não faria sentido fazer o rightsize de nenhuma delas individualmente. O agrupamento dos resultados por tamanho de disco revela que todos eles têm exatamente 100 gigabytes, que é o volume de inicialização padrão. O cliente faz uma alteração em sua imagem de inicialização e recebe os benefícios ao longo do tempo. Ao alterar o modelo padrão para um tamanho menor, todos os ambientes recém-construídos não têm recomendações.

Perguntas frequentes sobre redimensionamento

Por que as instâncias spot são excluídas das recomendações de dimensionamento adequado?

Nosso mecanismo de rightsizing leva em conta sua carga de trabalho (métricas de utilização) e o custo para executá-la (tipo de instância atual e preço sob demanda) e gera uma lista de recomendações que você pode escolher para ajudá-lo a economizar dinheiro. As instâncias spot, por outro lado, já são oferecidas com grandes descontos; aplicar o rightsizing nessas situações resulta em uma economia insignificante. Por esse motivo, optamos por excluir as Instâncias Spot do rightsizing.

Com que frequência as recomendações são atualizadas?

Atualizamos diariamente nossas recomendações de dimensionamento de direitos. Você pode acessar as recomendações de recursos 24 horas após a criação do recurso, desde que haja dados de utilização suficientes.

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
