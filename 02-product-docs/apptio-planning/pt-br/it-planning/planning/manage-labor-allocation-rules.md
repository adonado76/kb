---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Regras de alocação de mão de obra"
breadcrumb:
  - "Planning"
  - "Planejamento trabalhista"
source_path: "it-planning/planning/manage-labor-allocation-rules.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Regras de alocação de mão de obra

Observação: as funções de administrador ou responsável pelo processo orçamentário são necessárias para configurar as regras de alocação de mão de obra.

As Regras de alocação de mão de obra permitem que você defina como os custos básicos de mão de obra (salário, benefícios, encargos) são distribuídos entre departamentos, centros de custo e contas GL. Quando uma linha de mão de obra se qualifica para uma regra, o sistema cria uma entrada financeira correspondente (ou entradas) aplicando a lógica da regra.

Essas regras ajudam a modelar **o custo total da mão de obra** e a garantir que as despesas sejam alocadas ao departamento, centro de custos e conta corretos, com base no número de funcionários planejados.

## Métodos de amortização

|  |  |  |
| --- | --- | --- |
| **Método** | **O que ele faz** | **Exemplo** |
| **Linha reta Períodos pares** | Distribui o custo uniformemente por todos os períodos em que o recurso está ativo ou orçado. | Uma regra gera US$ 12.000 anualmente; por 12 meses cada período = US$ 1.000. |
| **Linha reta usando dias do calendário** | Distribui o custo proporcionalmente com base nos dias do calendário por período. | uS$ 12.000 em 12 meses, fevereiro tem 28 dias → custo para fevereiro = (28/365)\*12.000 ≈ US$ 920. |
| **Linha reta usando dias úteis** | Distribui os custos usando o calendário de trabalho definido (por exemplo, excluindo finais de semana/feriados). | uS$ 12.000 anuais se 260 dias úteis → custo diário = US$ 46.15; março tem 22 dias úteis → US$ 1.015. |
| **Linha reta com base em dias do calendário e período fixo** | Distribui os custos com base no número de dias corridos de cada período fiscal em relação ao ano fiscal completo, sem ratear as datas de início ou término do contrato de trabalho. | Um valor anual **de** US$ 12.000 distribuído ao longo de um ano de 365 dias: fevereiro tem 28 dias, portanto, o custo para fevereiro = **(28 / 365) × 12.000 ≈ US$ 920**, independentemente das datas de início ou término do contrato de trabalho ao longo do ano. |
| **Método linear com base em dias úteis e período fixo** | Distribui os custos com base no número de dias úteis de cada período fiscal, utilizando o calendário de trabalho configurado, sem ratear as datas de início ou término do contrato de trabalho. Volta à distribuição uniforme por período quando os calendários de trabalho são fixos. | Um valor anual **de** US$ 12.000, distribuído por **260 dias úteis,** resulta em um custo diário de aproximadamente **US$ 46.15** Se março tiver **22 dias úteis**, o custo alocado para março = **22 × 46.15 ≈ $1.015**, independentemente das datas de início ou término do contrato de trabalho ao longo do ano. |

## Comportamento importante: Quantidade de funcionários e rateio dos custos de mão de obra

**Quantidade de funcionários**

A quantidade de funcionários **não** é rateada com base **na data de início** ou **na data de término** de um recurso de mão de obra.

- Se um recurso começar ou terminar no meio de um mês, ele ainda será contado como **um FTE (equivalente a tempo integral) d 1.0 e para todo o período, por padrão**.
- Por exemplo, um recurso de mão de obra que começa em **15 de janeiro** contará como **1 FTE para o mês inteiro de janeiro**, a menos que você ajuste manualmente o número de funcionários.

**Cálculo de custos vs. número de funcionários**

Os métodos de amortização afetam a forma como os custos de mão de obra são distribuídos ao longo do tempo, mas não afetam as quantidades de pessoal na guia Mão de obra.

- **O custo de mão de obra** é sempre calculado da seguinte forma: **Número de funcionários mensal × Taxa mensal**
- A rateio dos custos de mão de obra só é aplicado quando se utilizam os métodos de amortização linear por dias de calendário ou linear por dias úteis.

**Comportamento do método de amortização**

- **Linha reta por períodos iguais**
  - **Não** realiza rateio com base na data ao calcular o custo de mão de obra
  - O número de funcionários é padronizado como **1 FTE para o período**, independentemente da data de início ou término.
  - Os custos com mão de obra são calculados como **Número mensal de funcionários × Taxa mensal.**
  - Os custos são distribuídos uniformemente por todos os períodos em que o recurso de mão de obra está ativo.
  - Exemplo: Um recurso de mão de obra começa em 15 de janeiro com uma taxa mensal de $10.000. Usando a linha reta por períodos iguais, o recurso é contabilizado como um ETI ( 1.0 ) para janeiro, e os US$ 10.000 completos são alocados para janeiro.

    Se você deseja que janeiro reflita um custo parcial do mês, deve ajustar manualmente o número de funcionários (por exemplo, para um FTE d 0.5 ), o que resultaria em um custo de mão de obra de $5.000 para janeiro.
- **Linha reta por dias corridos** e **linha reta por dias úteis**
  - Esses métodos **levam** em consideração o rateio das datas de início e término ao calcular o custo da mão de obra.
  - O número de funcionários ainda é padronizado para **1.0 FTE para o período**, independentemente da data de início ou término.
  - O custo de mão de obra é rateado com base nos dias ativos do recurso dentro do período.
  - Exemplo: usando o mesmo recurso que começa em 15 de janeiro com uma taxa mensal de $10.000, a opção Linear por dias do calendário ou Linear por dias úteis calcula o custo de mão de obra com base nos dias ativos do recurso em janeiro.

    Com 16 dias ativos, o custo de mão de obra em janeiro é de aproximadamente US$ 5.161, embora o número de funcionários permaneça como um FTE e 1.0 e para o período.

Observação: se sua organização precisar representar o número parcial de funcionários ao usar o método de amortização linear por períodos iguais, você pode modelar o número parcial diretamente nas colunas periódicas.

## Configurar regras de alocação de mão de obra

As Regras de alocação de mão de obra definem como os custos de mão de obra são distribuídos entre os departamentos e as contas do GL. Cada item de linha de mão de obra no Apptio Planning começa com uma taxa básica e as regras de alocação aplicam automaticamente a lógica de distribuição - como uma porcentagem da taxa básica ou um valor fixo. Isso garante a precisão dos custos de mão de obra "totalmente onerados" e a alocação correta aos departamentos e contas GL apropriados.

1. Vá para **Configuration → Labor Allocation Rules.**
2. Exporte um modelo ou insira os seguintes campos diretamente na interface do usuário:
   1. **Conta** - O código da conta dos dados de referência da conta. Isso gera uma entrada de despesa para cada linha de mão de obra que atenda às condições da regra.
   2. **Output Value Type (Tipo de valor de saída** ) - Define como o custo é calculado:
      1. **Valor fixo** - Aplica um valor anual fixo.
      2. Percentual **da taxa básica** - Calcula um percentual da taxa básica de mão de obra.
      3. Porcentagem **de outra taxa** - Calcula uma porcentagem da taxa de outro trabalho.
   3. **Excluir do cálculo de mão de obra** - Determina se esse custo está incluído no total do ano fiscal mostrado na guia Mão de obra:
      1. **Verdadeiro (marcado)** - Exclui o custo do total (por exemplo, para cobranças cruzadas ou custos não onerados).
      2. **Falso (desmarcado)** - Inclui o custo no total do ano fiscal.
   4. **Valor** - A porcentagem ou valor fixo a ser aplicado com base no tipo de valor de saída.
   5. **Método de amortização de mão** de obra - Define como o custo é distribuído entre os períodos de tempo (consulte *Métodos de amortização de mão de obra* para obter mais detalhes):
   6. **Straight Line Even Periods (Linha reta para períodos pares** ) - Distribui o custo uniformemente por todos os períodos.
   7. **Linha reta usando dias do calendário** - Distribui o custo proporcionalmente ao número de dias em cada período.
   8. **Straight Line Using Working Days (Linha reta usando dias úteis** ) - Usa o calendário de trabalho definido para ponderar a distribuição de custos.
3. **Importe** o arquivo “ CSV ” preenchido e **publique** as alterações para que as regras de alocação fiquem disponíveis para uso nos planos.

## Exemplos

**Exemplo A – Valor fixo (anual), sem regras de nível do plano**

Este exemplo demonstra como o mesmo valor anual (US$ 2.000) é distribuído usando diferentes métodos de amortização.

Valor fixo (anual) = US$ 2.000, **Data de início:** 15 de janeiro

1. **Método de amortização = Linha reta Períodos pares**

   Taxa mensal: $2.000 ÷ 12 meses = $ 166.67 por mês

   Alocação mensal:

   |  |  |  |  |
   | --- | --- | --- | --- |
   | **Mês** | **Qte** | **Cálculo** | **Quantia** |
   | Janeiro | 1 | ( $2.000 ÷ 12 meses) × 1 FTE | $166.67 |
   | Fevereiro | 1 | ( $2.000 ÷ 12 meses) × 1 FTE | $166.67 |
   | Março | 1 | ( $2.000 ÷ 12 meses) × 1 FTE | $166.67 |
2. **Método de amortização = Linha reta usando dias do calendário**

   Taxa diária: $2.000 ÷ 365 dias = $ 5.48 por dia

   Alocação mensal:

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Mês** | **Qte** | **dias** | **Cálculo** | **Quantia** |
   | Janeiro | 1 | 31 | ((31 - 14 dias) × $ 5.48 ) × 1 FTE | $93.16 |
   | Fevereiro | 1 | 28 | (28 dias × $ 5.48 ) × 1 FTE | $153.44 |
   | Março | 1 | 31 | (31 dias × $ 5.48 ) × 1 FTE | $169.88 |
3. **Método de amortização = Linha reta usando dias úteis**

   Definição do calendário de trabalho: 260 dias úteis

   Taxa diária: $2.000 ÷ 260 dias = $ 7.69 por dia

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Mês** | **Qte** | **Dias úteis** | **Cálculo** | **Quantia** |
   | Janeiro | 1 | 21 | ((21 - 8 dias) × $ 7.69 ) × 1 FTE | $161.49 |
   | Fevereiro | 1 | 19 | (19 dias × $ 7.69 ) × 1 FTE | $146.11 |
   | Março | 1 | 21 | (21 dias × $ 7.69 ) × 1 FTE | $161.49 |

**Exemplo B – Porcentagem da taxa básica, sem regras de nível do plano**

Um funcionário tem uma **Taxa Básica** de **US$ 120.000 por ano** e uma regra de alocação aplica **10% da Taxa Básica** como um custo adicional (por exemplo, benefícios ou despesas gerais).

Alocação anual: US$ 120.000 × 10% = US$ 12.000 por ano, **data de início:** 15 de janeiro

1. **Método de amortização = Linha reta Períodos pares**

   Fórmula: uS$ 12.000 ÷ 12 meses = US$ 1.000 por mês

   |  |  |  |  |
   | --- | --- | --- | --- |
   | **Mês** | **Qte** | **Cálculo** | **Quantia** |
   | Janeiro | 1 | (US$ 12.000 ÷ 12 meses) × 1 FTE | $1.000 |
   | Fevereiro | 1 | (US$ 12.000 ÷ 12 meses) × 1 FTE | $1.000 |
   | Março | 1 | (US$ 12.000 ÷ 12 meses) × 1 FTE | $1.000 |
2. **Método de amortização = Linha reta usando dias do calendário**

   Fórmula: $12.000 ÷ 365 dias = $ 32.88 por dia

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Mês** | **Qte** | **dias** | **Cálculo** | **Quantia** |
   | Janeiro | 1 | 31 | ((31 - 14 dias) × $ 32.88 ) × 1 FTE | $558.96 |
   | Fevereiro | 1 | 28 | (28 dias × $ 32.88 ) × 1 FTE | $920.64 |
   | Março | 1 | 31 | (31 dias × $ 32.88 ) × 1 FTE | $1, 019.28 |
3. **Método de amortização = Linha reta usando dias úteis**

   Definição do calendário de trabalho: 260 dias úteis

   Fórmula: $12.000 ÷ 260 dias = $ 46.15 por dia

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Mês** | **Qte** | **Dias úteis** | **Cálculo** | **Quantia** |
   | Janeiro | 1 | 21 | ((21 - 8 dias) × $ 46.15 ) × 1 FTE | $599.95 |
   | Fevereiro | 1 | 19 | (19 dias × $ 46.15 ) × 1 FTE | $876.85 |
   | Março | 1 | 21 | (21 dias × $ 46.15 ) × 1 FTE | $969.15 |

## Regras de alocação de mão de obra com eficiência de tempo no nível do plano

Observação: é necessário ter a função de administrador ou de responsável pelo processo orçamentário para configurar regras de alocação no nível do plano.

Por padrão, as regras de alocação de mão de obra são mantidas como dados de referência globais, e todos os planos utilizam os mesmos valores de regra ao gerar partidas individuais de despesas com mão de obra. As regras de alocação de mão de obra com efeito temporal no nível do plano permitem que planos individuais mantenham seus próprios cronogramas de taxas, possibilitando o planejamento de cenários e a modelagem de premissas variáveis de custo de mão de obra ao longo do horizonte de planejamento, ao mesmo tempo em que preservam as definições globais subjacentes das regras.

***Principais recursos***

- **Amplie as regras globais com cronogramas específicos para cada plano** – Herde as Regras Globais de Alocação de Mão de Obra e defina entradas adicionais relativas ao tempo no nível do plano, sem alterar os dados de referência compartilhados.
- **Definir valores de vigência** – Controle exatamente quando uma alteração no valor de uma regra entra em vigor dentro do período do plano. É possível definir várias entradas de taxa no mesmo mês.
- **Aplicação automática de taxa** – Durante a geração dos custos de mão de obra, o sistema seleciona o valor efetivo no nível do plano cuja data de início de vigência seja a data mais recente igual ou anterior à data relevante que está sendo avaliada. Se nenhuma taxa no nível do plano abranger o período, o sistema recorre ao valor da regra global.
- **Modelagem de cenários plurianuais** – Aplique diferentes taxas de benefícios, porcentagens de bônus ou custos de treinamento em diferentes anos de um plano plurianual sem precisar criar regras globais separadas.

**Definir regras de alocação no nível do plano**

- Abra **o** seu Plano e, na barra de navegação à esquerda, selecione “**Configurações do Plano** ”.
- Selecione **“Regra de alocação de mão de obra”** no menu de configurações do plano. A tabela **“Regras de alocação de mão de obra – Períodos”** lista todas as regras globais que podem ser substituídas.
- Localize a regra que você deseja ampliar e clique em **“Exibir regras”** na coluna **“Regras avançadas”** para expandir as linhas das regras avançadas.
- No painel “**Taxas avançadas** ”, clique **em “+ Adicionar taxa”** para adicionar uma entrada com validade por tempo.
- Especifique o **valor** (porcentagem ou valor fixo) e a data **de vigência a partir** da qual esse valor deve ser aplicado.
- Adicione entradas de taxas adicionais para modelar as variações de valor ao longo de diferentes períodos. Cada registro deve ter uma data de início de vigência exclusiva.
- Use o botão **“Ordenar por data”** para organizar as entradas de taxas em ordem cronológica, facilitando a análise.
- Clique em **Salvar** para salvar as alterações.

**Geração de dados financeiros de mão de obra para regras no nível do plano**

O sistema sempre seleciona a taxa cuja data **de vigência** seja a data mais recente, inclusive, até a data que está sendo avaliada. O comportamento principal por método de amortização é:

- **Períodos lineares:** No **mês** inicial, a taxa em vigor na **data de início do** contrato de trabalho é aplicada a todo o mês. Para todos **os meses completos subsequentes**, é utilizada a taxa em vigor no dia **1º desse mês**. As alterações nas taxas realizadas no meio do mês não são aplicadas nesse mesmo mês.
- **Método linear com base em dias do calendário:** o custo diário é recalculado para cada **segmento tarifário** dentro do mês. No **mês** de início, apenas os dias a partir da Data de Início do trabalho são considerados ativos, e a taxa em vigor na Data de Início se aplica a esses dias (e daí em diante, até a próxima alteração da taxa ). **Nos meses seguintes**, cada segmento tarifário contribui com uma parcela proporcional do custo daquele mês, com base nos dias do calendário.
- **Linha reta com base em dias úteis:** A lógica é idêntica à dos dias de calendário, mas apenas **os dias úteis** (conforme definido pelo calendário de trabalho configurado) são contabilizados em cada segmento de tarifa.
- Se não houver uma taxa definida no nível do plano para um determinado período, o sistema **recorre ao valor da regra global**.

Observação: as regras de alocação no nível do plano e seus cronogramas de taxas são copiados automaticamente ao criar um plano a partir de uma linha de base. A sincronização de dados de referência (Atualizar dados de referência) adicionará novas regras globais ao plano e removerá as que foram excluídas, preservando todas as entradas de taxas no nível do plano que você tiver configurado.

**Exemplos com regras de validade temporal no nível do plano**

Os exemplos a seguir **(C, D e E)** ampliam **o Exemplo B** (Porcentagem da Taxa Base, $120,000/year, Quantidade = 1 ETI, **Data de Início = 15 de janeiro** ) ao adicionar taxas efetivas por tempo no nível do plano. Todos os três exemplos utilizam a mesma linha do tempo de taxas do plano, na qual as taxas mudam mensalmente e também **no meio do mês** em janeiro e fevereiro.

*Cronograma de taxas por plano (aplicável aos Exemplos C, D e E)*

|  |  |  |
| --- | --- | --- |
| **Válido de** | **Taxa (% da base)** | **Notas** |
| 01/01/2026 | 10% | Início do plano |
| 15/01/2026 | 11% | Mudança em meados de janeiro — coincide com a data de início do contrato de trabalho |
| 02/01/2026 | 12% | Mudança em fevereiro |
| 10/02/2026 | 13% | Mudança em meados de fevereiro |
| 01/03/2026 | 14% | Mudança em março |

**Salário base:** $120,000/year │ Quantidade **:** 1 ETC │ **Data** de início: 15 de janeiro

**Exemplo C – Períodos uniformes em linha reta com regras no nível do plano**

Com **o método de amortização linear**, a taxa em vigor na **data de início** do contrato de trabalho (15 de janeiro) é aplicada a todo o mês de início. Para os meses completos subsequentes, é utilizada a taxa em vigor no dia **1º de cada mês**. As alterações nas taxas ocorridas no meio do mês dentro de um mesmo mês (por exemplo, 10/02 → 13%) **não** são aplicadas — apenas a taxa em vigor no dia 1º desses meses é considerada.

**Taxas aplicáveis:** Jan → 11% (taxa na data de início 15/01), Fev → 12% (taxa em 01/02), Mar → 14% (taxa em 01/03)

|  |  |  |  |
| --- | --- | --- | --- |
| **Mês** | **Qte** | **Cálculo** | **Quantia** |
| Janeiro | 1 | (($120.000 × 11%) ÷ 12) × 1 ETI | US$ 1.100 |
| Fevereiro | 1 | (($120.000 × 12%) ÷ 12) × 1 ETI | US$ 1.200 |
| Março | 1 | (($120.000 × 14%) ÷ 12) × 1 ETI | US$ 1.400 |

Observação: Para o **mês inicial (janeiro)**, o sistema utiliza a alíquota em vigor na **Data de Início** do contrato de trabalho (15/01 → 11%), e não a alíquota em vigor no dia 1º do mês (01/01 → 10%). Para os meses completos subsequentes, é utilizada apenas a taxa em vigor no dia 1º do mês — alterações no meio do mês, como 10/02 → 13%, não são aplicadas para os períodos pares.

**Exemplo D – Linha reta utilizando dias de calendário com regras no nível do plano**

Com **o método linear com base em dias de calendário**, os custos são calculados **por segmento tarifário** dentro de cada mês. No **mês** de início (janeiro), apenas os dias a partir da data de início do trabalho (15 de janeiro) estão ativos.

**Janeiro (17 dias úteis: 15 a 31 de janeiro)**

A taxa em vigor na data de início do contrato de trabalho (15 de janeiro) é de **11%**. Não haverá alterações adicionais nas tarifas antes de 1º de fevereiro; portanto, todos os dias ativos em janeiro serão cobrados com base nessa tarifa.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Taxa** | **Taxa Diária** | **dias** | **Custo do segmento** |
| Segmento 1 | 15 de janeiro | 31 de janeiro | 11% | (120.000 $ × 11%) ÷ 365 = 36.16 $ | 17 | $614.79 |

**Fevereiro (28 dias)**

O mês de fevereiro apresenta dois segmentos de taxas devido à alteração de taxas que entra em vigor em 10 de fevereiro.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Taxa** | **Taxa Diária** | **dias** | **Custo do segmento** |
| Segmento 1 | 1º de fevereiro | 9 de fevereiro | 12% | (120.000 $ × 12%) ÷ 365 = 39.45 $ | 9 | $355.07 |
| Segmento 2 | 10 de fevereiro | 28 de fevereiro | 13% | (120.000 $ × 13%) ÷ 365 = 42.74 $ | 19 | $812.05 |
| **Total de fevereiro** |  |  |  |  | **28** | **$1. 167.12** |

**Março (31 dias)**

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Taxa** | **Taxa Diária** | **dias** | **Custo do segmento** |
| Segmento 1 | 1º de março | 31 de março | 14% | (120.000 $ × 14%) ÷ 365 = 46.03 $ | 31 | $1. 426.85 |
| **Total de março** |  |  |  |  | **31** | **$1. 426.85** |

**Resumo – Exemplo D (Dias corridos)**

|  |  |  |  |
| --- | --- | --- | --- |
| **Mês** | **Qte** | **Segmentos** | **Total mensal** |
| Janeiro | 1 | 1 (11%, dias 15–31) | $614.79 |
| Fevereiro | 1 | 2 (12% + 13%) | $1. 167.12 |
| Março | 1 | 1 (14%) | $1. 426.85 |

**Exemplo E – Linha reta com base em dias úteis e regras no nível do plano**

Na opção “**Linha reta com dias úteis** ”, a lógica é idêntica à da opção “Dias de calendário”, mas apenas **os dias úteis** (excluindo fins de semana e feriados) são contabilizados em cada segmento tarifário.

Assim como no caso dos “Dias do calendário”, no **mês** inicial (janeiro), apenas os dias úteis a partir de 15 de janeiro estão ativos, e a taxa em vigor na Data de Início ( **11% a partir de 15/01** ) se aplica a todos eles.

Calendário de trabalho: **261 dias úteis por ano em 2026**

**Fórmula da taxa diária:** Taxa diária = (Taxa base × Taxa do plano) ÷ 261

**Distribuição estimada por dia útil para cada segmento tarifário:**

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Taxa** | **Dias úteis** |
| Jan – Seg 1 | 15 de janeiro | 30 de janeiro | 11% | 12 |
| Fev – Seg 1 | 2 de fevereiro | 9 de fevereiro | 12% | 6 |
| Fev – Seg 2 | 10 de fevereiro | 27 de fevereiro | 13% | 14 |
| Mar – Seg 1 | 1º de março | 31 de março | 14% | 22 |

**Janeiro (12 dias úteis: 15 a 31 de janeiro)**

A taxa em vigor a partir da data de início do contrato de trabalho (15/01) é de 11%. Todos os 12 dias úteis de janeiro se enquadram nesse único segmento tarifário.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Taxa** | **Tarifa diária** | **Dias úteis** | **Custo do segmento** |
| Segmento 1 | 15 de janeiro | 31 de janeiro | 11% | (120.000 $ × 11%) ÷ 261 = 50.77 $ | 12 | $606.90 |
| **Total de janeiro** |  |  |  |  | **12** | **$606.90** |

**Fevereiro (20 dias úteis)**

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Taxa** | **Tarifa diária** | **Dias úteis** | **Custo do segmento** |
| Segmento 1 | 2 de fevereiro | 9 de fevereiro | 12% | (120.000 $ × 12%) ÷ 261 = 55.17 $ | 6 | $331.03 |
| Segmento 2 | 10 de fevereiro | 27 de fevereiro | 13% | (120.000 $ × 13%) ÷ 261 = 59.77 $ | 14 | $836.78 |
| **Total de fevereiro** |  |  |  |  | **20** | **$1. 167.82** |

**Março (22 dias úteis)**

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Taxa** | **Tarifa diária** | **Dias úteis** | **Custo do segmento** |
| Segmento 1 | 1º de março | 31 de março | 14% | (120.000 $ × 14%) ÷ 261 = 64.37 $ | 22 | $1. 416.09 |
| **Total de março** |  |  |  |  | **21** | **$1. 416.09** |

**Resumo – Exemplo E (Dias úteis)**

|  |  |  |  |
| --- | --- | --- | --- |
| **Mês** | **Qte** | **Segmentos** | **Total mensal** |
| Janeiro | 1 | 1 (11%, dias 15–30 da semana) | $606.90 |
| Fevereiro | 1 | 2 (12% + 13%) | $1. 167.82 |
| Março | 1 | 1 (14%) | $1. 416.09 |
