---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Componente CTF - Unidades de Trabalho: instalar e configurar"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-laborunits-component.html"
images:
  - "resources/images/ct_images/laborunits_configure_labor_from_luke.png"
  - "resources/images/ct_images/laborunits_internal_headcount.png"
  - "resources/images/ct_images/laborunits_labor_allocation.png"
  - "resources/images/ct_images/laborunits_other_labor_allocation.png"
  - "resources/images/ct_images/laborunits_sample_data.png"
  - "resources/images/ct_images/laborunits_time_tracking.png"
  - "resources/images/ct_images/laborunitsmodel.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Componente CTF - Unidades de Trabalho: instalar e configurar

Use o componente CTF - Labor Units para integrar o modelo Agile Insight Headcount em Costing Standard.

Aplica-se a: TBM Studio 12.8 e posterior, com o modelo v107 e posterior

## Introdução

O modelo Labor Units é instalado com o componente CTF - Labor Units e se integra ao modelo Agile Insights Headcount para alocar mão de obra em um modelo operacional de TI de projeto, ágil ou híbrido. A dimensão do efetivo de mão de obra existente usa o modelo de unidades de mão de obra, se estiver instalado. Se o modelo de unidades de mão de obra não estiver instalado, será usado o número de funcionários da mão de obra dos dados mestre de mão de obra.

Para organizações totalmente ágeis, o modelo de unidades de trabalho faz o seguinte:

- Aloca adequadamente as despesas de mão de obra de TCO de aplicativos e produtos do modelo Costing Standard
- Substitui o objeto Agile Labor
- Requer a alteração de determinadas alocações (como mão de obra para aplicativos)
- Permite que você modele o trabalho até aplicativos e produtos em ambientes de desenvolvimento em cascata e ágil

O componente Unidades de mão de obra permite alocar o efetivo de mão de obra entre mão de obra interna e externa e até projetos e aplicativos para proporcionar uma melhor experiência de relatório ao visualizar o efetivo de mão de obra. Como resultado, o número total de funcionários é informado corretamente por projeto e aplicativo. Além disso, essa nova camada de alocação cria um relatório mais preciso dos funcionários que realizam trabalhos em várias subárvores de recursos de TI.

AVISO

Sem a instalação desse componente, os relatórios de mão de obra personalizados podem não atualizar as dimensões do Headcount de mão de obra, resultando em um comportamento inesperado.

## Sobre o componente

A base do modelo é o objeto Labor. Os drivers desse objeto são Internal Headcount e External Headcount, que obtêm dados dos dados mestre da mão de obra. O objeto Labor impulsiona os objetos Time Tracking e Other Labor Allocations. A alocação entre esses objetos é ponderada pelos dados mestre de Outras alocações de mão de obra.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/laborunitsmodel.png)

## Métricas

As seguintes métricas estão instaladas:

- Drivers de número de funcionários internos e externos
- Unidades de trabalho

## Conjunto de dados mestre

O conjunto de dados mestre Other Labor Allocations (Outras alocações de mão de obra) está instalado.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/laborunits_other_labor_allocation.png)

## Colunas

As colunas a seguir estão incluídas no conjunto de dados mestre:

- Identificação do trabalho
- Metadados do OID
- Torre de recursos de TI
- Subtracção de recursos de TI
- Fator de ponderação

## Amostra de dados de apoio

Mapeamento de torres de recursos de mão de obra para TI:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/laborunits_sample_data.png)

## Novo campo

Um novo campo foi adicionado aos dados mestre de mão de obra para separar o número de funcionários internos do número de funcionários externos: O trabalho interno é

## Configuração

As instruções a seguir pressupõem que o site Costing Standard já esteja instalado.

1. Em TBM Studio, vá para Projetos > Componentes e clique em **CTF - Unidades de trabalho** para instalar o componente Unidades de trabalho. Os seguintes drivers estão instalados:
   - Número de funcionários internos
   - Número de funcionários externos

   Esses drivers extraem automaticamente os valores de headcount dos dados mestre de mão de obra para preencher os modelos de headcount interno e unidades de mão de obra

   .![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/laborunits_internal_headcount.png)

   Quando os drivers de unidade são preenchidos, o modelo de unidades de trabalho tem a seguinte aparência:

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/laborunits_labor_allocation.png)
2. Vá para **Etapas** **Unidades de trabalho** **modelo**.
3. Para aproveitar a ID de mão de obra e alocar outras alocações de mão de obra para mão de obra, defina De para mão de obra onde Verificar para TT = '0'.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/laborunits_configure_labor_from_luke.png)

   Observação: a instalação do componente Unidades de trabalho em um projeto existente pode resultar em uma alocação entre as Torres de recursos de trabalho e de TI. Se isso ocorrer, exclua a alocação no modelo Unidades de mão de obra e, em vez disso, crie uma alocação de mão de obra para Outras alocações de mão de obra e, em seguida, de Outras alocações de mão de obra para Torres de recursos de TI.
4. Selecione **Weight By (Ponderar por** ), depois **Table Column (Coluna da tabela** ) e **Weighting Factor (Fator de ponderação** ).
5. Para Relacionamento de dados, insira **ID do trabalho** para a **coluna de origem** e **a coluna de destino**.
6. Para o modelo restante, aproveite as alocações existentes do modelo de custos. Se houver alocações personalizadas, selecione as seguintes métricas a serem aplicadas a essa alocação para rastrear o número de funcionários:
   - Número de funcionários internos
   - Número de funcionários externos
   - Unidades de trabalhop

     ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/laborunits_time_tracking.png)

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
