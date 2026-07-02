---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Etapa 7: Revise o aplicativo atualizado na ramificação de upgrade"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step7.html"
images:
  - "resources/images/ct_images/upgrade-from-v3-12.png"
  - "resources/images/ct_images/upgrade-from-v3-13.png"
  - "resources/images/ct_images/upgrade-from-v3-14.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Etapa 7: Revise o aplicativo atualizado na ramificação de upgrade

1. Na guia Projeto, clique em **Componentes**.

   A caixa de diálogo **Configuração de componentes** é aberta.
2. Verifique se as compilações foram concluídas.

   Você verá uma lista dos check-ins individuais.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-12.png)
3. Na barra de navegação, selecione **Transparência de custos** no menu Aplicativo.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-13.png)
4. Selecione o ramo de upgrade (por exemplo, **Upgrade da versão 104** ).
5. A nova página inicial será exibida.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-14.png)

   Observação: se a TBM Review aparecer na barra de menus e a nova página de destino não for exibida, será necessário alterar a página de destino de TBM Review para Service Costing usando o conjunto de dados "params", como segue:
   1. Retornar para **TBM Studio**.
   2. Na guia **Project (Projeto** ), abra a seção **Tables (Tabelas** ) no painel esquerdo.
   3. Digite "params" na caixa de pesquisa.
   4. Clique em **Params**.
   5. Confira o documento.
   6. Clique na etapa **Upload** transform.
   7. Clique em **Params.csv** e selecione **Download**.
   8. Abra o Excel.
   9. Altere o valor da coluna "InitialReport" para ".View:tab:Service Costing"
   10. Clique em **Salvar**.
   11. Clique em **Params.csv e selecione** **Overwrite (Sobrescrever** ).
   12. Selecione o arquivo salvo e carregue-o no Apptio.
   13. Clique na etapa de transformação **da tabela**.
   14. Verifique se o valor **InitialReport** o valor foi alterado para ".View:tab:Service Costing"
   15. Clique em **Salvar**.
   16. Verifique a mudança.

## Informações relacionadas

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
