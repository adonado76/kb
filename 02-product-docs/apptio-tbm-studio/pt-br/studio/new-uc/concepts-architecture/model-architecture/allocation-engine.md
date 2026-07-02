---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "O mecanismo de alocação"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura do modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/allocation-engine.html"
images:
  - "resources/images/studio_images/allocation-pattern.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# O mecanismo de alocação

A alocação é a operação central que torna possível a modelagem de custos. Em essência, a alocação é o processo de distribuir custos de um objeto de origem para um ou mais objetos de destino com base em regras definidas. Esta seção explica como o motor funciona por baixo do capô.

## Noções básicas de alocação

Cada alocação segue o mesmo padrão básico:

![Mecanismo de alocação](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/allocation-pattern.png)

O motorista decide as proporções. A fonte fornece o valor total. O alvo recebe a sua parte. Este é o mecanismo fundamental por trás de todas as alocações no TBM Studio.

## Tipos de alocação

O TBM Studio oferece cinco tipos de alocação, cada um adequado a diferentes cenários de distribuição de custos. É essencial saber quando usar cada tipo.

**Alocação de valor ponderada**

O tipo de alocação mais comum. O valor ponderado distribui os custos proporcionalmente com base na proporção dos valores de uma coluna da tabela de destino.

**Como funciona:** cada linha de destino recebe uma parcela do custo de origem igual ao seu peso dividido pelo peso total de todas as linhas de destino.

**Fórmula:** *Valor alocado = Total da fonte × (Peso da linha / Peso total)*

**Exemplo prático: Custos do data center ponderados por servidor**

Suponha que seu data center custe US$ 100.000 e você queira distribuir os custos com base no número de servidores:

|  |  |  |  |
| --- | --- | --- | --- |
| **Unidade de negócios** | **Número de servidores** | **Relação de peso** | **Custo alocado** |
| Vendas | 50 | 50 / 200 = 25% | US$ 25.000 |
| Engenharia | 100 | 100 / 200 = 50% | US$ 50.000 |
| Marketing | 30 | 30 / 200 = 15% | 15.000 dólares |
| Suporte | 20 | 20 / 200 = 10% | $10.000 |
| **Total** | **200** | **100%** | **$100.000** |

**Opções de distribuição no Valor Ponderado:**

- **Even:** O padrão. Se nenhuma coluna de ponderação for selecionada, os custos serão distribuídos igualmente por todas as linhas de destino.
- **Ponderação por:** os custos são divididos proporcionalmente com base em uma coluna da tabela de destino (conforme mostrado acima). A coluna de ponderação deve conter valores numéricos não negativos.
- **Relação entre os dados:** os custos são agrupados em categorias com base na correspondência entre os valores das colunas da fonte e do destino. Cada bucket realiza a alocação de forma independente. Isso elimina a necessidade de muitas linhas de alocação individuais.

Nota:

**Peso por armadilhas**

**Valores não numéricos:** Se a coluna de ponderação contiver pelo menos um valor não numérico, a ponderação será ignorada sem aviso prévio e os custos serão distribuídos uniformemente. Sempre verifique seus dados de ponderação.

**Valores negativos:** a ponderação por números negativos faz com que a alocação falhe. O TBM Studio aplica uma proteção para evitar problemas de cálculo decorrentes de pesos negativos.

**Distribuição do consumo**

A alocação de consumo distribui os custos com base na proporção entre as unidades consumidas e a capacidade disponível. Isso é ideal para modelar o uso real dos serviços de TI.

**Como funciona:** você especifica uma coluna de consumo (do destino) e uma coluna de capacidade (da origem). A alocação distribui os custos de origem com base na proporção da capacidade disponível que cada destino consumiu efetivamente.

**Quando usar:** Quando você dispõe de dados reais de uso — por exemplo, para distribuir os custos de computação em nuvem com base nas horas de CPU consumidas por cada aplicativo.

**Alocação de valor padrão**

A alocação de valor padrão atribui um valor igual ao que já existe na tabela de destino. Esta é uma alocação por mapeamento direto.

**Como funciona:** se a tabela de destino indicar que o Aplicativo A custa US$ 10.000, então US$ 10.000 são alocados ao Aplicativo A. Se a tabela de origem tiver um valor superior ou inferior ao total da tabela de destino, a tabela de origem terá um saldo remanescente ou será alocada em excesso.

**Quando usar:** Quando você dispõe de dados de custos diretos para cada alvo e deseja atribuir esses valores conhecidos, em vez de distribuir um montante global. É comum para custos de mão de obra em que se conhece o salário exato por pessoa ou por projeto.

**Fórmula de alocação**

A alocação por fórmula oferece controle total por meio de fórmulas personalizadas. Você pode escrever uma expressão que determine como cada linha de destino recebe sua parcela.

**Como funciona:** você insere uma fórmula usando a linguagem de cálculo do TBM Studio. A fórmula pode fazer referência à palavra-chave SOURCE (valor total da fonte), aos valores das colunas, ao operador ~ (tilde) para somas agregadas e à função Ratio.

**Fórmula de exemplo:** *=SOURCE \* Ratio( {Servers.Size}, ~ {Servers.Size} )*

Esta fórmula reproduz o comportamento do valor ponderado: cada linha recebe uma parcela proporcional ao seu valor de Tamanho em relação ao total. A função Ratio lida com o caso extremo em que todos os valores são zero recorrendo a uma distribuição uniforme.

**Alocação por recursão**

A alocação por recursão lida com situações em que os custos circulam entre serviços interconectados — por exemplo, quando os serviços de TI prestam suporte uns aos outros, além de darem suporte às unidades de negócios.

**Como funciona:** a alocação é executada de forma iterativa. Cada iteração transfere uma parte dos custos da origem para o destino. Os custos que retornam à origem são realocados na próxima iteração. Isso continua até que o valor restante fique abaixo de um limite de precisão ou até que o número máximo de iterações seja atingido.

**Quando usar:** Quando os serviços têm dependências mútuas (por exemplo, o Help Desk dá suporte aos servidores, e os servidores dão suporte ao Help Desk) e é necessário resolver o fluxo circular de custos.

Nota:

**Nota sobre o desempenho da recursão**

As alocações recursivas exigem muito mais capacidade de processamento do que as alocações padrão. Use um número limitado de alocações recursivas por modelo, mantenha o número de iterações baixo e defina o limite de precisão o mais alto possível.

## Resumo do tipo de alocação

|  |  |  |
| --- | --- | --- |
| **Tipo de alocação** | **Ideal para** | **Complexidade** |
| Valor ponderado | A maioria das distribuições de custos (divisão proporcional com base nos dados do motorista) | Baixo |
| Consumo | Alocações com base no consumo (consumo vs. capacidade) | Médio |
| Valor padrão | Atribuições de custos diretos em que os valores-alvo são conhecidos | Baixo |
| Fórmula | Lógica personalizada não abrangida pelos tipos padrão | Alto |
| Recursão | Interdependências entre áreas de serviço | Alto |
