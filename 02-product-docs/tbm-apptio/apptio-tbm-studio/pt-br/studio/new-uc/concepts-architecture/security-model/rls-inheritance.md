---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Herança e fluxo na RLS"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Segurança em nível de linha (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/rls-inheritance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Herança e fluxo na RLS

Compreender como o RLS circula pelo pipeline de dados é fundamental para evitar falhas de segurança.

**RLS nas alocações de modelos**

Quando os custos são alocados de uma tabela para outra, a configuração do RLS nas tabelas de origem e de destino é independente. Considere um exemplo em que a Unidade de Negócios 3 aloca custos à Unidade de Negócios 2:

- Se Bob (que só tem acesso à Unidade de Negócios 2) consultar os resultados da alocação, ele verá os custos alocados à Unidade de Negócios 2—including, custos esses que se originaram da Unidade de Negócios 3.
- Bob não consegue ver diretamente os dados de origem da BU 3, mas pode ver os efeitos das alocações nas unidades de negócios para as quais tem permissão.

Esse é um comportamento esperado — o RLS filtra as linhas visíveis, mas não impede que os custos alocados sejam repassados pelo modelo.

**RLS nas agregações de relatórios**

Quando um relatório exibe dados agregados (totais, somas, médias), a agregação reflete apenas as linhas visíveis para o usuário atual. Se Bob puder ver apenas a Unidade de Negócios 2, a coluna de custo total em seu relatório mostrará apenas os custos da Unidade de Negócios 2’s — e não o total da organização como um todo.

**RLS e publicação de tabelas editáveis**

Quando um usuário publica alterações de uma tabela editável, o RLS garante que apenas as linhas visíveis para esse usuário sejam editáveis. É importante ressaltar que as linhas ocultas são preservadas durante a publicação — elas não são excluídas nem sobrescritas. Isso significa que vários usuários podem editar diferentes subconjuntos da mesma tabela editável sem interferir nos dados uns dos outros.

Nota:

**Testando o RLS**

Use o filtro de visualização na etapa do pipeline do RLS para testar sua configuração. Digite o endereço de e-mail de um usuário para ver exatamente quais linhas esse usuário veria. Você também pode usar o recurso de representação (disponível para administradores) para visualizar relatórios na perspectiva de um usuário específico.

**Tópico principal:** [Segurança no nível da linha (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
