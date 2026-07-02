---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Como funciona a RLS"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Segurança em nível de linha (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/how-rls-worls.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Como funciona a RLS

O processo RLS segue uma sequência previsível sempre que um usuário solicita dados:

1. O usuário abre um relatório ou visualiza uma tabela no TBM Studio.
2. O sistema identifica o usuário conectado por meio de seu ID de usuário (endereço de e-mail).
3. Para cada tabela com RLS configurado, o sistema consulta o ID do usuário na(s) tabela(s) de mapeamento correspondente(s).
4. O sistema determina quais valores de dimensão (como unidades de negócios, centros de custo ou centros de dados) o usuário tem permissão para visualizar.
5. O sistema filtra a tabela, exibindo apenas as linhas em que os valores da dimensão em questão correspondem aos valores permitidos pelo usuário.
6. O usuário vê apenas os dados autorizados — as agregações, os totais e as análises detalhadas refletem a visualização filtrada.

**Tópico principal:** [Segurança no nível da linha (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
