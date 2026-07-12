---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Priorização de Calc"
breadcrumb: []
source_path: "studio/admin/default-calc-prioritization.html"
images:
  - "resources/images/studio_images/calc-prior-dragdrop.png"
  - "resources/images/studio_images/calc-prioritization.png"
  - "resources/images/studio_images/cm-proj-calc-mgmt.png"
  - "resources/images/studio_images/cp-dev-queue.png"
  - "resources/images/studio_images/cp-dragdrop.png"
  - "resources/images/studio_images/cp-phase2.png"
  - "resources/images/studio_images/cp-staging-q.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Priorização de Calc

Aplica-se a: 12.10.9 e 12.10.10. De 12.11.0.

Os administradores podem priorizar o cálculo de projetos com base na importância do projeto ou na urgência de tempo. Ele é aplicável a todos os projetos, domínios e ramificações em sua instância em TBM Studio. Os projetos agora serão calculados de acordo com os números atribuídos a eles. Os administradores podem arrastar e soltar projetos para a ordem desejada e documentar o motivo das alterações. O principal benefício é definir a ordem de cálculo dos projetos após a redefinição de uma instância. Além disso, se um cálculo estiver em andamento, a priorização do cálculo determinará a ordem dos check-ins subsequentes.

Consulte [Gerenciamento de Calc](cacl-mgmt-settings.htm "(Abre em uma nova guia ou janela)")

O Calc Prioritization não está ativo por padrão. Para ativá-lo, navegue até **Projeto** > **Ativar recursos** e, em seguida, selecione **Gerenciamento de prioridades do Project Calc**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cm-proj-calc-mgmt.png)

Observação: o Default Calc Prioritization não é compatível com a instância de multilocação. O recurso atual suporta apenas a Priorização de Calc padrão. O aprimoramento futuro oferecerá suporte a alterações nas filas de cálculo de desenvolvimento e preparação.

:

## Navegação

Navegue até a guia **Build** na faixa de opções TBM Studio e selecione **Calc Prioritization**![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/calc-prioritization.png)

O pop-up Priorização de cálculo é exibido com três guias - Prioridade do projeto, Fila de desenvolvimento e Fila de preparação

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cp-dragdrop.png)

## Prioridade do projeto

Aplica-se somente a: 12.10.9 e 12.10.10. Essa guia mostra a lista de projetos com sua prioridade.

Essa guia mostra a lista de projetos com sua prioridade.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cp-phase2.png)

Insira um **motivo** para documentar a finalidade da alteração e clique em **Update Project Priority Queue (Atualizar fila de prioridade do projeto** ).

## Fila de desenvolvimento

Essa guia mostra a lista de tarefas que estão atualmente na fila de desenvolvimento. Há duas seções Active Calc e Queued Calc, que mostram as tarefas que estão em andamento e em fila, respectivamente.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cp-dev-queue.png)

A fila ativa é estática, enquanto a lista de filas pode ser modificada com base na preferência do usuário.

## Fila de preparação

Essa guia mostra a lista de projetos/filiais que estão atualmente na fila de preparação. Há duas seções Active Calc e Queued Calc, que mostram os projetos e/ou ramificações que estão em andamento e em fila, respectivamente.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cp-staging-q.png)

## Mudança de prioridades

Você pode alterar as prioridades de todos os itens em fila e da prioridade do projeto arrastando e soltando uma linha do projeto ou inserindo um valor manual para alterar a prioridade. O número de prioridade se ajustará automaticamente para criar a priorização desejada. O sistema atribuirá um número adicionando 1 ao projeto diretamente abaixo

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/calc-prior-dragdrop.png)

Você também pode pesquisar para filtrar por domínio, projeto e filial. As filas Dev e Staging podem ser atualizadas manualmente para verificar se há atualizações.

nota

Observação: As prioridades não podem ser alteradas para as tarefas em andamento.
