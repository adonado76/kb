---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Herança"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Relatórios principais"
source_path: "studio/new-uc/reference/report-studio-reference/inheritance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Herança

**Como os relatórios filhos herdam do mestre**

Quando você aplica um relatório mestre a um relatório personalizado (filho), o conteúdo do relatório mestre aparece como uma camada de fundo. O relatório filho herda a aparência visual e quaisquer elementos interativos definidos no relatório mestre, mas o modelo de herança segue o conceito de “papel de parede”:

- Os componentes principais são renderizados primeiro, formando a camada de base
- Os componentes do relatório filho são exibidos sobre a camada principal
- As duas camadas estão visualmente combinadas, mas permanecem funcionalmente separadas

**O que é herdado**

- **Estrutura do layout** : caixas de grupo, contêineres visuais e organização espacial
- **Componentes estáticos** : botões, notas, logotipos e elementos de identidade visual
- **Elementos interativos** : Componentes com guias (as guias funcionam quando o elemento principal é aplicado)
- **Navegação** : Links e botões que permitem navegar entre relatórios

**O que NÃO é herdado**

- **Editabilidade** : os componentes principais não podem ser modificados a partir do relatório secundário
- **Agrupamento de componentes** : as caixas de agrupamento perdem sua funcionalidade de agrupamento nos relatórios secundários
- **Áreas de conteúdo dos componentes das guias** : não é possível adicionar componentes a guias individuais dentro do relatório filho
- **Ligações de dados** : as configurações de dados específicas de cada relatório permanecem exclusivas para cada relatório

**Tópico principal:** [Relatórios principais](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
