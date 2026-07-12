---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Custos de instância reservados - Alocações dentro de Apptio"
breadcrumb: []
source_path: "cost-transparency/configuration/reservedcosts.html"
images:
  - "resources/images/ct_images/8454_1.png"
  - "resources/images/ct_images/8454_2.png"
  - "resources/images/ct_images/8454_3.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Custos de instância reservados - Alocações dentro de Apptio

As instâncias reservadas (RIs) incluem opções de preços pelas quais todos ou alguns dos custos são pagos antecipadamente no momento da compra. Para essas opções (All Upfront ou Partial Upfront), o site Apptio distribuirá o custo inicial uniformemente a cada mês durante o prazo de compra do RI. Esse custo mensal efetivo será adicionado a quaisquer taxas recorrentes associadas ao RI (0 no caso do All Upfront) para formar o custo mensal acumulado efetivo.

## Determinação de um custo mensal efetivo para compras no RI

É esse custo mensal acumulado efetivo para um RI que será usado na alocação de custos para os itens de linha de faturamento do site AWS para os recursos que se beneficiam das compras do RI. O diagrama a seguir ilustra como um custo simples de RI, do tipo "All Upfront", seria distribuído entre todos os meses do RI.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8454_1.png)

## Observação importante sobre as fontes de dados de faturamento: Relatório de alocação de custos versus relatório de custo e uso

Apptio atualmente utiliza o relatório de alocação de custos do site AWS para obter dados de faturamento mensal. AWS tem planos de descontinuar o relatório de alocação de custos e recomenda o uso do relatório de custo e uso. Como resultado, o site Apptio está atualmente desenvolvendo a integração com o relatório de custo e uso. Por enquanto, no entanto, o relatório de alocação de custos é a principal fonte de faturamento mensal e as alocações descritas abaixo são baseadas nas tarifas combinadas incluídas no relatório de alocação de custos.

## Como os custos fixos do RI são alocados aos itens de faturamento do site AWS?

Os custos da instância reservada não são refletidos nos itens de linha de faturamento para os recursos do AWS que se beneficiam dessas compras de RI. Para resolver essa questão, o site Apptio aloca os custos fixos (após amortizar esses custos em todos os meses do período do RI, conforme mostrado acima) a cada item de linha da fatura. Apptio a abordagem da empresa é distribuir os itens com base na família/tipo de instância, sistema operacional e região/zona de disponibilidade e ponderar pela quantidade de uso de cada item de linha aplicável. O diagrama abaixo ilustra como os custos serão distribuídos desde a compra até uma conta mensal.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8454_2.png)

## Observação importante sobre custos combinados no relatório de alocação de custos

AWS o cálculo dos custos no Relatório de Alocação de Custos é um fator importante a ser considerado no contexto da alocação dos custos fixos do RI de volta aos itens de linha de uso. O diagrama a seguir ilustra conceitualmente como o site AWS determina os custos combinados, especialmente quando há RIs envolvidos. A principal conclusão é que os custos no relatório de alocação de custos são baseados em uma taxa combinada, que é efetivamente o custo agregado dividido pela quantidade de uso agregada para um grupo de instâncias, independentemente da conta e das tags associadas.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8454_3.png)

## Como os novos e flexíveis RIs alteram as alocações de custos fixos do RI?

Com os novos EC2 RIs flexíveis regionais e de tamanho de instância, as alocações de custo dependerão da família de instância e da região, em vez do tipo de instância e da zona de disponibilidade. Os custos mensais de RI serão ponderados pela quantidade de uso do item de linha de uso multiplicada por um fator de normalização que leva em conta o tamanho relativo da instância. Essa alteração se aplica somente aos RIs de EC2, não aos RIs de outros serviços de AWS, como RDS ou Elasticache.

## Como as modificações do RI afetam minhas alocações de custos do RI?

Embora as modificações do RI estejam se tornando mais raras em decorrência da nova flexibilidade do RI introduzida por AWS, sua organização ainda pode ter instâncias reservadas que foram modificadas e será necessário trazer os dados de modificação do RI para Apptio. Por que essa etapa é necessária? Quando ocorre uma modificação, o site AWS cria um novo registro de compra de RI para os novos RIs criados como resultado da modificação e atualiza a data final do registro de compra de RI original de modo que ele expire na data da modificação. AWS não atualiza o custo inicial no registro de compra do RI original, nem o site AWS inclui um valor proporcional no custo inicial do novo registro de compra do RI (ou registros, se a modificação criar vários RIs). Portanto, quando os RIs forem modificados, os novos RIs parecerão artificialmente mais baratos do que os originais, pois nenhum dos custos iniciais será aplicado. As etapas a seguir ajudarão a resolver a situação por meio da ingestão e configuração das modificações do RI em seu ambiente Apptio.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
