---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Opções de edição de colunas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas editáveis nos relatórios"
source_path: "studio/new-uc/reference/report-studio-reference/column-editing-options.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Opções de edição de colunas

Cada coluna de uma tabela editável pode ser configurada com comportamentos de edição específicos. Essas configurações são definidas em Data Studio, mas afetam o comportamento da coluna no componente de relatório.

**Configuração editável vs. somente leitura**

As colunas podem ser definidas como editáveis ou somente para leitura no nível do relatório:

- **Colunas não editáveis:** acesse a faixa de opções “Tabelas editáveis” e expanda “Colunas não editáveis” para selecionar as colunas que devem ser somente de leitura
- **Colunas de origem:** em tabelas editáveis aprimoradas, as colunas da transformação de origem são, por padrão, somente para leitura
- **Permitir edição nas colunas incluídas:** uma caixa de seleção na configuração permite a edição das colunas de origem incluídas

**Tipos de entrada**

Os tipos de dados das colunas determinam a experiência de inserção:

|  |  |  |
| --- | --- | --- |
| **Tipo de entrada** | **Descrição** | **Data Studio Cenário** |
| Texto (Rótulo) | Digitação de texto livre | Tipo: Etiqueta |
| Número (numérico) | Valores numéricos com formatação de localidade | Tipo: Numérico |
| Lista suspensa | Seleção entre valores predefinidos | Valores possíveis configurados |
| Data | Seletor de data com controle de formato | Tipo: Data com formato de data |
| Booleano | Seleção da caixa de seleção Verdadeiro/Falso | Tipo: Booleano |

**Fontes de valores do menu suspenso**

Os menus suspensos podem ser configurados com valores estáticos ou dinâmicos:

- **Lista estática:** valores separados por vírgulas inseridos diretamente (por exemplo, ""OpEx, CapEx, Transfer")
- **Dado dinâmico da tabela:** Fórmula que faz referência a outra tabela: %TableName/!LIMIT\_COLUMNS[ ColumnName ]
- **Menus suspensos em cascata:** Filtre os valores com base em outra coluna usando: %Table/!FILTRAR[ Column="<%=OtherColumn%>" ]/!LIMIT\_COLUMNS[Coluna]

A configuração “Valores possíveis” determina como o texto dinâmico é avaliado: a opção “Linha atual” avalia as fórmulas no contexto da linha que está sendo editada, enquanto a opção “Relatório” avalia no contexto geral do relatório.

**Valores padrão**

Quando os usuários adicionam novas linhas, os valores padrão podem ser preenchidos automaticamente:

- Defina no campo "Valor padrão" na configuração de uma coluna d Data Studio
- Podem ser valores fixos ou fórmulas
- Útil para definir datas padrão, valores de status ou atribuições de proprietário

**Tópico principal:** [Componentes de relatórios: Tabelas editáveis em relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
