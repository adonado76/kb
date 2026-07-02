---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Implementar segurança no nível da linha para o acesso do usuário"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Gerenciar usuários e permissões"
  - "Controle de acesso"
source_path: "studio/new-uc/howtoguides/manage-users-permission/implement-rls.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Implementar segurança no nível da linha para o acesso do usuário

|  |  |
| --- | --- |
| **Objetivo** | Configure os mapeamentos entre usuários e dados para que os usuários vejam apenas as linhas para as quais têm autorização |
| **Tempo estimado** | 30 a 45 minutos para a configuração inicial; manutenção contínua à medida que os usuários mudam |
| **Pré-requisitos** | Função de administrador ou usuário avançado; usuários configurados no projeto; compreensão dos seus requisitos de segmentação de dados |

## Quando utilizar este procedimento

Utilize a segurança no nível da linha quando os usuários precisarem visualizar diferentes subconjuntos de dados com base em sua identidade. Entre os cenários mais comuns estão: gerentes de unidades de negócios que visualizam apenas os custos de seus departamentos, gerentes regionais que acessam apenas os dados de suas regiões ou responsáveis por centros de custo distribuídos que analisam seus próprios orçamentos.

Este guia aborda o aspecto do mapeamento de usuários do RLS. Para obter informações completas sobre a implementação técnica, incluindo a configuração do pipeline de transformação, consulte **a seção “ 3.1.4: : Segurança de dados** ”.

## Compreendendo a arquitetura do RLS

A segurança por linha no TBM Studio consiste em dois componentes principais:

- **Tabelas de mapeamento:** Defina quais usuários podem acessar quais itens de dados (por exemplo, o usuário bob@acme.com pode visualizar a Unidade de Negócios 2)
- **Filtros RLS:** aplicados às tabelas de transformação para garantir o cumprimento das regras de mapeamento quando os usuários visualizam relatórios

As tabelas de mapeamento são armazenadas no projeto **Row-Level Security**, que é instalado automaticamente quando uma nova instância do TBM Studio é criada e se aplica a todos os projetos de um domínio.

## Passos

## Passo 1: Planeje a estrutura do seu RLS

Antes de criar tabelas de mapeamento, determine:

- Por qual dimensão você vai filtrar? (por exemplo, Unidade de Negócios, Centro de Custos, Região)
- Quais usuários precisam ter acesso a quais valores dessa dimensão?
- Existem usuários que precisam de acesso a todos os dados? (Talvez seja necessário criar uma tabela de mapeamento separada com "acesso total")

## Passo 2: Criar a tabela de mapeamento

1. Abra o menu Configurações e clique em **Configurar segurança no nível da linha**.
2. Crie uma nova tabela (ou prepare uma externamente no formato Excel/ CSV ) com duas colunas obrigatórias:
   - **ID:** O ID do usuário (endereço de e-mail correspondente à tabela Usuários)
   - **Item:** O valor ao qual o usuário pode acessar (por exemplo, "BU 2", "América do Norte")
3. Preencha a tabela de mapeamento com associações entre usuários e itens. Por exemplo:

   |  |  |
   | --- | --- |
   | **ID** | **Unidade de Negócios** |
   | bob@acme.com | BU 2 |
   | rachel@acme.com | BU 1 |
   | rachel@acme.com | BU 3 |

   Dica: Se um usuário precisar acessar vários valores, inclua várias linhas para esse usuário (como mostrado para rachel@acme.com acima).
4. Carregue a tabela de mapeamento no projeto de Segurança em Nível de Linha.

## Etapa 3: Criar um mapeamento de acesso total (opcional)

Para usuários que precisam visualizar todos os dados (por exemplo, executivos, administradores financeiros), crie uma tabela separada com acesso total, em vez de listar todos os valores possíveis:

|  |  |
| --- | --- |
| **ID** | **É o administrador** |
| sally@acme.com | Sim |

Essa abordagem garante que os usuários com acesso total vejam automaticamente os novos itens de dados sem precisar atualizar seu mapeamento.

## Passo 4: Aplicar filtros RLS às tabelas

Depois de criar as tabelas de mapeamento, aplique-as às suas tabelas de dados. Para obter instruções detalhadas sobre como configurar as etapas do pipeline do RLS, consulte **a seção “Segurança de dados do 3.1.4:** ”.

## Etapa 5: Testar a configuração do RLS

- Use o **filtro de visualização** na etapa RLS para testar o que usuários específicos verão
- Use o recurso **"Representar"** para visualizar relatórios na perspectiva de um usuário específico
- Verifique se os usuários com acesso total têm acesso a todos os dados
- Verifique se os usuários com acesso restrito visualizam apenas os dados para os quais têm autorização

## Comportamento do RLS em diferentes recursos

Compreender como o RLS se comporta nas diferentes funcionalidades do TBM Studio:

- **Tabelas de transformação:** o RLS filtra as linhas antes que os dados apareçam em qualquer uso posterior
- **Tabelas editáveis:** o RLS restringe quais linhas os usuários podem ver E editar. Os usuários só podem modificar as linhas visíveis.
- **Relatórios:** as agregações refletem apenas os dados filtrados visíveis ao usuário
- **Publicação:** Quando os usuários publicam tabelas editáveis, as linhas ocultas são mantidas — não são excluídas
- **Relatórios de visão geral do modelo:** cada nível reflete apenas o RLS aplicado a esse nível específico; os valores podem não corresponder aos totais apresentados nos níveis superiores

Importante: As tabelas não herdam automaticamente as configurações de RLS. É necessário adicionar uma etapa RLS para cada tabela que precise de filtragem no nível da linha.

## Armadilhas comuns

- **IDs de usuário incompatíveis:** a coluna ID na sua tabela de mapeamento deve corresponder exatamente ao ID de usuário na tabela Usuários. Mesmo que sejam pequenas diferenças (distinção entre maiúsculas e minúsculas, espaços a mais), o RLS pode falhar.
- **Contorno de privilégios de administrador:** Não confie no RLS para proteger os dados contra usuários com privilégios de administrador. Eles podem acessar o modo Studio e modificar a configuração do RLS.
- **Custos alocados:** Se os custos forem alocados de áreas restritas para áreas visíveis, os usuários poderão visualizar custos que se originaram fora do seu âmbito de autorização.
- **RLS ausente nas tabelas de detalhamento:** Certifique-se de que o RLS esteja configurado em todas as tabelas que aparecem nos relatórios de detalhamento.

## Tarefas relacionadas

- [Configurar etapas do pipeline do RLS](../work-with-data/htg-arls.html)
- Carregue os dados do RLS através do site DataLink (Seção 5.1 )
- [Entenda o modelo de segurança](../../concepts-architecture/studio-model/security-architecture.html) (Seção 4.4 )

**Tópico principal:** [Controle de acesso](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
