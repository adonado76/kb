---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Funções e permissões do usuário"
breadcrumb:
  - "Costing Standard"
  - "Administração"
source_path: "cost-transparency/admin/user-role-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Funções e permissões do usuário

IBM Apptio O Costing Standard utiliza controle de acesso baseado em funções para garantir que os usuários tenham visibilidade e permissões adequadas em modelos de custos, dados e relatórios. As funções definem o nível de acesso dentro do aplicativo, enquanto as permissões fornecem um controle mais granular sobre tarefas específicas. Essa estrutura ajuda as organizações a equilibrar governança, segurança e acesso self-service entre as partes interessadas das áreas financeira, de TI e de negócios. IBM Apptio usa o aplicativo **Frontdoor** para gerenciar usuários, suas funções e permissões em toda a plataforma. A Frontdoor fornece gerenciamento centralizado de identidade e acesso, garantindo uma governança consistente dos usuários em todos os projetos e soluções.

## Gerenciar usuários

Os administradores podem gerenciar usuários adicionando novos usuários, ativando ou desativando usuários existentes, exportando a lista de usuários e excluindo usuários quando o acesso não for mais necessário.

Para gerenciar usuários, navegue até o menu **Configurações** (![engrenagem](_829212255.)) e selecione **Administração de acesso**. O console de administração do Access abre com a guia **Usuários** selecionada por padrão. Nesta página, os administradores podem pesquisar todos os registros de usuários, filtrar e classificar a lista de usuários e ocultar usuários inativos usando os controles disponíveis na parte superior da página.

Use esta tela para adicionar, atualizar ou remover o acesso do usuário conforme necessário para manter a governança e a segurança adequadas.

Para obter mais detalhes sobre como realizar essas ações, clique [aqui.](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-users "(Abre em uma nova guia ou janela)")

## Gerenciar funções e permissões do usuário

As funções definem um conjunto de permissões e capacidades que controlam as ações que os usuários podem realizar dentro de IBM Apptio. Cada usuário recebe uma ou mais funções que determinam seu nível de acesso e funcionalidade.

Para gerenciar funções, navegue até o menu **Configurações (**![engrenagem](_8791317.)**)** e selecione **Administração de acesso**. No menu de navegação à esquerda, clique em **Funções e Permissões**. Esta página permite que os administradores adicionem, modifiquem ou removam atribuições de funções para usuários dentro de um projeto.

Para obter mais detalhes sobre como gerenciar funções e permissões, clique [aqui.](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(Abre em uma nova guia ou janela)")

## Funções padrão do usuário

IBM Apptio O Padrão de Custeio inclui estas funções predefinidas:

- **Admin**
- Acesso administrativo completo às aplicações Costing Standard, TBM Studio, Datalink, Planning e Interactive Benchmarking, sem restrições funcionais.
- **Administração empresarial**
- Executa tarefas administrativas avançadas, incluindo promoções de autoatendimento e configuração e execução de DataLink.
- **Usuário avançado**
- Cria e gerencia projetos e modelos, carrega e transforma dados e elabora relatórios e painéis.
- **Analista**
- Cria relatórios e análises pessoais utilizando os dados disponíveis e visualiza relatórios existentes.
- **Gerenciador de Serviços**
- Carrega dados e analisa relatórios relacionados com serviços e desempenho operacional.
- **Gestor de Projeto**
- Analisa relatórios financeiros e operacionais relacionados ao projeto para acompanhar custos, progresso e resultados.
- **Financeiro**
- Visualiza relatórios financeiros para analisar custos, orçamentos e variações em todos os domínios de TI.
- **Usuário corporativo**
- Relatórios compartilhados de visualizações disponibilizados em toda a organização para insights gerais sobre os negócios.
- **Usuário executivo**
- Visualiza todos os relatórios publicados para apoiar a tomada de decisões estratégicas e executivas.
- **Somente visualizar**
- Fornece acesso somente leitura aos relatórios de produção; os usuários podem visualizar o conteúdo publicado, mas não podem modificar ou criar relatórios.

## Funções customizadas

Além das funções padrão, IBM Apptio permite criar **funções personalizadas** usando o aplicativo Frontdoor. As funções personalizadas permitem que as organizações adaptem o acesso dos usuários com base em responsabilidades específicas e requisitos de governança.

Você também pode duplicar uma função padrão existente e modificar suas permissões, adicionando ou removendo recursos para atender às necessidades da sua organização.

Para obter mais detalhes sobre como criar e gerenciar funções personalizadas, clique [aqui](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles#Manageuserpermissionsandroles__Createcustomroles__title__1 "(Abre em uma nova guia ou janela)").
