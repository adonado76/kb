---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "CopyEditableTable função"
breadcrumb: []
source_path: "studio/apptioscript/copyeditabletable_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CopyEditableTable função

Use a função CopyEditableTable para copiar tabelas editáveis (tabelas editáveis de relatórios ou conjuntos de dados brutos) em um projeto ou para um projeto diferente na mesma instância. Essa capacidade de copiar tabelas de transformação para projetos diferentes pode ser muito útil em uma solução de vários projetos, evitando a necessidade de soluções alternativas, como exportar e fazer novo upload.

## Sintaxe

```
CopyEditableTable(path, project, editableTableName , mode, autoCheckIn)
```

Observação: autoCheckIn é um parâmetro opcional, com o valor padrão "false"

## caminho

O caminho totalmente qualificado para a tabela de origem a ser copiada. A tabela de origem pode ser uma tabela de relatório ou um conjunto de dados brutos.

```
tests.apptio.net:UIT_BankDemoLite/Data/January:FY2015/Business+Units+Info
```

A sintaxe desse exemplo é domainname:projectname/Data/timeplaceholder/transform table name

Dica: A data no caminho não pode incluir .DateGoesHere

## Tabela de relatórios

Uma tabela de relatório é qualquer tabela que possa ser visualizada em Apptio (basicamente qualquer coisa que tenha um caminho de dados). Para usá-la como tabela de origem em CopyEditableTable,, tudo o que você precisa é o caminho de dados completo. Esses caminhos são usados para extrair informações parciais ou condicionais de uma tabela.

Para obter o caminho de dados completo:

1. Clique com o botão direito do mouse na tabela e selecione Show Full Data Path (Mostrar caminho completo dos dados).
2. Copie e cole em um editor de texto.
3. Remova as quebras de linha para que o caminho fique contíguo.

Exemplo:

```
Customer.com:Project A/Data/.DateGoesHere/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
```

A parte “.DateGoesHere” do caminho do relatório não funcionará com CopyTable,, portanto, você precisará editá-la.

- Se estiver copiando de um projeto não habilitado para tempo, substitua .DateGoesHere por Eon:FY2000

  Exemplo - Não ativado por tempo:

  ```
  Customer.com:Project A/Data/Eon:FY2000/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
  ```
- Se estiver copiando de um projeto habilitado para tempo e quiser copiar de um único período de tempo estático, substitua .DateGoesHere por Month:Year (por exemplo, January:FY2011 )

  Exemplo - Hora codificada:

  ```
  Customer.com:Project A/Data/January:2011/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
  ```
- Se estiver copiando de um projeto com tempo ativado e quiser copiar do período de tempo selecionado na parte superior da página em Apptio, substitua .DateGoesHere por /<%=CurrentDate("MMMM:yyyy" )%>/

  Exemplo - Hora codificada

  ```
  Customer.com:Project A/Data/<%=CurrentDate("MMMM:yyyy")%>/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
  ```

## Conjunto de dados brutos

Um conjunto de dados brutos é considerado um dado carregado, não transformado, que não está em uma tabela de relatório. A maneira mais fácil de obter o caminho para um conjunto de dados brutos é clicar no ícone URL no painel de visualização da tabela na guia Data (Dados).

## projeto

O projeto de destino deve ser fornecido no formato "Domain Name: Nome do projeto".

O domínio e o projeto do projeto para o qual copiar, na forma de domínio:projeto

Exemplo:

`customer.com:Project B`

Dica: As tabelas podem ser copiadas dentro do mesmo projeto. Nesse caso, basta inserir o mesmo projeto no parâmetro editableTableName.

Lembre-se de que, ao copiar entre dois projetos, eles devem residir na mesma instância. Tenha muito cuidado ao digitar o domínio e o projeto. Se você digitar errado (e, portanto, o domínio ou o projeto não corresponder aos existentes), serão criados novos.

## editableTableName

O nome da tabela para a qual copiar no projeto

editableTableName é o conjunto de dados para o qual você está copiando a tabela editável. O formato deve ser fornecido simplesmente como o nome do conjunto de dados.

Se sua intenção for copiar para um conjunto de dados existente, basta digitar o nome do conjunto de dados (diferencia maiúsculas de minúsculas).

Exemplo:

`Example Data Set`

Se quiser copiar para um novo conjunto de dados, digite o nome de um conjunto de dados que ainda não exista, e ele será criado após a execução de CopyEditableTable.

Dica: se a sua intenção for copiar para um conjunto de dados existente e você digitar incorretamente, criará inadvertidamente um novo conjunto de dados e copiará para ele, em vez do conjunto existente pretendido.

## modo

O método para carregar dados na tabela editável, com os valores como anexar ou sobrescrever.

**Exemplo**

```
CopyEditableTable( "tests.apptio.net:UIT_BankDemoLite/Reports/January:FY2015/CostModels/Default/.TableTransform:Business Units Info/!GROUPBY[{Business Unit}]/.Summary/!SORT[{Business Unit}|asc]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[{Business Unit},{FTEs}][][][orderByIncludeList]/", "tests.apptio.net:UIT_BankDemoLite", "MyTable69", "append", autocheckin = "true")
```

```
CopyEditableTable( "tests.apptio.net:UIT_BankDemoLite/Reports/January:FY2015/CostModels/Default/.TableTransform:Business Units Info/!GROUPBY[{Business Unit}]/.Summary/!SORT[{Business Unit}|asc]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[{Business Unit},{FTEs}][][][orderByIncludeList]/", "tests.apptio.net:UIT_BankDemoLite", "MyTable69", overwrite", autocheckin = "false")
```

## Diretrizes

Ao copiar entre projetos, os dois projetos devem residir na mesma instância ( URL ). Supondo que estejam no mesmo endereço URL, as tabelas editáveis podem ser copiadas entre projetos ou domínios.

| Projetos | Diretrizes |
| --- | --- |
| Mesma instância, mesmo domínio | O Projeto A e o Projeto B estão no mesmo URL ( customer.apptio.com ) e no mesmo domínio ( customer.com ). Isso pode ser obtido com CopyEditableTable. |
| Mesma instância, domínios diferentes | O Projeto A e o Projeto B estão no mesmo URL ( customer.apptio.com ), mas em dois domínios diferentes ( customer.com e test.com ). Isso pode ser obtido com CopyEditableTable. |
| Instância diferente | O Projeto A e o Projeto B estão em dois URL diferentes ( customer-dev.apptio.com e customer-stg.apptio.com ). Eles têm o mesmo domínio ( customer.com ). Isso não pode ser obtido com o site CopyEditableTable. |

É possível enviar para vários destinos simultaneamente a partir de um único botão de origem. Para fazer isso, configure o botão com várias ocorrências de CopyEditableTable( ), separadas por;.

Em várias partes da sintaxe do site CopyTable, talvez seja necessário inserir um formato de Período de tempo (por exemplo, ao designar o período de tempo de destino).

O formato do período de tempo deve ser sempre o seguinte: Mês:Ano

Exemplo:

`January:FY2011`

Observe que deve ser a palavra completa do mês, não uma abreviação (ou seja, "janeiro" em vez de "jan" ou "01").

Usando a sintaxe de formato de data em Apptio, isso pode ser expresso como "MMMM:FYyyyy"

Dica:

Os seguintes caracteres, frequentemente usados no!FILTRO e!As funções NEWCOLUMN exigem escape ou a codificação URL :

"

/

+

?

## Configuração de botões

Para iniciar o CopyEditableTable,, você pode colocar a sintaxe acima em um botão na superfície do relatório.

Para configurar um botão para usar CopyEditableTable:

1. Mudar para o modo de edição.
2. Clique com o botão direito do mouse no botão e selecione Propriedades.
3. Selecione a guia Ações.
4. No campo Server Action (Ação do servidor), digite a sintaxe CopyEditableTable.
5. Clique em OK.

Quando clicado, o botão iniciará o CopyEditableTable conforme definido pelos parâmetros em sua sintaxe.

## Exemplo

```
CopyEditableTable( "tests.apptio.net:UIT_BankDemoLite/Reports/January:FY2015/CostModels/Default/.TableTransform:Business Units Info/!GROUPBY[{Business Unit}]/.Summary/!SORT[{Business Unit}|asc]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[{Business Unit},{FTEs}][][][orderByIncludeList]/", "tests.apptio.net:UIT_BankDemoLite", "MyTable", "overwrite", autocheckin = "true")
tests.apptio.net:UIT_BankDemoLite/Data/January:FY2015/Business+Units+Info
```
