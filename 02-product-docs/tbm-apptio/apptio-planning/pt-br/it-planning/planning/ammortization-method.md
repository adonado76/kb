---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Métodos de amortização"
breadcrumb:
  - "Planning"
  - "Planejamento de contratos"
source_path: "it-planning/planning/ammortization-method.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Métodos de amortização

A amortização de contratos é o processo de distribuição do custo de um contrato em vários períodos.

## Visão geral

Apptio O planejamento suporta cinco métodos de amortização, cada um com casos de uso específicos para lidar com custos de contrato:

1. [Linha reta Períodos pares](#amormeth__sleven)
2. [Linha reta usando dias do calendário](#amormeth__slcal)
3. [Linha reta ratear primeiro e último](#amormeth__slfirst)
4. [Linha reta por duração](#amormeth__sldur)
5. [Amortização manual](#amormeth__slamor)

Apptio O planejamento também suporta **extensões de contrato**, permitindo que os custos continuem além da data final do contrato original. As extensões podem aplicar novas taxas e, opcionalmente, ser compostas ao longo do tempo.

Os casos de uso de cada método de amortização estão descritos abaixo:

## 1. Linha reta Períodos pares

Distribui o custo total do contrato uniformemente em todos os períodos, independentemente do número de dias em cada período. Um período é considerado completo mesmo que o contrato cubra apenas um único dia dentro dele.

**Exemplo:**

Data de início do contrato: 15 de janeiro de 2025

Data de término do contrato: 15 de junho de 2025

Duração: 6 meses

Valor: $6,000

**Sem extensão:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Fev** | **Mar** | **Abr** | **Mai** | **Jun** | **Jul** | **Ago** | **Set** | **Out** | **Nov** | **Dez** |
| $1.000 | $1.000 | $1.000 | $1.000 | $1.000 | $1.000 |  |  |  |  |  |  |

Jan-Jun = $6000 / 6 meses = $1000

**Com extensão até o final do ano:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Fev** | **Mar** | **Abr** | **Mai** | **Jun** | **Jul** | **Ago** | **Set** | **Out** | **Nov** | **Dez** |
| $1.000 | $1.000 | $1.000 | $1.000 | $1.000 | $1.000 | $1.000 | $1.000 | $1.000 | $1.000 | $1.000 | $1.000 |

## 2. Linha reta usando dias do calendário

Distribui o custo proporcionalmente ao número de dias em cada mês durante o contrato. Os períodos com mais dias recebem uma parcela maior, com as datas de início e término contadas.

**Exemplo:**

Data de início do contrato: 15 de janeiro de 2025

Data de término do contrato: 15 de junho de 2025

Duração: 152 dias

Valor: $6,000

**Sem extensão:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Fev** | **Mar** | **Abr** | **Mai** | **Jun** | **Jul** | **Ago** | **Set** | **Out** | **Nov** | **Dez** |
| $671 | $1.105 | $1.224 | $1.184 | $1.224 | $592 |  |  |  |  |  |  |

Janeiro = $6000 \* 17 dias / 152 dias = $671

Fev = $6000 \* 28 dias / 152 dias = $1.105

Março = $6000 \* 31 dias / 152 dias = $1.224

Abril = $6000 \* 30 dias / 152 dias = $1.184

Maio = $6000 \* 31 dias / 152 dias = $1.224

Junho = $6000 \* 15 dias / 152 dias = $592

**Com extensão até o final do ano:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Fev** | **Mar** | **Abr** | **Mai** | **Jun** | **Jul** | **Ago** | **Set** | **Out** | **Nov** | **Dez** |
| $671 | $1.105 | $1.224 | $1.184 | $1.224 | $1.184 | $1.224 | $1.224 | $1.184 | $1.224 | $1.184 | $1.224 |

Janeiro = $6000 \* 17 dias / 152 dias = $671

Fev = $6000 \* 28 dias / 152 dias = $1.105

Março = $6000 \* 31 dias / 152 dias = $1.224

Abril = $6000 \* 30 dias / 152 dias = $1.184

Maio = $6000 \* 31 dias / 152 dias = $1.224

Jun = ($6000 \* 15 dias / 152 dias) + ($6000 \* 15 dias / 152 dias) = $1.184

Julho = $6000 \* 31 dias / 152 dias = $1.224

Agosto = $6000 \* 31 dias / 152 dias = $1.224

Set = $6000 \* 30 dias / 152 dias = $1.184

Outubro = $6000 \* 31 dias / 152 dias = $1.224

Nov = $6000 \* 30 dias / 152 dias = $1.184

Dez = $6000 \* 31 dias / 152 dias = $1.224

## 3. Linha reta ratear primeiro e último

Rateia o primeiro e o último períodos de um contrato pelo número de dias e, em seguida, distribui uniformemente o custo restante pelos períodos intermediários.

**Exemplo:**

Data de início do contrato: 15 de janeiro de 2025

Data de término do contrato: 15 de junho de 2025

Duração: 152 dias

Valor: $6,000

**Sem extensão:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Fev** | **Mar** | **Abr** | **Mai** | **Jun** | **Jul** | **Ago** | **Set** | **Out** | **Nov** | **Dez** |
| $671 | $1.184 | $1.184 | $1.184 | $1.184 | $592 |  |  |  |  |  |  |

Janeiro = $6000 \* 17 dias / 152 dias = $671

Fevereiro = $6.000 - $671 - $592 / 4 meses = $1.184

Março = $6000 - $671 - $592 / 4 meses = $1.184

Abril = $6000 - $671 - $592 / 4 meses = $1.184

Maio = $6000 - $671 - $592 / 4 meses = $1.184

Junho = $6000 \* 15 dias / 152 dias = $592

**Com extensão até o final do ano:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Fev** | **Mar** | **Abr** | **Mai** | **Jun** | **Jul** | **Ago** | **Set** | **Out** | **Nov** | **Dez** |
| $671 | $1.184 | $1.184 | $1.184 | $1.184 | $1.184 | R$ 1.214 | R$ 1.214 | R$ 1.214 | R$ 1.214 | $1.184 | $1.194 |

Contrato original: 15 de janeiro a 15 de junho de 2025

Primeira extensão: 16 de junho a 15 de novembro de 2025

Segunda prorrogação: 16 de novembro de 2025 - 16 de abril de 2026

Janeiro = $6000 \* 17 dias / 152 dias = $671

Fevereiro = $6.000 - $671 - $592 / 4 meses = $1.184

Março = $6000 - $671 - $592 / 4 meses = $1.184

Abril = $6000 - $671 - $592 / 4 meses = $1.184

Maio = $6000 - $671 - $592 / 4 meses = $1.184

Jun = ($6000 \* 15 dias / 152 dias) + ($6000 \* 15 dias / 152 dias) = $1.184

Jul = $6000 - $671 - $592 / 4 meses = $1.184

Agosto = $6000 - $671 - $592 / 4 meses = $1.184

Set = $6000 - $671 - $592 / 4 meses = $1.184

Outubro = $6000 - $671 - $592 / 4 meses = $1.184

Nov = ($6000 \* 15 dias / 152 dias) + ($6000 \* 15 dias / 152 dias) = $1.184

Dez = $6000 - $592 - $631 / 4 meses = $1.194

## 4. Linha reta por duração

Verifica se as datas de início e término do contrato cobrem totalmente os períodos em que se enquadram. Se ambos forem períodos completos, o custo será dividido igualmente entre todos os períodos. Se a data de início ou de término não cobrir totalmente o período final, o último período será atribuído a 0 e o custo será distribuído uniformemente pelos períodos restantes.

**Exemplo:**

Data de início do contrato: 15 de janeiro de 2025

Data de término do contrato: 15 de junho de 2025

Duração: 152 dias = 5 meses

Valor: $6,000

**Sem extensão:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Fev** | **Mar** | **Abr** | **Mai** | **Jun** | **Jul** | **Ago** | **Set** | **Out** | **Nov** | **Dez** |
| $1.200 | $1.200 | $1.200 | $1.200 | $1.200 |  |  |  |  |  |  |  |

Janeiro a maio = US$ 6.000 / 5 meses = US$ 1.200

**Com extensão até o final do ano:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Fev** | **Mar** | **Abr** | **Mai** | **Jun** | **Jul** | **Ago** | **Set** | **Out** | **Nov** | **Dez** |
| $1.200 | $1.200 | $1.200 | $1.200 | $1.200 | $1.200 | $1.200 | $1.200 | $1.200 | $1.200 | $1.200 | $1.200 |

Jan-Dez = $6000 / 5 meses = $1.200

## 5. Amortização manual

Permite que os usuários insiram diretamente os valores de amortização para cada período, em vez de depender de métodos calculados pelo sistema. Isso proporciona total flexibilidade para definir exatamente como os custos devem ser distribuídos entre os períodos.

Se a opção **Atualizar automaticamente o total do contrato** estiver ativada no Perfil da empresa, a coluna Valor somará automaticamente o total com base nos valores de amortização inseridos para cada período.
