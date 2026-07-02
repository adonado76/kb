---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar alocações simples (um para um)"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Criar alocações"
source_path: "studio/new-uc/howtoguides/build-cost-model/setup-sa.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar alocações simples (um para um)

**Objetivo:** Distribuir os custos de uma tabela de origem para uma tabela de destino utilizando um método de distribuição simples.

**Quando usar:** É necessário alocar custos com base em um atributo mensurável, como número de funcionários, número de servidores, número de usuários ou metragem quadrada. Este é o padrão de alocação mais comum e serve de base para modelos de custos mais complexos.

**Tempo estimado:** 15 a 20 minutos

## Entendendo os tipos de alocação

Antes de criar uma alocação, escolha o tipo que melhor se adapta ao seu caso:

|  |  |  |
| --- | --- | --- |
| **Tipo de alocação** | **Quando usar** | **Exemplo** |
| **Valor ponderado** | Distribuir os custos proporcionalmente com base em uma coluna numérica | Alocar os custos do data center com base no uso da CPU |
| **Consumo** | Comparar o consumo real com a capacidade disponível | Alocar os custos dos serviços com base nas unidades consumidas |
| **Valor padrão** | A tabela de metas contém o valor exato a ser alocado | Alocar custos fixos quando a meta especificar o valor em dólares |
| **Mesmo** | Distribuição igualitária por todas as linhas de destino | Dividir os custos compartilhados igualmente entre os departamentos |

## Passo a passo: Criar uma alocação de valores ponderada

Este procedimento ilustra o padrão de alocação mais comum: distribuir os custos proporcionalmente com base em uma coluna de ponderação.

**Cenário:** Alocar US$ 500.000 em custos de data center entre cinco aplicativos com base no número de servidores de cada um.

**Passos**

1. **Dê uma olhada nas duas tabelas**
   - No Project Explorer, clique com o botão direito do mouse na tabela de origem (por exemplo, “Custos do Datacenter”) e selecione “Check Out”.
   - Repita o procedimento para a tabela de destino (por exemplo, "Aplicativos").
2. **Abra a etapa "Modelo" da tabela de origem**
   - Clique na tabela de origem no Explorador de Projetos.
   - No fluxo de transformação, clique na etapa Modelo.
   - A área de trabalho do modelo é aberta, exibindo o diagrama de Sankey.
3. **Adicionar uma nova alocação**
   - No diagrama de Sankey, clique em “Adicionar alocação” sob o título “Alocações”.
4. **Configure as definições de alocação**
   - **Atribuir:** Selecione as métricas às quais esta atribuição se aplica (por exemplo, Custo, Orçamento).
   - **Procedimento:** Selecione “Valor ponderado” como tipo de alocação.
   - **Para:** Selecione a tabela de destino (por exemplo, "Aplicativos").
5. **Configurar a ponderação**
   - Em “Classificar por”, selecione “Tabela” (a opção mais comum).
   - Selecione a coluna que contém os valores de ponderação (por exemplo, “Número de servidores”).

   Dica: A coluna de ponderação deve conter apenas valores numéricos. Valores não numéricos fazem com que a ponderação seja ignorada, resultando, em vez disso, em uma distribuição uniforme.
6. **Visualizar a alocação**
   - Clique em “Visualizar” para ver como os custos serão distribuídos.
   - Analise a tabela de pré-visualização para verificar se as porcentagens de alocação correspondem às suas expectativas.

   |  |  |  |
   | --- | --- | --- |
   | **Aplicativo** | **Número de servidores** | **Valor da alocação** |
   | Aplicativo A | 50 | US$ 125.000 (25%) |
   | Aplicativo B | 130 | $200.000 (40%) |
   | Aplicativo C | 30 | US$ 75.000 (15%) |
   | Aplicativo D | 25 | US$ 62.500 ( 12.5 %) |
   | Aplicativo E | 15 | US$ 37.500 ( 7.5 %) |
   | **Total** | **200** | **US$ 500.000** |
7. **Salvar a alocação**
   - Clique em Salvar para adicionar a alocação ao seu modelo.
   - O diagrama de Sankey é atualizado para mostrar a linha de alocação que liga a origem ao destino.

## Resultados esperados

Após salvar:

- O diagrama de Sankey exibe uma linha que vai da tabela de origem até a tabela de destino.
- A largura da linha é proporcional ao valor alocado.
- Ao passar o mouse sobre a linha de alocação, é exibido o valor total alocado.
- A tabela de destino agora contém custos alocados que podem ser transferidos para tabelas subsequentes.

## Explicação das opções de distribuição

**Distribuição uniforme (padrão)**

- Distribui os custos igualmente por todas as linhas de destino.
- Utilize quando não houver fator de ponderação ou quando a distribuição igualitária for intencional.
- Exemplo: US$ 100.000 distribuídos por 5 candidaturas = US$ 20.000 para cada uma.

**Peso por**

- Distribui os custos proporcionalmente com base em uma coluna da tabela, uma métrica ou outro fator determinante.
- Exemplo: US$ 100.000 alocados a aplicativos ponderados pelo número de usuários.

**Relação entre dados**

- Distribui os custos pelas linhas correspondentes com base em pares de valores de colunas.
- Utilize quando a fonte e o destino compartilham uma chave comum (por exemplo, Região, Departamento).
- Exemplo: Custos do data center regional alocados apenas às aplicações na mesma região.

## Armadilhas comuns

|  |  |  |
| --- | --- | --- |
| **Problema** | **Sintoma** | **Solução** |
| Coluna de ponderação não numérica | Os custos são distribuídos uniformemente, em vez de por peso | Verifique se há valores de texto, espaços em branco ou caracteres especiais na coluna de ponderação |
| Valores de ponderação negativos | A alocação falha com um erro | Valores negativos impedem a alocação. Use valores absolutos ou segmente os dados. |
| Peso zero para todas as linhas | Ocorre uma distribuição uniforme | Certifique-se de que pelo menos algumas linhas do conjunto-alvo tenham valores de ponderação diferentes de zero |
| A mesa não foi reservada | Não é possível salvar a alocação | Verifique as tabelas de origem e de destino antes de configurar |

**Tópico principal:** [Criar alocações](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
