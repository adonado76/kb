---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar e gerenciar usuários"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Gerenciar usuários e permissões"
  - "Gerenciamento de usuários"
source_path: "studio/new-uc/howtoguides/manage-users-permission/create-manage-users.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar e gerenciar usuários

**Objetivo:** Criar novas contas de usuário e gerenciar usuários existentes no TBM Studio.

**Quando usar:** Ao integrar novos membros da equipe, atualizar informações de usuários ou gerenciar o ciclo de vida dos usuários (ativar/desativar contas).

**Tempo estimado:** 5 a 10 minutos por usuário

**Pré-requisitos**

- Você deve ter a função de administrador ou uma função personalizada com permissões de gerenciamento de usuários.
- Acesso à Administração de Acesso Avançado (Frontdoor).
- O endereço de e-mail do usuário (usado como ID de login), o nome completo e a função pretendida.

## Passos para criar um novo usuário

1. **Acesse a Administração de Acesso Avançado.** No TBM Studio, clique na guia **Projeto** e selecione **Controlar acesso às aplicações d Apptio**. Isso abre a interface de administração do Acesso Avançado.
2. **Acesse a seção Usuários.** Na Administração de Acesso Avançado, localize a seção **Usuários** no menu de navegação.
3. **Clique em “Adicionar usuário”** (ou opção equivalente) para criar uma nova conta de usuário.
4. **Insira os dados do usuário:**
   - **E-mail:** O endereço de e-mail do usuário. Isso passa a ser o nome de usuário para o login.
   - **Nome completo:** O nome e o sobrenome do usuário, tal como constam no sistema.
   - **Senha:** Defina uma senha inicial (o usuário poderá alterá-la posteriormente) ou configure o SSO.
5. **Atribuir função(ões) inicial(is).** Selecione a(s) função(ões) apropriada(s) na lista de funções disponíveis. Consulte *“Atribuir funções aos usuários”* abaixo para obter orientações detalhadas.
6. **Salvar o usuário.** Clique em **Salvar** ou **Criar** para concluir a criação do usuário.

## Resultados esperados

O novo usuário aparece na lista de usuários. Agora, o usuário pode fazer login com seu endereço de e-mail e senha. O nível de acesso deles é determinado pela(s) função(ões) atribuída(s).

## Gerenciamento de usuários existentes

Você pode modificar contas de usuário a qualquer momento por meio da Administração de Acesso Avançada:

- **Editar propriedades do usuário:** atualizar nome, e-mail ou outras informações do perfil.
- **Alterar atribuições de funções:** adicione ou remova funções à medida que as responsabilidades mudam.
- **Redefinir senhas:** Redefina a senha de um usuário caso ele tenha sido bloqueado.
- **Desativar contas:** Desative as contas de usuário quando os funcionários saírem da empresa ou não precisarem mais de acesso.

Aviso: a desativação de um usuário não exclui seus dados históricos nem o registro de auditoria. Se você precisar excluir completamente um usuário por motivos de conformidade, entre em contato com o suporte do Apptio.

## Armadilhas comuns

- **Formato do e-mail:** Certifique-se de que os endereços de e-mail estejam formatados corretamente. Os usuários não conseguem fazer login se o endereço de e-mail estiver digitado incorretamente.
- **Incompatibilidade de domínio:** os usuários devem ser criados no domínio correto para acessar os projetos pretendidos.
- **Falta de atribuição de função:** usuários sem nenhuma função atribuída não podem acessar o TBM Studio. Sempre atribua pelo menos uma função.

**Tópico principal:** [Gestão de usuários](../../../../studio/new-uc/howtoguides/manage-users-permission/manage-up-intro.html)
