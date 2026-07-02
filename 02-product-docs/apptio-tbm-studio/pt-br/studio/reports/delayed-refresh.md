---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Atualização diferida"
breadcrumb: []
source_path: "studio/reports/delayed-refresh.html"
images:
  - "resources/images/studio_images/del-ref-popup_885x911.png"
  - "resources/images/studio_images/delayed-refresh-new_875x416.png"
  - "resources/images/studio_images/df-checkin_855x279.png"
  - "resources/images/studio_images/df-chkout_842x344.png"
  - "resources/images/studio_images/df-report_844x395.png"
  - "resources/images/studio_images/df-tbm_883x327.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Atualização diferida

O recurso de atualização atrasada fornece um tempo diferido para que os usuários selecionem filtros, seletores ou segmentações e vejam os resultados atualizados com base no relatório. Isso é útil para relatórios grandes e complexos em que são feitas várias seleções interativas.

Em 12.10.8, esse recurso estava disponível como parte de Report Studio > Barra de navegação, com as opções Live, 2 segundos, 5 segundos e Atualização manual.

Em 12.10.9, o recurso foi aprimorado para remover as opções Live, 2 segundos e 5 segundos. As novas opções são:

- **Atraso de atualização: 3s** : O sistema aguarda 3 segundos antes de atualizar a tela.
- **Atualização manual** : Esse modo exige que o usuário selecione Atualizar para atualizar o relatório.

Esse recurso está disponível em três exibições:

## Transparência de custos

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/delayed-refresh-new_875x416.png)

Observação: As alterações feitas no CT Report Studio não são persistentes para o usuário. Se o usuário estiver desconectado, as configurações padrão de 3 segundos serão novamente aplicáveis.

## TBM Studio

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-tbm_883x327.png)

O recurso Atualização adiada está disponível para todos os usuários, com o padrão de **Atraso de atualização: 3s** para todos os projetos, mas o administrador pode alterar a configuração para Atualização manual. Para relatórios simples, é possível definir 3 segundos, enquanto que para um relatório grande com vários slicers, pickers e pivôs, o usuário pode mudar para a opção **Atualização manual**. Para alterar as configurações de atualização, navegue até a guia **Projeto** > **Configurações do projeto** e altere o valor no campo **Atualização diferida** no pop-up Editar configurações do projeto.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/del-ref-popup_885x911.png)

Essa configuração será aplicada a todos os relatórios. Mas você pode alterar as configurações de atualização de relatórios específicos seguindo estas etapas:

1. Na guia **Home** de um relatório, selecione **Checkout**

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-chkout_842x344.png)
2. A guia **Relatório** está ativada. Aplique os filtros apropriados e modifique as configurações de atualização, conforme aplicável.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-report_844x395.png)
3. Na **página inicial**, selecione **Salvar** e, em seguida, selecione a opção **Checkin**.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-checkin_855x279.png)
