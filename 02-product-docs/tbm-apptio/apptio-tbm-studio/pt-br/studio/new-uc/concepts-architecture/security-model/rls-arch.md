---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "RLS Arquitetura"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Segurança em nível de linha (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/rls-arch.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# RLS Arquitetura

A implementação do RLS requer dois componentes essenciais: tabelas de mapeamento que definem as relações entre usuários e dados, e regras de filtragem que aplicam essas relações às tabelas de dados.

**O Projeto de Segurança em Nível de Linha**

O RLS é gerenciado por meio de um projeto específico chamado Row-Level Security. Este projeto é instalado automaticamente quando uma nova instância do Apptio é criada e se aplica a todos os projetos de um domínio. Você acessa essa opção no menu Configurações clicando em “Configurar segurança por linha”.

**Tabelas de mapeamento**

As tabelas de mapeamento definem quais dados cada usuário pode visualizar. Uma tabela de mapeamento deve ter pelo menos duas colunas:

- **ID do usuário:** O endereço de e-mail do usuário, que deve corresponder ao seu ID de usuário na tabela Usuários.
- **Item:** O valor que o usuário tem permissão para visualizar, tal como aparece na tabela de dados protegida (por exemplo, nome de uma unidade de negócios, código de centro de custo ou nome de um centro de dados).

**Exemplo — Tabela de mapeamento de acesso da BU:**

|  |  |
| --- | --- |
| **ID de Usuário** | **Unidade de negócios** |
| bob@acme.com | BU 2 |
| rachel@acme.com | BU 1 |
| rachel@acme.com | BU 3 |
| tom@acme.com | BU 1 |

Neste exemplo, Bob só pode ver os dados da BU 2. Rachel consegue ver a BU 1 e a BU 3. Tom consegue ver apenas a BU 1. Observe que Rachel tem duas linhas — uma para cada unidade de negócios à qual ela tem permissão de acesso.

**Padrão de acesso total**

Para usuários que precisam visualizar todos os dados (como executivos ou analistas responsáveis por toda a organização), é possível criar uma tabela de mapeamento separada com uma coluna de marcação, em vez de listar todos os valores possíveis.

|  |  |
| --- | --- |
| **ID de Usuário** | **É o administrador** |
| sally@acme.com | Sim |
| cfo@acme.com | Sim |

Em seguida, adicione uma coluna de fórmula à tabela protegida que sempre retorne “Sim” e crie uma regra de filtro RLS usando a lógica OR: o usuário deve constar na tabela de mapeamento padrão para suas unidades de negócios específicas OU constar na tabela de acesso total. Essa abordagem se adapta automaticamente quando novas unidades de negócios são adicionadas — não é necessário atualizar os registros dos usuários com acesso total.

**Lógica de filtragem**

As regras de filtragem RLS conectam as tabelas de mapeamento às tabelas de dados. Cada regra de filtro possui quatro componentes:

1. **Coluna da tabela:** a coluna na tabela de dados que contém os itens a serem filtrados (como a coluna BU em Cost Source).
2. **Tabela de mapeamento:** A tabela de mapeamento que contém as definições do RLS (como o acesso à unidade de negócios).
3. **Coluna de mapeamento:** a coluna na tabela de mapeamento que contém os valores permitidos (como a coluna “Unidade de Negócios” no BU Access).
4. **Coluna do usuário:** a coluna na tabela de mapeamento que contém os IDs dos usuários (como a coluna “ID do usuário” no BU Access).

Quando várias entradas de filtro são definidas, elas utilizam a lógica OR por padrão — se qualquer uma das entradas for verdadeira, o usuário poderá ver a linha. É assim que funciona o padrão de acesso total: o usuário corresponde à tabela de mapeamento padrão OU à tabela de acesso total.

**Tópico principal:** [Segurança no nível da linha (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
