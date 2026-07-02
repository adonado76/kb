---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de proporção"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/ratio.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug354.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de proporção

**Aplica-se a** : TBM Studio 12.0 e posterior

Use em fórmulas avançadas de alocação para lidar com situações em que os valores da coluna de ponderação são zero. A função retorna um valor de 1.

## Onde usar

Essa função pode ser usada em:

- Fórmulas de fontes de alocação
- Em uma fórmula de alocação **avançada** em um modelo

## Sintaxe

`Ratio({column},~{column})`

## Argumentos

*coluna*

O nome da coluna no objeto de destino que será usado para ponderar a alocação.

O "~" é um operador de aplicativo que diz ao aplicativo para somar os valores na coluna.

## Tipo de retorno

O número 1.

## Exemplo

Neste exemplo, os custos de todos os data centers são alocados aos servidores com base na correspondência dos nomes dos data centers no objeto Data Centers com os nomes dos data centers no objeto Servers. A alocação é ponderada pelo tamanho dos servidores em cada data center com base em uma fórmula avançada. Os data centers sem correspondência no objeto Servers não são alocados.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug354.png)

## Fórmula

A fórmula avançada usada é:

`=SOURCE*({Server.Size)/Sum(Size){Servers.Size},~{Servers.Size})`

SOURCE representa o valor do objeto Data Centers. Ele é "filtrado" pela opção Data-based reference (Referência baseada em dados) selecionada na seção **To (Para** ) da caixa de diálogo **Properties (Propriedades** ). Servers.Size representa o valor na coluna Size da tabela de unidades de objeto Servers. O "~" é um operador que diz ao aplicativo para somar os valores na coluna Tamanho.

## Cálculos de dados

As tabelas a seguir mostram como a alocação é calculada. A alocação é baseada na correspondência dos nomes dos centros de dados na tabela Data Centers com os nomes dos centros de dados na tabela Servers. As alocações são distribuídas entre os servidores em um data center com base no tamanho relativo dos servidores. Por exemplo, 1/5 dos US$ 100.000 associados ao data center de Boston são alocados para Server1 e 4/5 são alocados para Server2. Os custos do data center de Seattle não são alocados porque não há servidores no data center de Seattle.

## Tabela de data centers

| Servidor | Datacenter | Tamanho | Alocação |
| --- | --- | --- | --- |
| Server1 | Boston | 1 | $100.000 x 1/5 = $20.000 |
| Server2 | Boston | 4 | $100.000 x 4/5 = $80.000 |
| Server3 | Dallas | 1 | $50.000 x 1/3 = $16.667 |
| Server4 | Dallas | 2 | $50.000 x 2/3 = $33.333 |
| Server5 | Chicago | 8 | $10.000 x 8/8 = $10.000 |
| 5 servidores |  | 16 | $160.000 |

## Tabela de servidores

| Data center | Arrendamento | Capacidade |
| --- | --- | --- |
| Boston | $100.000 | 22 |
| Dallas | US$ 50.000 | 22 |
| Chicago | $10.000 | 22 |
| Seattle | US$ 40.000 | 22 |
| Total | US$ 200.000 | 40 |

## Manuseio de valores zero

Se houver pelo menos um valor na coluna de ponderação que não seja zero, o aplicativo calculará os valores corretamente. Se todos os valores da coluna de ponderação forem zero, o aplicativo não conseguirá calcular os valores. Nesses casos, você pode usar a função Ratio para definir efetivamente os valores calculados como 1. O resultado é que o valor alocado será distribuído uniformemente entre as unidades de destino.

No exemplo acima, se os valores de Size fossem todos zero, você usaria a seguinte fórmula avançada:

`=SOURCE*Ratio({Servers.Size},~{Servers.Size})`

Observe que as colunas são inseridas como argumentos para a função, não como uma proporção. Os argumentos são separados por vírgula.
