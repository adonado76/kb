---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "AWS EC2 Grupo de dimensionamento automático (ASG)"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/rightsizing-for-aws-autoscaling-groups.html"
images:
  - "images/edit-icon.jpg"
  - "images/recommendations-aws-autoscaling.jpg"
  - "images/rightsizing-aws-ec2_asg_dashboard.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS EC2 Grupo de dimensionamento automático (ASG)

Você pode usar o painel Rightsizing para visualizar as recomendações de otimização de recursos para Amazon Web Services ( AWS ) Elastic Compute Cloud ( EC2 ) Auto Scaling Groups (ASG). O painel mostra as recomendações de rightsizing e de inatividade (encerramento). Você pode visualizar as recomendações em várias contas a partir de um único painel.

[Rightsizing em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

[Ação de autoescala para redimensionamento](rightsizing-autoscale-action.html)

Antes de começar

Para visualizar o painel ASG do AWS EC2, certifique-se de que os seguintes requisitos sejam atendidos:

Você conectou o site Cloudability às contas AWS corretas.

Você está usando AWS AutoScaling Groups.

A tag aws:autoscaling:groupName está incluída nos arquivos do Relatório de Custo e Uso (CUR) fornecidos a Apptio e os arquivos atualizados foram assimilados.

[Conexão com AWS - Guia de integração do cliente](../admin/aws-credentialing-standard-enterprise-home.html)

Nota:

Atualmente, esse recurso tem a seguinte limitação:

- As recomendações excluem instâncias pontuais. O painel mostra apenas as instâncias sob demanda.

Acesse o painel ASG do AWS EC2

Para acessar o painel ASG do AWS EC2, abra a página inicial do Cloudability e, no menu de navegação à esquerda, selecione Otimizar > Redimensionamento. Na página Rightsizing, selecione a guia AWS e, em seguida, selecione a subguia EC2 ASG.

![aws ec2 asg dashboard captura de tela](../../../../03-media/cloudability-premium/images/rightsizing-aws-ec2_asg_dashboard.jpg)

Personalizar o painel de controle

Você pode definir as seguintes opções para personalizar seu painel.

Especificar a base de custos

A base de custo determina como as recomendações são calculadas. A base de custo pode ser On-Demand ou Effective. A base de custos On-Demand é selecionada por padrão.

Nota:

[Consulte](../chatbot/custom-discounts-enterprise-discount.html) para saber mais.

- Sob demanda: A base de custos sob demanda fornece uma comparação direta entre a instância listada na coluna Atual e a instância recomendada na coluna Nova com base exclusivamente no preço sob demanda. Ele não inclui nenhum impacto potencial de instâncias reservadas (RIs) ou planos de economia (SPs). Observe que os preços sob demanda refletirão quaisquer acordos de preços personalizados que você tenha configurado em Cloudability.
- Efetivo: A base de custo efetiva leva em conta o impacto histórico das instâncias reservadas (RIs) e dos planos de economia (SPs) para calcular o custo do tipo de instância atual durante o período do relatório. Assim como a métrica de custo (amortizado), ela inclui todos os custos iniciais e recorrentes associados.   
   Em outras palavras, a base de custo efetivo mostra o custo efetivo da execução de sua instância atual. Os valores de custo para o tipo de instância New recomendado são baseados nos preços sob demanda. Isso ocorre porque a nova configuração pode não se beneficiar de RIs ou SPs. Essa comparação é a opção mais conservadora. Mesmo que você se afaste inadvertidamente dos RIs ou SPs, sua nova taxa geral ainda será melhor. Como resultado, a economia total relatada usando essa metodologia às vezes será menor. O preço personalizado será aplicado a esses valores, se aplicável.

Use a base de custo On-Demand se estiver procurando remover a natureza imprevisível dos descontos baseados em compromisso de sua análise e maximizar o número de recomendações fornecidas a você. Use a base de custo efetivo se preferir basear suas recomendações no custo real histórico da execução de suas instâncias e adotar uma abordagem conservadora.

Selecionar conta

Por padrão, o painel mostra recomendações para todas as contas. Para visualizar as recomendações de uma conta específica, selecione o nome da conta no menu suspenso Conta.

Especificar o cronograma

Você pode optar por revisar as despesas dos últimos 10 dias ou dos últimos 30 dias. Por padrão, a opção Linha do tempo é definida como 10 dias. Para a maioria dos usuários, 10 dias é o período de tempo recomendado porque captura as tendências de desempenho mais recentes e é mais preditivo do uso futuro de recursos.

Aplicar opções

Você também pode definir opções em nível de página para incluir ou excluir determinadas recomendações.

Aplicar filtros

Você pode adicionar filtros para incluir ou excluir dados com base em uma ou mais condições.

Adicionar um filtro

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

1. Selecione o ícone de filtro ![ícone de edição](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
2. Selecione X ao lado do filtro que você deseja remover.

Indicadores-chave de desempenho

Você pode visualizar os seguintes indicadores-chave de desempenho (KPIs) no painel do Rightsizing:

- Total de despesas : Mostra o total de despesas alocadas atuais.
- Economia ociosa estimada : Mostra a economia total estimada para todas as recomendações de encerramento.
- Economia estimada do Rightsize : Mostra a economia potencial total estimada que pode ser obtida com todas as recomendações do Rightsize.
- Despesas otimizadas estim adas : mostra o total estimado de despesas após a aplicação das recomendações.

Nota:

Para EC2, o gasto é determinado pelo uso da instância.

Tabela de recomendações de dimensionamento

O painel contém uma tabela de recomendações de dimensionamento de direitos, que fornece uma visão geral de todos os seus recursos do EC2 ASG. A tabela inclui as seguintes colunas:

Nota:

Por padrão, os dados são classificados pela coluna Economia de custos. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- ID do recurso: a ID da conta mais o nome do ASG.
- Nome do recurso : O nome do ASG.
- Nome da conta : O nome da conta AWS.
- Fonte de dados : a fonte ou o APM (como o Cloudwatch) que fornece os dados.
- Contagem mínima de instâncias : O número mínimo de instâncias observadas.
- Max Instance Count : O número máximo de instâncias observadas.
- Inativo : O tempo gasto abaixo de 2% da CPU em uma escala de 1 a 100.
- Custo : o custo total de todas as instâncias em execução no ASG.
- Atual : O tipo de instância do ASG. Para ASGs com vários tipos, a coluna mostrará vários.
- Novo : O tipo de instância ASG mais recomendado.
- Ação : Recomendação para o recurso. A recomendação pode ser uma das seguintes.

| Recomendação | Descrição |
| --- | --- |
| Encerrar | Encerre seu recurso porque ele está predominantemente ocioso. |
| Escala automática | Configure o dimensionamento automático para o recurso. |
| Nenhuma ação | Nenhuma ação é recomendada por padrão, mas recomendações adicionais com níveis de risco mais altos podem estar disponíveis no painel Detalhes. |

Economia de custos : O valor estimado de economia de custos em 10 ou 30 dias.

Exportar recomendações para um arquivo Excel

Para exportar as recomendações para um arquivo Excel, selecione Exportar. Observe que o arquivo do Excel incluirá várias colunas adicionais, como região, sistema operacional, preço unitário e outras.

Detalhes da recomendação

Para exibir os detalhes da recomendação de um determinado recurso, selecione View Details (Exibir detalhes ) no menu More Options (Mais opções) (3 pontos).

A figura a seguir mostra um exemplo de painel de detalhes de recomendação.

![captura de tela dos detalhes da recomendação](../../../../03-media/cloudability-premium/images/recommendations-aws-autoscaling.jpg)

Além das informações fornecidas no painel de detalhes EC2, o painel de detalhes ASG mostra as seguintes informações:

Contagem de instâncias: A contagem mínima e máxima de instâncias observadas.

Ação (Autoscale) : quando a ação recomendada para um ASG é Autoscale, a configuração recomendada de contagem mínima e máxima de instâncias é mostrada entre parênteses ao lado do texto. Para obter mais informações sobre como as recomendações de autoescala são utilizadas, consulte [Ação de](rightsizing-autoscale-action.html) autoescala para ajuste de capacidade.

Risco : caracteriza a probabilidade de atingir os limites de capacidade de uma determinada recomendação, com base no aumento de escala para um número maior de instâncias com menor capacidade individual.

Métricas de utilização : as métricas de utilização exibidas para ASGs são baseadas nos seguintes parâmetros:

| Parâmetro | Descrição |
| --- | --- |
| Total da CPU (%) | - CPU Total (linha azul) : a porcentagem normalizada da utilização máxima da CPU na hora indicada, com base na contagem máxima de instâncias para todo o ASG na janela de tempo de 10 ou 30 dias. - Por exemplo, se um ASG contiver 5 instâncias e todas as 5 instâncias utilizarem 100% da CPU, o Total da CPU (%) mostrará 100%. Se uma instância utilizou 100% da CPU, enquanto as outras 4 instâncias utilizaram 0% da CPU, então o Total da CPU (%) mostrará 20%. - Contagem de instâncias (linha vermelha) : o número total de instâncias em execução para esse ASG na hora indicada. - Recomendado (linha tracejada amarela) : a porcentagem normalizada recomendada de alocação de utilização da CPU para todo o ASG na hora indicada. - Contagem de instâncias recomendadas (linha amarela, exibida ao passar o mouse) : o número total de instâncias recomendadas para esse ASG na hora indicada. |
| Total da rede (Bits/s) | - Total da rede (linha azul) : o número total de bits por segundo utilizados com base na contagem máxima de instâncias para todo o ASG na hora indicada. - Contagem de instâncias (linha vermelha) : o número total de instâncias em execução para esse ASG na hora indicada. - Recomendado (linha tracejada amarela) : A alocação de rede recomendada para todo o ASG na hora indicada. - Contagem de instâncias recomendadas (linha amarela, exibida ao passar o mouse) : o número total de instâncias recomendadas para esse ASG na hora indicada. |
| Memória Total (%) | - Total de memória (linha azul) : a porcentagem normalizada da utilização máxima de memória na hora indicada, com base na contagem máxima de instâncias para todo o ASG na janela de tempo de 10 ou 30 dias. - Por exemplo, se um ASG contiver 5 instâncias e todas as 5 instâncias utilizarem 100% da memória, o Total de memória (%) mostrará 100%. Se uma instância utilizou 100% de memória, enquanto as outras quatro instâncias utilizaram 0% de memória, o Total de memória (%) mostrará 20%. - Contagem de instâncias (linha vermelha) : o número total de instâncias em execução para esse ASG na hora indicada. - Recomendado (linha tracejada amarela) : a porcentagem normalizada recomendada de alocação de utilização de memória para todo o ASG na hora indicada. - Contagem de instâncias recomendadas (linha amarela, exibida ao passar o mouse) : o número total de instâncias recomendadas para esse ASG na hora indicada. |
| GPU Total (%) | - Total da GPU (%): É tratado da mesma maneira que o Total da CPU (%). |
| Total de memória da GPU (%) | - Total de memória da GPU (%): Isso é tratado da mesma maneira que o Total de memória da CPU (%) |

Nota:

As métricas de disco não são usadas para recomendações de dimensionamento automático.

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
