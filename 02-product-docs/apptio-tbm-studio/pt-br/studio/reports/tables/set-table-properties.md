---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Definir propriedades da tabela"
breadcrumb: []
source_path: "studio/reports/tables/set-table-properties.html"
images:
  - "resources/images/studio_images/properties.png"
  - "resources/images/studio_images/studioimages/icons/edit_21x21_icon.png"
  - "resources/images/studio_images/studioimages/icons/hydration_warning_15x15icon.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Definir propriedades da tabela

**Aplica-se a** : TBM Studio 12.0 e posterior

Há uma grande variedade de propriedades disponíveis para tabelas que controlam a aparência de uma tabela. Muitas das propriedades estão disponíveis na faixa de opções. Outros estão disponíveis na caixa de diálogo **Propriedades da tabela**.

Consulte também [Como fazer: criar uma tabela gerada](https://community.apptio.com/docs/DOC-8377 "(Abre em uma nova guia ou janela)")

## Abra a caixa de diálogo Propriedades

Clique com o botão direito do mouse na barra Total da tabela e selecione **Propriedades**.

A caixa de diálogo Propriedades é exibida.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/properties.png)

A caixa de diálogo Properties organiza as propriedades da tabela nas seguintes guias:

- Dados
- Geral
- Avançado

Para visualizar as alterações, selecione **Apply (Aplicar** ). Para salvar as alterações, selecione **OK**.

Observação: algumas tabelas terão um subconjunto desses campos. Os campos marcados com um asterisco ( \* ) aplicam-se somente a tabelas herdadas.

## Propriedades de dados

| **Campo** | **Descrição** |
| --- | --- |
| **Linhas máximas** | Especifica o tamanho da página para a tabela de paginação. Por exemplo, se você definir **Maximum Rows** como 20 para uma tabela com 15 linhas, não haverá barra de paginação, apenas uma barra de rolagem. |
| **Ocultar barra de paginação** | Oculta a barra de paginação para tabelas de várias páginas. Se estiver oculto, somente o número de linhas designado no campo **Maximum Rows (Linhas máximas** ) será exibido. O usuário não pode exibir linhas adicionais. Use essa opção quando quiser que apenas um número x de linhas seja exibido em uma tabela. Por exemplo, os 10 roteadores mais usados. |
| **Incluir colunas** | Abra a lista suspensa e selecione as colunas a serem incluídas na tabela. Ao usar esse recurso, você deve selecionar todas as colunas que deseja exibir na tabela, inclusive as colunas exibidas no momento. |
| **Excluir colunas** | Abra a lista suspensa e selecione as colunas a serem excluídas da tabela. |
| **Filtro de pesquisa automática** | Essa opção adiciona campos de pesquisa abaixo de cada cabeçalho de coluna, conforme mostrado abaixo. Você pode digitar o texto da pesquisa nos campos.    Quando você insere texto em um campo, a tabela exibe apenas as linhas que contêm o texto. O filtro não diferencia maiúsculas de minúsculas. Para colunas numéricas, você pode usar os operadores padrão: <, <=, >, >=. Para colunas de rótulos, "=" é compatível com correspondências exatas com distinção entre maiúsculas e minúsculas. Por exemplo, =Billing incluirá Billing, mas excluirá Billing Extract. |
| **Mostrar linhas para as quais todos os valores métricos são 0\*** | Por padrão, se uma linha da tabela tiver zeros em todas as colunas métricas, a linha não será exibida. Você pode exibir a linha marcando essa opção. |
| **Coluna para redimensionar** | Permite que você ajuste automaticamente as colunas da tabela selecionada para que se ajustem ao espaço disponível no relatório.  Digite os nomes das colunas separados por vírgula, por exemplo, Nome do projeto, ID do fornecedor. |

## Propriedades gerais

| **Campo** | **Descrição** |
| --- | --- |
| **Nome** | Digite um nome a ser exibido no cabeçalho da tabela acima do componente. O nome é exibido quando a opção **Mostrar cabeçalho** é selecionada. |
| **Legenda** | Insira informações adicionais sobre a tabela. As informações são exibidas com base na configuração do campo **Caption Position (Posição da legenda** ). Você pode usar código HTML no campo, mas o código HTML não pode incluir links. A restrição do código HTML é por motivos de segurança. |
| **Posição da legenda** | Na lista, selecione uma posição de legenda em relação à tabela: **Superior**, **Inferior**, **Esquerda** ou **Direita**. Para ocultar a legenda, selecione **Hide (Ocultar** ). |
| **Mostrar cabeçalho** | O cabeçalho do componente exibe o conteúdo do campo **Nome**. Selecione essa opção para tornar o cabeçalho da tabela visível. No modo Editar, é possível exibir um cabeçalho oculto ao pausar o ponteiro do mouse sobre a tabela. |
| **Mostrar borda** | Selecione essa opção para exibir uma borda ao redor da tabela. No modo Editar, você pode exibir uma borda oculta ao pausar o cursor sobre a tabela. |
| **Título da embalagem** | Envolve o texto inserido no campo **Name (Nome** ) para acomodar a largura da tabela. |

## Propriedades avançadas

| **Campo** | **Descrição** |
| --- | --- |
| **Dados URL \*** | Exibe o caminho para a tabela que fornece os dados para esse relatório. Você pode inserir uma função de tabela nesse campo clicando no ícone **Editar caminho de dados**  à direita do campo. O aplicativo exibe a caixa de diálogo **Editar caminho**. **Aviso** : não edite o caminho se você não estiver totalmente familiarizado com caminhos de dados. |
| **Atualização automática quando os cálculos são concluídos** | Quando o aplicativo exibe uma tabela, ele a exibe com os dados calculados que estão disponíveis no momento. Em muitos casos, o aplicativo pode estar calculando novos valores em segundo plano. Se você quiser que os resultados sejam exibidos quando os cálculos forem concluídos, marque essa opção. A opção se aplica somente à tabela selecionada no momento.  A opção é relevante somente quando a **Política de cálculo** (na caixa de diálogo **Cálculo do projeto** ) de um projeto está definida como **Publicação dinâmica**. |
| **Ativar/desativar o upload** | Ativa o botão **Upload** para uma tabela editável. |
| **Anexar dados após o upload** | Os administradores usam essa opção para definir o comportamento de upload da tabela como "anexar" ou "substituir". |
| **Suprimir a solicitação de dados inicial** | Suprime os dados do relatório pela primeira vez. |
| **Adicionar coluna de caixa de seleção** | Ativa a coluna da caixa de seleção nas tabelas editáveis. |
| **Edições datadas** | Essa opção permite o transporte de valores. Ao ativar, qualquer modificação feita em uma coluna numérica será transferida para todas as colunas numéricas subsequentes à sua direita. |
| **Permitir excluir todas as linhas** | Ativa o botão **Excluir todas as linhas** de uma tabela editável. |
| **Período de tempo dos dados** | Determina os dados exibidos na tabela. A opção padrão, **Data atual do projeto**, exibe dados para o período de tempo selecionado no momento.  **Start of Current Project (Início do projeto atual** ) garante que os dados sejam inseridos no mês de início do projeto.  Se você selecionar uma opção diferente de **Data atual do projeto**, o aplicativo exibirá um pequeno ícone de cadeado no canto inferior direito da tabela. O ícone indica que os dados inseridos em uma tabela serão aplicados ao período de tempo selecionado. |
| **Ocultar aviso de bloqueio de tempo** | Se você tiver definido o campo **Período de tempo dos dados** como um valor diferente de **Hora atual do projeto**, um ícone de cadeado será exibido no canto inferior direito da tabela. Marcar essa opção oculta o ícone. |
| **Ocultar aviso de hidratação** | No modo Editar, se você colocar um componente em um relatório de objeto que seja baseado em uma unidade diferente do próprio relatório, o aplicativo exibirá um ícone de aviso  e uma mensagem de texto no canto inferior direito do componente. Eles não são exibidos no modo Exibir. Se você selecionar essa opção, os avisos não serão exibidos no modo Editar.  Por exemplo, suponha que você tenha um objeto Business Units e faça uma pesquisa em um relatório Business Unit A com um gráfico e uma tabela que exibem dados sobre a Business Unit A. No mesmo relatório, você deseja exibir informações sobre a Business Unit B para fins de comparação. Você adiciona uma tabela ao relatório para exibir as informações. Como você fez isso intencionalmente, não deseja que o aplicativo exiba o aviso de hidratação, portanto, selecione a opção **Hide Hydration Warning (Ocultar aviso de hidratação** ). |
| **Reduzir automaticamente os nomes de novas colunas pontilhadas** | Exibe apenas a parte de um nome de coluna que segue o "." ponto. Por exemplo, se o nome da coluna for Data Center Costs.Data Center Hosting Cost, o nome será exibido como Data Center Hosting Cost. |
| **Linhas por linha** | Define o número de linhas para cada linha da tabela. O padrão é zero, o que permite que o conteúdo da célula seja envolvido. Se você inserir um valor nesse campo, todas as linhas da tabela serão exibidas com esse número de linhas. O texto que não cabe na célula é truncado. |
| **Máximo. Colunas a serem exibidas** | Limita o número de colunas que podem ser exibidas em uma tabela. Observe que uma tabela com muitas colunas pode afetar o desempenho. |
| **Incluir coluna PK** | Incluirá a coluna padrão no gráfico/tabela, independentemente de ela estar ou não especificada na lista normal de "colunas a serem incluídas". Em tabelas não agrupadas, esse é normalmente o identificador do objeto que faz o backup do componente do relatório. Para tabelas agrupadas, normalmente é a coluna usada para o agrupamento. |
| **Linha dinâmica Col** | A coluna na tabela de origem que fornece os valores para a primeira coluna na tabela dinâmica. |
| **Pivô Col Col** | A coluna na tabela de origem que fornece os cabeçalhos para as colunas de dados na tabela dinâmica. |
| **Pivô Val Col** | A coluna na tabela de origem que fornece os valores para as células na tabela dinâmica. |
| **Usar aliases de coluna** | Se você tiver dois objetos com as mesmas colunas exibidas na mesma tabela, como Consumer.Master Table.L0 Name e Provider.Master Table.L0 Name, marcar essa opção permite configurar corretamente as colunas na tabela. **Recomendação** : deixe essa opção selecionada. |
