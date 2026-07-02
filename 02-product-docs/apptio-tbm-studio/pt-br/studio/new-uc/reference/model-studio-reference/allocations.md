---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Alocações"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
source_path: "studio/new-uc/reference/model-studio-reference/allocations.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Alocações

As alocações são o mecanismo central para distribuir valor entre objetos do modelo. Elas determinam como os custos, orçamentos e outras métricas são transferidos dos objetos de origem para os objetos de destino com base em regras configuráveis.

## Tipos de alocação

O TBM Studio oferece cinco tipos de alocação para atender a diferentes necessidades de distribuição.

**Alocação de valor ponderada**

**Descrição:** Distribui os valores com base na proporção (tamanho relativo) dos valores em uma coluna selecionada da tabela de destino. Este é o tipo de alocação mais comum.

**Parâmetros de configuração**

|  |  |  |  |
| --- | --- | --- | --- |
| **Parâmetro** | **Necessário** | **Valores** | **Descrição** |
| Atribuir (Métricas) | Sim | Custo, Orçamento, Previsão | Quais métricas devem ser atribuídas |
| Para (Destinatário) | Sim | Objeto modelo | Objeto do modelo de destino |
| Distribuição | Sim | Uniforme, Peso por, Relação de dados | Como o valor é distribuído |
| Peso por | Condicional | Tabela, Sistema métrico, Outros motoristas | Fonte de ponderação (se a opção “Ponderar por” estiver selecionada) |
| Relação entre dados | Condicional | Par de colunas | Colunas correspondentes (se selecionado) |

**Opções de distribuição**

|  |  |  |
| --- | --- | --- |
| **Opção** | **Comportamento** | **Exemplo** |
| Mesmo | Distribui igualmente por todas as linhas de destino | $100K / 5 aplicativos = $20K cada |
| Peso por – Tabela | Distribui com base nas proporções das colunas no destino | Coluna “Peso por número de usuários” |
| Peso em – Sistema métrico | Distribui com base nos valores de outra métrica | Orçamento de peso por distribuição de custos |
| Peso por – Outro motorista | Ajusta a velocidade de acordo com o padrão de outro motorista | Corresponder ao padrão de alocação de mão de obra |
| Relação entre dados | Distribui pelas linhas em que as colunas coincidem | Comparar o ID do fornecedor entre as tabelas |

**Observação:** as opções “Peso por – Métrico” e “Peso por – Outro motorista” estão disponíveis no TBM Studio 12.5 e versões posteriores.

**Exemplo: Alocação de valor ponderada**

Alocar US$ 100.000 entre cinco candidaturas, ponderadas pelo número de usuários:

|  |  |  |
| --- | --- | --- |
| **Aplicativo** | **Número de usuários** | **Alocação** |
| Aplicativo A | 50 | $25.000 (50/200 × $100.000) |
| Aplicativo B | 130 | $40.000 (80/200 × $100.000) |
| Aplicativo C | 30 | $15.000 (30/200 × $100.000) |
| Aplicativo D | 25 | $12.500 (25/200 × $100.000) |
| Aplicativo E | 15 | $7.500 (15/200 × $100.000) |

**Armadilhas comuns**

Aviso: Peso com valor não numérico: Se a coluna de ponderação contiver algum valor não numérico, a ponderação será ignorada e a alocação será feita por distribuição uniforme por padrão.

Observação: Peso negativo: as alocações falham se os valores de ponderação incluírem números negativos. Consulte a seção “Sobre ponderação e números negativos” para obter soluções alternativas.

Consulte [“Criar alocações ponderadas” para obter o procedimento passo a passo](../../howtoguides/build-cost-model/create-allocation.html)

**Distribuição do consumo**

**Descrição:** Aloca com base nas unidades efetivamente consumidas em relação à capacidade total disponível. Utiliza-se quando se dispõe de dados específicos de consumo que mostram quanto de um serviço ou recurso cada alvo consome.

**Parâmetros de configuração**

|  |  |  |  |
| --- | --- | --- | --- |
| **Parâmetro** | **Necessário** | **Valores** | **Descrição** |
| Coluna de Consumo | Sim | Coluna do alvo | Número de unidades consumidas |
| Coluna de Capacidade | Sim | Coluna da fonte | Capacidade total disponível |
| Distribuição | Sim | Uniforme, Peso por, Relação de dados | Lógica de distribuição adicional |

**Casos de uso**

- Consumo de serviços em nuvem (armazenamento consumido em GB vs. total provisionado)
- VM alocação (máquinas virtuais utilizadas por cada unidade de negócios em comparação com o total disponível)
- Licenças de serviço (licenças utilizadas vs. total adquirido)

**Alocação de valor padrão**

**Descrição:** Distribui um valor igual ao valor já existente na tabela de destino, independentemente do valor de origem. Isso faz com que o valor atual do alvo seja transferido diretamente.

**Comportamento-chave**

- Se o destino tiver $10.000 e a origem tiver $15.000: $10.000 são alocados, restando $5.000 na origem
- Se o destino tiver US$ 10.000 e a origem tiver US$ 5.000: Sobrealocação de 200%
- O valor de origem não limita a alocação; o valor de destino determina o montante

Aviso: As alocações de valores padrão podem gerar situações de sobrealocação. Monitore as porcentagens de alocação para garantir a integridade do modelo.

**Fórmula de alocação**

**Descrição:** Utiliza uma fórmula personalizada para controlar a distribuição da alocação. Oferece flexibilidade máxima para cenários complexos de alocação que os métodos padrão não conseguem resolver.

**Palavras-chave especiais**

|  |  |
| --- | --- |
| **Palavra-chave** | **Descrição** |
| Origem | Representa o montante que está sendo alocado a partir do objeto de origem |
| ~ (operador til) | Obtém o valor total de uma coluna em todas as linhas correspondentes (semelhante à função SUM, mas respeita as relações entre os dados) |

**Exemplos de fórmulas**

|  |  |
| --- | --- |
| **Propósito** | **Fórmula** |
| Alocação ponderada (equivalente a “Ponderar por”) | =SOURCE\*Ratio( {Servers.Size},~ {Servers.Size} ) |
| Valor direto da coluna (como o valor padrão) | =Servers.Size |
| Alocação baseada em porcentagem | =FONTE\*( {Table.Percent} /100) |

**Observação:** as alocações por fórmula não podem reproduzir os comportamentos das alocações por consumo ou recursivas.

Consulte Fórmulas e funções do 5.4: para obter a sintaxe completa das fórmulas

**Alocação por recursão**

**Descrição:** Lida com padrões de alocação circular, nos quais os serviços alocam custos entre si. Processa as alocações de forma iterativa até que seja atingido um limite de precisão ou o número máximo de iterações.

**Parâmetros de configuração**

|  |  |  |  |
| --- | --- | --- | --- |
| **Parâmetro** | **Necessário** | **Padrão** | **Descrição** |
| Precisão | Sim | Varia | Valor mínimo para continuar a iteração |
| Número máximo de iterações | Sim | Varia | Número máximo de ciclos de alocação |
| Usar o modo incremental | Não | Desmarcado | Adiciona o valor da iteração à fonte |

**Requisitos**

- As tabelas de origem e de destino devem ter unidades idênticas
- Deve permanecer algum valor nas unidades-alvo após cada iteração
- As alocações de recursão múltipla não devem se sobrepor

Aviso: as alocações recursivas exigem muito mais capacidade de processamento. Use com moderação e com o mínimo de repetições.

*→ Consulte [“Configurar alocações recursivas” para obter instruções detalhadas sobre a configuração](../../howtoguides/build-cost-model/config-drivers.html)*

- **[Todas as opções de configuração de alocação](../../../../studio/new-uc/reference/model-studio-reference/allocation-config.html)**
- **[Ordem e prioridade de alocação](../../../../studio/new-uc/reference/model-studio-reference/allocation-order.html)**
- **[Comportamento do cálculo de alocação](../../../../studio/new-uc/reference/model-studio-reference/allocation-calc-behaviour.html)**
