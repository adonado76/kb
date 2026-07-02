---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Organizar visualizações usando visualizações hierárquicas"
breadcrumb:
  - "Cloudability Premium"
  - "Administração"
  - "Criar e gerenciar visualizações"
source_path: "admin/hierarchical-views.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Organizar visualizações usando visualizações hierárquicas

## Visão geral

O que são visualizações hierárquicas?

As Visualizações Hierárquicas (HV) organizam as visualizações em uma estrutura pai-filho. Nessa hierarquia, uma View pode conter outras Views — chamadas de Views filhas — que, por sua vez, podem ter outras filhas, formando uma estrutura aninhada.

Uma View que contém Views filhas é chamada de Grupo de Views. A condição do filtro é herdada automaticamente de seus filhos, representando a união de todas as suas instruções de filtro. Isso significa que você pode gerenciar a lógica de um Grupo de Visualizações simplesmente adicionando ou removendo Visualizações filhas — sem a necessidade de editar manualmente os critérios de filtro.

**Exemplo:**

- `Marketing` Exibir → Filtro: Tag = “Marketing”
- `Engineering` Exibir → Filtro: Tag = “Engenharia”
- `All Departments` (pai) → O filtro passa automaticamente a ser “Marketing OU Engenharia”.

| Nível | Nome de exemplo | Filtro |
| --- | --- | --- |
| Ver grupo | `All Departments` | (herda tudo o que vem a seguir) |
| Visão da criança 1 | `Marketing` | Tag = “Marketing” |
| Visualização da criança 2 | `Engineering` | Tag = “Engenharia” |

Benefícios das visualizações hierárquicas

1. Filtragem simplificada: os filtros filhos são automaticamente aplicados às visualizações pai, eliminando a necessidade de gerenciar filtros duplicados.
2. Simplifica o gerenciamento de acesso dos usuários: ao atribuir um usuário a uma Visualização pai (Grupo de Visualizações), o acesso é concedido automaticamente a todas as suas Visualizações filhas — e a quaisquer descendentes mais abaixo na hierarquia.
3. Clareza organizacional: visualize seus gastos com nuvem em uma estrutura que reflita a organização da sua empresa no mundo real.
4. Criação e sincronização automáticas com o Mapeamento Hierárquico de Negócios (HBM): as visualizações hierárquicas são geradas automaticamente a partir de um Mapeamento Hierárquico de Negócios (HBM), economizando tempo e reduzindo a configuração manual. Cada valor no arquivo de mapeamento se torna uma Visualização, e o arquivo define como as Visualizações são agrupadas em Grupos de Visualizações. Uma vez criada, a estrutura HV permanece sincronizada e é atualizada automaticamente sempre que o HBM sofre alterações.

## Configurando visualizações hierárquicas

Criar uma visualização hierárquica

1. Acesse Organizar > Visualizações.
2. Selecione “Nova visualização hierárquica ”. A caixa de diálogo “Nova visualização hierárquica” é aberta.
3. Selecione um mapeamento hierárquico de negócios a ser utilizado para definir as visões na hierarquia.
4. Clique em “Adicionar” para criar a hierarquia de visualização.

Nota:

Isso criará automaticamente visualizações que correspondam à definição do HBM. Isso pode levar alguns minutos para ser concluído.

Gerenciar visualizações hierárquicas

Você pode editar e compartilhar visualizações dentro da hierarquia ou excluir a hierarquia inteira.

Nota:

Não é possível editar as condições de filtro das visualizações dentro de uma Visualização Hierárquica (HV), nem excluir visualizações individuais. Tanto as visualizações quanto suas condições de filtro são controladas pelo Mapeamento Hierárquico de Negócios (HBM) associado ao HV.

Alteração das permissões de privacidade de toda a Visualização Hierárquica

Os autores das visualizações podem alterar as permissões (aumentar ou diminuir) da hierarquia de visualizações. Veja como fazer:

1. Acesse Organizar > Visualizações.
2. Clique nas reticências (…) Clique no ícone na linha do nó raiz HV e selecione “Editar ”.

   O painel “Editar grupo de visualização hierárquica” é exibido.
3. Altere a permissão entre “Toda a organização” e “Usuários e grupos”.

   Nota:

   Ao alterar o modo de privacidade para “Organização inteira” e clicar em “Salvar”, todas as atribuições de compartilhamento de usuários existentes serão removidas de todos os nós da hierarquia. Proceda com cautela.

Edição de uma visualização hierárquica

Os usuários com acesso de visualização podem editar as configurações de compartilhamento de uma Visualização Hierárquica. Siga as etapas abaixo:

1. Acesse Organizar > Visualizações.
2. Clique nas reticências (…) Clique no ícone na linha da visualização que você deseja editar e selecione “Editar ”.

   O painel “Editar grupo de visualização hierárquica” é exibido.
3. Selecione os Usuários e Grupos para compartilhar sua visualização com usuários específicos. Use o menu suspenso “Compartilhado com” para selecionar usuários específicos, grupos de usuários ou grupos de IDs do Entrap com os quais deseja compartilhar a visualização.

   Nota:

   Quando uma visualização é atribuída aos usuários, eles também passam automaticamente a ter acesso a todas as visualizações subordinadas. É possível ver os usuários que herdaram acesso à visualização atual na seção “Permissão herdada da visualização ”.

   Quando atribuída, os usuários não podem visualizar nenhum dado até que tenham a permissão ViewsFeatureFullAccess. Para obter mais informações, acesse [Gerenciamento de permissões e funções dos usuários](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(Abre em uma nova guia ou janela)") =

Exclusão de uma visualização hierárquica

Para excluir uma visualização hierárquica, siga as etapas abaixo:

1. Acesse Organizar > Visualizações.
2. Clique nas reticências ao lado do nó raiz e selecione “Excluir”
3. Confirme se deseja excluir o Grupo de Visualizações importado.

   Nota:

   Não é possível excluir visualizações individuais dentro de uma Visualização Hierárquica (HV); apenas o nó raiz pode ser excluído, e somente por um usuário que tenha acesso a ele.

   No entanto, o nó raiz não pode ser excluído se alguma de suas Visualizações filhas for compartilhada com outros usuários. Para prosseguir com a exclusão, é necessário primeiro remover todo o acesso dos usuários a todo o HV.

   Para remover todo o acesso compartilhado:

   - Edite o nó raiz e defina seu modo de compartilhamento como “Toda a organização” e, em seguida, clique em “Salvar”.
   - Edite novamente o nó raiz e altere o modo de compartilhamento de volta para “Usuários e Grupos”; em seguida, salve novamente.

   Esse processo deve remover todos os acessos de usuários existentes, permitindo que você exclua o nó raiz.

**Tópico principal:** [Criar e gerenciar visualizações](../admin/create-and-manage-views.html)
