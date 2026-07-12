---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "CopyTable função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/copytable.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CopyTable função

**Aplica-se a** : TBM Studio v12.0+

## Sobre esta tarefa

A função CopyTable oferece uma maneira de copiar tabelas de relatórios ou conjuntos de dados brutos. CopyTable permite copiar tabelas dentro de um projeto ou para um projeto diferente dentro da mesma instância. Essa capacidade de copiar tabelas para projetos diferentes pode ser muito útil em uma solução de vários projetos e, assim, evitar a necessidade de usar soluções alternativas, como exportar e fazer novo upload. Além disso, a função CopyTable é flexível e permite a cópia para um período de tempo específico em um projeto de destino.

A função CopyTable é acionada por meio de um botão em um relatório. Na caixa de diálogo Properties (Propriedades), ative CopyTable com sintaxe no campo Server Action (Ação do servidor) na guia Actions (Ações).

![](../../../resources/images/studio_images/studioimages/studio/stu277.png)

## Visão geral e limitações

Antes de usar o site CopyTable,, revise e compreenda os seguintes conceitos importantes sobre os recursos dessa função:

- O caminho da tabela CopyTable deve ser codificado em URL. Para obter o caminho da tabela, clique com o botão direito do mouse na tabela e selecione **Show Full Data Path (Mostrar caminho completo dos dados** ). Se o caminho não estiver codificado, você deverá escapar dos seguintes caracteres especiais URL : " / +?

  Consulte a Internet para obter informações sobre como escapar dos personagens.
- A tabela de destino é sempre um conjunto de dados, em contraste com a origem, que pode ser uma tabela de relatório ou um conjunto de dados brutos. Os conjuntos de dados existentes no destino podem ser substituídos ou novos conjuntos de dados podem ser criados.
- Ao copiar entre projetos, os dois projetos devem residir na mesma instância ( URL ). Supondo que os projetos estejam no mesmo URL, as tabelas podem ser copiadas entre projetos ou entre domínios.

  Exemplos
  :   **Exemplo 1** : (Mesma instância, mesmo domínio): O Projeto A e o Projeto B estão no mesmo URL ( customer.apptio.com ) e no mesmo domínio ( customer.com ). CopyTable **pode** ser usado.

      **Exemplo 2** : (Mesma instância, domínios diferentes): O Projeto A e o Projeto B estão no mesmo URL ( customer.apptio.com ), mas em dois domínios diferentes ( customer.com e test.com ). CopyTable **não pode** ser usado.

      **Exemplo 3** : (instância diferente): O Projeto A e o Projeto B estão em dois URLs diferentes ( customer-dev.apptio.com e customer-stg.apptio.com ). Eles têm o mesmo domínio ( customer.com ). CopyTable **não pode** ser usado.
- Você pode copiar para vários destinos simultaneamente a partir de um único botão de origem. Para fazer isso, configure o botão com várias ocorrências de CopyTable( ), separadas por uma nova linha.
- O formato do período de tempo usado em CopyTable deve ser sempre Month:Fiscal Year ou Period:Fiscal Year (exemplo: January:FY2011 ou P1:FY2011 ). Para calendários gregorianos, você pode usar a palavra completa do mês ou a abreviação de três letras (por exemplo: January ou Jan). Usando a sintaxe de formato de data no aplicativo, isso pode ser expresso como MMMM:ffff. Para tipos de calendário de período, você pode usar ppp:ffff.

## Onde usar

Use a sintaxe no campo **Ação do servidor** de um botão em um relatório.

## Sintaxe

```
CopyTable("Source Table","Destination Project","Destination Data Set","Time Period
        to Copy To", autocheckin=”true”|”false”)
```

Observação: cada argumento deve ser colocado entre aspas.

## Argumentos

**Tabela de origem** - A tabela de origem pode ser uma tabela de relatório ou um conjunto de dados brutos.

**Tabela de relatório** - Uma tabela de relatório é qualquer tabela que possa ser visualizada no aplicativo (basicamente qualquer coisa que tenha um caminho de dados). Para usá-la como tabela de origem em CopyTable,, você precisa apenas do caminho completo dos dados. Para obter o caminho completo dos dados:

1. Clique com o botão direito do mouse na tabela e selecione Show Full Data Path (Mostrar caminho completo dos dados). Consulte How To: Use show full data path para saber mais.
2. Copie e cole o caminho dos dados em um editor de texto.
3. Remova as quebras de linha para que o caminho de dados fique em uma linha.
4. Substitua a cadeia de caracteres .DateGoesHere por um período de tempo apropriado. Consulte Período de tempo para copiar para obter mais informações sobre cadeias de caracteres de período de tempo válidas.
5. Remova a string add\_total se ela estiver presente para evitar ter uma linha de total no destino.

Por exemplo, digamos que você comece com o seguinte caminho de dados (observe as partes em vermelho):

```
customer.com:Test Project A/
Reports/
.DateGoesHere/
CostModels/
Default/
Test/
!GROUPBY[{Test Table.Item},{Test Table.Group}]/
.Summary/
!SORT[{Cost}|desc]/
!FILTER_ZERO[{Cost}]/
!PIVOT2[{Test Table.Item}][{Test Table.Group}][{Cost}]/
!LIMIT[0,2147483647,add_total]/
!LIMIT_COLUMNS[][][][orderByIncludeList] /
```

Ele seria editado para ficar parecido com o seguinte se você quisesse usar um período de tempo dinâmico como fonte.

```
customer.com:Test Project A/Reports/<%=CurrentDate("ppp:ffff")%>/CostModels/Default/Test/!GROUPBY[{Test Table.Item},{Test Table.Group}]/.Summary/!SORT[{Cost}|desc]/!FILTER_ZERO[{Cost}]/!PIVOT2[{Test Table.Item}][{Test Table.Group}][{Cost}]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[][][][orderByIncludeList]/
```

## **Conjunto de dados brutos**

Um conjunto de dados brutos é considerado qualquer dado carregado e não transformado que não esteja em uma tabela de relatório.

Para obter o caminho para um conjunto de dados brutos de /data, siga estas etapas:

1. Navegue até a tabela em TBM Studio.
2. Selecione **Table (Tabela** ) no pipeline Steps (Etapas).
3. Copie o segmento da URL após o -@C. **Exemplo** : Parte relevante da URL destacada:![](https://help.apptio.com/en-us/resources/images/studio_images/studioimages/studio_acme%20gl_table.png)
4. Substitua o %253A por %3A e o .DateGoesHere por uma cadeia de caracteres de tempo apropriada.
5. Copie o segmento da URL após o -@C. **Exemplo** : Parte relevante da URL destacada:![](https://help.apptio.com/en-us/resources/images/studio_images/studioimages/studio_acme%20gl_table.png)
6. Substitua o %253A por %3A e o .DateGoesHere por uma cadeia de caracteres de tempo apropriada.

Consulte a seção a seguir, Time for the Source, para obter mais informações sobre o que pode substituir o site .DateGoesHere.

- **Original** - reference.apptio.com%253ACost+Transparency/Data/.DateGoesHere/Acme+GL
- **Substituição** - reference.apptio.com%3ACost+Transparency/Data/Jan:FY2018/Acme+GL

## Tempo para a fonte

Ao criar a fonte para uma operação CopyTable( ), você deve especificar um período de tempo válido. Esse período de tempo é injetado no site .DateGoesHere ao examinar os caminhos mostrados na seção anterior. **Não** é a data atual do calendário. Dependendo da situação, talvez seja necessário usar um período de tempo específico (por exemplo: Jan:FY2018, September:2018, e assim por diante) ou talvez você queira algo dinâmico que seja executado dentro do período de tempo atualmente selecionado no seletor de datas. Você pode especificar períodos de tempo como:

## Projeto não habilitado para tempo

Se você estiver copiando de um projeto que **não** esteja habilitado para tempo, haverá apenas um período de tempo elegível para obter o caminho de Eon:FY2000. Aqui está um exemplo do que você faria nesse caso:

- **Original** - customer.com%3AProject+A/Data/.DateGoesHere/Example+Data+Set/
- **Substituição** - customer.com%3AProject+A/Data/Eon:FY2000/Example+Data+Set/

## Projeto com tempo limitado

Se estiver copiando de um projeto com tempo ativado, você tem duas opções:

1. Substitua o endereço .DateGoesHere por uma cadeia de datas válida, conforme mostrado aqui:
   - **Original** - customer.com%3AProject+A/Data/.DateGoesHere/Example+Data+Set/
   - **Substituição** - customer.com%3AProject+A/Data/January:FY2011/Example+Data+Set/
2. Substitua o .DateGoesHere por [wikitext](https://community.apptio.com/docs/DOC-5729 "(Abre em uma nova guia ou janela)") chamando a [função CurrentDate](https://help.apptio.com/en-us/studio/formulas-and-functions/functions/currentdate.htm "(Abre em uma nova guia ou janela)"), conforme mostrado aqui:
   - **Original** - customer.com%3AProject+A/Data/.DateGoesHere/Example+Data+Set/
   - **Substituição** - customer.com%3AProject+A/Data/<%=CurrentDate( "ppp:ffff")%>/Example+Data+Set/

## Projeto de destino

O projeto de destino deve ser fornecido no formato Nome do domínio: Nome do projeto.

**Exemplo** : customer.com:Project B.

Nota:

O nome do projeto **não** precisa ser codificado. Se houver espaços no nome, eles deverão ser mantidos e **não** substituídos por caracteres de codificação.

## Conjunto de dados de destino

O conjunto de dados de destino deve ser uma tabela bruta. Não pode ser uma tabela de transformação. A tabela de destino é fornecida como uma string entre aspas, que é simplesmente o nome da tabela. Os espaços são permitidos e não precisam ser codificados.

**Exemplo** : Projeto B

Dica:

- As tabelas podem ser copiadas dentro do mesmo projeto. Nesse caso, basta inserir o mesmo projeto no parâmetro Destination Project (Projeto de destino).
- Se estiver copiando entre dois projetos, os projetos devem residir na mesma instância.

## Período de tempo para copiar para

Esse é o período de tempo de destino ao qual você deseja que os dados sejam aplicados.

Pode ser necessária uma sintaxe diferente, dependendo do cenário de tempo.

- Se estiver copiando para um projeto não habilitado para tempo, insira Eon:FY2000**.NOTICE**

  R12 requer que você tenha tempo configurado, portanto, isso só se aplica a R11.
- Se estiver copiando para um projeto habilitado para tempo e quiser copiar para um período de tempo específico e estático, você codificaria um valor de Period:Fiscal Year (exemplo: January:FY2011 ).
- Se estiver copiando de um projeto habilitado para tempo e quiser direcionar o período de tempo de destino com base no período de tempo selecionado na parte superior do relatório no aplicativo, poderá usar <%=CurrentDate("ppp:ffff" )%>.

No momento, não é possível copiar de um projeto não habilitado para tempo e selecionar dinamicamente um mês de destino específico.

## Controle as permissões de edição no destino

Se você estiver copiando de uma tabela de origem que seja editável, a tabela bruta terá uma coluna.PK quando for copiada. Apptio reconhecerá a tabela como editável. Se não quiser que a tabela de destino seja editável, você filtrará a coluna.PK usando a opção!LIMIT\_COLUMN, conforme mostrado aqui:

`customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/!LIMIT_COLUMNS[][][{.PK}]`

## Configurar um botão para usar CopyTable

Para configurar um botão em um relatório para usar CopyTable:

1. Navegue até o relatório em TBM Studio ( r12 ) ou alterne para o Modo de Edição ( r11 ).
2. Adicione um botão e nomeie-o adequadamente.
3. Clique com o botão direito do mouse no botão e selecione Propriedades.
4. Selecione Ações.
5. No campo Server Action (Ação do servidor), digite a sintaxe CopyTable.

Agora, quando um usuário clicar no botão, a função CopyTable será executada.

Um botão pode ser configurado para executar várias funções CopyTable colocando mais de uma função CopyTable( ) no campo Server Action (Ação do servidor). Cada função deve ser separada por uma nova linha de retorno.

**Exemplo** : Suponha que você queira copiar uma tabela do Projeto A para os Projetos B, C e D. Você deve inserir as seguintes funções CopyTable no campo **Server Action (Ação do servidor** ):

```
CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/","customer.com:Project
          B","Example Data Set","<%=CurrentDate("ppp:ffff")%>")
```

```
CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/","customer.com:Project
          C","Example Data Set","<%=CurrentDate("ppp:ffff")%>")
```

```
CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/","customer.com:Project
          D","Example Data
    Set","<%=CurrentDate("ppp:ffff")%>")
```

## Exemplos

- **Exemplo 1** - Copiar um conjunto de dados no Projeto A para um conjunto de dados no Projeto B (somente R11, tempo desativado em ambos os projetos). Observação: o exemplo a seguir é encapsulado, mas está todo em uma única linha.

  ```
  CopyTable("customer.com%3AProject+A/Data/Eon%3A2000/Example+Data+Set/","customer.com:Project
                B","Example Data Set","Eon:2000")
  ```
- **Exemplo 2** - Copiar um conjunto de dados no Projeto A para um conjunto de dados com o mesmo nome no Projeto B (horários específicos). Observação: o exemplo a seguir é encapsulado, mas está todo em uma única linha.

  ```
  CopyTable("customer.com%3AProject+A/Data/Jan%3AFY2019/Example+Data+Set/",
                  "customer.com:Project B","Example Data
                Set","January:FY2018")
  ```
- **Exemplo 3** - Copiar um conjunto de dados no Projeto A para um nome diferente no mesmo projeto (período de tempo dinâmico). Observação: o exemplo a seguir é encapsulado, mas está todo em uma única linha.

  ```
  CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Original+Data+Set/",
                "customer.com:Project A","Another Data
                Set","<%=CurrentDate("ppp:ffff")%>")
  ```
- **Exemplo 4** - Copiar um conjunto de dados editável do Projeto A para o Projeto B, convertendo-o em não editável - (somente R11, período de tempo dinâmico). Observação: o exemplo a seguir é encapsulado, mas está todo em uma única linha.

  ```
  CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Editable+Data+Set/!LIMIT_COLUMNS[][][{.PK}]",
                  "customer.com:Project A","Data
                Set","<%=CurrentDate("ppp:ffff")%>")
  ```
- **Exemplo 5** - Copiar um caminho de relatório no Projeto A para um conjunto de dados no Projeto B (período de tempo dinâmico). Observação: o exemplo a seguir é encapsulado, mas está todo em uma única linha.

  ```
  CopyTable("customer.com:Test Project
                  A/Reports/<%=CurrentDate("ppp:ffff")%>/CostModels/Default/.View:Report
                  Name/Source/!GROUPBY[{Source.UID},{Source.Group}]/.Summary/!SORT[{Cost}|desc]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[{Source.UID},{Source.Group},{Cost}][][][orderByIncludeList]/","customer.com:Test
                  Project B","Table
                Name","<%=CurrentDate("ppp:ffff")%>")
  ```
- **Exemplo 6** - Copiar um caminho de relatório no Projeto A para um conjunto de dados no mesmo projeto (período de tempo dinâmico). Observação: o exemplo a seguir é encapsulado, mas está todo em uma única linha.

  ```
  CopyTable("customer.com:Test Project
                A/Reports/<%=CurrentDate("ppp:ffff")%>/CostModels/Default/.View:Report
                Name/Source/!GROUPBY[{Source.UID},{Source.Group}]/.Summary/!SORT[{Cost}|desc]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[{Source.UID},{Source.Group},{Cost}][][][orderByIncludeList]/","customer.com:Test
                Project A","Table Name","<%=CurrentDate("ppp:ffff")%>")
  ```
