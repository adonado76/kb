---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Usar o componente de avaliação de desempenho"
breadcrumb: []
source_path: "studio/admin/use_the_performance_review.html"
images:
  - "resources/images/ai_images/analyze-performance.png"
  - "resources/images/studio_images/revert-project-setting.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Usar o componente de avaliação de desempenho

Aplica-se a: Apptio TBM Studio 12.5 e posterior. O componente Performance Review é um utilitário no aplicativo que cria relatórios que o administrador do Apptio TBM Studio pode usar para obter informações sobre o impacto da configuração atual do projeto no desempenho do aplicativo. Esse componente está disponível em R12.5 e posteriores e fazia parte do payload de conteúdo v.105.

Este documento fornece uma visão geral dos relatórios que são instalados pelo componente Performance Review.

- Para obter instruções de instalação, consulte [Instalar o componente Performance Review](install-performance-review.html "Aplica-se a: Apptio Cálculo de custos padrão no TBM Studio 12.5 e posterior. O componente Performance Review é um utilitário no aplicativo que cria relatórios que um administrador do Apptio TBM Studio pode usar para obter informações sobre o impacto que a configuração atual do projeto tem sobre o desempenho do aplicativo.")
- Para obter informações mais detalhadas sobre o ajuste de desempenho da configuração, consulte [Melhorando o desempenho em seus projetos R12](https://community.apptio.com/viewdocument/improving-performance-in-your-r12-p "(Abre em uma nova guia ou janela)")

## Atualizar o componente de avaliação de desempenho

Siga estas instruções se o componente de avaliação de desempenho já estiver instalado. Se não estiver, você precisará instalar o componente. Para obter mais informações, visite [Instalar o componente Performance Review](install-performance-review.html "Aplica-se a: Apptio Cálculo de custos padrão no TBM Studio 12.5 e posterior. O componente Performance Review é um utilitário no aplicativo que cria relatórios que um administrador do Apptio TBM Studio pode usar para obter informações sobre o impacto que a configuração atual do projeto tem sobre o desempenho do aplicativo.").

1. Na guia Projeto, no grupo Configuração de projeto, selecione **Configurações de projeto**.
2. Na lista suspensa Versão dos componentes, selecione **a Versão 110** (ou a mais recente) e clique em **Salvar**.
3. Na guia Projeto, no grupo Dados do projeto, selecione **Componentes**. Agora você deve ver o componente Performance Review.
4. Selecione **Performance Review**.
5. Se, nesse momento, você vir mensagens indicando que houve personalizações, será necessário **Revertê-las**. Para reverter, role até a parte inferior da página **Analisar componente de desempenho**. Se houver personalizações presentes, selecione a seta de reversão ao lado da entrada do componente personalizado para reverter. Depois de reverter qualquer personalização de componente, selecione o botão **Upgrade**.
6. Agora, a última análise de desempenho aparece no Project Explorer em **Report > Service Costing > Analyze Performance**.
7. Nesse momento, você pode optar por reverter a alteração na versão dos componentes, para que todos os componentes não sejam mostrados como tendo atualizações. Para fazer isso, reverta as **configurações do projeto** da seguinte forma:
   1. Na guia Início, no grupo Documento, selecione **Reverter alterações**.
   2. Na caixa de diálogo de reversão, selecione apenas **Configurações do projeto** e selecione **Reverter check-out**.

      ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/revert-project-setting.png)

## Navegue até os Relatórios do componente de análise de desempenho

A instalação do componente Performance Review cria um relatório que pode ser acessado em throughApptio TBM Studio. Esse relatório está disponível para usuários com a função ADMIN. Para obter mais informações, consulte Gerenciar permissões e funções de usuários. O relatório está localizado no Project Explorer, em Reports > Service Costing > Analyze Performance.

![Interface gráfica do usuário, texto, aplicativo, e-mail Descrição gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_2_sui.png)

O relatório tem três guias principais:

- Visão geral
- Detalhe do modelo
- Informações sobre o projeto

  ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/ai_images/analyze-performance.png)

As guias Detalhes do modelo e Informações do projeto têm subguias que contêm os relatórios discutidos neste documento.

**Novos recursos em 12.9.3 / Conteúdo v109**

- Oferece suporte à análise de alterações no espaço de trabalho de um usuário.
- Oferece suporte à comparação do espaço de trabalho em relação ao palco.
- Suporte para alterar a métrica que o analisador examina.
- Suporte para identificar problemas de contagem de caminhos.
- Suporte para "exercícios de foco" personalizados.
- Suporte para alterar o limite de linhas pequenas.
- Melhorias na precisão da tabela de linhas pequenas.

## Dicas importantes

Clique no ícone ToolTip ![imagem](../../resources/images/use%20the%20performance%20review%20component/use%20the%20performance%20review_3.png) de uma determinada tabela para obter informações sobre o conteúdo da tabela. Em alguns casos, o conteúdo das guias pode não ser renderizado inicialmente. Se uma tabela não for carregada, clique com o botão direito do mouse e selecione atualizar dados.

## Guia Visão geral

Essa guia contém informações básicas sobre o componente Performance Review e contém links para informações suplementares sobre o desempenho do projeto R12 no site da comunidade TBM Connect.

## Guia Detalhes do modelo

Na guia Detalhes do modelo, você pode observar a métrica do modelo que o relatório está configurado para examinar no momento. Na captura de tela a seguir, o modelo de custo está configurado para análise.

## Modificação do modelo e/ou do objeto inferior

Para examinar um modelo diferente, você pode modificar a tabela Performance Review Config clicando no link do relatório.

![Interface gráfica do usuário, texto, aplicativo, e-mail Descrição gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_4_sui.png)

Para analisar um modelo diferente, você pode editar o valor Metric da tabela Performance Review Config. Você também pode especificar um Objeto inferior diferente para situações como modelos personalizados com um objeto inferior diferente da Fonte de custos. Quando você alterar isso em seu espaço de trabalho, as alterações serão refletidas nos relatórios Analisar desempenho em seu espaço de trabalho.

![imagem](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_5_sui.png)

## Detalhe do modelo: Informações de alocação

Essa guia mostra todos os objetos do modelo que têm relações de alocação e mostra o tamanho das tabelas de relações de alocação para cada alocação. Isso permite a rápida identificação das maiores alocações que podem estar contribuindo para o aumento do tempo de cálculo do modelo. Para ver os maiores relacionamentos, selecione Row Count > Sort Descending (Contagem de linhas > Classificação decrescente).

![Interface gráfica do usuário Descrição gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use%20the%20performance%20review_6.png)

## Detalhe do modelo: Informações sobre a furadeira e o identificador

A guia Drill and Identifier Information contém informações sobre a granularidade da tabela e a eficiência das alocações entre as tabelas. A tabela usa formatação condicional para ajudar a identificar áreas em que os identificadores de objetos e as relações de dados entre tabelas relacionadas podem estar atingindo limites que podem afetar negativamente o desempenho do projeto e os tempos gerais de cálculo.

## Linhas AR

Para visualizar as maiores tabelas de proporções de atribuição de todos os objetos no modelo em relação ao objeto inferior, selecione AR rows > Sort Descending. Selecione o ícone ToolTip ![imagem](../../resources/images/use%20the%20performance%20review%20component/use%20the%20performance%20review_3.png) no relatório para obter mais informações.

![Interface gráfica do usuário, descrição da tabela gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use%20the%20performance%20review_7.png)

## Esparsidade

A coluna "Sparseness" (Esparsidade) pode ser classificada em ordem decrescente para visualizar o quão próximas as tabelas de AR estão do pior caso teórico. O pior caso teórico é uma distribuição uniforme de tudo no objeto inferior para o objeto superior.

![Interface gráfica do usuário, texto, aplicativo, e-mail Descrição gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_8_sui.png)

## Identificador Pontuação de saúde

A coluna "Identifier Health Score" (Pontuação de integridade do identificador) exibe a integridade estimada dos identificadores, medida pela variação do identificador ao longo do ano. As pontuações estão em uma escala de 1 (pior) a 100 (melhor).

Uma maneira de pensar nisso é que, em um mundo ideal, seu identificador de objeto seria o mesmo em todos os períodos de tempo. Portanto, se houver 10 identificadores exclusivos em todos os períodos, haverá 120 no total para o ano ou exatamente uma proporção de 1:12. Se a proporção for maior, isso indica mais variação ao longo do tempo. A grande variação de identificadores significa que o sistema precisa calcular uma tabela maior para informar sobre agregados de tempo (por exemplo, ano até a data ou tendências).

A execução desse relatório pode causar uma carga significativa, dependendo de sua configuração. Esteja atento a isso ao trabalhar com uma configuração suspeita.

![imagem](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_10_sui.png)

## Detalhe do modelo: Granularidade do modelo

Essa guia se concentra na interseção entre a granularidade do objeto do modelo e as unidades alocadas por linha, identificando as áreas do modelo em que as alocações de baixo valor podem estar contribuindo para os longos tempos de cálculo do modelo. No exemplo a seguir, o objeto Storage, que tem uma contagem total de linhas de 71.787 linhas e um valor total de US$ 19.233.756, tem 57.787 linhas, ou 80% de sua contagem total de linhas, representando um total de US$ 3, 115.57. Isso sugere uma oportunidade de otimização das fileiras pequenas.

![Interface gráfica do usuário Descrição gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_11_sui.png)

## Detalhe do modelo: Brocas de foco

Às vezes, a configuração leva a grandes perfurações entre dois objetos que não têm nada a ver com a origem do custo. Se isso acontecer, a tabela Focus Drills pode ser usada para adicionar exercícios personalizados para relacionamentos de dados problemáticos em um modelo. Use isso como um meio de complementar a tabela de informações de broca e identificador para brocas específicas em modelos específicos que precisam de atenção extra. Você não deve usá-la como substituta da tabela Drill and Identifier Information.

Para personalizar a tabela, clique no link Performance Review Focus Drills para navegar até a tabela associada.

Confira e edite a tabela adequadamente para adicionar ou remover brocas personalizadas:

![Interface gráfica do usuário, aplicativo, tabela, Excel Descrição gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_13_sui.png)

Visualizar os resultados no relatório:

![Interface gráfica do usuário, descrição do aplicativo gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_14_sui.png)

Para visualizar a coluna Modelo:

1. Clique com o botão direito do mouse no cabeçalho da tabela.
2. Selecione Show/Hide Columns (Mostrar/Ocultar colunas).
3. Marque a caixa Modelo.
4. Clicar em OK
5. Mova a coluna Modelo, se desejar.

   ![Interface gráfica do usuário, aplicativo, Descrição do Word gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_15_sui.png)

## Detalhe do modelo: Comparação por ambiente

A guia Comparison by Environment (Comparação por ambiente) exibe os tamanhos das tabelas de AR, os tamanhos dos identificadores, as perfurações de pior caso e a dispersão em seu espaço de trabalho em relação à última compilação do Stage. Isso permite que você avalie se o seu espaço de trabalho contém uma configuração que possa ter um efeito negativo no desempenho antes de fazer o check-in da configuração. Filtre as várias colunas "change" usando "!BLANK" e a classificação para visualizar as alterações e sua magnitude. A execução desse relatório pode causar uma carga significativa, dependendo de sua configuração. Esteja atento a isso ao trabalhar com uma configuração suspeita.

![Descrição da tabela gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_16_sui.png)

## Detalhe do modelo: Caminhos do modelo

A guia Caminhos do modelo mede a complexidade do seu modelo. Quando o site Apptio se prepara para calcular os exercícios de apoio aos relatórios, ele primeiro precisa determinar todos os caminhos que as alocações podem tomar. Em alguns casos, o cálculo do caminho do modelo pode se tornar significativo, o que aumenta o tempo de cálculo. Se o valor de "Paths to Bottom" for maior que um milhão, a complexidade do modelo pode estar afetando seus tempos de cálculo. Consulte o seu TAM ou o suporte Apptio para obter orientação sobre como reduzir a contagem de caminhos.

![Descrição da tabela gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_17_sui.png)

## Guia Informações do projeto

A guia Informações sobre o produto contém informações que podem ser difíceis de obter de outra forma.

## Informações sobre o projeto: Informações sobre o relatório

O relatório usa os seguintes campos:

| Campo | Descrição |
| --- | --- |
| ID de relatório | Número de identificação do relatório usado pela plataforma |
| Título | Nome real do relatório  Se o relatório tiver um nome com alias, ele não exibirá o alias nessa coluna. |
| Pré-carga | O relatório configurado para ser pré-calculado. Essa é uma configuração na faixa de opções do relatório |
| Customizado | Essa coluna mostra se um relatório Out of the Box foi modificado por um usuário em TBM Studio |
| Data da última modificação | A data do último salvamento desse relatório na interface do usuário |
| Última modificação por | Este nome de usuário do último editor para salvar este relatório |
| Acesso | Quais funções do site TBM Studio têm acesso a esse relatório  Se esse campo estiver em branco, o relatório poderá ser acessado por todas as funções que tenham acesso ao projeto. |
| Caminho completo | O caminho URL para esse relatório, conforme mostrado na barra de endereços de um navegador da Web |

## Informações sobre o projeto: Tamanho do conjunto de dados

A guia Dataset Sizes (Tamanhos do conjunto de dados) mostra informações sobre todos os conjuntos de dados que fazem parte do projeto:

| Campo | Descrição |
| --- | --- |
| Nome | Essa coluna contém o nome da tabela conforme aparece no TBM Studio Project Explorer. |
| Origem | O nome do arquivo de origem. No caso de o sistema ter gerado o arquivo, você poderá ver Mestre ou Gerado pelo sistema como a origem. |
| Tipo | Essa coluna mostra a fonte do conjunto de dados.  - Mestre - Esse conjunto de dados é um conjunto de dados mestre que é criado pelo sistema pelo conteúdo do aplicativo - Transformar - Esse conjunto de dados é uma transformação de outro conjunto de dados - Dados criados pelo sistema - São dados criados pelo aplicativo, mas que não são um conjunto de dados mestre - Dados de API - Dados carregados por Datalink ou por uma chamada manual de API - Tabela editável - Uma tabela de fontes editáveis - Tabela gerada - Uma tabela de fontes geradas - Upload - Arquivos que são carregados por um usuário por meio da interface do usuário |
| Categoria | O valor no campo Categoria. Isso é definido pelo usuário no upload. |
| Escondido da vista | Tabelas que não serão exibidas no Project Explorer, a menos que sejam explicitamente selecionadas no filtro de campo |
| Escondido da inferência | Essas são tabelas que entraram em TBM Studio R12 a partir de uma atualização da plataforma R11  Essa é uma configuração de legado. |
| Copiar para frente | Uma configuração herdada de projetos que entraram em R12 a partir da atualização da plataforma R11 |
| Estado de personalização | Mostra se uma tabela Out of the Box foi modificada por um usuário por meio da interface do usuário |
| Contagem de linhas | Essa é a contagem de linhas da tabela após o processamento de todas as etapas do Transform Pipeline |

## Informações sobre o projeto: Transformar versões

Essa guia informa quando uma transformação foi versionada.

![imagem](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_19_sui.png)

## Informações sobre o projeto: Tendências de tamanho

Essa guia é útil para visualizar o crescimento do tamanho da linha da tabela ao longo do tempo e isolar os picos que podem estar associados a problemas de desempenho.

![Descrição da tabela gerada automaticamente](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_20_sui.png)
