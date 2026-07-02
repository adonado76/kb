---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Melhores práticas de layout"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Opções de layout"
source_path: "studio/new-uc/reference/report-studio-reference/layout-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Melhores práticas de layout

**Alinhamento e espaçamento**

- Use caixas de grupo com layout vertical ou horizontal para obter um espaçamento uniforme.
- Defina valores de espaçamento explícitos na caixa de diálogo "Espaçamento" para obter espaços uniformes entre os componentes.
- Alinhe componentes relacionados (por exemplo, um gráfico e sua tabela correspondente) usando caixas de grupo.

**Formatos otimizados para impressão**

- Teste os layouts no modo de layout de impressão antes de finalizar.
- Use o fluxo vertical em relatórios com muitos componentes para garantir uma paginação consistente.
- Insira os filtros de segmentação no final para que os relatórios impressos mostrem o contexto da filtragem.
- Evite colocar informações importantes perto das margens da página.

**Padrões comuns de layout**

|  |  |
| --- | --- |
| **Padrão** | **implementação** |
| **Layout do painel** | Várias caixas de grupo com gráficos e KPIs; filtros em um grupo na barra lateral |
| **Relatório detalhado** | Tabela grande com segmentadores associados; use o fluxo vertical para impressão |
| **Análise por abas** | Componente com guias, apresentando visualizações diferentes em cada guia; filtros compartilhados fora das guias |
| **Mestre-detalhe** | Tabela resumida com botões de detalhamento para acessar relatórios detalhados |

**Tópico principal:** [Opções de layout](../../../../studio/new-uc/reference/report-studio-reference/layout-options.html)
