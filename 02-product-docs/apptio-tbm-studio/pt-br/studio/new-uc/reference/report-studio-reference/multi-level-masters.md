---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Mestrados em vários níveis"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Relatórios principais"
source_path: "studio/new-uc/reference/report-studio-reference/multi-level-masters.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Mestrados em vários níveis

O TBM Studio permite aplicar relatórios mestre a outros relatórios mestre, criando uma hierarquia potencial. No entanto, **essa prática não é recomendada**.

**Por que não se recomenda fazer mestrados em várias áreas**

- **Complexidade** : os vários níveis de herança dificultam o rastreamento de quais elementos provêm de qual modelo
- **Carga de manutenção** : alterações em qualquer nó mestre da cadeia podem ter efeitos em cascata
- **Dificuldade no diagnóstico de problemas** : as falhas visuais tornam-se mais difíceis de diagnosticar com várias camadas de herança
- **Considerações sobre desempenho** : camadas de renderização adicionais podem afetar o tempo de carregamento dos relatórios

Observação: caso precise de relatórios-mestre em vários níveis, considere reformular sua estrutura de relatórios-mestre para utilizar um único relatório-mestre abrangente que inclua todos os elementos necessários.

**Tópico principal:** [Relatórios principais](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
