---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Melhores práticas de navegação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Navegação"
source_path: "studio/new-uc/reference/report-studio-reference/navigation-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Melhores práticas de navegação

**Padrões de navegação consistentes**

- Coloque os controles de navegação em locais consistentes em todos os relatórios (por exemplo, sempre no canto superior esquerdo)
- Use os mesmos estilos e cores de botões para ações de navegação semelhantes
- Forneça opções de navegação para voltar (botão Voltar ou trilha de navegação) para relatórios detalhados
- Inclua rótulos claros e dicas de ferramenta que descrevam o destino da navegação

**Projeto da hierarquia de navegação**

- Crie caminhos de detalhamento que sigam hierarquias lógicas de dados (do resumo ao detalhe)
- Limite a profundidade da navegação a 3 ou 4 níveis para evitar que o usuário se perca
- Crie todos os relatórios como relatórios de nível superior para simplificar o gerenciamento de links
- Caminhos de navegação dos documentos para os responsáveis pela manutenção dos relatórios

**Considerações sobre desempenho**

- Evite acessar relatórios com cálculos complexos que possam causar atrasos
- Mantenha os relatórios em caixas de diálogo modais simples, sem filtros ou seletores complexos
- Considere usar a atualização diferida para relatórios com muitos destinos de navegação
- Teste os caminhos de navegação com volumes de dados realistas

**Resolução de problemas de navegação**

**Encontrar o caminho correto do relatório:**

1. Acesse o relatório desejado
2. Clique com o botão direito do mouse em uma tabela e selecione “Mostrar API” URL
3. O caminho mostrado pode ser adaptado para a sintaxe de links no estilo Wiki
4. Remova o prefixo.View: e use o caminho restante

**Tópico principal:** [Componentes do relatório: Navegação](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
