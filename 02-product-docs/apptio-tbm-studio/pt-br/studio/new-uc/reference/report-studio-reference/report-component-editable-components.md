---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Componentes do relatório: Tabelas editáveis nos relatórios"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
source_path: "studio/new-uc/reference/report-studio-reference/report-component-editable-components.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componentes do relatório: Tabelas editáveis nos relatórios

O componente de relatório “Tabela editável” permite fluxos de trabalho de entrada de dados diretamente na interface de relatórios. Os usuários podem inserir, modificar e publicar dados sem precisar acessar o TBM Studio, o que torna a solução ideal para cenários de coleta de dados distribuída, como fluxos de trabalho de inserção de orçamento, enriquecimento de dados e classificação de dados.

## Visão geral do componente de tabela editável

O componente de relatório “Tabela editável” exibe dados de uma tabela editável subjacente (criada no Data Studio ) e permite que usuários autorizados modifiquem esses dados diretamente a partir de um relatório. Entender como esse componente difere de outros tipos de tabela é essencial para uma implementação adequada.

**Diferenças em relação às tabelas de relatórios padrão**

As tabelas padrão nos relatórios (Seção 5.3.1 ) exibem dados somente para leitura provenientes de tabelas de transformação ou objetos de modelo. As principais diferenças em relação aos componentes de tabela editáveis incluem:

- As tabelas padrão não podem ser modificadas pelos usuários finais; os componentes editáveis das tabelas permitem a inserção direta de dados
- As tabelas padrão exibem dados calculados ou agregados; as tabelas editáveis armazenam valores inseridos pelo usuário
- As tabelas padrão são atualizadas automaticamente quando as fontes de dados são alteradas; as tabelas editáveis exigem ações explícitas de salvamento e publicação
- As tabelas editáveis incluem controles adicionais para as operações de adicionar linha, excluir linha, salvar e publicar

**Diferença em relação às tabelas editáveis do Data Studio**

As tabelas editáveis são definidas em Data Studio (Seção 5.1 ) e disponibilizadas por meio de componentes de relatório. A relação funciona da seguinte maneira:

- Data Studio : Define o esquema da tabela editável, os tipos de coluna, as regras de validação e os valores possíveis
- Report Studio: Cria o componente voltado para o usuário que exibe a tabela e permite sua edição
- O componente de relatório herda as definições de colunas da configuração do ` Data Studio `
- As configurações no nível do relatório determinam quais colunas ficam visíveis e editáveis, bem como a forma como os dados são apresentados

**Casos de uso comuns**

Os componentes de tabela editáveis são ideais para os seguintes cenários:

- **Entrada no orçamento:** Permitir que os responsáveis pelos centros de custo insiram as previsões orçamentárias diretamente nos relatórios
- **Enriquecimento de dados:** permite que os usuários adicionem classificações, categorias ou mapeamentos aos dados importados
- **Mapeamento de mão de obra:** permita que as equipes de RH ou de finanças atribuam funcionários a centros de custo ou projetos
- **Explicações sobre os desvios:** Recolher as justificativas dos chefes de departamento para os desvios orçamentários
- **Fluxos de trabalho de aprovação:** acompanhe o status da aprovação e os comentários relativos às partidas individuais

- **[Configuração editável da tabela](../../../../studio/new-uc/reference/report-studio-reference/editable-table-config.html)**
- **[Opções de edição de colunas](../../../../studio/new-uc/reference/report-studio-reference/column-editing-options.html)**
- **[Configuração de validação](../../../../studio/new-uc/reference/report-studio-reference/validation-config.html)**
- **[Operações em linhas](../../../../studio/new-uc/reference/report-studio-reference/row-operations.html)**
- **[Salvar comportamento](../../../../studio/new-uc/reference/report-studio-reference/save-behavior.html)**
- **[Editar permissões](../../../../studio/new-uc/reference/report-studio-reference/edit-permissions.html)**
- **[Formatação de tabelas editáveis](../../../../studio/new-uc/reference/report-studio-reference/styling-editable-tables.html)**
- **[Tabela editável + Integração com relatórios](../../../../studio/new-uc/reference/report-studio-reference/et-ri.html)**
- **[Padrões comuns](../../../../studio/new-uc/reference/report-studio-reference/common-patterns.html)**
- **[Resolução de problemas](../../../../studio/new-uc/reference/report-studio-reference/editable-troubleshoot.html)**
