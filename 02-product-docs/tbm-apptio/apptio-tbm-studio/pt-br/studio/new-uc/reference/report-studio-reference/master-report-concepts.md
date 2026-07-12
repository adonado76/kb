---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Conceitos do Relatório Principal"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Relatórios principais"
source_path: "studio/new-uc/reference/report-studio-reference/master-report-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conceitos do Relatório Principal

**O que é um Relatório Principal**

Um relatório mestre é um tipo especial de relatório que define elementos de layout reutilizáveis que podem ser aplicados a vários relatórios filhos, como um modelo. O conceito é semelhante ao das diapositivas-modelo em aplicativos de apresentação como o PowerPoint. Quando você aplica um relatório mestre a um relatório personalizado, os componentes do relatório mestre aparecem como uma camada de fundo (frequentemente chamada de “papel de parede”) que proporciona uma estrutura visual consistente.

Os relatórios mestre podem incluir todos os componentes disponíveis nos relatórios comuns, como botões, caixas de grupo, itens de ação, cabeçalhos e elementos de navegação. No entanto, seu objetivo principal é estabelecer uma estrutura consistente na qual o conteúdo específico do relatório seja inserido.

**Diferenças entre o relatório principal e o relatório padrão**

|  |  |  |
| --- | --- | --- |
| **Aspecto** | **Relatório Geral** | **Relatório periódico** |
| **Propósito** | Modelo para vários relatórios | Relatório independente para usuários finais |
| **Nível de hierarquia** | Sempre no nível superior por padrão | Pode ser qualquer nível da hierarquia |
| **Edição de componentes** | Componentes estáticos em relatórios secundários | Todos os componentes são totalmente editáveis |
| **Disponibilidade** | Listado no menu suspenso “Mestrados” | Listado no Explorador de Projetos |
| **Exclusão** | Os modelos padrão não podem ser excluídos | Pode ser excluído (exceto OOTB) |

**Casos de uso para relatórios principais**

Os relatórios-mestre são ideais para situações em que é necessária uma apresentação consistente em vários relatórios:

- **Identidade visual corporativa** : utilize logotipos, cores e estilo consistentes da empresa em todos os relatórios de um projeto
- **Estruturas de navegação** : definir botões e links de navegação uniformes que orientem os usuários pelo conjunto de relatórios
- **Padronização do layout** : definir a disposição consistente de cabeçalhos, rodapés e áreas de conteúdo
- **Conjuntos de filtros comuns** : fornecem segmentadores e filtros compartilhados que se aplicam a relatórios relacionados
- **Coleções de relatórios** : crie uma identidade visual coesa para um conjunto de relatórios analíticos relacionados

**O Modelo do Papel de Parede**

Pense nos relatórios-mestre como um papel de parede. Quando aplicados a um relatório personalizado, os componentes de um relatório mestre:

- Não pode ser editado ou modificado a partir do relatório secundário
- Aparecer como uma camada de fundo estática
- Os componentes que você adiciona ao relatório filho ficam "sobre" os componentes principais
- Só pode ser modificado editando-se diretamente o relatório mestre

Dica: Por exemplo, se o relatório principal incluir uma caixa de grupo, você pode posicionar os componentes no relatório secundário de forma que eles apareçam visualmente dentro da caixa de grupo, mas sem estarem, na verdade, vinculados ou agrupados com a caixa de grupo do relatório principal.

**Tópico principal:** [Relatórios principais](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
