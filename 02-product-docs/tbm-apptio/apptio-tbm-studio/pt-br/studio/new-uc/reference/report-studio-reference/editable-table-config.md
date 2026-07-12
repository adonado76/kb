---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configuração editável da tabela"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas editáveis nos relatórios"
source_path: "studio/new-uc/reference/report-studio-reference/editable-table-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuração editável da tabela

A configuração de um componente de tabela editável envolve conectar-se a uma fonte de dados, selecionar colunas e definir comportamentos de edição.

**Conexão com a fonte de dados**

Para adicionar um componente de tabela editável a um relatório:

1. Confira o relatório no Report Studio
2. Vá até a guia Relatório e selecione o componente Tabela editável
3. No painel Configuração de Componentes, selecione a tabela editável na perspectiva Tabelas
4. Arraste as colunas da tabela para a área “Colunas incluídas”

Dica: Somente as tabelas criadas como tabelas editáveis no Data Studio aparecerão como fontes válidas para componentes de tabela editáveis.

**Mapeamento de colunas**

Ao configurar o componente, você controla quais colunas ficam visíveis e em que ordem:

- **Colunas incluídas:** Arraste as colunas da tabela de origem para torná-las visíveis no relatório
- **Ordem das colunas:** Reorganize as colunas arrastando-as dentro da área “Colunas incluídas”
- **Colunas ocultas:** as colunas não incluídas permanecem na tabela subjacente, mas não são exibidas

Colunas do sistema, como.PK (chave primária),.Username e .EditDate, podem ser exibidas ou ocultadas clicando com o botão direito do mouse no cabeçalho da coluna e selecionando Exibir ou Ocultar.

**Filtragem de linhas**

Você pode limitar quais linhas aparecem no componente de tabela editável:

- Arraste as colunas de filtro para a área Filtros do painel Configuração de Componentes
- Clique com o botão direito do mouse no filtro e selecione “Editar filtro” para definir os valores do filtro
- Os filtros podem ser estáticos (valores fixos) ou vinculados a segmentadores para filtragem dinâmica

Aviso: *Quando a Segurança por Linha (RLS) está ativada, os usuários veem apenas as linhas para as quais têm autorização, independentemente dos filtros definidos no relatório.*

**Tópico principal:** [Componentes de relatórios: Tabelas editáveis em relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
