---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "TableMatch função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/tablematch.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# TableMatch função

Retorna um valor com base em uma tabela de regras que funciona como um conjunto de instruções IF. Cada linha da tabela de regras define uma regra. As condições na mesma linha são combinadas com AND, e os valores na mesma célula são tratados como condições OR.

A função TableMatch substitui instruções IF longas e complexas. Ele usa uma tabela de regras para capturar as informações contidas nos comandos IF. Na tabela, cada coluna representa uma instrução AND. As entradas em uma coluna separadas por vírgula representam uma instrução OR. A última coluna da tabela representa o valor que será retornado pela função. Se nenhuma linha for avaliada como verdadeira, o valor da última linha da tabela será retornado como o resultado.

## Recurso de classificação

Desde 12.10.1, a função Tablematch() foi aprimorada para funcionar melhor com tabelas editáveis. Anteriormente, as tabelas editáveis usadas no Tablematch não eram classificadas, o que podia resultar no retorno do valor errado. A função TableMatch tem dois novos parâmetros: sort=ColumnName e sortOrder (o padrão é ascendente; use sortOrder=desc para descendente) para permitir que os administradores definam a classificação desejada para retornar os valores corretos.

- sort=ColumnName
- sortOrder

o padrão é ascendente se não houver parâmetro

sortOrder=desc para descida

Exemplo:

Ascendente: Matched Result =TableMatch(Rules\_Tablename, Value, sort=ColumnName\_to\_Sort )

Descendente: Matched Result =TableMatch(Rules\_Tablename, Value, sort=ColumnName\_to\_Sort, sortOrder=desc )

- **exclui** o parâmetro opcional da função tablematch().

Exemplo:

`=TABLEMATCH(RulesData,Value,exclude=Foo,exclude={Bar},exclude=Baz)`

A partir da versão 12.5 +, o recurso de coluna de classificação TableMatch( ) também inclui um parâmetro opcional "exclude" para a função tablematch(). Veja a sintaxe como exemplo.

Observação: essa função pode ter um impacto significativo no desempenho. Ele deve ser usado somente em conjuntos de dados, nunca em um relatório.

Aqui está um exemplo de uma tabela de regras:

| A | B | C |
| --- | --- | --- |
| Seattle | Windows, UNIX | Servidor |
| Seattle | laptop | móvel |
| Seattle | PC | área de trabalho |
| Workstation | monitorar | LCD |
| Workstation | desenvolvedor | núcleo duplo |
|  |  | desconhecido |

Algumas das regras representadas pela tabela acima são:

- Primeira linha: Se Seattle e Windows ou UNIX, então o servidor.
- Quarta linha: Se for estação de trabalho e monitor, então LCD.
- Última linha: Se nenhuma das regras for avaliada como verdadeira, retorne o valor "unknown" (desconhecido)

A função suporta texto e números.

Assista a este vídeo da Apptio Serviços Educacionais: [A Função TableMatch](https://community.ibm.com/community/user/viewdocument/the-tablematch-function-7-min?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(Abre em uma nova guia ou janela)").

## Valores da tabela de regras suportados

Você pode prefaciar o texto com o! para pesquisar entradas que não contenham o texto. Para números, você pode usar os operadores padrão: =,<, <=, >, >=,!=. Para pesquisar uma célula vazia, digite a palavra **BLANK** na caixa de filtro. Para pesquisar células que não estejam vazias, digite!**BLANK** na caixa do filtro. O curinga \* é compatível. As opções de pesquisa estão resumidas na tabela abaixo.

| Opção | Descrição |
| --- | --- |
| Texto | Pesquise por "texto" As vírgulas podem ser escapadas usando o caractere de barra invertida. Por exemplo, "ABC\, Inc" seria a marcha de "ABC, Inc". |
| text1,text2,text...n | Pesquise entradas que contenham uma de duas ou mais cadeias de texto. Essa é uma operação "ou". NÃO coloque os valores dentro de parênteses. |
| !texto | Procure entradas que não contenham "text" |
| !(text1,text2,text...n) | Pesquisar entradas que não contenham duas ou mais cadeias de texto. Essa é uma operação AND. Uma entrada corresponderá somente se não contiver todas as cadeias de texto. |
| BRANCO | Digite essa palavra para pesquisar células vazias. |
| !BRANCO | Digite essa palavra para pesquisar células que não estejam vazias. |
| =  >  <  >=  <=  != | Use esses operadores com colunas de números.  Uma vírgula pode ser usada como um operador "ou". Por exemplo: =10,=20 pode ser lido como "igual a 10 ou igual a 20"  Uma vírgula pode ser usada como um operador "e" quando colocada entre parênteses. Por exemplo: (>10,<20) pode ser lido como "maior que 10 e menor que 20" |
| \*texto  texto\*  texto\*texto  \*texto\* | O \* indica qualquer número de caracteres que venha antes, depois ou no meio de uma cadeia de texto. |

## Sintaxe

TableMatch(Rules Tabela, coluna, sort=ColumnName\_to\_Sort, sortOrder=asc|desc, exclude=ColumnName\_to\_Exclude,exclude=...)

- a classificação é opcional
- sortOrder é opcional, o padrão é ascendente
- exclude é opcional

Para versões anteriores a 12.5:

```
TableMatch(Rules Table, Column[,
          suppressNullReturnsOnMatch=true])
```

Para a versão 12.5 +:

```
TableMatch(Rules Table, Column[, specifiedColumn=column_name, useRegex=false,
          suppressNullReturnsOnMatch=true])
```

=TABLEMATCH( RulesData,Value,exclude=Foo,exclude={Bar },exclude=Baz)

## Argumentos

*Tabela de regras*

O nome da tabela que contém as regras.

*Coluna*

A coluna na tabela de regras que contém o valor que será retornado pela função.

**AVISO**

Não use chaves ao redor do nome da coluna.

**Exemplo** :

Correto: =Tablematch(Rules Table,Server-Unix)

Incorreto: =Tablematch(Rules Table, {Server-Unix} )

*suppressNullReturnsOnMatch*

Se esse parâmetro for incluído, a função não retornará valores nulos.

*useRegex* (Compatível com TBM Studio12.5 e superior; [Saiba mais](https://community.ibm.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=a6c0a783-3c7e-435c-bdea-824da6988f07&forceDialog=0 "(Abre em uma nova guia ou janela)") )

Se esse parâmetro for incluído, a função usará expressões regulares ao fazer a correspondência. A tabela de correspondências é tratada como expressões regulares.

Para obter mais informações sobre a sintaxe regex ou para testar suas próprias instruções regex, visite [http://www.rexegg.com/regex-quickstart.html](http://www.rexegg.com/regex-quickstart.html "(Abre em uma nova guia ou janela)") e [regex101.com](http://regex101.com/ "(Abre em uma nova guia ou janela)").

*specifiedColumn* (Compatível com TBM
Studio12.5 e superior; [Saiba mais](https://community.ibm.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=a6c0a783-3c7e-435c-bdea-824da6988f07&forceDialog=0 "(Abre em uma nova guia ou janela)") )

Se esse parâmetro for incluído, a função retornará o valor da coluna da tabela de origem especificada se nenhuma regra for correspondida.

## Tipo de retorno

Sequência

**Observações** :

Essa função não é compatível com a barra de fórmulas **da faixa de opções** nem com a função de visualização de dados na guia **Dados**.

## Exemplos

=TableMatch(Cost Center Rules,Cost Center, sort=Cost Center, sortOrder=asc, exclude=SomeColumn1, exclude=SomeColumn2 )

Suponha que você tenha dados do razão geral, como os seguintes, em uma tabela chamada Centro de custo:

| Número da conta | Código | Custo | Data |
| --- | --- | --- | --- |
| 100 | RSF | 1.000 | 3/6/2010 |
| 200 | RRT | 2.000 | 8/6/2010 |
| 300 | CAC | 1.500 | 8/6/2010 |
| 400 | CAC | 3.500 | 12/06/2010 |
| 500 | SIS | 6.000 | 18/06/2010 |
| 600 | SIS | 5.000 | 21/06/2010 |
| 900 | ACD | 4.500 | 21/06/2010 |

Você deseja atribuir os custos aos seguintes objetos de centro de custo em seu modelo de custos:

- Software
- Rede
- Servidores
- Suporte
- Datacenter

Para fazer isso, você deseja criar uma nova coluna na tabela do razão geral mostrada acima, chamada **Centro de custo**. Para preencher a nova coluna, você cria um novo conjunto de dados chamado Cost Center Rules, que servirá como tabela de regras. A tabela de regras é mostrada abaixo:

| Número da conta | Código | Centro de custo |
| --- | --- | --- |
| 100 | RSF, RSG | Software |
| 200 | RRT | Rede |
| 300 | CAC, CAD | Servidores |
| 400 | CAC, CAD | Suporte |
| 500.600 | SIS | Datacenters |
|  |  | Desconhecido |

Observe o seguinte sobre a tabela de regras:

- As colunas **Acct No** e **Code** são usadas para criar uma instrução AND. Por exemplo, a primeira linha seria a seguinte: Se o número da conta for igual a 100 e o código for igual a RSF ou RSG, o centro de custos será Software.
- A última linha fornece o valor padrão de "Unknown" (Desconhecido) se nenhuma das regras for avaliada como verdadeira.

A seguinte função TableMatch é inserida como o valor da nova coluna:

```
=TableMatch(Cost Center Rules,Cost
      Center)
```

Na função, Cost Center Rules é o nome da tabela de regras e Cost Center é o nome da coluna que contém os resultados.

Depois de aplicar a função TableMatch, a tabela do livro-razão terá a aparência da tabela a seguir:

| Número da conta | Código | Custo | Data | Centro de custo |
| --- | --- | --- | --- | --- |
| 100 | RSF | 1.000 | 3/6/2010 | Software |
| 200 | RRT | 2.000 | 8/6/2010 | Rede |
| 300 | CAC | 1.500 | 8/6/2010 | Servidores |
| 400 | CAD | 3.500 | 12/06/2010 | Suporte |
| 500 | SIS | 6.000 | 18/06/2010 | Datacenters |
| 600 | SIS | 5.000 | 21/06/2010 | Datacenters |
| 900 | ACD | 4.500 | 21/06/2010 | Desconhecido |
