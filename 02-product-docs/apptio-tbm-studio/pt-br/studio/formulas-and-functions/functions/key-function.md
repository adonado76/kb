---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função-chave"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/key-function.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu269.png"
  - "resources/images/studio_images/studioimages/studio/stu270.png"
  - "resources/images/studio_images/studioimages/studio/stu271.png"
  - "resources/images/studio_images/studioimages/studio/stu272.png"
  - "resources/images/studio_images/studioimages/studio/stu273.png"
  - "resources/images/studio_images/studioimages/studio/stu274.png"
  - "resources/images/studio_images/studioimages/studio/stu279.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função-chave

**Aplica-se a** : TBM Studio 12.0 e posterior

O objetivo da função Key é criar uma coluna com valores exclusivos para cada linha em uma tabela. A função define uma nova coluna em um conjunto de dados como a combinação de duas ou mais colunas e/ou uma cadeia de texto ou uma fórmula. Normalmente, a coluna seria usada como um identificador de unidade para um objeto em um modelo ou para estabelecer um relacionamento no mapa de inferência.

A função Key é o método preferido para criar uma coluna-chave para uma tabela quando você tem um conjunto de dados com mais de 1 milhão de linhas. Ele aborda a situação em que as colunas concatenadas em uma tabela não produzirão um valor exclusivo para cada linha. Por exemplo, suponha que você tenha a seguinte tabela:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu272.png)

Se você usar a concatenação para criar uma terceira coluna (= {Value 1} & {Value2} ), obterá o resultado mostrado abaixo. Observe que os valores da coluna-chave não são exclusivos.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu273.png)

Se você usar a função Key para criar uma terceira coluna (=Key(Value 1,Value2 ), obterá o resultado mostrado abaixo. Os valores da coluna-chave agora são exclusivos.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu274.png)

Se você usasse a concatenação &&, ela produziria valores exclusivos no exemplo dado acima, mas não forneceria valores exclusivos se você tivesse a tabela a seguir, na qual uma célula em cada coluna é nula. Quando as colunas Value 1 e Value 2 são combinadas, elas resultam na coluna Concat.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu279.png)

Além disso, a função Key resulta em um desempenho mais rápido do sistema do que a concatenação.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados

## Sintaxe

`Key(value1,value2,...)`

## Argumentos

*valor*

Um valor pode ser o nome de uma coluna, uma cadeia de texto entre aspas ou uma fórmula.

## Tipo de retorno

|value1,value2,...|

Observe que as barras no início e no final do valor de retorno indicam que o valor é uma combinação dos elementos. Não se trata de uma nova cadeia de texto, como a que você obteria se concatenasse duas ou mais colunas.

**Observações** :

- Um valor criado com a função Key() é equivalente apenas a outros valores criados com a função Key(). O resultado de uma função-chave só será vinculado por inferência a valores gerados por outras funções Key(). Além disso, a função de rastreamento nos modelos agora funcionará com os valores da função Key().
- Se você estiver trabalhando com um conjunto de dados com menos de 1 milhão de linhas, deverá usar a concatenação para criar a coluna-chave. Para obter mais informações sobre concatenação, consulte [Concatenação de strings](../string-concatenation.htm "(Abre em uma nova guia ou janela)").

## Exemplos

Suponha que você tenha a seguinte tabela:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu269.png)

Para adicionar a coluna-chave mostrada abaixo, você deve digitar o seguinte no campo **Value (Valor)** da coluna:

```
=key(Application,Service
      Level,Type)
```

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu270.png)

Para adicionar a coluna-chave mostrada abaixo, você deve digitar o seguinte no campo **Value (Valor)** da coluna:

```
=key("Key:",Application,Service
      Level)
```

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu271.png)
