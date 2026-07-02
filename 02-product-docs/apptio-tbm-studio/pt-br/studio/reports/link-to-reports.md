---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Link para relatórios"
breadcrumb: []
source_path: "studio/reports/link-to-reports.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep254_145x160.png"
  - "resources/images/studio_images/studioimages/reports/rep255.png"
  - "resources/images/studio_images/studioimages/reports/rep256.png"
  - "resources/images/studio_images/studioimages/reports/rep257.png"
  - "resources/images/studio_images/studioimages/reports/rep259.png"
  - "resources/images/studio_images/studioimages/reports/rep260.png"
  - "resources/images/studio_images/studioimages/reports/rep261.png"
  - "resources/images/studio_images/studioimages/reports/rep262.png"
  - "resources/images/studio_images/studioimages/reports/rep264.png"
  - "resources/images/studio_images/studioimages/reports/rep265.png"
  - "resources/images/studio_images/studioimages/reports/rep266.png"
  - "resources/images/studio_images/studioimages/reports/rep268.png"
  - "resources/images/studio_images/studioimages/studio/stu632.png"
  - "resources/images/studio_images/studioimages/studio_reports_options.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Link para relatórios

**Aplica-se a** : TBM Studio 12.1 e posterior

É possível dar aos usuários que visualizam um relatório a opção de selecionar um valor em uma tabela ou selecionar um gráfico inteiro e exibir um relatório relacionado. Cada coluna em uma tabela pode ser vinculada a um relatório diferente. Um gráfico só pode ser vinculado a um único relatório. As propriedades de navegação são mostradas na imagem a seguir. Nas tabelas, os links são exibidos como texto azul.

![Link para relatórios](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu632.png)

Você pode criar links para relatórios em qualquer lugar dentro de um projeto, incluindo relatórios filhos. No entanto, a melhor prática é criar todos os relatórios como relatórios de nível superior.

Observação: Os links de relatório só se aplicam a tabelas baseadas em objetos. Não é possível vincular relatórios a partir de tabelas de transformação.

## Acessar as propriedades de navegação

Para editar as propriedades de navegação:

1. Selecione uma coluna em uma tabela ou selecione um gráfico inteiro.
2. Selecione a guia **Ad Hoc** e clique em **Drill** na seção Navigation (Navegação).

## Descrições de campo

Os campos de navegação estão descritos na tabela abaixo. Você pode selecionar mais de uma das opções do Context Includes.

| Campo | Descrição |
| --- | --- |
| Ativar navegação | Torna os nomes das unidades em uma tabela ou as barras ou fatias em um gráfico ativos como links para navegação. Se a opção não for selecionada, os links não serão ativados para o column.NOTE:. Nos gráficos, a navegação deve ser digitada na coluna de valor, não na coluna de rótulo. |
| Abrir como Modal | Quando selecionado, o relatório de pesquisa será exibido como um pop-up. O usuário pode visualizar o relatório e, em seguida, clicar no botão Fechar para retornar ao relatório original. O relatório de metas deve ser simples. Não inclua filtros complexos ou seletores de colunas. |
| Navegue até: | Selecione o nome de um relatório que será o destino dos links. O relatório pode ser qualquer um dos relatórios do projeto. Além disso, você pode criar um novo relatório clicando em **New Report (Novo relatório** ). A caixa de diálogo **Novo relatório** é exibida, onde você pode definir o novo relatório. |
| Filtro na linha selecionada | Filtra o relatório de destino pelo valor selecionado pelo usuário. As opções determinam qual combinação de linhas é usada para o filtro. Linhas refere-se às entradas na seção **Linhas** (ou seção **Legenda** para gráficos) da caixa de diálogo **Configuração de consulta ad hoc**. Para que essa opção funcione, os dados dos dois relatórios devem ser vinculados por meio do mecanismo de inferência. Se essa opção e as outras opções não forem selecionadas, o relatório de destino exibirá todas as linhas**.Filter on all Rows columns.** Filtra usando os valores em todas as colunas incluídas na seção **Linhas** da caixa de diálogo **Configuração de consulta ad hoc****. Filtrar somente em colunas agrupadas.** Filtra usando os valores em todas as colunas agrupadas incluídas na seção **Linhas** da caixa de diálogo **Configuração de consulta ad hoc****.** Filtra usando apenas a coluna que contém o valor selecionado pelo usuário. |
| Filtro nas seleções de slicer aplicadas | Filtre o relatório de destino pelos valores selecionados nas segmentações. Se essa opção e as outras opções não forem selecionadas, o relatório de destino exibirá todas as linhas. |
| Incluir os filtros do relatório atual | Inclui os filtros definidos na seção **Filtros** da caixa de diálogo **Configuração de consulta ad hoc**. Se essa opção e as outras opções não forem selecionadas, o relatório de destino exibirá todas as linhas. |
| Adicionar coluna atualmente selecionada | Se a coluna selecionada não existir no relatório de destino, ela será adicionada ao relatório de destino. |
| Incluir as colunas adicionadas do relatório atual | Mantém o contexto do relatório atual e o aplica ao relatório de destino. Se o relatório atual incluir colunas adicionadas, as colunas serão adicionadas ao relatório de destino. |

## Exemplos de navegação

Suponha que você tenha as três tabelas a seguir em três relatórios separados:

|  |  |  |
| --- | --- | --- |
| Relatório A | Relatório B  Unidade de negócios FTE | Relatório C |

**Exemplo 1: Selecione um valor na tabela Business Unit Costs no Relatório A e vincule-o ao Relatório B. Exiba todos os valores no Relatório B.**

O resultado pretendido é mostrado abaixo:

|  |  |  |
| --- | --- | --- |
| Relatório A  Custos da unidade de negócios | ---> | Relatório B Relatório FTE da unidade de negócios B |

Para obter esse resultado, selecione a coluna **Unidade de negócios** na tabela **Custos da unidade de negócios** no Relatório A e defina as opções de navegação conforme mostrado abaixo:

![Navegue até Relatórios](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep257.png)

**Exemplo 2: Selecione um valor na tabela Business Unit Costs (Custos da unidade de negócios) no Relatório A e exiba a tabela Business Unit FTEs (FTEs da unidade de negócios) no Relatório B. Exiba somente a linha selecionada.**

O resultado pretendido é mostrado abaixo:

|  |  |  |
| --- | --- | --- |
| Relatório A  Exemplo de custo de unidade de negócios | ---> | Relatório B  Exemplo de FTE de unidade de negócios |

Para obter esse resultado, selecione a coluna **Unidade de negócios** na tabela **Custos da unidade de negócios** no Relatório A e defina as opções de navegação conforme mostrado abaixo:

![Exemplo de navegação](../../resources/images/studio_images/studioimages/studio_link%20to%20reports_example%201.png)

**Exemplo 3: Selecione um valor na coluna Custo da tabela Custos da unidade de negócios no Relatório A e exiba o Relatório B com a coluna Custo adicionada à tabela FTEs da unidade de negócios.**

O resultado pretendido é mostrado abaixo:

| Coluna de custo dos custos da unidade de negócios | Coluna de custo adicionada aos FTEs da unidade de negócios |  |
| --- | --- | --- |
| Relatório A  Valores de custo da unidade de negócios | ---> | Relatório B  Valores de FTE da unidade de negócios |

Para obter esse resultado, selecione a **coluna Cost (Custo** ) na tabela **Business Unit Costs (Custos da unidade de negócios** ) no Relatório A e defina as opções de navegação conforme mostrado na imagem a seguir:

![Exemplo de navegação](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep262.png)

**Exemplo 4: Selecione um valor na coluna Unidade de negócios da tabela Custos da unidade de negócios no Relatório A e exiba o Relatório B com a exibição apenas dos dados da unidade de negócios selecionada. Selecione a unidade de negócios exibida no Relatório B e exiba a tabela Centros de custo da unidade de negócios no Relatório C com todas as unidades de negócios exibidas.**

O resultado pretendido é mostrado nas imagens a seguir:

| Relatório A | ---> | Relatório B | ---> | Relatório C |
| --- | --- | --- | --- | --- |
| Relatório A  Exemplo de BUC | ---> | Relatório B  Exemplo de FTE | ---> | Relatório C |

Para obter esse resultado:

1. Selecione a coluna **Custo** na tabela Custos da **Unidade de Negócios** no Relatório A e defina as opções de navegação conforme mostrado abaixo:

   ![Exemplo de navegação](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_reports_options.png)
2. Selecione a coluna **Business Unit** na tabela **Business Unit FTEs** no Relatório B e defina as opções de navegação conforme mostrado na imagem a seguir:

   ![Exemplo de navegação 1](../../resources/images/studio_images/studioimages/studio_business%20unit%20costs%20table_result.png)
