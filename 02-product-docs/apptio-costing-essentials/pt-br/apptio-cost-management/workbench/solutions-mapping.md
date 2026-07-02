---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "pt-br"
doc_type: "apptio-cost-management"
title: "Mapeamento de soluções"
breadcrumb:
  - "Costing Essentials"
  - "Ambiente de Trabalho"
source_path: "apptio-cost-management/workbench/solutions-mapping.html"
images:
  - "resources/images/studio_images/sm-1_1145x703.png"
  - "resources/images/studio_images/sm-2_1088x621.png"
  - "resources/images/studio_images/sm-3_932x541.png"
  - "resources/images/studio_images/sm-5_937x255.png"
  - "resources/images/studio_images/sm-6_849x499.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Mapeamento de soluções

Use as tabelas editáveis no Solution Mapping para conduzir as alocações das unidades de negócios de custo OpEx/CapEx.

## Mapeamentos de categorias de negócios

Fornece a capacidade de definir as alocações de custos de serviço para consumidores empresariais, no nível de tipos de solução e categorias de solução.

- As Ofertas de Serviços para Crianças dentro de cada combinação de Tipo de Solução de origem + Categoria de Solução serão alocadas à(s) Organização(ões) de destino especificada(s) com base na ponderação definida
- Organization Id representa a ID exclusiva de cada consumidor empresarial
- O Business Consumer representará
- Uma unidade de negócios ou
- Um departamento com uma unidade de negócios
- Ponderação
- Talvez uma alocação de 100% (insira "1") ou dividida entre vários consumidores (unidades de negócios/departamentos)

![mapeamento da categoria de negócios da solução](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/sm-1_1145x703.png)

## Ofertas

Oferece a capacidade de gerenciar a lista de aplicativos, produtos e/ou ofertas de serviços disponíveis em seu catálogo de serviços, para alocações de custos subsequentes.

Os usuários do IDP devem verificar/atualizar os principais metadados de suas ofertas de serviços, incluindo: Método de alocação, entrega, uso estimado de infraestrutura, tipo de oferta, objetivo de investimento, proprietário de TI, proprietário de negócios, unidade de negócios principal, custo médio unitário e finalidade.

O uso estimado de infraestrutura da oferta será usado para definir a divisão percentual (%) entre infraestrutura e plataforma. Cada linha da oferta deve ser fornecida apenas com o uso estimado de infraestrutura para definir a porcentagem (%) dividida para a infraestrutura. O uso estimado da plataforma será derivado do uso estimado da infraestrutura definido.

Por exemplo: Se o uso estimado da infraestrutura tiver sido definido como 0.6 (60%) para a oferta Acme.com, o uso estimado da plataforma será definido como 0.4 (40%) com a diferença entre o uso estimado da infraestrutura 0.6 (60%) e o Total 1 (100%)

## Métodos de alocação

- O método Direct Allocation ativa a coluna Direct Allocation, que será 1 por padrão e deverá ter apenas uma linha.
- O método Percent Split habilita a coluna Percent Split e deve ter 2 ou mais linhas com ponderação relativa atribuída.
- O método Volume Split ativa a coluna Volume Split e deve ter 2 ou mais linhas com volumes atribuídos.
- O método Weighted Estimated Usage ativa as colunas % Headcount Usage e User Weighting e deve ter 2 ou mais linhas.

![guia ofertas de soluções](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/sm-2_1088x621.png)

## Mapeamentos de ofertas

As ofertas representam os aplicativos, produtos ou serviços usados pela organização e podem ser alocadas direta ou indiretamente com base no método de alocação e nas entradas dessa tabela. Mapeie cada linha da oferta de solução para uma ou mais IDs de organização e defina o método de alocação.

![guia de mapeamento de ofertas de soluções](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/sm-3_932x541.png)

## Mapeamentos perdidos

Use essa tabela para verificar se alguma linha de oferta está faltando atribuições para Soluções. Como alternativa, selecione (Em branco) no divisor Nome do centro de custo na guia Mapeamentos de soluções.

![guia de mapeamento perdido](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/sm-5_937x255.png)

## Volumes

Fornece a capacidade de especificar os volumes estimados ou reais de cada ID de oferta (se aplicável), com base nas informações disponíveis (consumo).

Um exemplo de utilização dessa tabela poderia ser para suas ofertas de soluções para dispositivos de usuários finais, em que você inseriria a unidade de medida (por exemplo, laptop) e definiria o número esperado em cada período. Com base nos custos do modelo, seria possível obter um custo unitário e comparar o volume planejado com o volume real.

![guia de mapeamento de soluções](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/sm-6_849x499.png)
