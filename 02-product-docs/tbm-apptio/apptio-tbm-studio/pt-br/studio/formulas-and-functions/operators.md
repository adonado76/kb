---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Operadores"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/operators.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Operadores

**Aplica-se a** : TBM Studio 12.0 e posterior

A sintaxe do aplicativo suporta muitos operadores padrão, bem como operadores de rollup, que fazem referência às unidades de origem ou destino de um rollup de dados.

Você pode usar os seguintes operadores em fórmulas e funções:

- **+** - Adição e [concatenação de strings](string-concatenation.html "Aplica-se a: TBM Studio 12.0 e posterior")
- **-** - Subtração
- **\*** - Multiplicação
- **/** - Divisão
- **=** - Igual (esse operador pode ser usado com datas e cadeias de caracteres, bem como com valores numéricos)
- **!=** - Não é igual
- **<** - Menos de
- **<=** - Menor ou igual a
- **>** - Maior que
- **>=** - Maior ou igual a
- **&** - Concatenação
- **@** - Operador de rollup, origem
- **~** - Operador de rollup, alvo

## Operadores de rollup

Os operadores de rollup podem ser usados em conjuntos de dados, mas não em tabelas de relatórios.

A seguir, descrevemos os operadores de rollup:

- **@SOURCE** - @ ou SOURCE pode ser usado para representar a soma dos valores no objeto de origem que serão transferidos para a linha atual na tabela de destino.
- **~TARGET** - ~ ou TARGET pode ser usado para representar a soma dos valores no objeto de destino que receberá valores da tabela de origem.

Os operadores de rollup são aplicáveis em duas situações:

- Em um modelo, ao transferir valores de um objeto para outro. Nesse caso, @ ou SOURCE se refere a todas as linhas que estão sendo transferidas do objeto de origem, e ~ ou TARGET se refere a todas as linhas que estão sendo transferidas para o objeto de destino.
- Em uma transformação de tabela com um agrupamento, você pode usar funções estatísticas como [AVERAGE (média](functions/average.html "Retorna o valor médio em uma coluna ou métrica especificada.") ), [LARGE (grande](functions/large.html "Retorna o maior valor em uma coluna especificada.") ) e [SMALL (pequeno](functions/small.html "Retorna o menor valor em uma coluna especificada.") ). Por exemplo, você pode usar AVERAGE(@column) para que uma célula contenha a média da coluna nomeada para todas as linhas de origem que foram agrupadas. Para obter mais informações, consulte [Referência a colunas agrupadas](referencing-column-names.html "Aplica-se a: TBM Studio 12.0 e posterior"). A coluna que está sendo operada deve ter a opção **Group By** definida no painel **Column Details (Detalhes da coluna** ). Os operadores de rollup são opcionais para essas funções.

Por exemplo, considere a seguinte tabela de unidades para um objeto de destino chamado Servers e uma tabela de origem chamada Utility:

## Tabela de servidores

| Nome do host | Data center | Espaço | CPUs | .Contagem |
| --- | --- | --- | --- | --- |
| Host1 | Boston | 4 | 4 | 1 |
| Host2 | Seattle | 1 | 1 | 1 |
| Host3 | Boston | 2 | 4 | 1 |
| Host4 | Seattle | 1 | 1 | 1 |

## Mesa de utilidades

| ID | Host | .Contagem | Custo |
| --- | --- | --- | --- |
| A | Host1 | 1 | US$ 100 |
| B | Host2 | 1 | US$ 100 |
| C | Host3 | 1 | US$ 100 |
| D | Host4 | 1 | US$ 100 |

No caso de um rollup direto de Utilitário para Servidores, você pode alocar custos de **Todos os Utilitários** para **Servidores por Servers.Hostname** usando a seguinte fórmula na opção Alocação **avançada** :

`=@Cost`

Isso significa que, para cada linha na tabela de destino, encontre as linhas na tabela de origem que correspondam ao identificador Hostname e aloque a soma da coluna Custo para essas linhas.

A tabela de unidades resultante para Servidores é:

| Nome do host | Data center | Espaço | CPUs | .Contagem | Custo |
| --- | --- | --- | --- | --- | --- |
| Host1 | Boston | 4 | 4 | 1 | US$ 200 |
| Host2 | Seattle | 1 | 1 | 1 | US$ 100 |
| Host3 | Boston | 2 | 4 | 1 | US$ 100 |
| Host4 | Seattle | 1 | 1 | 1 | $0 |

Examinando a primeira linha da tabela de unidades acima, o valor na coluna Custo é US$ 200 porque duas linhas na tabela Utilities de origem correspondem ao identificador Host1, cada uma valendo US$ 100, portanto a soma é US$ 200. A última linha contém 0 na coluna Custo, porque nenhuma linha na tabela de origem corresponde ao identificador Hostname.Host4.

Para ilustrar o operador ~, considere a seguinte tabela de origem chamada Data Centers:

| Data center | .Contagem | Custo |
| --- | --- | --- |
| Boston | 1 | $1000 |
| Seattle | 1 | $1000 |

No caso de um rollup direto de Data Centers para Servidores, você pode alocar custos de **Todos os Data Centers** para o **Data Centers.Data Center** usando a seguinte fórmula na opção Alocação **avançada** :

`=@Cost*(Servers.Space/~Servers.Space)`

Essa fórmula multiplica os valores somados pela taxa de espaço, que é o espaço dividido pelo espaço total consumido pelos hosts em um determinado data center. No exemplo acima, Boston está implementando dois servidores, Host1 e Host3, portanto, para Host1 na tabela de destino, a fórmula diz para pegar o valor do custo do data center de Boston (US$ 1.000) e multiplicá-lo pela proporção de espaço para Host1. A proporção de espaço para Host1 é obtida pegando o valor na coluna Espaço (4) e dividindo-o pela soma da coluna Espaço para linhas em que Data Center = Boston, que é 6 (4 para Host1 mais 2 para Host3 ).

Portanto, a alocação para Host1 é:

```
=$1000 * (4 / 6)
=$1000 * 0.6667
=$666.6667
```

A tabela de unidades resultante para Servidores é:

| Nome do host | Data center | Espaço | CPUs | .Contagem | Custo |
| --- | --- | --- | --- | --- | --- |
| Host1 | Boston | 4 | 4 | 1 | R$ 667 |
| Host2 | Seattle | 1 | 1 | 1 | $500 |
| Host3 | Boston | 2 | 4 | 1 | R$ 333 |
| Host4 | Seattle | 1 | 1 | 1 | $500 |
