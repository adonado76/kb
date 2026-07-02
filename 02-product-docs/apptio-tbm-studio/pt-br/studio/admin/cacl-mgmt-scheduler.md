---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Agendador de gerenciamento de cálculo"
breadcrumb: []
source_path: "studio/admin/cacl-mgmt-scheduler.html"
images:
  - "resources/images/icons/pencil-icon.jpg"
  - "resources/images/studio_images/build-calc-schedule.png"
  - "resources/images/studio_images/calc-config-delete-confirmation.png"
  - "resources/images/studio_images/calc-config-scheduler.png"
  - "resources/images/studio_images/calc-scheduler.png"
  - "resources/images/studio_images/create-schedule-popup.png"
  - "resources/images/studio_images/project-config-calc-scheduler.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Agendador de gerenciamento de cálculo

Aplica-se a: 2.16 e posterior. Esse recurso automatizará os cálculos de preparação em nível de projeto e de filial.

Para ativar o Calc Management Schedule, navegue até **Projeto** > **Ativar recursos** e selecione **Mostrar Calc Scheduler**. Será exibida uma janela pop-up para confirmar que o recurso está ativado.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/calc-scheduler.png)

## Configuração do projeto

Navegue até a guia **Build** na faixa de opções do site TBM Studio e selecione **Calc Schedule**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/build-calc-schedule.png)

Para criar uma programação, faça o seguinte

1. Clique no botão **Create Schedule**.

   ![Criar cronograma](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/create-schedule-popup.png)
2. Digite **Schedule Name**.
3. No campo **Weekly (Semanal** ), selecione os dias desejados para realizar os cálculos.
4. Selecione **Re enable time** para reiniciar os cálculos.
5. Selecione **Disable time** para interromper os cálculos.
6. Selecione **Fuso horário**.
7. Clique no botão **Enviar**.

Os cronogramas criados podem ser aplicados a vários projetos.

![Configuração do projeto](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/project-config-calc-scheduler.png)

Ele contém as seguintes informações:

| Campo | Descrição |
| --- | --- |
| Nome do Projeto | Nome do projeto |
| Ramificação | Nome da filial |
| Nome de agendamento | Nome do cronograma. Selecione um cronograma para atribuir ao projeto no menu suspenso da lista de cronogramas. |
| Ocorrência | Exibir os dias em que os cálculos ocorrem |
| Desativar o Calc | Exibir o tempo de desativação para interromper o cálculo. |
| Reativar o Calc | Exiba o tempo de reativação para reiniciar o cálculo. |

## Configuração de cálculo

![Configuração de cálculo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/calc-config-scheduler.png)

Para editar a programação existente, selecione o ícone de edição![Lápis](../../../../../03-media/apptio-tbm-studio/resources/images/icons/pencil-icon.jpg)

- Depois que um cálculo for iniciado, a edição do **tempo de reativação** ou do **tempo de desativação** não encerrará os cálculos em execução no momento.
- Durante o cálculo, as alterações no **tempo de reativação** ou no **tempo de desativação** só terão efeito em cálculos futuros.

Para excluir a programação existente, selecione o ícone de exclusão. Clique no botão **Confirm (Confirmar** ) na janela pop-up de aviso.

![Excluir confirmação](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/calc-config-delete-confirmation.png)

Observação: para alterar o estado de ativação/desativação do Re de um projeto, navegue até **Build** > **[Calc Management](cacl-mgmt-settings.html "Aplica-se a: 12.11.0 e posterior. Os clientes agora podem desativar/ativar os cálculos de preparação em um nível de projeto, para que possam controlar quais projetos são calculados e, por sua vez, reduzir o número total de cálculos.")** e edite manualmente Disable/Enable Staging Calc conforme necessário.
