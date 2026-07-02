---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Alocações de fórmula"
breadcrumb: []
source_path: "studio/model_studio/formula-allocations.html"
images:
  - "resources/images/studio_images/studioimages/studio_diagram_example_allocation.jpg"
  - "resources/images/studio_images/studioimages/studio_diagram_fictional_tables.jpg"
  - "resources/images/studio_images/studioimages/studio_diagram_from_to_tables.jpg"
  - "resources/images/studio_images/studioimages/studio_formula_alloc_source_and_size_table.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Alocações de fórmula

**Aplica-se a** : TBM Studio 12.0 e posterior

Use a opção Fórmula para inserir uma fórmula personalizada para controlar a alocação. Essa fórmula será executada na tabela que recebe dinheiro da alocação. A fórmula tem dois conceitos especiais que não são usados por outras fórmulas em Apptio : esses conceitos são a palavra-chave SOURCE e a operação ~.

A palavra-chave SOURCE representa a quantidade de dinheiro que está sendo alocada do objeto de origem. A função de uma fórmula de alocação avançada é pegar o valor da moeda SOURCE e determinar quanto deve ir para cada linha correspondente do objeto de destino. Portanto, a fórmula deve incluir a palavra-chave SOURCE para obter um resultado útil.

A operação ~ permite que você modifique uma referência de coluna para obter seu valor total em relação às linhas correspondentes, em vez do valor da linha atual. Quando sua fórmula é avaliada em relação à linha de recebimento da tabela de destino, você pode fazer referência a qualquer coluna nessa tabela para obter o valor dessa coluna para sua linha atual. No entanto, o dinheiro do SOURCE é normalmente alocado em várias linhas. O operador ~, combinado com um nome de coluna, fornece o total de uma coluna para todas as outras linhas que correspondem ao mesmo dinheiro SOURCE que está sendo distribuído para a sua linha.

Para uma alocação simples sem relacionamento de dados e sem filtros, isso é o mesmo que o total da coluna. Ao adicionar filtros, você filtra as linhas do conjunto incluído no operador ~. Da mesma forma, se você tiver um relacionamento de dados definido, as únicas linhas incluídas na operação ~ serão as linhas com os mesmos valores nas colunas usadas para o relacionamento de dados como a linha atual. Esse símbolo de operador pode ser considerado como tendo um significado semelhante ao das funções Soma ou SumIF.

## Exemplo

Imagine que você não tenha filtros, nenhum relacionamento de dados e a seguinte fórmula:

> `=SOURCE*({Servers.Size}/~{Servers.Size})`

Como não há filtros nem relacionamento de dados, SOURCE representa todo o dinheiro no objeto de origem. Da mesma forma, o operador ~ é equivalente ao operador SUM. Portanto, nesse caso simplificado, a fórmula acima é equivalente a:

> `=SOURCE*({Servers.Size}/SUM({Servers.Size}))`

Essa fórmula calcula a porcentagem de uma coluna que existe na linha de destino. Essa porcentagem do valor da SOURCE é então alocada.

Observação: Quando você adiciona filtros e relações de dados, o operador ~ e a função SUM fornecem resultados diferentes.

Para algumas tabelas fictícias, podemos calcular SOURCE e ~Size da seguinte forma:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_from_to_tables.jpg)

Nesse caso, cada linha da tabela To calculará seu custo como sendo $1300/210 \* Tamanho. Esse exemplo será mais interessante em seções posteriores.

Isso é semelhante ao comportamento da ponderação em Apptio ao usar a opção Weighting distribution (Distribuição de ponderação). Se você utilizar a função Ratio, obterá o mesmo comportamento. A função Ratio garante que, quando a coluna Servers.Size for **0** para todas as linhas, elas receberão uma distribuição uniforme. Isso resulta na seguinte fórmula:

> `=SOURCE*Ratio({Servers.Size},~{Servers.Size})`

As fórmulas avançadas de alocação podem ser combinadas com filtros na tabela De. Quando você define um filtro na tabela From (De) dentro de sua alocação, o valor SOURCE (Origem) em sua alocação avançada simplesmente filtrará um conjunto de linhas e não incluirá os custos dessas linhas no valor da palavra-chave SOURCE (Origem).

## Exemplo

Imagine que usemos nossa fórmula anterior:

> `=SOURCE*({Servers.Size}/~{Servers.Size})`

e colocá-lo em uma linha de alocação com um filtro From de Data Center!= SEA. Alteramos nosso SOURCE VALUE da seguinte forma:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_formula_alloc_source_and_size_table.jpg)

Observe que o comportamento de alocações modifica somente o valor SOURCE e agora aloca US$ 1.200 em vez de US$ 1.300.

As fórmulas avançadas de alocação podem ser combinadas com filtros na tabela To. Quando você define um filtro na tabela To em sua alocação, sua fórmula simplesmente não será executada nas linhas que não corresponderem ao filtro. Essas linhas receberão US$ 0 da alocação. Essas linhas também não serão incluídas no cálculo do valor ~ de uma coluna.

## Exemplo

Imagine que usemos nossa fórmula anterior de:

> `=SOURCE*({Servers.Size}/~{Servers.Size})`

e colocá-lo em uma linha de alocação com um filtro To de Data Center!= SEA. Alteramos o valor de ~Size da seguinte forma:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_example_allocation.jpg)

Observe que o comportamento das alocações modifica apenas os valores ~ e agora tem um valor ~Size de 160 em vez de 210.

## Relacionamento de dados

Você poderia criar uma alocação com um filtro From (De) de SEA e um filtro To (Para) de SEA e alocar dinheiro apenas do data center SEA para apenas os servidores desse data center. No entanto, não recomendamos fazer isso. Ele cria uma linha de alocação por datacenter e, toda vez que você adiciona um datacenter, precisa adicionar uma nova linha de alocação. A opção **Relacionamento de dados** permite que você crie uma única linha de alocação que imite esse conjunto de linhas de alocação de maneira sustentável. A opção Relacionamento de dados permite que você restrinja as linhas usadas pelas palavras-chave SOURCE e ~ para representar subconjuntos das tabelas From e To. Esses subconjuntos restritos de custo calculam suas alocações independentemente uns dos outros, exatamente como se fossem as alocações independentes acima.

Cada valor exclusivo em sua coluna de relacionamento de dados resultará em um valor SOURCE separado e em um conjunto de linhas To. As duas linhas com esse valor em sua coluna de relacionamento de dados receberão o valor total de outras linhas que tenham o mesmo valor. Isso efetivamente divide a alocação em compartimentos para cada valor exclusivo na coluna. Cada bucket tem um valor de origem e um valor ~.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_fictional_tables.jpg)

Quando a fórmula é executada em uma linha, ela usa os valores SOURCE e ~ que correspondem a esse intervalo de linhas.

Você pode especificar mais de um relacionamento. Se você especificar mais de uma relação, todas as relações deverão corresponder para que o valor seja alocado.

## Fórmulas avançadas de alocação

Esta seção fornece fórmulas de alocação avançadas que imitam os métodos de distribuição padrão disponíveis sem as fórmulas de alocação avançadas. Às vezes, elas podem ser úteis como referência ao criar uma nova fórmula de alocação avançada.

## Alocações de valor ponderado

> `=SOURCE*Ratio({Servers.Size},~{Servers.Size})`

**VEJA TAMBÉM**

- [Alocações de valor ponderado](weighted-value-allocations.html "Aplica-se a: TBM Studio 12.0 e posterior")
- [Sobre ponderação e números negativos](about-weighting-and-negative-numbers.html "aplica-se a: TBM Studio 11.8.3.1 e posterior; TBM Studio 12.0 e posterior. O objetivo de uma ponderação é alocar o número de origem onde a soma é a mesma no destino.")

## Alocações de valor padrão

> `=Servers.Size`

Essa alocação não faz referência à moeda de origem, mas simplesmente aloca um valor de uma coluna no objeto receptor.

Consulte também [Alocações de valor padrão.](standard-value-allocations.html "Aplica-se a: TBM Studio 12.0 e posterior")

## Alocações fora do padrão

Os métodos de distribuição a seguir não podem ser replicados usando uma fórmula de alocação avançada:

- Consumo
- Alocações recursivas
