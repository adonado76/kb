---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Âmbito do RLS: Onde o RLS se aplica"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Segurança em nível de linha (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/rls-scope.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Âmbito do RLS: Onde o RLS se aplica

O RLS pode ser aplicado em várias áreas do TBM Studio. Entender onde isso se aplica — e onde não se aplica — é essencial para uma cobertura de segurança completa.

|  |  |  |
| --- | --- | --- |
| **Área** | **Comportamento da RLS** | **Notas** |
| Tabelas de transformação ( Data Studio ) | Aplicado por meio de uma etapa do pipeline RLS adicionada individualmente a cada tabela | Ao adicionar uma etapa RLS, uma etapa de modelagem é adicionada automaticamente. Apenas tabelas modeladas e tabelas editáveis podem ter RLS. |
| Objetos de modelo (Model Studio) | Os filtros RLS são transmitidos a partir das tabelas de transformação subjacentes | Cada etapa do modelo requer sua própria configuração do RLS. O RLS não é herdado automaticamente entre as etapas do modelo. |
| Relatórios (Report Studio) | Os relatórios exibem dados filtrados pelo RLS. As agregações refletem a visualização filtrada. | Todas as tabelas criadas com o Ad Hoc Query são censuradas. Algumas tabelas legadas podem não estar. |
| Tabelas editáveis | Os usuários só podem visualizar e editar as linhas permitidas pela sua configuração de RLS | As linhas ocultas são mantidas durante a publicação — elas não são excluídas nem sobrescritas. |
| Relatórios de visão geral do modelo | Cada nível reflete o RLS aplicado à tabela desse nível específico | Os valores de um nível podem não corresponder ao total exibido nos níveis superiores se o RLS for aplicado apenas aos níveis subordinados. |
| Relatórios detalhados | O RLS é aplicado à tabela de resultados com base na configuração de RLS da própria tabela | A tabela derivada utiliza suas próprias regras RLS, e não as regras da tabela pai. |

Importante:

**Importante: o RLS não é herdado automaticamente**

As tabelas não herdam automaticamente as configurações de RLS. É necessário adicionar uma etapa RLS para cada etapa do modelo que exija segurança de dados. Se você configurar o RLS na Origem de Custos, mas não nas Torres de Recursos de TI, os usuários poderão ver dados não filtrados ao visualizar relatórios baseados nas Torres de Recursos de TI.

**Tópico principal:** [Segurança no nível da linha (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
