---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tabelas editáveis"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura de dados"
  - "Tabelas e tipos de tabelas"
source_path: "studio/new-uc/concepts-architecture/data-architecture/editable-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tabelas editáveis

**Objetivo:** Permitir a entrada manual de dados e o aprimoramento manual de dados gerados por máquinas.

As tabelas editáveis permitem que os usuários insiram, modifiquem e gerenciem dados diretamente no TBM Studio. Elas atuam como uma ponte entre os fluxos de dados automatizados e o julgamento humano necessário para tarefas como a classificação de centros de custo, o mapeamento de mão de obra e as anotações orçamentárias.

O TBM Studio suporta dois tipos de tabelas editáveis:

**Tabelas em branco editáveis**

Uma tabela em branco editável começa vazia. Os administradores definem as colunas (esquema), os tipos de dados, as regras de validação e os valores opcionais das listas suspensas. Os usuários preenchem a tabela por meio da interface de relatórios ou da entrada direta de dados.

- **Caso de uso:** Entrada de dados totalmente manual, como a criação de uma tabela de mapeamento para atribuições de centros de custo a soluções, a inserção de justificativas de variações orçamentárias ou a criação de tabelas de referência.
- Os usuários podem adicionar e remover linhas livremente.
- A tabela editável é a fonte de verdade — ela não depende de dados de fontes anteriores.

**Tabelas editáveis com recursos avançados**

Uma tabela editável enriquecida começa com os dados de uma tabela de transformação existente. O sistema carrega todas as linhas e colunas de origem, e os administradores podem adicionar colunas editáveis para que os usuários as preencham. Os usuários podem modificar as colunas editáveis, mas não podem excluir as linhas existentes provenientes da transformação de origem.

- **Caso de uso:** Adicionar contexto humano a dados gerados por máquinas. Por exemplo, um arquivo de faturamento do AWS (transformação de origem) pode exigir que um usuário atribua um projeto responsável a cada tag de instância (coluna editável).
- As linhas de origem são somente para leitura; apenas as colunas adicionadas podem ser editadas.
- Os registros de sobreposição modificam as células nas linhas originais da fonte ou adicionam novas linhas, mas não podem excluir linhas da fonte.

**Tópico principal:** [Tabelas e tipos de tabelas](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
