---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gerenciamento de usuários"
breadcrumb:
  - "TBM Studio"
  - "Administração"
source_path: "studio/new-uc/admin/user-management.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gerenciamento de usuários

**Tipo de conteúdo:** Guia prático / Referência

**Público-alvo:** Administradores

**Pré-requisitos:** Função de administrador, acesso à Administração do Access

A gestão de usuários no TBM Studio envolve a criação e o gerenciamento de contas de usuário, a atribuição de funções e o controle do acesso a projetos e recursos. A principal ferramenta para o gerenciamento de usuários é a Administração de Acesso Avançada (Frontdoor).

## Entendendo funções e permissões

As funções determinam quais ações os usuários podem realizar no TBM Studio. Cada usuário é atribuído a uma ou mais funções, e as permissões combinadas de todas as funções atribuídas definem seu nível de acesso.

**Funções padrão do sistema:**

|  |  |
| --- | --- |
| **Função** | **Recursos** |
| **Admin** | Acesso total a todos os recursos, incluindo gerenciamento de usuários, configurações de projeto, configurações de domínio e todas as funções do TBM Studio. Pode criar e encerrar ramos. |
| **Usuário avançado** | Acesso ao modo TBM Studio para construir modelos, criar relatórios e configurar fluxos de dados. Não é possível gerenciar usuários ou configurações de domínio. |
| **Usuário corporativo** | Acesso somente para visualização a relatórios e painéis. Pode interagir com tabelas editáveis, se configurado. Não é possível acessar o modo TBM Studio. |

**Nota:** *É possível criar funções personalizadas para proporcionar um controle granular de permissões. Entre em contato com o administrador do sistema para configurar funções personalizadas de acordo com as necessidades da sua organização.*

## Gerenciamento de contas de usuário

O gerenciamento de contas de usuário é realizado por meio do Enhanced Access Administration (Frontdoor). Essa interface centralizada permite que os administradores criem contas, atribuam funções e gerenciem o acesso em todas as aplicações d Apptio.

**Para acessar o gerenciamento de usuários:**

1. Clique no ícone **de Configurações** no canto superior direito.
2. Selecione "**Administração de acesso** ".
3. Acesse a guia **“Usuários”** para visualizar e gerenciar contas de usuário.

## Propriedades do usuário

Cada conta de usuário possui propriedades que controlam sua experiência no TBM Studio. Os usuários podem modificar algumas dessas propriedades por conta própria através da caixa de diálogo “Minha conta”.

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| **E-mail** | O identificador de login do usuário. Não pode ser alterado pelo usuário. |
| **Nome Completo** | Nome de exibição mostrado na lista de usuários e nos registros de atividades. |
| **Função atual** | Função ativa que determina as permissões. Os usuários podem alternar entre as funções disponíveis. |
| **Moeda** | Moeda padrão para relatórios. As preferências do usuário têm prioridade sobre as configurações do projeto. |
| **Localidade** | Preferência de formatação de números (por exemplo, EUA: 12. 345.67, em comparação com a Alemanha: 12.345,67). |

## Controle da visibilidade do projeto

A visibilidade do projeto determina quais funções podem visualizar e acessar projetos específicos. Isso permite restringir o acesso a projetos confidenciais ou em desenvolvimento.

**Para configurar a visibilidade do projeto:**

1. Acesse **Configurações > Administração** de acesso.
2. Na guia **“Aplicativos”**, localize seu projeto.
3. Clique em **“Editar visibilidade”** para selecionar quais funções podem acessar o projeto.
4. Clique em **“Salvar”** e, em seguida**, em “Mostrar”** para tornar o projeto visível.
