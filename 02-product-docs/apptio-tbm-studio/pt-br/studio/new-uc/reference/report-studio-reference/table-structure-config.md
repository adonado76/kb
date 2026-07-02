---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configuração da estrutura da tabela"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas"
source_path: "studio/new-uc/reference/report-studio-reference/table-structure-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuração da estrutura da tabela

A estrutura da tabela é configurada por meio do painel "Configuração de Componentes", que é exibido quando você adiciona ou seleciona uma tabela em um relatório.

**Áreas de configuração de componentes**

O painel de configuração de componentes inclui quatro áreas principais para a criação de tabelas:

|  |  |  |
| --- | --- | --- |
| **Área** | **Descrição** | **Limitadores** |
| Linhas | Fornece os dados para a primeira coluna da tabela. As entradas duplicadas são agrupadas automaticamente. Vários campos criam subgrupos. | Aceita dimensões (campos de rótulo). É permitido preencher vários campos. |
| Colunas | Fornece os títulos das colunas da tabela. Utilizado principalmente para pivôs baseados no tempo. | É possível adicionar apenas UM campo. Normalmente usado para dimensões temporais. |
| Valores | Apresenta os dados exibidos no corpo da tabela. Essas se tornam as colunas numéricas. | Aceita métricas e campos numéricos. É permitido preencher vários campos. |
| Filtros | Filtra os registros exibidos na tabela. Restringe os dados aos critérios correspondentes. | Aceita dimensões e métricas. É permitido usar vários filtros. |

**Adicionar e remover colunas**

**Para adicionar colunas:**

1. Selecione a tabela no relatório.
2. Arraste os campos do Explorador de Projetos para a área apropriada (Linhas ou Valores) no painel Configuração do Componente.
3. A tabela será atualizada automaticamente para exibir a nova coluna.

**Para remover colunas:**

- Arraste o campo para fora da área de configuração de componentes, OU
- Clique com o botão direito do mouse no campo e selecione “Remover”.

**Ordenação das colunas**

**Para reordenar as colunas:**

- Clique e arraste o cabeçalho da coluna para uma nova posição na tabela.
- Reorganize os campos na área "Valores" para alterar a ordem das colunas.

**Observação:** Durante a exportação para o Excel, as colunas mantêm a ordem configurada no componente de relatório. Quaisquer colunas que não estejam explicitamente configuradas são automaticamente acrescentadas ao final.

**Agrupamento de colunas**

Você pode agrupar duas ou mais colunas sob um cabeçalho comum. Isso é útil para organizar métricas relacionadas, como agrupar as colunas “Custo” e “Orçamento” sob o título “Finanças”.

**Para agrupar colunas:**

1. Mantenha pressionada a tecla Ctrl (Windows) ou Alt (Mac) e clique no cabeçalho de cada coluna para incluí-la no grupo.
2. Clique com o botão direito do mouse e selecione “Agrupar colunas”.
3. Digite o texto do cabeçalho do grupo e clique em OK.

**Dica:** você pode usar texto dinâmico nos cabeçalhos dos grupos. Por exemplo, <%=CurrentDate( )%> exibe o período atual.

Para desagrupar colunas, clique com o botão direito do mouse no cabeçalho da coluna e selecione “Desagrupar colunas”.

**Agrupamento de linhas**

As tabelas são agrupadas automaticamente por pelo menos um campo na área “Linhas”. O agrupamento adicional consolida os dados e exibe valores agregados.

**Para configurar o agrupamento de linhas:**

1. Selecione a tabela e clique em “Agrupar” na guia “Dados”.
2. Na caixa de diálogo "Agrupar", selecione as colunas a serem usadas para o agrupamento.
3. Clique em “Grupo” para se inscrever.

Quando agrupadas, as colunas com vários valores diferentes exibem três pontos verticais (vários), e é adicionada uma coluna “Contagem” que mostra o número de entradas agrupadas.

**Subtotais e totais gerais**

Quando há vários campos na área “Linhas”, o TBM Studio agrupa automaticamente os valores e pode exibir subtotais. Configure os subtotais usando a caixa de diálogo “Subtotais” na guia “Dados”.

|  |  |  |
| --- | --- | --- |
| **Opção** | **Descrição** | **Padrão** |
| Mostrar linha completa | Exibe uma linha "Total" na parte inferior da tabela com os valores agregados. | Ativado |
| Mostrar coluna Total | Exibe uma coluna “Totais” que mostra os totais das linhas. | Desativado |
| Mostrar outra linha | Quando o número de linhas é limitado, exibe uma linha “Outros” com os totais restantes. | Desativado |
| Insira os rótulos de subtotal | Determina em qual coluna são exibidos os rótulos de subtotal. | Primeira coluna agrupada |
| Níveis de subtotal (1-4) | Número de níveis de agrupamento para os quais serão exibidos subtotais. | 1 |

**Dica:** A linha “Total” lida de forma inteligente com diferentes tipos de colunas: ela soma colunas numéricas e, no caso de colunas calculadas (como “Custo por servidor”), recalcula os valores usando os totais, em vez de somar valores individuais.

**Estrutura em árvore do subtotal**

Para dados hierárquicos, crie tabelas em forma de árvore expansíveis que permitam aos usuários navegar pelos diferentes níveis.

**Para criar uma árvore de subtotais:**

1. Arraste dois ou mais campos para a área “Linhas”.
2. Adicione um ou mais campos à área Valores.
3. Na guia Dados, no grupo Estrutura, clique em Como árvore.
4. Opcionalmente, defina o número máximo de itens para limitar as linhas exibidas, incluindo um link “Outros” para os itens restantes.

**Tópico principal:** [Componentes do relatório: Tabelas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
