---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tabela editável + Integração com relatórios"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas editáveis nos relatórios"
source_path: "studio/new-uc/reference/report-studio-reference/et-ri.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tabela editável + Integração com relatórios

Os componentes editáveis da tabela interagem com outros elementos do relatório e com o fluxo de dados.

**Impacto em outros componentes do relatório**

As alterações nos dados da tabela editável não afetam imediatamente os outros componentes do relatório:

- Os gráficos e tabelas vinculados às tabelas de transformação mostram os dados da última publicação

- As alterações salvas, mas não publicadas, só ficam visíveis no componente de tabela editável

- Após a publicação, é necessário que uma compilação ou um cálculo seja concluído para que os demais componentes reflitam as alterações

**Comportamento de atualização**

Após salvar ou publicar:

- O componente de tabela editável é atualizado automaticamente
- Outros componentes podem exigir uma atualização manual ou uma recarga completa do relatório
- Para atualizações em tempo real, configure horários de publicação recorrentes

**Colunas calculadas**

Você pode adicionar colunas de fórmula a componentes de tabela editáveis:

- As colunas calculadas podem fazer referência a valores editáveis de outras colunas
- Os valores são atualizados à medida que os usuários inserem dados
- As colunas de fórmula são sempre de leitura exclusiva

**Tópico principal:** [Componentes de relatórios: Tabelas editáveis em relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
