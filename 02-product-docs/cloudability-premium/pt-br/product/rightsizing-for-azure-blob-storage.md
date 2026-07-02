---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Azure Blob Storage"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/rightsizing-for-azure-blob-storage.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Azure Blob Storage

Você pode usar o painel de controle "Rightsizing" para visualizar recomendações de otimização para o serviço " Azure Blob Storage ". O painel exibe recomendações tanto de ajuste de capacidade quanto de inatividade, e você pode visualizar as recomendações de várias assinaturas a partir de um único painel.

[Reestruturação na Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Azure Blob Storage visão geral

Azure Blob Storage é a solução de armazenamento em objeto d Microsoft Azure, organizada em contêineres. Os contêineres são entidades de nível superior nas contas de armazenamento. Você pode usar contêineres para armazenar blobs associados a uma camada de acesso e organizá-los hierarquicamente em diretórios virtuais.

Contêineres

Em cada contêiner, é possível armazenar um número ilimitado de blobs. Os custos são baseados no nível de acesso do blob, no armazenamento alocado (GB por mês), nas operações (leitura, gravação, listagem), nas operações de recuperação para os níveis Cool, Cold e Archive, nas operações de reidratação para o nível Archive e no volume de transferência de dados (saída).

Níveis de acesso

Os níveis de acesso são projetados para diferentes padrões de acesso e necessidades de durabilidade, abrangendo desde dados acessados com frequência até armazenamento de arquivos acessados com pouca frequência. Os blobs no mesmo contêiner podem ser atribuídos a diferentes níveis de acesso.

Azure Blob Storage Os níveis de acesso diferem em termos de preço, desempenho, disponibilidade e requisitos mínimos de duração de armazenamento. Dependendo do nível de acesso, podem ser cobradas taxas adicionais por operações de recuperação e por exclusão antecipada, quando os blobs forem excluídos, sobrescritos ou movidos antes do cumprimento do prazo mínimo de armazenamento.

Por padrão, os blobs do Azure são criados na camada de acesso Hot. Para otimizar manualmente blobs individuais, é necessário identificar as tarifas regionais para cada camada de acesso, coletar padrões históricos de acesso e dados de operações, e avaliar as vantagens e desvantagens, incluindo taxas de exclusão antecipada.

Antes de começar

Para visualizar o painel do Azure Blob Storage, certifique-se de ter conectado o Cloudability às assinaturas corretas do Azure e de ter as configurações de monitoramento e diagnóstico do Azure definidas.

Nota:

Azure São necessárias configurações de monitoramento e diagnóstico para as recomendações de ajuste de capacidade d Azure Blob Storage. O acompanhamento da "Hora do último acesso" deve ser explicitamente ativado nas contas de armazenamento para que sejam feitas recomendações com base no padrão de acesso. Para obter informações sobre como conectar o Azure ao Cloudability, consulte [a seção “Conectar-se ao Microsoft Azure](../admin/azure-cm-setup.html) ”.

Acesse o painel do Azure Blob Storage

Para acessar o painel do Azure Blob Storage, abra a página inicial Cloudability. No menu de navegação à esquerda, selecione Otimizar > Redimensionamento. Na página "Rightsizing ", selecione a guia " Azure " e, em seguida, selecione a subguia "Blob Storage".

Nota:

Só são exibidos os contêineres com custos incorridos superiores a zero.

Todos os dias, o Cloudability analisa suas métricas de custo, uso e utilização do Azure Blob Storage referentes aos últimos 30 dias. O Rightsizing gera insights e recomendações de otimização no nível do contêiner. O gasto é determinado pelos GB-meses.

Nota:

Os recursos ociosos ou volumes de armazenamento alocados que contêm dados insignificantes ou nenhum dado também são exibidos no painel de Rightsizing.

Personalize o painel

Você pode usar as seguintes opções para personalizar seu painel.

Selecionar assinatura

Por padrão, o painel exibe recomendações para todas as assinaturas. Para ver as recomendações para uma assinatura específica, selecione o nome da assinatura no menu suspenso “Assinatura ”.

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

Você também pode adicionar filtros selecionando os valores com hiperlink azul na tabela principal. A regra de filtragem é aplicada automaticamente ao campo Filtros. Você pode selecionar apenas um valor ou parâmetro de cada coluna por vez.

Remover um filtro

Para remover um filtro: Selecione o X ao lado do filtro que deseja remover.

Tabela de recomendações para o redimensionamento

O painel contém uma tabela de recomendações de ajuste de tamanho, que oferece uma visão geral dos seus recursos do Azure Blob Storage. A tabela inclui as seguintes colunas:

Nota:

Por padrão, os dados são classificados pela coluna Economia de custos. Para alterar a ordem de classificação, basta selecionar o nome da coluna.

- Nome do contêiner : O nome do contêiner do serviço de contêineres ( Azure Blob Storage ).
- Nome da conta de armazenamento : O nome da conta de armazenamento do serviço de armazenamento em nuvem do Microsoft ( Azure ).
- Grupo de recursos : O grupo de recursos Azure que contém a conta de armazenamento.
- Assinatura : O identificador da assinatura do serviço de notificação de eventos ( Azure ).
- Tamanho : O tamanho de todos os blobs dentro do contêiner.
- Blobs : O número de blobs dentro do contêiner.
- Operações : O número de operações (leitura, gravação, listagem) realizadas por meio do portal ou da API.
- Custo : O custo incorrido nos últimos 30 dias com os blobs no contêiner.
- Atual : O nível de acesso derivado para o contêiner. Se 100% dos blobs estiverem no mesmo nível de acesso, esse nível será exibido. Se um contêiner contiver blobs em vários níveis de acesso, será exibido “MIXED ”. Selecione os detalhes para visualizar a distribuição relativa entre esses níveis.
- Novo : O nível de acesso ideal recomendado para todos os blobs dentro do contêiner.
- Ação : A recomendação para o recurso. A recomendação pode ser uma das seguintes:

| Recomendação | Descrição |
| --- | --- |
| Dimensionamento correto | Passe para o nível de acesso especificado na coluna “Novo ”. |
| Sem ação | Por padrão, nenhuma ação é recomendada, mas recomendações adicionais com níveis de risco mais elevados podem estar disponíveis no painel de detalhes. |

Exportar recomendações para um arquivo do Excel

Para exportar as recomendações para um arquivo do Excel, selecione Exportar. O arquivo do Excel inclui colunas adicionais, como região, localização e índice de confiança.

Detalhes da recomendação

Para ver os detalhes das recomendações de um recurso, selecione “Ver detalhes” no menu “Mais opções”.

O painel de detalhes do " Azure Blob Storage " exibe as seguintes informações:

Recomendações

São exibidas uma ou mais recomendações, classificadas por economia de custos e risco (0-5).

- Economia: porcentagem estimada de economia para o período de 30 dias.
- Economia de custos : valor estimado da economia (deduzidas as taxas de cancelamento antecipado).
- Nível de acesso : Nível de acesso recomendado.
- Ação : Ação recomendada.
- Risco : Numa escala de 0 a 5, o número de transições de nível de acesso de acesso frequente para acesso pouco frequente.
- Período de retorno : tempo necessário para recuperar as taxas de cancelamento antecipado (se aplicável).
- Índice de confiança : Nível de confiança da recomendação (0-100%) com base na integridade dos dados e na disponibilidade da data da última consulta.

Gráficos

- Tamanho do armazenamento (GB) : Exibe a quantidade de espaço de armazenamento por nível de acesso. Os valores possíveis incluem os seguintes:
  - Quente
  - Frio
  - Frio
  - Archive
  - Smart Tier
- Operações (Contagem de operações de leitura/gravação): Exibe a contagem de operações de leitura e gravação realizadas no contêiner. Este gráfico fornece informações valiosas sobre a categoria de uso do contêiner, como predominância de leituras, equilíbrio entre leituras e gravações ou orientação para gravações.
- Número de blobs (contagem) : O gráfico mostra o número de blobs no contêiner ao longo do período.
- Dados transferidos (GB) : Volume de tráfego de saída para a Internet (ou dados transferidos entre regiões).
- Volume de recuperação (GB) : Quantidade de dados recuperados dos níveis Cool, Cold ou Archive.
- Eventos de reidratação (contagem) : Número de operações de reidratação no nível de arquivo, por prioridade (Padrão/Alta).
- Exclusão antecipada (GB/mês) : Quantidade de dados excluídos de camadas nas quais há um período mínimo de retenção.

Tomar medidas com base nas recomendações

Níveis de acesso

Para fazer a transição do nível de acesso dos blobs ou configurar a otimização de armazenamento no nível do contêiner, você tem várias opções:

- Gerenciamento do ciclo de vida

  Você pode configurar regras de gerenciamento do ciclo de vida no nível da conta de armazenamento para transferir automaticamente os blobs para o nível de acesso recomendado com base na idade do blob, na data da última modificação ou em outras condições.

  Para obter mais informações sobre gerenciamento do ciclo de vida, consulte [Azure Blob Storage lifecycle management](https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-overview "(Abre em uma nova guia ou janela)").
- Smart Tier

  Ative o Smart Tier nos contêineres para transferir automaticamente os blobs entre as camadas de acesso Hot, Cool e Cold com base nos padrões de acesso, eliminando a necessidade de regras manuais de ciclo de vida.

  Para obter mais informações sobre o Smart Tier, consulte [Azure Blob Storage access tiers](https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview#smart-tiering "(Abre em uma nova guia ou janela)").

Entendendo o Smart Tier

O Smart Tier é um recurso no nível do contêiner que transfere automaticamente os blobs entre camadas de acesso com base nos padrões de acesso. Quando ativado, o Smart Tier monitora os padrões de acesso de cada blob e os transfere automaticamente entre as camadas de acesso Hot, Cool e Cold, mediante uma taxa de monitoramento além das tarifas específicas de cada camada.

O ajuste de tamanho no nível do contêiner ajuda a identificar quais contêineres podem se beneficiar desse recurso. Os novos blobs começam na camada Hot. O Smart Tier transfere-os automaticamente para o nível Cool após 30 dias de inatividade e para o nível Cold após 90 dias de inatividade. O acesso a um blob o move de volta para o nível Hot e reinicia o ciclo.

O Smart Tier não é compatível com o nível de arquivamento. Para dados de arquivamento de longo prazo, utilize a seleção manual de camadas ou políticas de ciclo de vida. Os blobs com menos de 128 KiB permanecem no nível Hot e estão isentos de taxas de monitoramento.

Nota:

O Smart Tier cobra uma taxa de monitoramento de US$ 0.04 por 10.000 blobs por mês para blobs com mais de 128 KiB. Não há taxas de cancelamento antecipado nem de recuperação para transições para o plano Smart Tier. Todas as operações de acesso são cobradas de acordo com os preços da camada Hot.

Para obter mais informações, consulte [“Smart tiering” para o Azure Blob Storage](https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview#smart-tiering "(Abre em uma nova guia ou janela)").

Entendendo as taxas de cancelamento antecipado

Azure Blob Storage cobra taxas de exclusão antecipada quando os blobs são excluídos, sobrescritos ou movidos antes que o período mínimo de armazenamento seja cumprido para os níveis Cool (30 dias), Cold (90 dias) ou Archive (180 dias). Essas taxas são calculadas proporcionalmente com base nos dias restantes do período mínimo de vigência.

Cloudability As recomendações levam em conta as taxas de quitação antecipada ao calcular a economia prevista e os prazos de retorno do investimento. As recomendações que envolvem taxas de rescisão antecipada significativas apresentam um período de retorno, que indica quanto tempo leva para recuperar os custos iniciais por meio de economias contínuas.

Para obter mais informações sobre taxas de cancelamento antecipado, consulte [os níveis de acesso](https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview "(Abre em uma nova guia ou janela)") do Azure Blob Storage.

Acompanhamento da data da última consulta

O monitoramento da "Hora do último acesso" deve ser explicitamente ativado nas contas de armazenament Azure es para fornecer recomendações baseadas em padrões de acesso. Quando a data da última acesso não estiver disponível, o " Cloudability " utiliza a data da última modificação para análises baseadas no tempo, semelhantes às políticas de ciclo de vida; no entanto, as recomendações resultantes são menos precisas.

As recomendações baseadas na data da última modificação apresentam índices de confiança mais baixos (70-89%) do que as recomendações baseadas na data do último acesso (90-100%). Os detalhes da recomendação indicam se o rastreamento da "Última hora de acesso" está ativado.

Para obter mais informações sobre como ativar a opção “Hora do último acesso”, consulte [a seção “Mover dados com base na hora do último acesso](https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-overview#move-data-based-on-last-accessed-time "(Abre em uma nova guia ou janela)") ”.

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
