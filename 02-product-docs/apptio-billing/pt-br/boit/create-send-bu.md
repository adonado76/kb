---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Criar e enviar contas da unidade de negócios"
breadcrumb: []
source_path: "boit/create-send-bu.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Criar e enviar contas da unidade de negócios

Você pode personalizar as mensagens de texto que são exibidas no cabeçalho e no rodapé de uma fatura. As mensagens são armazenadas na tabela Email Invoice Messages (Mensagens de fatura por e-mail). As descrições das três mensagens são as seguintes:

- **Mensagem global** - Uma mensagem que será exibida na parte superior de cada fatura. Isso é um acréscimo à mensagem de cabeçalho padrão.
- **Mensagem de cabeçalho padrão** - A mensagem padrão que será exibida na parte superior de cada fatura se uma mensagem de cabeçalho padrão não tiver sido definida na tabela Lista de faturas do destinatário ou por uma mensagem inserida em Produção no momento em que a fatura for enviada.
- **Mensagem de rodapé padrão** - A mensagem padrão que será exibida na parte inferior de cada fatura se uma mensagem de rodapé não tiver sido definida na tabela Lista de faturas do destinatário.

Para editar as mensagens:

1. No Project Explorer do site TBM Studio , abra a tabela **Email Invoice Messages (Mensagens de fatura de e-mail** ). A tabela está localizada abaixo do grupo.
2. Na guia **Home**, clique em **Exportar** e selecione **Excel** para exportar a tabela para o Excel.
3. Modifique o texto no Excel e salve o arquivo.
4. Faça upload do arquivo para a tabela Email Invoice Messages (Mensagens de fatura por e-mail).
   - Defina a data como a data de início do projeto.
   - Clique na etapa **Upload**.
   - Clique em **Initial Upload** e selecione **Overwrite**.
   - Localize o arquivo Excel que deseja carregar.

**Designar os destinatários e suas informações sobre a conta**

Os usuários que receberão uma fatura são determinados pela lista de usuários na tabela Lista de faturas de destinatários. Mantenha a lista em uma planilha do Excel e carregue o arquivo no. Consulte [Carregar um arquivo de dados](../studio/data_studio/upload-data-file.htm "(Abre em uma nova guia ou janela)").

Os campos da tabela incluem:

- **Nome da conta** - Cada linha deve ter um valor exclusivo.
- **Coluna de filtro** - Você pode limitar as entradas em uma fatura aplicando um filtro. Digite o nome de uma coluna da tabela de dados mestre de alocação de unidades de negócios. As colunas usadas com mais frequência são Corpo Governante, Unidade de Negócios e Departamento. A coluna pode ser uma coluna personalizada na tabela de dados mestre.
- **Valor do filtro** - Insira um valor da coluna de filtro. Por exemplo, você pode inserir o nome de uma unidade de negócios.
- **Destinatário** - Digite o nome do destinatário seguido do endereço de e-mail. Você pode inserir um e-mail individual ou um alias. Os nomes são opcionais. É necessário apenas um endereço de e-mail.   
   **Exemplo** : Pat Smith <psmith@abc \_company.com >.
- **Responder a** - O nome e o endereço de e-mail da pessoa com quem os destinatários devem entrar em contato para obter mais informações sobre a fatura.   
   **Exemplo** : Pat Smith <psmith@abc \_company.com >.   
   **OBSERVAÇÃO** : Um alias de e-mail pode ser usado no campo, mas você não pode inserir uma lista de endereços de e-mail.
- **Mensagem de cabeçalho padrão** - A primeira mensagem exibida na parte superior da fatura. Se o campo for deixado em branco, será usada a Mensagem global.
- **Mensagem de rodapé** - A mensagem exibida na parte inferior da fatura. Se o campo for deixado em branco, será usada a Mensagem de rodapé padrão.

**Bloquear para Staging e promover para Production**

As faturas podem ser enviadas somente do ambiente de produção. Você deve bloquear o projeto no ambiente de preparação e, em seguida, promover o projeto para o ambiente de produção. Veja [Bloquear e promover um projeto](https://community.apptio.com/docs/doc-5117 "(Abre em uma nova guia ou janela)").

**Designar contas a serem enviadas**

1. Mude para o ambiente de produção.
2. Na página inicial, clique em **Manage and Send Invoices (Gerenciar e enviar faturas** ).
3. Clique na fatura que deseja enviar ou clique em **Send all Bills (Enviar todas as faturas** ) na página principal.   
    Ele só enviará contas que ainda não tenham sido enviadas.

**Digite uma mensagem personalizada para uma fatura específica**

Você pode inserir uma mensagem personalizada para uma fatura específica.

1. Abra a fatura que você deseja editar.
2. Navegue até a seção de comentários à esquerda da tela.
3. Digite seu comentário na caixa.
4. Se você quiser enviar a fatura com a mensagem personalizada agora, clique em **Enviar**.
5. Se desejar enviar a fatura em um momento posterior, clique em **Salvar**.   
    Isso salvará a mensagem personalizada e a exibirá na próxima vez que você abrir a fatura.
6. Reabrir uma fatura com uma mensagem salva permitirá que você edite a mensagem novamente ou envie a fatura

**Visualizar uma fatura**

Você pode visualizar uma fatura antes de enviá-la de duas maneiras.

- **Navegue até o relatório Fatura** :
  - Esse relatório está localizado na coleção de relatórios de **Taxas de Serviço**. Para exibir o relatório, clique em **Fatura**.
  - Use o **fatiador global de hierarquia de unidades de negócios** para criar variantes da fatura para visualização.   
     Observe que essa tela não terá impacto sobre a fatura real. As alterações que você fizer aqui são apenas para fins de visualização.
- **Clique na fatura e localize o painel de visualização no lado direito da tela** - Essa tela mostrará o que será realmente enviado. A coluna e o valor do filtro definidos no conjunto de dados serão aplicados aqui e não podem ser alterados na produção. Essa tela é muito semelhante à que o destinatário verá ao abrir o e-mail.

**Enviar fatura(s) da unidade de negócios**

Você pode enviar contas individuais ou enviar todas as contas. Se você clicar em **Send All Bills (Enviar todas as faturas** ), somente as faturas que não foram enviadas anteriormente serão enviadas.

Para enviar uma única fatura:

1. Clique na fatura que você deseja enviar.
2. Navegue até a caixa de comentários no lado esquerdo da tela.
3. Digite um comentário ou deixe a mensagem padrão.
4. Clique em **Enviar**.
5. Observe a barra de status acima da caixa de comentários. Essa barra de status o informará quando a fatura tiver sido enviada com sucesso.
6. Se você deseja reenviar uma fatura que já foi enviada anteriormente:
   1. Abrir a fatura enviada anteriormente
   2. Clique em **Reset** na caixa de comentários à esquerda da tela.
   3. Clique em **Enviar**.
   4. A redefinição da fatura também permitirá que você envie a fatura usando a funcionalidade **Enviar todas as faturas**

Para enviar todas as faturas, clique em **Enviar todas as faturas** no Relatório de distribuição.

**Acompanhar o status das contas**

Uma fatura pode ter um dos seguintes status:

- **Not Sent (Não enviado** ) - A fatura não foi enviada e requer ação por parte do remetente.
- **Enviado** - A fatura foi enviada com êxito, mas não foi lida pelo destinatário.
- **Read (Ler** ) - A fatura foi enviada e lida pelo destinatário.
- **Erro** - Ocorreu um erro ao enviar a mensagem. Você pode visualizar a caixa de diálogo de erros para investigar.

**Remover o link do e-mail da fatura**

A partir de TBM Studio 2.9.1, você pode remover do e-mail da fatura o link que envia o usuário para a fatura que gerou o e-mail. Você pode remover esse link, se necessário.

Para remover o link de e-mail:

1. No Project Explorer do site TBM Studio , vá para **Tables (Tabelas) >** e clique em **Recipient Invoice List (Lista de faturas do destinatário)**
2. Na caixa de diálogo **Append to Recipient Invoice List (Anexar à lista de faturas do destinatário** ), defina o valor **Link Visible (Link visível** ) como "no" (não).   
    Qualquer outro valor nessa coluna impede a capacidade de ocultar o link. Para remover o link, o valor deve ser "não".
3. Todos os e-mails futuros não exibirão mais o link.
