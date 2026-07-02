---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Gerenciar notificações por e-mail"
breadcrumb:
  - "Planning"
  - "Fluxos de trabalho e colaboração"
source_path: "it-planning/planning/manage-email-notifications.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gerenciar notificações por e-mail

Apptio envia automaticamente notificações por e-mail para eventos importantes no processo de planejamento. Essas notificações ajudam a informar os usuários sobre as ações necessárias, alterações de status e atualizações feitas durante os fluxos de trabalho de envio e aprovação do orçamento.

Os administradores podem controlar se os usuários devem receber notificações por e-mail ou não.

## Notificações por e-mail sobre alterações no status do plano

As notificações por e-mail são enviadas com base na **função** do usuário, **nas permissões de edição** e **na posição na cadeia de aprovação**.

**Quando um plano é aberto**

Os usuários com acesso de edição ao plano ( **Nível de edição: Proprietário, Editar e enviar, Editar** ) recebem uma notificação por e-mail.

**Quando um plano é apresentado**

- Os usuários com acesso de edição ao Departamento enviado ( **Nível de edição: Proprietário, Editar e Enviar, Editar** ) recebem um e-mail confirmando o envio.
- **Os aprovadores de nível 1** recebem uma notificação por e-mail solicitando aprovação.

**Quando um plano é parcialmente aprovado**

- Os usuários com acesso de edição ao Departamento aprovado ( **Nível de edição: Proprietário, Editar e Enviar, Editar** ) recebem um e-mail indicando que o plano foi aprovado pelo nível de aprovação atual.
- **O aprovador do próximo nível** na cadeia de aprovação recebe um e-mail solicitando a aprovação.
- Esse processo continua em todos os níveis de aprovação.

**Quando um plano é totalmente aprovado**

Os usuários com acesso de edição ao Departamento aprovado ( **Nível de edição: Proprietário, Editar e Enviar, Editar** ) recebem um e-mail confirmando a aprovação final.

**Quando um plano é devolvido**

Os usuários com acesso de edição ao Departamento ( **Nível de edição: Proprietário, Editar e Enviar, Editar** ) recebem uma notificação por e-mail informando que o plano foi devolvido.

**Quando um plano é desbloqueado**

Os usuários com acesso de edição (Nível de edição: Proprietário, Editar e Enviar e Editar) para o Departamento receberão uma notificação por e-mail informando que seu plano foi revogado/não enviado.

**Quando um comentário é adicionado**

Os usuários com acesso de edição ao departamento relacionado recebem uma notificação por e-mail.

Esses eventos garantem que os usuários sejam informados quando sua revisão ou ação for necessária. Consulte [Fluxos de trabalho de](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-about-approval "(Abre em uma nova guia ou janela)") aprovação para obter mais detalhes.

## Ativar notificações por e-mail

Observação: *as funções de administrador ou responsável pelo processo orçamentário são necessárias para realizar essas tarefas.*

1. Navegue até **Configurações (ícone de engrenagem) → Perfil da empresa**.
2. Habilite **o envio de notificações por e-mail para eventos do processo de planejamento.**
3. Selecione **Salvar e Sair**.
