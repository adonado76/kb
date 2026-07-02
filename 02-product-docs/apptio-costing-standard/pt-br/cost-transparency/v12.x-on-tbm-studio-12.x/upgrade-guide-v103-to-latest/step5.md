---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Etapa 5: Faça upgrade de componentes individuais e verifique as alterações"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step5.html"
images:
  - "resources/images/ct_images/upgrade-from-v3-10.png"
  - "resources/images/ct_images/upgrade-from-v3-7.png"
  - "resources/images/ct_images/upgrade-from-v3-8.png"
  - "resources/images/ct_images/upgrade-from-v3-9.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Etapa 5: Faça upgrade de componentes individuais e verifique as alterações

1. Na caixa de diálogo Configuração de componentes, clique duas vezes em um componente específico, por exemplo, **CTF - Fonte de custos**.

   Uma página de componente é aberta.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-7.png)
2. Role para baixo, abaixo da lista de relatórios incluídos, até a seção **Upgrade disponível**.
   - Uma caixa azul indica que não foram feitas personalizações em nenhum item do componente.
   - Uma caixa amarela indica que foram encontradas personalizações nos dados, métricas calculadas ou relatórios.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-8.png)

   Ocasionalmente, a caixa amarela permanece depois que você reverte todas as personalizações. Para continuar, clique no botão **Upgrade** na caixa amarela.
3. Se houver personalizações, clique em **View Conflicts (Exibir conflitos** ) ou role até a parte inferior da página.
4. Reverter todos os relatórios personalizados e métricas calculadas.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-9.png)
5. Para conjuntos de dados personalizados, reverta os conjuntos de dados personalizados para os seguintes componentes relacionados à nuvem:
   - CTF - Provedor de serviços em nuvem
   - CTF- Amazon Web Services
   - CTF- Azure

   Faça uma captura de tela de seus mapeamentos atuais para ajudar no remapeamento dos campos de marcação.

   Observação: **NÃO** reverta os conjuntos de dados de nenhum outro componente. Se você reverter as alterações do conjunto de dados, será necessário reanexar e mapear novamente os arquivos de origem para os conjuntos de dados mestre.
6. Clique em **Upgrade**.

   O aplicativo leva alguns minutos para processar a atualização. Depois que a página do componente for atualizada e retornar à página de configuração do componente, você poderá continuar. Confirme se a seta de atualização não é mais exibida.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-10.png)
7. Se você reverteu as alterações do conjunto de dados para os relatórios do Cloud, remapeie os arquivos de origem para os dados mestre, como segue:
   1. No Project Explorer, clique em **Tables (Tabelas** ).
   2. Clique em **Dados mestre**.
   3. Anexar.
   4. Mapeie as colunas de origem para as colunas de dados mestre apropriadas.

      Use a captura de tela feita na etapa anterior para verificar os mapeamentos.
8. Após a conclusão do upgrade, você deve alterar manualmente os conjuntos de dados que não foram revertidos. Para v104, consulte a lista cumulativa de [atualizações de dados do modelo v103 a v104](../../user-guide/template103to104dataupdates-9027.html) para identificar quais alterações são necessárias.
9. Faça o check-in de todas as alterações relacionadas ao upgrade de componente único, uma de cada vez, da seguinte forma:

   Observação: se você não seguir essas etapas para fazer o check-in dos componentes um de cada vez, poderá ocorrer um erro que o fará perder o trabalho e reiniciar a atualização desde o início.

   1. Selecione **Projetos** e clique em **Check-in**.

      A caixa de diálogo Check-in é aberta.
   2. Selecione **Todos os itens** no painel esquerdo (padrão).
   3. Digite uma descrição dos itens no painel **Mensagem**.

      Observação: insira uma descrição útil, como "Fonte de custos: reverter alterações no conjunto de dados, componente atualizado" Isso é fundamental para as atividades de mesclagem de ramificações mais adiante neste processo de atualização. Revise [a Etapa 9: mesclar alterações no projeto principal (Tronco)](step9.html) para entender por que isso é importante.
   4. Clique em **Check In**.
   5. Continue com a Etapa 6.

## Informações relacionadas

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
