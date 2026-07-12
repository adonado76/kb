---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Melhores práticas para permissões"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Permissões do relatório"
source_path: "studio/new-uc/reference/report-studio-reference/permission-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Melhores práticas para permissões

**Padrões de projeto de permissões**

**Padrão 1: Acesso amplo com filtragem RLS**

- Defina as permissões do relatório como “Todos”
- Use o RLS para filtrar dados confidenciais por usuário
- Simplifica o gerenciamento de permissões, mantendo a segurança dos dados

**Padrão 2: Relatórios segmentados por função**

- Crie relatórios separados para cada público
- Configure cada relatório para funções específicas
- Oferece experiências personalizadas, mas aumenta a manutenção

**Padrão 3: Relatório único com visibilidade de componentes**

- Crie um relatório destinado a vários públicos
- Use a visibilidade dos componentes para mostrar ou ocultar elementos de acordo com a função
- Reduz o número de relatórios, ao mesmo tempo em que oferece visualizações adequadas a cada função

**Padrão 4: Organização baseada em coleções**

- Relatórios por público nas coleções
- Configurar permissões no nível da coleção
- Os relatórios herdam as configurações da coleção, reduzindo a necessidade de configurações individuais

**Princípio do privilégio mínimo**

Aplique o princípio do privilégio mínimo ao configurar as permissões dos relatórios:

1. **Comece de forma restrita:** inicie com acesso limitado e amplie conforme necessário
2. **Use funções específicas:** evite conceder acesso a “Todos”, a menos que seja realmente apropriado
3. **Segurança em camadas:** combine permissões de relatórios com o RLS para dados confidenciais
4. **Revisão periódica:** Verifique regularmente quem tem acesso a relatórios confidenciais

**Tópico principal:** [Permissões de relatório](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
