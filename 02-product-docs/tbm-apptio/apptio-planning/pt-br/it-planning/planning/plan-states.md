---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Estados do Plano (Novo, Aberto, Final)"
breadcrumb:
  - "Planning"
  - "Criação e gerenciamento de planos"
source_path: "it-planning/planning/plan-states.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Estados do Plano (Novo, Aberto, Final)

Apptio O planejamento usa **Plan States** para controlar o ciclo de vida de um plano. Cada estado governa quem pode acessar o plano, quais ações podem ser tomadas e quando os dados são bloqueados para relatórios. Isso garante o controle de versões e a governança adequada durante o processo de planejamento.

Observação: As funções de administrador ou de proprietário do processo orçamentário são necessárias para gerenciar os estados do plano.

## Estados do Plano

Os planos passam por três estados do ciclo de vida:

- **Novo**
  - Criado e gerenciado apenas por administradores.
  - Os proprietários de centros de custo não podem visualizar ou editar planos nesse estado.
- **Aberto**
  - Editável por proprietários de centros de custo e usuários autorizados.
  - Se as notificações por e-mail estiverem ativadas, os usuários com acesso de edição a um departamento receberão uma notificação quando um plano for aberto.
- **Final**
  - Estado somente de leitura.
  - Bloqueia os valores planejados, preservando a versão aprovada para análises e relatórios.

## Modificação de um estado do plano

Para atualizar o estado de um plano:

1. Navegue até o **Plano.**
2. Selecione o **menu de estouro de três pontos** no canto superior direito.
3. Para abrir um plano, selecione a opção **Open Plan (Abrir plano** ).
4. Quando um plano estiver aberto, retorne ao menu de estouro e selecione **Finalize Plan (Finalizar plano** ).
   1. Se alguns Departamentos tiverem alterações não enviadas, você poderá fazê-lo:
      - **Submit all changes and finalize (Enviar todas as alterações e finalizar** ) - envia todas as alterações pendentes e move o plano para Final.
      - **Finalize without submitting (Finalizar sem enviar** ) - finaliza o plano, excluindo as alterações não enviadas do departamento.
5. Os administradores sempre podem reabrir um plano finalizado se forem necessários ajustes.
