---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Referência completa das etapas de transformação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Data Studio Referência"
  - "Etapas da transformação"
source_path: "studio/new-uc/reference/complete-transform-steps.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referência completa das etapas de transformação

**Adicionar etapa**

**Objetivo:** Adicionar linhas de uma ou mais tabelas de origem à tabela de destino

**Quando usar:** Combinar dados de várias fontes em uma única tabela

**Pode ser adicionado apenas uma vez:** Sim

**Comportamento:**

- Os dados anexados são adicionados como novas linhas (as linhas nunca são combinadas)
- As colunas de origem podem ser mapeadas para colunas de destino existentes
- As colunas da tabela de origem podem ser adicionadas como novas colunas à tabela de destino

**Parâmetros:**

|  |  |
| --- | --- |
| **Parâmetro** | **Descrição** |
| Adicionar fonte de dados | Selecione a(s) tabela(s) de origem à qual(is) deseja anexar |
| Mapeamento de colunas | Mapeie as colunas de origem para as colunas de destino |
| Colunas de fonte adicionais | Adicionar colunas da tabela de origem que não estão na tabela de destino |

**Etapa de divisão por data**

**Objetivo:** Distribuir automaticamente dados com data e hora por períodos de tempo

**Pode ser adicionado apenas uma vez:** Sim

**Parâmetros baseados em linhas:**

|  |  |
| --- | --- |
| **Parâmetro** | **Descrição** |
| Data de Início | Coluna que contém as datas de início |
| Data de Término | Coluna contendo datas de término (opcional) |

**Parâmetros baseados em colunas:**

|  |  |
| --- | --- |
| **Parâmetro** | **Descrição** |
| Interpretar o ano como | Ano fiscal ou ano civil |
| Novo prefixo de coluna | Rótulo adicionado às colunas particionadas |
| Conjuntos de colunas | Selecione quais grupos de colunas devem ser particionados |

**Etapa de filtragem**

**Objetivo:** Remover linhas com base em condições de valores de coluna

**Pode ser adicionado apenas uma vez:** Sim

**Operadores de filtro:**

|  |  |  |
| --- | --- | --- |
| **Operador** | **Tipo de dados** | **Descrição** |
| Contém | Sequência | Correspondência parcial |
| Não contém | Sequência | Exclusão parcial |
| Começa com | Sequência | Correspondência de prefixo |
| Termina com | Sequência | Correspondência de sufixo |
| Menor que | Numérico | Menos do que o valor |
| Maior que | Numérico | Mais do que o valor |
| Igual | Todos os Tipos | Correspondência exata |
| Diferente | Todos os Tipos | Diferente de |
| É nulo | Todos os Tipos | Valor vazio |
| Não é nulo | Todos os Tipos | Valor não vazio |
| Está em | Todos os Tipos | Correspondência de valores múltiplos |
| Não está em | Todos os Tipos | Exclusão múltipla |

**Combinação de filtros:**

- **E:** Todas as condições devem ser verdadeiras
- **OU:** Qualquer condição deve ser verdadeira
- **Entre parênteses:** Condições relacionadas ao grupo

**Etapa das fórmulas**

**Objetivo:** Adicionar colunas calculadas, alterar tipos de coluna ou substituir valores existentes

**Operações com colunas:**

|  |  |
| --- | --- |
| **Operação** | **Descrição** |
| Adicionar coluna | Criar nova coluna calculada |
| Editar coluna | Modificar a fórmula ou o tipo de uma coluna existente |
| Excluir coluna | Remover uma coluna de fórmula |

**Veja também:** Seção Fórmulas e funções do 5.4, para uma referência completa das fórmulas

**Passo em grupo**

**Objetivo:** Agregar dados da tabela agrupando-os por uma ou mais colunas

**Pode ser adicionado apenas uma vez:** Sim

**Comportamento:**

- Cria uma linha para cada combinação única de valores de agrupamento
- Adiciona uma coluna " {.Count} " que mostra o número de linhas por grupo
- As colunas numéricas são somadas
- As colunas de texto com valores variáveis exibem "..." (reticências)

**Junte-se à Step**

**Objetivo:** Combinar dados de várias tabelas com base na correspondência de valores de colunas

**Pode ser adicionado apenas uma vez:** Sim

**Juntar vs. Anexar:**

|  |  |
| --- | --- |
| **Junção** | **Anexo** |
| Combina os dados nas mesmas linhas | Adiciona dados como novas linhas |
| Com base na correspondência dos valores das colunas | Com base no mapeamento de colunas |
| Utilizar para enriquecimento | Utilizar para combinar conjuntos de dados |

**Etapa de colunas do mapa**

***Aplicável a:*** *TBM Studio 12.7 e versões posteriores*

**Objetivo:** Alinhar os dados das tabelas aos esquemas dos conjuntos de dados mestres para garantir a conformidade da aplicação

**Pode ser adicionado apenas uma vez:** Sim

**Opções de mapeamento:**

|  |  |
| --- | --- |
| **Opção** | **Descrição** |
| Escolher origem | Selecione a coluna no menu suspenso |
| Insira um valor fixo | Valor constante para todas as linhas |
| Adicionar coluna personalizada | Criar uma nova coluna no conjunto de dados mestre |
| Junção | Usar colunas de tabelas unidas |

**Passo giratório**

**Objetivo:** Resumir dados convertendo linhas em colunas

**Pode ser adicionado apenas uma vez:** Sim

**Parâmetros:**

|  |  |
| --- | --- |
| **Parâmetro** | **Descrição** |
| Linha de pivô | Coluna para os valores da primeira coluna |
| Coluna de pivô | Coluna para cabeçalhos de coluna |
| Valor de pivô | Coluna numérica a ser agregada nas células |

**Etapa de remoção de duplicatas**

**Objetivo:** Filtrar as linhas com valores duplicados nas colunas especificadas

**Pode ser adicionado apenas uma vez:** Sim

**Parâmetros:**

|  |  |
| --- | --- |
| **Parâmetro** | **Descrição** |
| Coluna-chave | Coluna para verificar se há duplicatas |
| Coluna de comparação | Coluna usada para determinar qual linha deve ser mantida |
| Tipo de comparação | Maior ou menor - determina a linha a ser mantida |

**Etapa de segurança no nível da linha**

***Aplicável a:*** *TBM Studio 12.2 e versões posteriores*

**Objetivo:** Filtrar os dados da tabela com base no usuário atual para fins de governança de dados

**Pode ser adicionado apenas uma vez:** Sim

**Parâmetros de filtragem:**

|  |  |
| --- | --- |
| **Campo** | **Descrição** |
| Primeiro campo | Coluna da tabela a ser filtrada |
| Segundo campo (intersecções) | Tabela de mapeamento com dados de segurança |
| Terceiro campo | Coluna na tabela de mapeamento com valores permitidos |
| Quarto campo (onde o usuário está) | Coluna na tabela de mapeamento com IDs de usuário |

**Etapa de despivotação**

**Objetivo:** Converter os valores das colunas em linhas adicionais

**Pode ser adicionado apenas uma vez:** Sim

**Colunas de saída:**

|  |  |
| --- | --- |
| **Coluna** | **Descrição** |
| Recolher coluna | Nomes originais dos cabeçalhos das colunas |
| Ocultar valor | Valores originais da coluna |

**Avisos:**

- Evite misturar tipos de colunas em colunas não agrupadas
- Monitorar a expansão excessiva das linhas (as linhas multiplicam-se pelo número de colunas)

**Tópico principal:** [Etapas da transformação](../../../studio/new-uc/reference/transform-steps.html)
