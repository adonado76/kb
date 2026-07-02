---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Compreender os compromissos utilizando os relatórios nativos d Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Guia para a funcionalidade de compromisso avançado"
source_path: "product/understanding_commitments_using_cloudability_native_reporting.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Compreender os compromissos utilizando os relatórios nativos d Cloudability

Os Planos de Poupança (SP) são o novo instrumento de desconto lançado pelo AWS. Este tópico explica como os planos de economia diferem do desconto tradicional com instâncias reservadas (RI) e também fornece informações detalhadas sobre as implicações de faturamento. Você pode usar a dimensão *Tipo de locação*, juntamente com outras dimensões e métricas regulares sobre o uso do SP.

**Comparação de RIs**

- As taxas de desconto são idênticas entre os SPs de instância do EC2 e os RIs padrão, e entre os SPs de computação e os RIs conversíveis.
- Com os planos de economia, você pode assumir um compromisso acima do nível do serviço e regional (no caso de planos de economia de computação). Isso tem implicações importantes para a forma como você planeja e controla sua conta de nuvem.
- Em vez de se comprometer com *horas de instância*, agora você está se comprometendo com *horas em dólares*. Você pode verificar se os dólares por hora que você está comprometendo são os dólares após o desconto do Plano de Poupança ou o custo líquido.

**Análise aprofundada das implicações de faturamento**

As principais diferenças entre a forma como os Planos de Poupança e os RIs são tratados na faturação detalhada (ficheiro CUR) são mencionadas aqui:

- As horas de uso cobertas pelos SPs são amplamente representadas como horas sob demanda.
  - A descrição do item parece ser **US$ 0.156 por On Demand Linux**...
  - As métricas de custo padrão Custo não combinado e Taxa não combinada baseiam-se nos valores On Demand. Isso contrasta com as IR, onde os números são bastante reduzidos.
- Embora os custos recorrentes para RIs (no caso de sem adiantamento ou adiantamento parcial) aparecessem como um único item no início de cada mês para os SPs, os custos recorrentes são divididos em itens individuais para cada hora do mês. Todas as linhas do mês são carregadas no início do mês, o que significa que você tem relatórios de custos futuros no arquivo CUR.
- Existe um novo tipo de linha de faturamento chamado **Negação,** que permite que as métricas de custo regulares representem com precisão sua fatura mensal.

**Caso de uso**

Vamos ver como isso se aplica a um SP consumido ao longo de uma hora. Este é um exemplo muito simples do arquivo CUR para um Plano de Economia de Instância sem pagamento inicial EC2 :

![Ícone de notas](../images/understanding_how_aws_savingsmceclip0.jpg)**Observação:**

As duas primeiras linhas são as horas reais de uso da instância do EC2 que consomem totalmente o SP para aquela hora.

**O cenário**

O custo não combinado resulta na taxa recorrente, que é a nossa taxa com desconto. Isso é resultado da linha de negação negar completamente as duas linhas de uso. No entanto, nem a negação nem as linhas recorrentes incluem o ID do recurso ou informações importantes, como tags. Isso significa que, se você estiver alocando custos com base em tags ou IDs de recursos, obterá o custo *sob demanda* para as horas cobertas por SPs e custos bastante reduzidos para as horas cobertas por RIs. O que fazer?

**A solução**

Cloudability oferece duas maneiras simples de alocar custos de forma justa em um mundo onde RIs e SPs estão afetando os itens de custo. A métrica **Custo (Lista)** elimina completamente o impacto de qualquer desconto baseado em compromissos, removendo assim a natureza imprevisível dos descontos aplicados. A métrica **Custo (amortizado)** permite que você repasse os benefícios para suas equipes, garantindo um comportamento consistente entre RIs e SPs. Essa métrica pode ser usada em toda a Cloudability e associa o custo total (incluindo o componente inicial) de RIs e SPs no nível dos recursos. Isso permite um cálculo completo do custo real.

**Mais informações**

- Para conhecer o comportamento histórico das RIs, consulte [Entendendo as métricas de custo d AWS : você tem uma métrica de custo real?](https://www.ibm.com/links?url=https%3A%2F%2Fwww.apptio.com%2Femerge%2Funderstanding-aws-cost-metrics-do-you-have-a-true-cost-metric%2F "(Abre em uma nova guia ou janela)")
- Para saber mais sobre relatórios, consulte [Relatório personalizado](https://www.ibm.com/links?url=https%3A%2F%2Fapp.cloudability.com%2Flogin%23%2Freports%2Freport%3Fdimensions%3Dreservation_identifier%26dimensions%3Denhanced_service_name%26dimensions%3Dtransaction_type%26dimensions%3Doffering_class%26end_date%3D23%3A59%3A59%26filters%3Dlease_type%3D%3Dsavings%2Bplan%26limit%3D50%26metrics%3Dunblended_cost%26metrics%3Dtotal_amortized_cost%26metrics%3Dpublic_on_demand_cost%26order%3Ddesc%26sort_by%3Dunblended_cost%26start_date%3D7%2Bdays%2Bago%2Bat%2B00%3A00%3A00%26title%3Dcustom%2Breport "(Abre em uma nova guia ou janela)").

**Tópico principal:** [Guia para a funcionalidade de compromisso avançado](../product/guide_to_advanced_commitment_functionality.html)
