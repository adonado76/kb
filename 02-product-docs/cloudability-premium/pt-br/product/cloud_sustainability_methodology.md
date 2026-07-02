---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Metodologia de sustentabilidade da nuvem"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Relatório de sustentabilidade na nuvem"
source_path: "product/cloud_sustainability_methodology.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Metodologia de sustentabilidade da nuvem

Antes de mergulhar na metodologia usada para calcular as emissões de carbono, é importante entender primeiro os dois principais tipos de emissões envolvidas. As pegadas de carbono geralmente se originam de duas fontes principais: emissões operacionais e emissões incorporadas.

**Emissões operacionais**

As emissões operacionais resultam da operação diária da infraestrutura de nuvem. Essas emissões são geradas principalmente pela eletricidade consumida pelos data centers em nuvem para alimentar e resfriar servidores, equipamentos de rede e dispositivos de armazenamento que hospedam serviços em nuvem.

**Emissões incorporadas**

As emissões incorporadas (ou embutidas) referem-se à quantidade de carbono emitida durante a fabricação, o transporte e o descarte de dispositivos de hardware.

Para estimar as emissões incorporadas na nuvem, calculamos a fração do total de emissões incorporadas que corresponde ao uso ou à carga de trabalho do cliente. Por exemplo, se um usuário utiliza apenas um subconjunto de CPUs virtuais disponíveis em um servidor físico, uma quantidade proporcional de emissões incorporadas é alocada para representar esse uso.

Além disso, as emissões são classificadas em duas categorias: diretas e indiretas.

- **Emissões diretas** : Liberadas diretamente de fontes pertencentes ou controladas pela organização.

- **Emissões indiretas** : Resultam das atividades da organização, mas são geradas por fontes que não são de sua propriedade ou diretamente controladas por ela.

***Novamente, essas emissões são categorizadas em escopos de emissão de carbono.***

- **Escopo 1 (Emissões diretas):** Emissões geradas a partir de fontes pertencentes ou controladas pela empresa.
  - Os exemplos incluem a combustão de combustível em geradores de propriedade da empresa, processos de fabricação no local e caldeiras de propriedade da empresa.
- **Escopo 2 (Emissões indiretas):** Emissões geradas pelo consumo de fontes de energia adquiridas, como eletricidade, vapor ou gás.
  - Exemplos incluem a compra de eletricidade para prédios de escritórios ou vapor/gás para processos industriais.
- **Escopo 3 (Emissões indiretas):** Emissões que ocorrem como consequência das atividades da empresa, mas que são geradas em sua cadeia de suprimentos. Exemplo: Emissões operacionais de serviços em nuvem, como máquinas virtuais e armazenamento fornecidos por CSPs.

Como clientes de serviços em nuvem, consumimos recursos oferecidos pelos CSPs sem controlar a geração de energia subjacente. Como não produzimos nem compramos eletricidade diretamente (isso é feito pelas CSPs), as emissões operacionais resultantes do uso da nuvem são classificadas no Escopo 3.

Observação: *o site Cloudability considera as emissões operacionais e incorporadas do Escopo 3 e as publica por meio das métricas de sustentabilidade em sua plataforma.*

**Metodologia de cálculo - Emissões operacionais**

Cloudability são baseadas na metodologia Cloud Carbon Footprint (CCF), aprimorada com fatores adicionais, como dados de utilização real e modelagem de consumo de energia baseada em aprendizado de máquina.

Essa abordagem usa uma metodologia de baixo para cima, em que as emissões de recursos individuais são calculadas separadamente e, em seguida, agregadas para representar as emissões totais relacionadas à nuvem de uma organização.

**Fórmula: Emissões de carbono estimadas (CO₂e) = Consumo de energia por hora × Eficácia do uso de energia (PUE) × Emissões da rede × Horas de uso**

Em que:

- **Consumo de energia por hora:** Calculado usando modelos de ML treinados em especificações de máquinas e métricas de utilização.

- **Eficácia do uso de energia (PUE)** : Uma medida de eficiência energética do data center que é publicada pelos CSPs.

- **Emissões da rede** : Carbono emitido por unidade de eletricidade gerada (média anual).

- **Horas de uso** : Total de horas de operação da máquina.

**Fontes de dados**

|  |  |
| --- | --- |
| Conjunto de dados | Origem |
| Eficácia do uso de energia (PUE) | GCP PUE – Google Cloud; AWS / Azure – Pegada de carbono na nuvem; OCI – Oracle Infraestrutura em nuvem |
| Emissões da rede | EEA, EPA, Our World in Data e Cloud Carbon Footprint |
| Horas de uso | Derivado de dados de custo fornecidos por cada provedor de nuvem |
| Utilização | Com base nos dados de utilização coletados por Cloudability |
| Especificações da máquina | Com base nos dados de preços e descrição de recursos coletados por Cloudability |

**Metodologia de cálculo - Emissões incorporadas**

As emissões incorporadas são calculadas usando a metodologia Cloud Carbon Footprint.

**Fórmula: Emissões incorporadas = TE × ( TR1 / EL) × (RR / TR2 )**

Onde

- **TR1** = Tempo reservado, o período de tempo em que o hardware está reservado para uso pelo software (a quantidade de tempo em que uma determinada instância de computação estava em execução)

- **EL** = Expected Lifespan, o tempo previsto para a instalação do equipamento (4 anos escolhido pela equipe da Teads) [(Dell PowerEdge R740 Full Lifecycle Assessment)](https://www.delltechnologies.com/asset/en-us/products/servers/technical-support/Full_LCA_Dell_R740.pdf "(Abre em uma nova guia ou janela)")

- **RR** = Recursos reservados, o número de recursos reservados para uso pelo software (número de vCPUs da instância em questão)

- **TR2** = Total Resources, o número total de recursos disponíveis (a maior instância vCPUs para a família em questão)

- **TE** = Total de emissões incorporadas, a soma das emissões da avaliação do ciclo de vida (LCA) para todos os componentes de hardware. TE que estamos calculando com a ajuda do aprendizado de máquina.

**Emissões totais incorporadas (TE)**

Cloudability segue a metodologia Cloud Carbon Footprint (CCF) para calcular as Emissões Incorporadas, as emissões de carbono associadas à fabricação, ao transporte e ao processamento no fim da vida útil do hardware de nuvem, como servidores, redes e equipamentos de armazenamento.

Embora a estrutura do CCF forneça uma base sólida, seus dados de emissões incorporadas disponíveis publicamente não foram atualizados desde 2022. Como resultado, os dados dos tipos de máquinas e gerações de hardware mais recentes dos principais provedores de serviços em nuvem (CSPs) podem estar incompletos. Para garantir uma cobertura abrangente e atualizada, a equipe do Cloudability desenvolveu um modelo baseado em aprendizado de máquina que estima o total de emissões incorporadas (TE) para todos os tipos de máquinas disponíveis em AWS, Azure e Google Cloud. Esse aprimoramento permite que o site Cloudability forneça estimativas de carbono incorporado mais precisas, atuais e confiáveis, apoiando as organizações na tomada de decisões de sustentabilidade informadas.

**Exemplo** : Para a família de instâncias m5, a maior máquina ( m5.24xlarge ) tem 96 vCPUs e um total de emissões incorporadas (TE) de 1610.79 kgCO₂e com uma vida útil de 4 anos. Se uma instância do m5.xlarge (4 vCPUs ) for executada por 30 minutos, suas emissões incorporadas serão iguais a 1610.79 × ( 0.5 / 35.040) × (4 / 96) = 0.00134 kgCO₂e.

**Benefícios dessa metodologia**

- **Cobertura abrangente:** Captura emissões operacionais e incorporadas, oferecendo uma visão completa do impacto do carbono relacionado à nuvem.

- **Consistência entre nuvens:** utiliza uma metodologia unificada entre os provedores de serviços em nuvem ( AWS, Azure, GCP e OCI) para permitir uma comparação precisa.

- **Utilização real:** Utiliza métricas de utilização real e modelagem baseada em aprendizado de máquina para melhorar a precisão das estimativas de carbono operacional e incorporado.

- **Estimativa atualizada:** Aborda as lacunas de dados em estruturas públicas (como CCF) aplicando modelos de ML para estimar valores para gerações de hardware mais recentes.

- **Visibilidade granular:** Fornece insights de emissões no nível do ID do recurso, com roll-ups por região, serviço, fornecedor ou período de tempo (mês, ano, ano até a data, etc.).

- **Perspectiva de ciclo de vida:** Contabiliza as emissões em todo o ciclo de vida do hardware, desde a fabricação e operação até o descomissionamento.

- **Suporte a decisões:** Permite a correlação de tendências de custo e emissões para impulsionar operações de nuvem sustentáveis e econômicas.

**Tópico principal:** [Relatórios de sustentabilidade na nuvem](../product/cld-sustainability-reporting.html)
