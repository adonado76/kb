---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "SumIfHierarchy"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/sumifhierarchy.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug346.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SumIfHierarchy

**Aplica-se a** : TBM Studio 12.0, 12.1

A função SumIfHierarchy é usada para calcular o custo de um serviço com base no custo de seus subserviços. A função é usada para calcular o valor de uma coluna adicionada a uma tabela de transformação de custo de serviço. A função requer um conjunto, uma hierarquia conhecida que não contenha nenhuma referência circular. A hierarquia pode ter um número ilimitado de níveis.

## Onde usar

Essa função pode ser usada em:

- Definições de datas

## Sintaxe

Para demanda, use a seguinte sintaxe:

`SumIfHierarchy(Service,Consumes,Quantity)`

Para o preço, use a seguinte sintaxe:

`SumIfHierarchy(Consumes,Service,Quantity,BasePrice)`

## Argumentos

*Serviço*

O nome da coluna que contém o nome do serviço.

*Consome*

O nome da coluna que contém o nome do subserviço.

*Quantidade*

O nome da coluna que contém o número de subserviços consumidos pelo serviço.

*BasePrice*

O nome da coluna que contém o preço atribuído aos subserviços.

## Tipo de retorno

Número

## Exemplo

A tabela abaixo ilustra o uso da função SumIfHierarchy para calcular a demanda e o preço do serviço para estações de trabalho. Os preços base são inseridos para cada subserviço, por exemplo, monitor, teclado e mouse. Observe que um preço base não é inserido para o subserviço Standard Software Suite porque ele é composto de outros subserviços, especificamente Microsoft Office, Microsoft Visio e VPN. O custo total das estações de trabalho para desktops e laptops é fornecido nas duas últimas linhas da tabela:

![Exemplo](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug346.png)

A equação da coluna Demanda de serviço é:

`=SumIfHierarchy(Service,Subservice,Quantity)`

A equação para a coluna Preço do serviço é:

```
=SumIfHierarchy(Subservice,Service,Quantity,Base
          Price)
```
