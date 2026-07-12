---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tabelas editáveis: Acomodando a entrada do usuário"
breadcrumb: []
source_path: "studio/data_studio/editabletables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tabelas editáveis: Acomodando a entrada do usuário

**Aplica-se a** : TBM Studio 12.6 e posterior

As tabelas são uma forma útil de apresentar dados e são um elemento comum em relatórios. Há dois tipos de tabelas:

- **Transformar** - Uma tabela de transformação é uma tabela que pode realizar cálculos potencialmente demorados. Essas tabelas passam pelo processo de cálculo do Apptio e podem receber dados de tabelas editáveis. Elas ficam visíveis na seção **Tabelas** do **Project Explorer**.
- **Editável** - As tabelas editáveis permitem que os usuários insiram dados nas tabelas. Uma tabela editável é usada para inserir dados que são mantidos diretamente no banco de dados do projeto Apptio. A tabela é geralmente usada para apoiar a entrada manual de dados para os quais não há outro sistema de origem. Por exemplo, para mapear outros pools de custos para as Torres de Recursos de TI.

  [Saiba mais sobre tabelas editáveis](enter-data-manually.html "Aplica-se a: TBM Studio R12.0 e posterior")

As informações abaixo descrevem tabelas editáveis. Para obter detalhes sobre tabelas de transformação, consulte [Data Studio : adquirir e transformar dados](about-data-transforms.html "Aplica-se a: TBM Studio 12.0 e posterior").

## Copiar e colar dados entre o Excel e as tabelas do aplicativo

Você pode copiar e colar dados entre o Excel e uma tabela editável. Especificamente, você pode:

- Copiar células de uma tabela editável e colá-las no Excel.
- Copie células do Excel e cole-as em uma tabela editável.

O formato das células é ignorado. As células podem ser coladas em qualquer lugar em uma tabela editável.

Observação: Quer você comece no Excel ou em uma tabela em Apptio, as células copiadas devem estar em um intervalo contíguo. Se você tentar copiar células não adjacentes ou um bloco incompleto de células, receberá uma mensagem informando que a seleção não é válida.

## Copiar dados de tabelas para o Excel

Para copiar dados de uma tabela editável para o Excel:

1. Selecione as células desejadas.
2. Copie as células para a área de transferência. Em um PC com Windows, pressione Control+C. Em um Mac, pressione ⌘+C.
3. No Excel, cole as células na pasta de trabalho.

## Copiar células do Excel para uma tabela editável

Para copiar dados do Excel para um conjunto de dados brutos ou para uma tabela editável em um relatório:

1. No Excel, copie as células.
2. Exibir o relatório ou conjunto de dados de destino.
3. Execute uma das seguintes ações:
   - Para colar novas linhas de dados, selecione **Add Row (Adicionar linha** ) e, em seguida, selecione a célula mais à esquerda na nova linha.
   - Para substituir os dados existentes, clique para selecionar a célula superior esquerda no intervalo a ser colado.
4. Cole os dados.

Observação: Não há limite para o número de linhas que podem ser copiadas ou coladas. Se houver muitas pesquisas presentes em um relatório ou se a formatação for aplicada a muitas colunas ao tentar colar mais de 100 registros, poderá ocorrer um erro. Neste caso, é recomendável usar [o upload de arquivo com o recurso de anexação](https://help.apptio.com/en-us/studio/reports/table-report-upload-component.dita "(Abre em uma nova guia ou janela)").

## Exibir propriedades do conjunto de dados

As tabelas editáveis têm propriedades exclusivas que controlam o comportamento de edição de cada coluna. Para editar as propriedades da tabela:

1. Selecione a tabela.
2. Clique na parte das colunas do pipeline.
3. Clique na coluna que você deseja modificar.

   Observação: a coluna **.PK** é uma coluna de chave primária gerada pelo sistema e tem um conjunto diferente de propriedades específicas para ela. Além disso, em uma tabela gerada, muitas propriedades não estão disponíveis para colunas incluídas na tabela base.

A imagem a seguir mostra as propriedades do conjunto de dados exibidas na etapa **Configure Columns (Configurar colunas** ). A guia é exibida quando você seleciona uma tabela editável no **Project Explorer.**

![](../../resources/images/studio_images/studioimages/studio_configure%20columns_benchmark%20sub-tower.png)

## Propriedades da coluna

Esta tabela descreve as propriedades do conjunto de dados na etapa **Configure Columns (Configurar colunas** ).

| Coluna | Descrição |
| --- | --- |
| **Padrão de ID exclusivo** | Essa propriedade existe somente quando se visualiza a coluna **.PK** gerada pelo sistema. A entrada é um padrão numérico com o qual a ID de linha exclusiva será exibida. Um valor de word-0000 fará com que os valores de PK sejam do tipo word-00001 e word-00002. Os padrões numéricos suportam 2 símbolos especiais para representar o número da linha.  - **0** - Um dígito. Use essa opção se quiser que a moeda seja exibida com dígitos, mesmo que seja 0. Portanto, 0000 pode ser usado para exibir sempre 4 dígitos, com zeros à esquerda. - **#** - Um dígito. Se o dígito for zero, ele não será exibido. |
| **Nome** | O nome da coluna. |
| **Descrição** | Insira notas sobre essa coluna e o motivo de sua existência. |
| **Tipo** | Selecione o tipo de dados esperados nas células da coluna. Selecione uma das seguintes opções no menu suspenso:  - **Rótulo** - dados de texto simples - **Date** - dados no formato de data. Ao selecionar essa opção, será exibida uma caixa de diálogo solicitando a entrada do formato de data desejado. Consulte [a função DateFormat](../formulas-and-functions/functions/dateformat.html "Converte uma expressão de data em um formato de data especificado.") para obter uma lista dos formatos permitidos. Observação: a cadeia de formato de data não deve ser colocada entre aspas. - **Numérico** - dados numéricos que suportam entradas numéricas na localidade do projeto |
| **Formato de data** | Ativado somente quando o campo Tipo é selecionado como Data. Uma vez selecionado, você pode alterar o formato atualizando-o para um formato permitido. Consulte [a função DateFormat](../formulas-and-functions/functions/dateformat.html "Converte uma expressão de data em um formato de data especificado.") para obter uma lista dos formatos aplicáveis. |
| **Valores possíveis** | Usado para configurar menus suspensos em uma coluna. Isso pode ser configurado de uma das seguintes maneiras:  - Uma lista de valores delimitada por vírgulas criará uma lista a partir dos valores digitados. - Uma fórmula com a sintaxe %tablename /TableFunction[ ]. - Não há suporte para os caracteres de nova linha "\n".  [Saiba mais sobre as configurações de Valores possíveis.](table-functions.html "Aplica-se a: TBM Studio 12.0 e posterior") |
| **Valores possíveis Contexto** | Fornece contexto para o uso de texto dinâmico em uma fórmula de valores possíveis. Isso permite a configuração de recursos avançados, como dropdowns dependentes. Em caso de dúvida, defina isso como **Linha atual**. |
| **Permitir valores que não estão na lista de valores possíveis** | Se marcada, o usuário poderá digitar um valor que não esteja na lista de valores possíveis e salvar a tabela. Se estiver desmarcada, eles devem escolher um valor no menu suspenso. |
| **Não permitir a edição na célula de valores possíveis** | Se marcada, os usuários não poderão digitar na coluna. A possibilidade de digitar é útil, pois permite filtrar o menu suspenso. |
| **Valor Padrão** | Se especificado, esse valor será inserido automaticamente em todas as novas linhas adicionadas à tabela. |
| **Valor necessário** | Se marcada, o usuário não poderá salvar as edições nessa tabela se uma linha não tiver especificado um valor para essa coluna. |
| **Permitir apenas valores exclusivos** | Se marcada, o usuário não poderá salvar as edições nessa tabela se essa coluna contiver valores duplicados. |

Consulte [Configurar cronograma de atualização de tabela](table-update-schedule.html "Aplica-se a: TBM Studio 12.6 e posterior") para publicar informações de uma tabela editável em uma tabela padrão.

- **[Funções da tabela](../../studio/data_studio/table-functions.html)**  
   **Aplica-se a** : TBM Studio 12.0 e posterior
- **[GRUPO](../../studio/data_studio/groupby.html)**
- **[Limit\_Columns](../../studio/data_studio/limit-columns.html)**  
   Determina as colunas exibidas em uma tabela. Você pode limitar as colunas usando a **faixa de opções**.
- **[SORT](../../studio/data_studio/sort.html)**  
   Classifica uma tabela em uma ou mais colunas especificadas na tabela. Você pode classificar uma tabela usando a faixa de opções. O!A função SORT pode ser aplicada usando uma, duas ou mais colunas em uma tabela.
- **[Configurar a programação de atualização de tabela](../../studio/data_studio/table-update-schedule.html)**  
   **Aplica-se a** : TBM Studio 12.6 e posterior
