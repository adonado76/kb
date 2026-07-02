---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tipos de componentes de entrada"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório - Componentes de entrada"
source_path: "studio/new-uc/reference/report-studio-reference/input-component-types.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tipos de componentes de entrada

O TBM Studio oferece recursos de inserção de dados por meio de configurações editáveis das colunas das tabelas. Cada tipo de coluna determina como os usuários inserem os dados.

**Entrada de texto**

As colunas de entrada de texto aceitam dados em texto simples e são utilizadas para rótulos, descrições e outros valores não numéricos.

**Configuração**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Tipo | Definir como "Etiqueta" para dados de texto simples |
| Nome | Nome de exibição mostrado no cabeçalho da coluna |
| Descrição | Texto de ajuda que descreve a finalidade da coluna |
| Valor Padrão | Valor predefinido para novas linhas |
| Valores possíveis | Opcional: restringir a uma lista controlada (cria um menu suspenso) |

**Notas de uso**

- Não é possível realizar operações matemáticas nas colunas de rótulo
- O quebra automático de linha não se aplica às colunas de fontes primárias em tabelas editáveis enriquecidas
- É possível copiar e colar texto do Excel usando Control+C / Control+V (Windows) ou ⌘+C / ⌘+V (Mac)

**Entrada numérica**

As colunas de entrada numérica aceitam valores inteiros ou decimais e seguem as configurações regionais do projeto para a formatação de números.

**Configuração**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Tipo | Defina como Numérico para dados numéricos |
| Nome | Nome de exibição mostrado no cabeçalho da coluna |
| Descrição | Texto de ajuda que descreve a finalidade da coluna |
| Valor Padrão | Valor predefinido para novas linhas |
| Valor necessário | Se estiver marcado, os usuários não poderão salvar sem inserir um valor |

**Notas de uso**

- As colunas numéricas suportam formatação específica da localidade (separadores decimais, separadores de milhares)
- A formatação de moeda e porcentagem é aplicada no nível do relatório, e não no nível da configuração da coluna
- Os valores numéricos podem ser utilizados em colunas de fórmula e cálculos
- O recurso "Carry Forward" ( 12.6 e versões posteriores) permite que os valores numéricos sejam propagados por colunas consecutivas

**Entrada de data**

As colunas de entrada de data aceitam valores de data com formatos de exibição configuráveis.

**Configuração**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Tipo | Definir como "Data" para dados de data |
| Formato de data | Especifique o formato usando padrões padrão (por exemplo, MM/dd/aaaa) |
| Nome | Nome de exibição mostrado no cabeçalho da coluna |
| Valor Padrão | Data predefinida para novas linhas |

**Formatos de data compatíveis**

|  |  |
| --- | --- |
| **Padrão** | **Exemplo de saída** |
| mm/dd/aaaa | 15/01/2025 |
| aaaa-MM-dd | 15 de janeiro de 2025 |
| MMM dd, aaaa | 15 de janeiro de 2025 |
| dd-MMM-aa | 15-Jan-25 |

*Observação: a string de formato de data não deve ser colocada entre aspas ao configurar a coluna.*

**Campos de seleção (menus suspensos)**

Os campos de seleção suspensa restringem a entrada de dados a um conjunto controlado de valores, garantindo a consistência dos dados e reduzindo os erros de inserção.

**Configuração básica do menu suspenso**

Configure um menu suspenso definindo a propriedade "Valores possíveis" usando um destes métodos:

**Método 1 - Lista estática: Insira uma lista de valores separados por vírgulas, como ""OpEx, CapEx, Transfer"**

**Método 2 - Lista baseada em fórmula: Consulte valores de outra tabela usando a sintaxe: %nome\_da\_tabela/!LIMIT\_COLUMNS[nome\_da\_coluna]**

**Propriedades do menu suspenso**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Valores possíveis | Lista estática ou fórmula que define as opções disponíveis |
| Contexto dos valores possíveis | Defina como “Relatório” para contexto estático ou “Linha atual” para filtragem dinâmica |
| Permitir valores que não constam na lista de valores possíveis | Se estiver marcado, os usuários poderão inserir valores personalizados |
| Desativar edição na célula de valores possíveis | Se estiver marcada, os usuários não poderão digitar na célula |

*Observação: O menu suspenso exibe os primeiros 15 valores únicos. Para listas com mais de 15 valores, aparece um botão “Pesquisar”.*

**Menus suspensos em cascata (dependentes)**

Crie menus suspensos em que as opções disponíveis dependam do valor de outra coluna, utilizando texto dinâmico. Por exemplo, uma lista suspensa de cidades que filtra com base no estado selecionado:

- Crie uma tabela de origem (por exemplo, Estados-Cidades) com as colunas Estado e Cidade
- Configure os valores possíveis da coluna “Estado”: %States-Cities/!LIMIT\_COLUMNS[Estado]
- Configure a coluna “Cidade” com um filtro: %States-Cities/!FILTRO[Estado="<%=Estado%>"]/!LIMIT\_COLUMNS[Cidade]
- Defina o contexto de valores possíveis da coluna “Cidade” como “Linha atual”

**Tópico principal:** [Componentes do relatório - Componentes de entrada](../../../../studio/new-uc/reference/report-studio-reference/report-component-input-components.html)
