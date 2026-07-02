---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "GCP Google Cloud Storage (GCS)"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/rightsizing-for-gcp-cloud-storage.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Google Cloud Storage (GCS)

Você pode usar o painel de controle do Rightsizing para visualizar as recomendações de otimização de recursos para o Serviço de Computação em Nuvem do Google ( Google Cloud Storage, GCS). O painel exibe tanto as recomendações de redimensionamento quanto as de desativação (encerramento). Você pode visualizar as recomendações de várias contas a partir de um único painel.

[Reestruturação em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Google Cloud Storage visão geral

Google Cloud Storage (GCS) é um serviço de armazenamento organizado em buckets. Os buckets são contêineres de nível superior. Você pode usar esses buckets para armazenar objetos individuais associados a uma classe de armazenamento e também organizar esses objetos hierarquicamente em pastas.

Baldes

Dentro de cada bucket, você pode armazenar um número ilimitado de objetos individuais. Os custos são calculados com base na tarifa da classe de armazenamento do objeto e no fator que leva em conta o espaço de armazenamento alocado (GB por mês), o número de operações (leitura, gravação, listagem), as operações de recuperação (para Nearline, Coldline e Archive) e o volume de dados transferidos (saída).

Classes de armazenamento

As classes de armazenamento são definidas com base nos padrões de acesso e nas necessidades de durabilidade, variando entre armazenamento frequente e pouco frequente (arquivamento). Apenas um objeto, e não um bucket, está associado a uma classe de armazenamento.

As classes de armazenamento do GCS diferem em termos de preço, desempenho, disponibilidade e requisitos mínimos de duração de armazenamento. Dependendo da classe de armazenamento utilizada, podem ser cobradas taxas adicionais pelas operações de recuperação (acesso a dados das classes Nearline, Coldline ou Archive).

Por padrão, os objetos do GCS são criados na classe de armazenamento Standard. Para otimizar manualmente objetos individuais, é necessário identificar as taxas de cada classe de armazenamento por localização, coletar os padrões de acesso e as operações anteriores e, em seguida, avaliar cada uma das alternativas levando em conta todas as vantagens e desvantagens.

Antes de começar

Para visualizar o painel do GCS, certifique-se de ter conectado o Cloudability às contas corretas do GCP e de ter o Faturamento por Nível de Recurso (RLB) ativado.

Nota:

O faturamento detalhado (também conhecido como faturamento por nível de recurso) é necessário para as recomendações de ajuste de recursos do GCS. Para obter informações sobre como ativar o Faturamento Detalhado na configuração do GCP, consulte [o artigo “Conecte-se” em Google Cloud](../admin/connect-google-cloud.html).

Acesse o painel do Google Cloud Storage

Para acessar o painel do GCS, abra a página inicial do Cloudability e, no menu de navegação à esquerda, selecione Otimizar > Redimensionamento. Na página Rightsizing, selecione a guia GCP e, em seguida, selecione a subguia GCS.

Nota:

Serão exibidos apenas os grupos com custos incorridos superiores a zero.

Todos os dias, o Cloudability analisa suas métricas de custo, consumo e utilização do GCS dos últimos 30 dias. O Rightsizing gera insights detalhados e recomendações de otimização. O gasto é determinado pelos meses GB.

Observação: os recursos ociosos ou volumes de armazenamento alocados que contenham dados insignificantes ou nenhum dado também são exibidos no painel de Rightsizing.

Personalizar o painel

Você pode definir as seguintes opções para personalizar seu painel.

Selecionar conta

Por padrão, o painel exibe recomendações para todas as contas. Para ver as recomendações para uma conta específica, selecione o nome da conta no menu suspenso Conta.

Aplicar filtros

Você pode adicionar filtros para incluir ou excluir dados com base em uma ou mais condições.

Adicionar um filtro

Para adicionar um filtro:

1. Selecione “Adicionar filtro” na barra de ferramentas.
2. No menu “Adicionar filtro ”, selecione uma dimensão.
3. Selecione um operador para definir uma condição lógica.
4. Escolha um valor para refinar seu filtro.
5. Selecione “Adicionar filtro” para aplicar o novo filtro à página.

Aplicar filtros com links

Você também pode adicionar filtros selecionando os valores com hiperlink azul na tabela principal. A regra de filtro é aplicada automaticamente ao campo Filtros. Você pode selecionar apenas um valor ou parâmetro de cada coluna por vez.

Remover um filtro

Para remover um filtro: Selecione o X ao lado do filtro que deseja remover.

Tabela de recomendações para o redimensionamento

O painel contém uma tabela de recomendações de ajuste de recursos, que oferece uma visão geral dos seus recursos do GCS. A tabela inclui as seguintes colunas:

Nota:

Por padrão, os dados são classificados pela coluna Economia de custos. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- Nome do bucket : O nome do bucket do GCS.
- Nome da conta : O nome da conta do GCP.
- Tamanho : O tamanho de todos os objetos contidos no bucket.
- Objetos : O número de objetos dentro do balde.
- Solicitações : O número de solicitações (leitura, gravação, listagem) realizadas por meio do console ou da API.
- Custo : O custo incorrido nos últimos 30 dias com os objetos contidos no bucket.
- Atual : A classe de armazenamento derivada para o bucket. Quando 100% de todos os objetos estiverem na mesma classe de armazenamento, essa classe de armazenamento será exibida. Se um bucket contiver objetos pertencentes a várias classes de armazenamento, será exibido MIXED. Ao clicar nos detalhes, será exibida a distribuição relativa entre essas classes.
- Novo : A classe de armazenamento ideal recomendada para todos os objetos dentro do bucket.
- Ação : Recomendação para o recurso. A recomendação pode ser uma das seguintes

| Recomendação | Descrição |
| --- | --- |
| Dimensionamento correto | Redimensione de acordo com o tipo de recurso especificado na coluna “Novo”. |
| Sem ação | Por padrão, nenhuma ação é recomendada, mas recomendações adicionais com níveis de risco mais elevados podem estar disponíveis no painel Detalhes. |

Exportar recomendações para um arquivo do Excel

Para exportar as recomendações para um arquivo do Excel, selecione Exportar. Observe que o arquivo do Excel incluirá várias colunas adicionais, como região, tipo de localização e outras.

Detalhes da recomendação

Para ver os detalhes da recomendação de um recurso específico, selecione Ver detalhes no menu Mais opções (três pontos).

O painel de detalhes do GCS exibe as seguintes informações:

Recomendações

Mostra uma ou mais recomendações, classificadas por economia de custos e risco (0-5).

- Economia: porcentagem estimada de economia para o período de 10 ou 30 dias.
- Economia de custos : valor estimado da economia.
- Classe de armazenamento : Classe de armazenamento recomendada.
- Ação : Ação recomendada.
- Risco : Em uma escala de 0 a 5, o número de transições de classe de armazenamento de acesso frequente para acesso pouco frequente.

Gráficos

- Tamanho do armazenamento (bytes) : exibe a quantidade de espaço de armazenamento por classe de armazenamento. Os valores possíveis incluem os seguintes:
  - Standard
  - Nearline
  - Coldline
  - Archive
  - Autoclass
- Operações (Contagem de operações de Classe A/Classe B) : Exibe a contagem de operações de Classe A e Classe B realizadas no bucket. Este gráfico fornece informações valiosas sobre a categoria de uso do bucket, como predominância de leituras, equilíbrio entre leituras e gravações ou orientação para gravações.
- Número de objetos (contagem) : O gráfico mostra o número de objetos no bucket ao longo do período.
- Dados transferidos (bytes) : Volume de tráfego de saída para a Internet (ou dados transferidos entre regiões).
- Dados transferidos (bytes) : Quantidade de dados recebidos da Internet (ou dados transferidos entre regiões).
- Exclusão antecipada (bytes/mês) : quantidade de dados excluídos de camadas nas quais existe um período mínimo de retenção.

Tomar medidas com base nas recomendações

Classes de armazenamento

Para alterar a classe de armazenamento dos objetos ou configurar a otimização de armazenamento no nível do bucket, você tem várias opções:

- Gerenciamento do ciclo de vida de objetos

  Você pode configurar regras de gerenciamento do ciclo de vida no nível do bucket para transferir automaticamente os objetos para a classe de armazenamento recomendada com base na idade do objeto, na data de criação ou em outras condições.

  Para obter mais informações sobre o gerenciamento do ciclo de vida de objetos, consulte [https://cloud.google.com/storage/docs/lifecycle](https://cloud.google.com/storage/docs/lifecycle "(Abre em uma nova guia ou janela)").
- Autoclass

  Ative o Autoclass nos buckets para transferir automaticamente os objetos entre classes de armazenamento com base nos padrões de acesso, eliminando a necessidade de regras manuais de ciclo de vida.

  Para obter mais informações sobre o Autoclass, consulte [https://cloud.google.com/storage/docs/autoclass](https://cloud.google.com/storage/docs/autoclass "(Abre em uma nova guia ou janela)").

Entendendo o Autoclass

O Autoclass é um recurso no nível do bucket que transfere automaticamente objetos entre classes de armazenamento com base nos padrões de acesso. Quando ativado, o Autoclass monitora os padrões de acesso de cada objeto e transfere automaticamente os objetos entre as classes de armazenamento Padrão, Nearline, Coldline e Arquivo, mediante uma taxa de monitoramento por objeto, além das tarifas específicas de cada classe de armazenamento.

O ajuste do tamanho dos buckets ajuda a identificar quais buckets se beneficiarão desse recurso. Embora a maioria dos objetos seja criada inicialmente na classe Padrão, à medida que seus buckets do GCS forem sendo otimizados ao longo do tempo, recomendações adicionais de otimização incremental, como Nearline, Coldline ou mesmo Archive, poderão ser sugeridas.

Para obter mais informações, consulte [https://docs.cloud.google.com/storage/docs/autoclass](https://docs.cloud.google.com/storage/docs/autoclass "(Abre em uma nova guia ou janela)").

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
