---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Imprimir e exportar relatórios"
breadcrumb: []
source_path: "studio/reports/printexportreports.html"
images:
  - "resources/images/studio_images/export-pdf-options.png"
  - "resources/images/studio_images/print-1.png"
  - "resources/images/studio_images/print-2.png"
  - "resources/images/studio_images/send-email_955x567.png"
  - "resources/images/studio_images/ugly-url.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Imprimir e exportar relatórios

**Aplica-se a** : Apptio TBM Studio R12.5 e posterior. TBM Studio depende da exportação de relatórios para o formato PDF para impressão e compartilhamento de relatórios fora da suíte TBM. O administrador do TBMA ou do TBM Studio pode personalizar as opções de layout de PDF por relatório para todos os usuários do Apptio ao imprimir ou enviar relatórios por e-mail.

Todos os usuários dos aplicativos de cálculo de custos do Apptio (como o Costing Standard) podem exportar um relatório para o formato PDF ou enviar o relatório por e-mail no formato PDF. Ao fazer isso, o PDF exportado usará as opções de layout definidas por meio das instruções abaixo.

**VEJA TAMBÉM** : [Práticas recomendadas: Impressão em PDF](https://community.apptio.com/docs/DOC-9644 "(Abre em uma nova guia ou janela)")

## Criar layouts de relatórios personalizados para exportação em PDF

Os TBMAs podem definir opções de layout por relatório em TBM Studio.

1. Verifique o relatório que você deseja ([Como?](../admin/bp-check-out.html "(Abre em uma nova guia ou janela)") ).
2. Na guia Página **inicial**, clique em **Exibir** e selecione **Layout de impressão**.TBM Studio alterna para o modo Layout de impressão.
3. Clique na guia **Layout de impressão**.

   ![](../../resources/images/studio_images/studioimages/studio_export%20to%20pdf_exit%20print%20layout%20mode.png)

   Dica: Para sair desse modo a qualquer momento, na guia **Layout de impressão**, clique em **Exit Print Layout Mode (Sair do modo de layout de impressão** )
4. Selecione um componente específico no relatório e, em seguida, faça as alterações desejadas nos componentes. As opções de componentes incluem:

   | Opção | Descrição |
   | --- | --- |
   | **Pino/Unpin** | Você pode fixar um único componente no final de um relatório. Um uso típico desse recurso é mover as segmentações para o final de um relatório para capturar a filtragem aplicada ao relatório. Além disso, você pode fixar todos os componentes de um tipo selecionado no final de um relatório. Por exemplo, você pode fixar todos os slicers no final de um relatório. |
   | **Exibir/Ocultar** | É possível ocultar um único componente em um relatório. Para ocultar vários componentes, clique em **Mostrar/Ocultar componentes do relatório** e, em seguida, desmarque as caixas dos componentes que deseja ocultar**.DICA** : Para filtrar uma longa lista de componentes para um conjunto específico de componentes, digite um texto no campo **Filtro**. |
5. Faça as alterações desejadas no layout de impressão. As opções de configuração de página incluem:

   | Opção | Descrição |
   | --- | --- |
   | **Tamanho da página** | Selecione um tamanho de papel no menu suspenso. |
   | **Fluxo** | O fluxo controla o posicionamento dos componentes na página do relatório.  **Manual** - Você coloca os componentes. Uma vez colocados, os objetos não se moverão.  **Vertical** - Os componentes são organizados automaticamente em uma única coluna vertical.  **Horizontal** - Os componentes são organizados automaticamente em linhas, com o número máximo de componentes colocados em cada linha. |
   | **Margens** | Selecione as configurações de margem desejadas. |
   | **Cabeçalho** | Você pode adicionar um cabeçalho a um relatório. O cabeçalho pode ser exibido em todas as páginas ou somente na primeira página. Você pode alterar o tamanho do cabeçalho arrastando as bordas da caixa de cabeçalho. Você pode formatar o texto no cabeçalho usando tags de formato HTML. Além disso, você pode usar texto dinâmico no cabeçalho. Por exemplo, o texto dinâmico a seguir adicionará o período atual: <%=CurrentDate( )%> |
   | **Rodapé** | Você pode personalizar totalmente o rodapé. Se você quiser um rodapé em branco, limpe o texto no campo Footer Left (Rodapé esquerdo), selecione a opção Specify footer text (Especificar texto do rodapé) e deixe o campo em branco. Ao contrário dos cabeçalhos, você não pode usar texto dinâmico no rodapé. |
   | **Retrato** | Clique nessa opção para obter a orientação vertical da página. |
   | **Paisagem** | Clique nessa opção para obter a orientação horizontal da página. |
   | **Escala** | Selecione o nível de zoom que deseja aplicar. |
6. Clique em **Save (Salvar** ) na guia **Print Layout (Layout** de impressão) para salvar as configurações de layout de impressão e, em seguida, clique em **Exit Print Layout Mode (Sair do modo de layout de impressão** ).
7. Confira o relatório.

Dica:

- Se você salvou as alterações na sessão atual do Layout de impressão, mas decidiu cancelar as alterações salvas, clique em **Update Layout from Report (Atualizar layout do relatório** ). Você também pode reverter para o último estado salvo na sessão atual do Layout de Impressão: clique em **Reverter Layout**.
- Nem todas as alterações de layout de página que você fizer ficarão visíveis no Modo de layout de impressão (cabeçalhos e rodapés não são visíveis, por exemplo). Você pode visualizar suas alterações clicando em **Exportar para PDF** na guia **Layout de impressão**. O PDF será aberto em uma nova guia.
- Para obter uma visualização de alta fidelidade do layout personalizado de um relatório em formato PDF, conclua a tarefa "Exportar um relatório para um arquivo PDF" descrita abaixo e selecione a opção **Baixar PDF diretamente**.

Observação: Durante a exportação do Excel, a ordem da coluna é mantida conforme configurada no componente de relatório. As colunas restantes que não fazem parte do relatório são anexadas.

## Configurar uma tabela para imprimir todas as linhas em várias páginas

1. Fazer check-out de um relatório
2. Na guia Página **inicial**, selecione **Exibir** e, em seguida, **Layout de impressão**.
3. Mova a tabela para sua própria página.
4. Selecione a tabela e, na guia **Layout de impressão**, selecione **Redimensionar componente para página inteira**.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/print-1.png)
5. Selecione a tabela e, na subguia **Tabela**, selecione **Imprimir todas as páginas**.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/print-2.png)
6. Quando o relatório for impresso em PDF, a tabela será impressa em várias páginas.

## Exportar um relatório para um arquivo PDF

As TBMAs podem gerar e compartilhar uma renderização em PDF de um relatório.

Para exportar um relatório em TBM Studio:

1. No Project Explorer, exiba o relatório que você deseja.
2. Na guia Página **inicial**, clique em **Exportar** e, em seguida, clique em **PDF**. A caixa de diálogo Exportar para PDF é exibida.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/export-pdf-options.png)
3. Clique em **Download to PDF directly** e, em seguida, clique em OK.The. A renderização em PDF do relatório é criada. Dependendo da configuração do seu navegador, ele poderá abrir em uma nova janela ou guia, ou aparecer na barra de downloads do navegador, pronto para ser aberto ou salvo.

## Envie um relatório por e-mail em formato PDF para outro usuário do site Apptio

Você pode gerar a renderização em PDF de um relatório e enviá-lo por e-mail a um destinatário. Você pode enviar por e-mail um link para o PDF ou enviar o PDF como um anexo de e-mail.

Para enviar um relatório por e-mail em TBM Studio:

1. No Project Explorer, exiba o relatório que você deseja.
2. Na guia Página **inicial**, clique em **Exportar** e, em seguida, clique em **PDF**. A caixa de diálogo Exportar para PDF é exibida.
3. Execute uma das seguintes ações:
   - Clique em **Incluir um link para o PDF em um e-mail**.
   - Clique em **Anexar o PDF a um e-mail**.
4. O ID de e-mail do usuário conectado é preenchido por padrão. Se desejar alterar, digite o endereço de e-mail apropriado.
5. Clique em **OK**.

   O exemplo de e-mail que o destinatário recebe é -

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ugly-url.png)

   Observação: Se você abrir o link do relatório no e-mail, verá o relatório no mesmo contexto, ou seja, todos os filtros, divisores, selecionadores e intervalos de datas aplicados persistirão e o relatório aparecerá exatamente como foi compartilhado pelo remetente.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/send-email_955x567.png)

## Exportar um relatório para um arquivo PDF em um aplicativo de cálculo de custos da TBM

Ao concluir essa tarefa, o PDF exportado usará as opções de layout definidas na tarefa "Criar e gerenciar layouts de relatórios personalizados para exportação de PDF", acima.

1. Inicie o aplicativo (por exemplo, Costing Standard) e visualize o relatório.
2. Na extremidade direita da barra de título da coleção de relatórios, clique no botão **Exportar** e, em seguida, clique em **PDF**.![](../../resources/images/studio_images/studioimages/studio_print%20export%20reports_button.png)A caixa de diálogo Exportar para PDF é exibida.
3. Execute uma das seguintes ações:
   - Clique em **Download PDF directly (Baixar PDF diretamente** ) e, em seguida, clique em **OK**. A renderização em PDF do relatório é criada. Dependendo da configuração do seu navegador, ele poderá abrir em uma nova janela ou guia, ou aparecer na barra de downloads do navegador, pronto para ser aberto ou salvo.
   - Clique em **Incluir um link para o PDF em um e-mail**, digite o endereço de e-mail do destinatário e clique em **OK**.
   - Clique em **Anexar o PDF a um e-mail**, digite o endereço de e-mail do destinatário e clique em **OK** noreply@apptio.com.

Observação: Para determinados recursos do site Apptio, como Exportar para PDF, os usuários devem permitir pop-ups no navegador a partir do site Apptio URL ([Como?](https://community.apptio.com/docs/DOC-9655 "(Abre em uma nova guia ou janela)") ).
