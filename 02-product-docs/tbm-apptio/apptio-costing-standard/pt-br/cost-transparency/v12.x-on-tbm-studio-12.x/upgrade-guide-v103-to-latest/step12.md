---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Etapa 12: Atualizar o ambiente de produção"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step12.html"
images:
  - "resources/images/ct_images/upgrade-from-v3-26.png"
  - "resources/images/ct_images/upgrade-from-v3-27.png"
  - "resources/images/ct_images/upgrade-from-v3-28.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Etapa 12: Atualizar o ambiente de produção

Depois de concluir a verificação dos relatórios, envie o aplicativo atualizado para a produção.

1. Ir para **TBM Studio**.
2. Selecione o ambiente **de preparação**.
3. Na faixa de opções **Projeto**, clique em **Bloquear**.

   Uma breve mensagem pop-up indicará que o ambiente está bloqueado. O ambiente agora está pronto para ser promovido à produção.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-26.png)
4. Na faixa de opções **Projetos**, clique em **Opções de promoção** e siga um destes procedimentos:
   - Clique em **Promote Now (Promover agora** ). A atualização é enviada para a produção imediatamente.
   - Clique em **Promote Later (Promover mais tarde** ) para programar quando o upgrade será publicado na produção.

     ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-27.png)
5. Na faixa de opções **Projeto**, clique em **Fila de cálculo** para verificar a compilação de produção.
6. Compare os números de compilação dos ambientes de desenvolvimento, preparação e produção.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-28.png)

## Informações relacionadas

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
