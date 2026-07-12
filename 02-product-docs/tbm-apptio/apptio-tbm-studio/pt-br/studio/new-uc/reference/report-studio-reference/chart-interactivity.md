---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Recursos de interatividade dos gráficos"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/chart-interactivity.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recursos de interatividade dos gráficos

**Dicas de ferramentas**

Quando os usuários passam o mouse sobre os elementos do gráfico, as dicas de ferramenta exibem informações contextuais:

- Gráficos de barras: A dica de ferramenta exibe o valor da barra.
- Gráficos de barras empilhadas: a dica de ferramenta mostra tanto o valor quanto a porcentagem do segmento.
- Gráficos de pizza: A dica de ferramenta exibe o valor da fatia e a porcentagem do total.
- Gráficos em cascata: quando a opção “Explicação nas dicas de ferramenta” está ativada, a dica de ferramenta inclui o texto explicativo.

**Interação com a legenda**

Em todos os gráficos com legendas, os usuários podem clicar nos itens da legenda para mostrar ou ocultar séries de dados específicas. Os itens ocultos aparecem em cinza. Isso permite que os usuários se concentrem em dados específicos sem alterar a configuração do gráfico. Quando os elementos estão ocultos, os cálculos percentuais (como em gráficos empilhados) são ajustados para refletir apenas os elementos visíveis.

**Ampliar (Gráficos de linhas)**

Os gráficos de linhas permitem o zoom interativo. Clique e arraste horizontalmente pelo gráfico para ampliar um período específico. Um link "Redefinir zoom" aparece no canto superior direito para voltar à visualização completa. O zoom é reiniciado automaticamente ao sair do relatório.

**Integração do Slicer**

Os gráficos criados com a Configuração de Componentes Ad Hoc respondem aos filtros no mesmo relatório. Quando os usuários selecionam valores em um filtro, o gráfico é filtrado automaticamente para exibir apenas os dados correspondentes. Isso se aplica a todos os tipos de gráficos, exceto aos gráficos em cascata (que respondem aos filtros, mas apresentam um comportamento especial para os passos intermediários).

**Tópico principal:** [Componentes do relatório: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
