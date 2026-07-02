---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Lista anotada de funções por tipo"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/annotated-list-of-functions-by-type.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Lista anotada de funções por tipo

**Aplica-se a** : TBM Studio 12.0 e posterior

As informações abaixo resumem as funções e sua sintaxe por tipo. As funções são listadas de acordo com os seguintes tipos:

- Banco de dados
- Data e hora
- Formatação
- Matemática
- Sequência
- Transformação da tabela

## Apptio relatórios relacionados ao projeto

## Funções do banco de dados

| **Função** | **Descrição** |
| --- | --- |
| [CopyTable](functions/copytable.html "Aplica-se a: TBM Studio v12.0+") | ``` CopyTable("Source Table","Destination Project","Destination Data Set","Time               Period to Copy To") ``` |
| [GetInfo](functions/getinfo.html "Aplica-se a: TBM Studio 12.0 e posterior") | `GETINFO("attribute1",["DomainName:ProjectName"]` |
| [Se](functions/if.html "Avalia uma expressão de filtro e retorna um valor se for verdadeira e outro valor se for falsa. Oferece suporte a operações AND e OR na condição.") | `If(filter_expression,true_expression,false_expression)` |
| [Chave](functions/key-function.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Key(value1,value2,...)` |
| [PeriodsInHalf](functions/periodsinhalf.html "Aplica-se a: TBM Studio e posterior") | `PeriodsInHalf(half)` |
| [PeriodsInQuarter](functions/periodsinquarter.html "Aplica-se a: TBM Studio e posterior") | `PeriodsInQuarter(quarter)` |
| [PeriodsInYear](functions/periodsinyear.html "Aplica-se a: TBM Studio e posterior") | `PeriodsInYear()` |
| [Substituir](functions/replace.html "Substitui valores em uma tabela com base em mapeamentos de uma tabela de pesquisa separada. A função faz a correspondência em colunas-chave e atribui novos valores de colunas especificadas na tabela de substituição. Todos os valores são tratados como cadeias de caracteres.") | `=Replace((transform_table_column1,transform_table_column2,...),search_and_replace_table,(match_column1,match_column2,...),(new_column1,new_column2,...),replace_table_column)` |
| [Linha](functions/row.html "Retorna o índice da linha atual na tabela, começando com zero para a primeira linha.") | ``` Row(               ) ``` |
| [RowCount](functions/rowcount.html "Retorna uma contagem do número total de linhas em uma tabela especificada. Se nenhuma tabela for especificada, ele retornará o número de linhas no contexto da tabela atual.") | `RowCount(table)` |
| [TableMatch](functions/tablematch.html "Retorna um valor com base em uma tabela de regras que funciona como um conjunto de instruções IF. Cada linha da tabela de regras define uma regra. As condições na mesma linha são combinadas com AND, e os valores na mesma célula são tratados como condições OR.") | `TableMatch(Table,Column)` |
| [UniqueCount](functions/uniquecount.html "Aplica-se a: TBM Studio 12.0 e posterior") | `UniqueCount(column)` |
| [UniqueValues](functions/uniquevalues.html) | `UniqueValues(column)` |

## Funções de data e hora

| Função | Sintaxe |
| --- | --- |
| [CurrentDate](functions/currentdate.html "Retorna a data de início do período de tempo selecionado no momento, se o tempo estiver ativado. Caso contrário, retorna o Eon 2000.") | `CurrentDate([format_string])` |
| [dias](functions/days.html "Converte uma data especificada em um valor numérico que representa o número de dias desde 1º de janeiro de 1970.") | `Days(date_expression)` |
| [DurationOfMonth](functions/durationofmonth.html) | `DurationOfMonth ("d/h/m/s/S", [month[, year]])` |
| [Decorrido](functions/elapsed.html "Calcula o tempo decorrido entre duas datas em segundos, contabilizando opcionalmente os períodos excluídos e oferecendo suporte à saída formatada.") | `Elapsed(startDate,endDate[,table[,startCol,endCol])` |
| [Horas](functions/hours.html "Converte um valor de data no número de horas desde 1º de janeiro de 1970, como um valor numérico.") | `Hours(date_expression)` |
| [Minutos](functions/minutes.html "Converte um valor de data no número de minutos desde 1º de janeiro de 1970, como um valor numérico.") | `Minutes(date_expression)` |
| [Meses](functions/months.html "Converte uma data especificada em um valor decimal que representa o número de períodos desde 1º de janeiro de 1970. Útil para cálculos baseados em tempo, como determinação de durações ou custos proporcionais.") | `Months(date_expression)` |
| [Agora](functions/now.html) | `Now(metric)` |
| [Período](functions/period.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Period(["time_period"][n])` |

## Funções de formatação

| Função | Sintaxe |
| --- | --- |
| [Moeda](functions/currency.html "Formata valores numéricos como cadeias de moeda, adicionando o símbolo de moeda apropriado com base na localidade. Por padrão, os valores negativos são exibidos em vermelho.") | `Currency(column[,pattern[;negative_pattern]])` |
| [DateFormat](functions/dateformat.html "Converte uma expressão de data em um formato de data especificado.") | `DateFormat(date_expression,format_string)` |
| [NumberFormat](functions/numberformat.html "Formata um valor numérico em um rótulo (string) usando padrões personalizados para números positivos e negativos, durações ou formatação de tamanho de dados. Essa função foi projetada para uso em colunas do tipo Label.") | `NumberFormat(column[,pattern[;negative_pattern]])` |
| [StatusIcon](functions/statusicon.html "Aplica-se a: TBM Studio 12.0 e posterior") | `StatusIcon(green_expression,red_expression)` |

## Funções matemáticas

| Função | Sintaxe |
| --- | --- |
| [Abs](functions/abs-function.html "Retorna o valor absoluto de um número ou expressão, removendo qualquer sinal negativo.") | `Abs(column)` |
| [Anual](functions/annual.html "Retorna um valor para a métrica especificada ajustada para frente ou para trás em um número de anos, com base no tipo de calendário selecionado.") | `Annual(metric[,delta[,type]])` |
| [Anualizar](functions/annualize.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Annualize(metric)` |
| [Média](functions/average.html "Retorna o valor médio em uma coluna ou métrica especificada.") | `Average(rollup_operator column)` |
| [DateSum](functions/datesum.html "Soma os valores em todas as colunas cujos nomes estão em conformidade com os formatos de data reconhecidos, ignorando as colunas que não são de data.") | `DateSum()` |
| [Grande](functions/large.html "Retorna o maior valor em uma coluna especificada.") | ``` Large               (rollup_operator column) ``` |
| [Máx.](functions/max.html "Compara duas expressões e retorna o maior valor.") | `Max(numeric_expression,numeric_expression)` |
| [Min](functions/min.html "Compara duas expressões numéricas e retorna o menor valor.") | `Min(numeric_expression,numeric_expression)` |
| [Mod](functions/mod.html "Divide um número por outro e retorna o restante, preservando o sinal do dividendo (primeiro número).") | `Mod(number,divisor)` |
| [Percentil](functions/percentile.html "Retorna o valor de percentil especificado para uma determinada coluna numérica. Um percentil representa o valor abaixo do qual uma determinada porcentagem dos dados se enquadra.") | `Percentile(rollup_operator column,percentage)` |
| [Energia](functions/power.html "Eleva um número de base especificado à potência de um expoente especificado, realizando um cálculo exponencial.") | `Power(base,exponent)` |
| [PreviousMonth](functions/previousmonth.html "Retorna o valor de uma métrica especificada do mês anterior na mesma tabela. Útil para comparar os valores atuais com os do mês anterior.") | `PreviousMonth(metric)` |
| [PreviousYear](functions/previousyear.html "Retorna a soma de uma métrica especificada na tabela atual para o número anterior de períodos em um ano fiscal. Em um calendário de 12 períodos, seriam 12 períodos. Em um calendário de 13 períodos, seriam 13 períodos.") | `PreviousYear(metric)` |
| [QuarterToDate](functions/quartertodate.html "Retorna o valor acumulado de uma métrica especificada desde o início do trimestre fiscal atual até o período atual, inclusive.") | `QuarterToDate(column)` |
| [Rand](functions/rand.html "Gera um número decimal aleatório entre 0.0 (inclusive) e 1.0 (exclusive).") | ``` Rand(               ) ``` |
| [Razão](functions/ratio.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Ratio(column,~column)` |
| [Etapa](functions/round.html "Arredonda um número real para um número especificado de casas decimais usando o algoritmo \"round-half-up\". Isso significa que os valores que terminam em 0,5 são arredondados para longe de zero.") | `Round(numeric_expression,digits)` |
| [SLN](functions/sln.html "Aplica-se a: TBM Studio 12.0 e posterior") | `SLN(original,salvage,lifespan)` |
| [Pequeno](functions/small.html "Retorna o menor valor em uma coluna especificada.") | `Small(rollup_operator column)` |
| [Soma](functions/sum.html "Retorna a soma total dos valores na coluna numérica especificada.") | `Sum(column)` |
| [TimePeriod](functions/timeperiod.html "Retorna o valor de uma métrica especificada no início de um período (por exemplo, mês, trimestre, ano) que é um número especificado de períodos antes ou depois do período atual. A unidade de tempo é determinada pela visualização selecionada ou por um sufixo de granularidade explícito.") | `TimePeriod(metric,time)` |
| [Trunc](functions/trunc.html "Trunca um número real removendo sua parte fracionária.") | `Trunc(value)` |
| [Desmarcar](functions/untag.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Untag(value)` |
| [YearToDate](functions/yeartodate.html "Retorna o valor acumulado de uma métrica especificada desde o início do ano fiscal atual até o período atual, inclusive. Isso difere da função Annual, que sempre retorna o total do ano inteiro, independentemente do período atual.") | `YearToDate(column)` |

## Funções de cadeia de caracteres

| Função | Sintaxe |
| --- | --- |
| [CapFirstLetter](functions/capfirstletter.html "Coloca a primeira letra de cada palavra no argumento da cadeia de caracteres em maiúscula e deixa todas as outras letras em minúsculas.") | `CapFirstLetter(string)` |
| [Avaliação](functions/eval.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Eval(string)` |
| [EvalWiki](functions/evalwiki.html "Aplica-se a: TBM Studio 12.0 e posterior") | `EvalWiki(wikitext)` |
| [Localizar](functions/find.html "Retorna a posição da primeira ocorrência de uma cadeia de caracteres de pesquisa em outra cadeia, começando em uma posição opcional. Essa função diferencia maiúsculas de minúsculas.") | `Find(search_string,in_string,[starting_position])` |
| [Pesquisa de IP](functions/iplookup.html "Aplica-se a: TBM Studio 12.0 e posterior") | ``` IPLookup(source_column,lookup_table,matching_column,replacement_column               ,default_value) ``` |
| [IsNumeric](functions/isnumeric.html "Avalia uma expressão para determinar se é um número válido, retornando 'true' ou 'false' como uma cadeia de caracteres.") | `IsNumeric("value") or ISNUMERIC({column name})` |
| [Esquerda](functions/left.html "Retorna um número específico de caracteres de uma cadeia de caracteres (incluindo espaços em branco), começando pela esquerda.") | `Left(string[,count])` |
| [Len](functions/len.html "Retorna o número de caracteres em uma determinada cadeia de caracteres, incluindo espaços.") | `Len(string_expression)` |
| [Função de pesquisa](functions/lookup.html "Procura um valor em uma tabela de pesquisa com base em uma correspondência entre uma coluna na tabela atual e uma coluna na tabela de pesquisa e retorna o valor correspondente de uma coluna de substituição.") | ``` Lookup(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value) ``` |
| [Função Lookup\_Wild](functions/lookup_wild.html "Procura um valor em uma tabela de pesquisa usando a correspondência de padrões (expressões regulares) na coluna de correspondência e retorna o valor correspondente de uma coluna de substituição.") | ``` Lookup_Wild(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value) ``` |
| [LookupEx](functions/lookupexandlookupex_wild.html "Realiza uma pesquisa em tabelas e retorna todos os valores correspondentes, criando novas linhas para cada correspondência. Essa função permite um relacionamento de um para muitos ao unir todas as linhas correspondentes da tabela de pesquisa à tabela transformada.") | ``` LookupEx(source_column,lookup_table,matching_column,replacement_column               [,leave_original_value][,replace_nulls][,ignore_case]) ``` |
| [LookupFromPath](functions/lookupfrompath.html "Aplica-se a: TBM Studio 12.0 e posterior") | `LookupFromPath("path",target_column,lookup_column,lookup_value_column)` |
| [LookupObjectTotalAllocated](functions/lookupobjecttotalallocated.html "Aplica-se a: TBM Studio 12.0 e posterior") | `LookupObjectTotalAllocated(metric)` |
| [LookupObjectTotalValue](functions/lookupobjecttotalvalue.html "Aplica-se a: TBM Studio 12.0 e posterior") | ``` LookupObjectTotalValue(object[,metric  [, driver]]) ``` |
| [LookupObjectUnitAllocated](functions/lookupobjectunitallocated.html "Aplica-se a: TBM Studio 12.0 e posterior") | ``` LookupObjectUnitAllocated  (sourceObject,destObject,metric,  columnInLocalTable,columnInSourceObjectTable) ``` |
| [LookupObjectUnitValue](functions/lookupobjectunitvalue.html "Aplica-se a: TBM Studio 12.0 e posterior") | ``` LookupObjectUnitValue  (object,metric,targetCol,lookupCol[,driver]) ``` |
| [LookUpMetric](functions/lookupmetric.html "Aplica-se a: TBM Studio 12.0 e posterior") | `LookUpMetric(metric,column)` |
| [Inferior](functions/lower.html "Converte a cadeia de caracteres de entrada para todas as letras minúsculas. caracteres") | `Lower(expression)` |
| [Médio](functions/mid.html "Retorna um número especificado de caracteres de uma cadeia de caracteres, começando em uma determinada posição a partir da esquerda.") | `Mid(string,start[,count])` |
| [Pluralizar](functions/pluralize.html "Aplica-se a: TBM Studio 12.0, 12.1") | `Pluralize(noun[,count])` |
| [Direita](functions/right.html "Retorna o número especificado de caracteres a partir do final (lado direito) de uma cadeia de caracteres, incluindo espaços em branco.") | `Right(string[,count])` |
| [Pesquisar](functions/search.html) | `Search(search_string,in_string[,starting_position])` |
| [Divisão](functions/split.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Split(expression,n[,delimiters])` |
| [Substituto](functions/substitute.html) | `Substitute(target_string,search_string,replacement_string)` |
| [Aparar](functions/trim.html "Remove os espaços à esquerda e à direita de uma cadeia de caracteres especificada. Ele não remove espaços em uma cadeia de caracteres.") | `Trim(expression)` |
| [Desfazer](functions/undrill.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Undrill(metric)` |
| [Superior](functions/upper.html "Converte a cadeia de caracteres de entrada em todos os caracteres maiúsculos.") | `Upper(expression)` |
| [Valor](functions/value.html "Converte uma cadeia de caracteres de aparência numérica em um número usando um padrão de formatação opcional. Útil para extrair valores numéricos de cadeias de caracteres que incluem texto ou símbolos.") | `Value(value[,pattern])` |

## Funções de transformação de tabelas

| Função | Sintaxe |
| --- | --- |
| [Usar\_Mapa\_Grade](functions/usemapgrid.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Use_Map_Grid(table:source_column[,notation])` |
| [Utilizar\_Tabela\_Mapa](functions/usemaptable.html "Aplica-se a: TBM Studio 12.0 e posterior") | ``` Deprecated.               Replaced by Use_Map_Grid. ``` |

## Apptio funções relacionadas ao projeto

| Função | Sintaxe |
| --- | --- |
| [DomainName](functions/domainname.html "Aplica-se a: TBM Studio 12.0 e posterior") | ``` DomainName(               ) ``` |
| [ProjectExists](functions/project-exists-function.html "Aplica-se a: TBM Studio 12.0 e posterior") | `ProjectExists(domain:project)` |
| [ProjectName](functions/projectname.html "Aplica-se a: TBM Studio 12.0 e posterior") | ``` ProjectName               ( ) ``` |

## Funções de relatórios

| Função | Sintaxe |
| --- | --- |
| [GetLastFilterColumn](functions/getlastfiltercolumn.html "Aplica-se a: TBM Studio 12.0 e posterior") | `GetLastFilterColumn()` |
| [GetLastFilterValue](functions/getlastfiltervalue.html "Aplica-se a: TBM Studio 12.0 e posterior") | `GetLastFilterValue(column)` |
| [GetReportName](functions/getreportname.html "Aplica-se a: TBM Studio 12.0 e posterior") | `GetReportName()` |
| [GetReportPath](functions/getreportpath.html "Aplica-se a: TBM Studio 12.0 e posterior") | `GetReportPath()` |
| [Ícone](functions/icon.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Icon(["icon-type"], expression, expression+)` |
| [ObjectName](functions/objectname.html "Aplica-se a: TBM Studio 12.0 e posterior") | `ObjectName()` |
| [Linha de faísca](functions/sparkline.html "Aplica-se a: TBM Studio 12.0 e posterior") | `Sparkline(past,future,column)` |
