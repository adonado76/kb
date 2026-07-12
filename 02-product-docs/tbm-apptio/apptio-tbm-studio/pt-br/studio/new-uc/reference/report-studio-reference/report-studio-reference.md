---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Referência do Report Studio"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
source_path: "studio/new-uc/reference/report-studio-reference/report-studio-reference.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referência do Report Studio

## Visão geral

O Report Studio permite criar relatórios interativos que apresentam dados de seus modelos às partes interessadas. Os relatórios podem incluir tabelas, gráficos e diversos componentes para filtragem, navegação e inserção de dados. Esta seção de referência oferece documentação completa sobre todos os recursos e componentes do Report Studio.

Use esta seção para consultar propriedades específicas dos componentes, opções de configuração e detalhes técnicos. Para obter instruções passo a passo sobre como criar relatórios, consulte ***a seção 3.3 Criar relatórios***.

## Ferramentas Importantes

- **Visualização de dados:** exiba dados do modelo usando tabelas e gráficos configuráveis com navegação detalhada
- **Filtragem interativa:** Facilite a descoberta de dados por meio de filtros, seletores de colunas e tabelas dinâmicas rápidas
- **Entrada de dados:** Permitir que os usuários finais insiram dados diretamente por meio de tabelas editáveis e componentes de upload
- **Identidade visual consistente:** aplique modelos de relatórios e paletas de cores personalizadas de acordo com os padrões da organização
- **Controle de acesso:** gerencie a visibilidade dos relatórios por meio de permissões baseadas em funções

## Índice da seção

Esta seção contém 11 subseções que abrangem todos os componentes e recursos do Report Studio:

|  |  |
| --- | --- |
| **Tópico** | **Descrição** |
| **Tabelas** | Configure tabelas baseadas em objetos e de transformação, adicione colunas (fórmula, calculada, calendário, minigráfico, total), defina agrupamento, ordenação e propriedades da tabela, incluindo formatação condicional e links de navegação. |
| **Gráficos** | Crie visualizações, incluindo gráficos de barras, barras empilhadas, colunas, colunas empilhadas, linhas, pizza, KPI, mapa de árvore e cascata. Configure paletas de cores, legendas e a navegação entre gráficos e relatórios. |
| **Filtros e segmentadores** | Adicione filtros para filtragem interativa, configure filtros compactos, seletores de colunas e tabelas dinâmicas rápidas. Permita a descoberta de dados por meio de combinações dinâmicas de filtros. |
| **Navegação** | Crie links de detalhamento entre relatórios, configure botões de navegação no estilo Wiki, crie navegadores de coleções de relatórios e configure relatórios em janelas pop-up modais. |
| **Componentes de entrada** | Adicione botões, caixas de texto HTML, notas, caixas de grupo e componentes com guias. Configure os componentes de upload de tabelas para que os usuários finais possam inserir dados sem precisar acessar o Studio. |
| **Tabelas editáveis** | Configure componentes de relatório em forma de tabela editável para a inserção direta de dados. Configure listas suspensas, valores possíveis, bloqueio de células, permissões de upload e fluxos de trabalho de publicação. |
| **Propriedades do relatório** | Configure as opções do relatório, incluindo o status ativo, o tipo de relatório (detalhado, filtrado, por unidade), os campos de pesquisa automática, as opções de cálculo e as propriedades avançadas. |
| **Layout** | Aplique opções dinâmicas de dimensionamento e posicionamento (centralizar, preencher, encaixar). Configure layouts responsivos, a visibilidade de grupos com abas e a disposição dos componentes dentro dos contêineres. |
| **Relatórios principais** | Crie e aplique modelos de relatório para garantir layouts consistentes. Use relatórios padrão ou crie modelos personalizados com contêineres, botões e elementos de identidade visual reutilizáveis. |
| **Coleções de relatórios** | Crie e gerencie coleções de relatórios para agrupar relatórios relacionados. Adicionar/remover relatórios, configurar navegadores de coleções e controlar a visibilidade dos relatórios dentro das coleções. |
| **Permissões do relatório** | Configure o controle de acesso baseado em funções para relatórios. Defina permissões de visualização, edição e exclusão nos níveis de relatório e coleção. Gerenciar a visibilidade dos componentes por função. |

## Orientação de navegação

**Como usar esta referência**

Esta seção foi organizada como um guia de referência para consultar detalhes específicos sobre os recursos do Report Studio. Acesse a subseção relevante de acordo com o que você precisa fazer:

- **Criação de visualizações de dados:** consulte [Tabelas](report-component-table.html) e [Gráficos](report-component-charts.html)
- **Adicionando interatividade:** consulte [Filtros, segmentadores](report-component-filters-slicers.html) e [navegação](report-component-navigation.html)
- **Habilitando a entrada de dados:** consulte [Componentes de entrada](report-component-input-components.html) e [Tabelas editáveis](report-component-editable-components.html)
- **Personalização da aparência:** consulte [Propriedades](report-properties.html) e [Layout do Relatório](layout-options.html)
- **Padronização de relatórios:** consulte [Relatórios Padrão](master-report.html)
- **Gerenciamento de acesso:** consulte [Coleções de relatórios](report-collection.html) e [Permissões de relatórios](report-permissions.html)

**Seções relacionadas**

Para obter orientações passo a passo sobre como criar e personalizar relatórios, consulte estas seções de instruções:

- **Noções básicas sobre relatórios:** instruções passo a passo para criar [relatórios](../../howtoguides/create-reports/create-basic-report.html), adicionar [tabelas](../../howtoguides/create-reports/add-tables-report.html) e [gráficos](../../howtoguides/create-reports/add-chart-visual.html)
- Procedimentos **de personalização de relatórios** para [perspectivas personalizadas](../../howtoguides/create-reports/create-cust-pers.html), [coleções](../../howtoguides/create-reports/build-rc.html) e [relatórios mestre](../../howtoguides/create-reports/design-master-rep.html)
- Orientação **avançada** sobre [relatórios](../../howtoguides/create-reports/drill-thru-reports.html) : relatórios com detalhamento, [componentes editáveis](../../howtoguides/create-reports/add-et-rep.html) e [exportações](../../howtoguides/create-reports/export-print-rep.html)

## Pré-requisitos

Antes de trabalhar com o Report Studio, certifique-se de que:

- Os dados foram enviados através do site Data Studio
- Os modelos de alocação foram criados no Model Studio (para relatórios baseados em objetos)
- Você possui as permissões de função adequadas (Administrador ou Usuário Avançado para edição; Usuário Corporativo para visualização)
- O projeto já possui dados calculados para o período que você deseja relatar

## Painel de configuração de componentes

Ao criar tabelas e gráficos, você usa o painel Configuração de Componentes para definir quais dados serão exibidos. O painel inclui quatro áreas principais: **Linhas** (dimensão de agrupamento), **Valores** (métricas a serem exibidas), **Colunas** (períodos de tempo) e **Filtros** (restrições de dados). Arraste os campos do Explorador de Projetos para essas áreas para configurar os componentes do seu relatório. O painel é exibido de maneira diferente para usuários avançados (acesso total) e analistas (apenas perspectivas personalizadas).
