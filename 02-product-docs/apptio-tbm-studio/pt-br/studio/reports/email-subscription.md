---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Assinatura de e-mail"
breadcrumb: []
source_path: "studio/reports/email-subscription.html"
images:
  - "resources/images/studio_images/ESsearch.png"
  - "resources/images/studio_images/bu-1.png"
  - "resources/images/studio_images/bu-2.png"
  - "resources/images/studio_images/bu-3.png"
  - "resources/images/studio_images/bu_toggle.png"
  - "resources/images/studio_images/ds-1.jpg"
  - "resources/images/studio_images/ds-2.jpg"
  - "resources/images/studio_images/ds-3.jpg"
  - "resources/images/studio_images/ds-5.jpg"
  - "resources/images/studio_images/ds2.jpg"
  - "resources/images/studio_images/ds3.jpg"
  - "resources/images/studio_images/ds4.jpg"
  - "resources/images/studio_images/ds5.jpg"
  - "resources/images/studio_images/ds6.jpg"
  - "resources/images/studio_images/ds7.jpg"
  - "resources/images/studio_images/ds8.jpg"
  - "resources/images/studio_images/em-sub-1.jpg"
  - "resources/images/studio_images/email-full.jpg"
  - "resources/images/studio_images/endisES.png"
  - "resources/images/studio_images/es-1.jpg"
  - "resources/images/studio_images/filter-view.jpg"
  - "resources/images/studio_images/ms-1.jpg"
  - "resources/images/studio_images/ms-2.jpg"
  - "resources/images/studio_images/ms-3.jpg"
  - "resources/images/studio_images/pdf-10.jpg"
  - "resources/images/studio_images/pdf-11.jpg"
  - "resources/images/studio_images/pdf-2.jpg"
  - "resources/images/studio_images/pdf-3.jpg"
  - "resources/images/studio_images/pdf-4.jpg"
  - "resources/images/studio_images/pdf-5.jpg"
  - "resources/images/studio_images/pdf-6.jpg"
  - "resources/images/studio_images/pdf-8.jpg"
  - "resources/images/studio_images/pdf-9.jpg"
  - "resources/images/studio_images/pdf-name.jpg"
  - "resources/images/studio_images/pdf1.jpg"
  - "resources/images/studio_images/pf-7.jpg"
  - "resources/images/studio_images/r-notes/dup-sub1.jpg"
  - "resources/images/studio_images/send-now-1.jpg"
  - "resources/images/studio_images/send-now.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Assinatura de e-mail

Esse recurso permite que as TBMAs se inscrevam para receber relatórios por e-mail regularmente. Eles também podem incluir outros usuários nessas assinaturas de relatórios, que serão notificados sobre os mesmos.

As assinaturas de e-mail também podem ser criadas por usuários com as seguintes permissões:

- EmailSubscriptionsCreate
- EmailSubscriptionsFilteredCreate

Nota:

- Por motivos de segurança, um e-mail pode ser enviado somente para os domínios autorizados no ambiente do cliente. Por exemplo, para o cliente acme, adicionar um e-mail para jdoe@acme.com funcionaria, mas adicionar um e-mail para jdoe@xyz.com não funcionaria.
- O RLS (Row Level Security) não é compatível com as assinaturas de e-mail

## Criar assinatura de e-mail

Navegue até qualquer relatório, expanda o ícone **Exportar** e selecione **Assinatura de e-mail**. Essa opção aparecerá somente para TBMAs.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/es-1.jpg)

A janela pop-up Assinaturas de e-mail é exibida.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/em-sub-1.jpg)

Insira valores nos campos a seguir. O \* indica um campo obrigatório.

| Campo | Descrição |
| --- | --- |
| Coleta de relatórios\* | O valor é preenchido automaticamente com o nome da coleção de relatórios que o relatório que você está visualizando.  Você pode alterar o valor selecionando-o na lista suspensa. |
| Nome do relatório\* | O valor é preenchido automaticamente com o nome do relatório que você está visualizando.  Você pode alterar o valor selecionando-o na lista suspensa. |
| Nome da assinatura\* | O nome é preenchido automaticamente como <Report Collection - Report Name>. Você pode editar esse nome ou inserir um novo nome. |
| Definir o corpo do e-mail | Em 12.11.9, selecione essa opção para alterar o assunto e a descrição do e-mail que é enviado ao assinante. Você pode inserir um máximo de 3.000 caracteres no corpo do e-mail. |
| Incluir PDF em anexo | Em 12.11.9, selecione essa opção para ver uma versão em PDF do relatório anexado ao e-mail. |
| Upload em massa XLS | Selecione essa opção se quiser enviar assinaturas de e-mail em massa com filtros. Se essa opção estiver ativada, o campo **Destinatários** será desativado. |
| Beneficiários\* | Digite o ID de e-mail das pessoas que devem receber as assinaturas de e-mail.  Em 12.11.8, é possível inserir manualmente um endereço de e-mail válido de um dos domínios compatíveis. |
| Período do relatório | O relatório será gerado com base nesse período de tempo. Selecione uma das opções:  **Período atual**  Se a opção **Ativar período de tempo padrão** não estiver selecionada, essa será a seleção padrão.  Se esse botão de opção estiver ativado, o usuário receberá um e-mail/pdf para o mês atual do calendário.  **Período anterior**  Se esse botão de opção estiver ativado, o usuário receberá um e-mail/pdf para o mês anterior, ou seja, para o mês anterior,  Se o Período padrão estiver ativado em "Configurações de tempo do projeto" --> Período anterior = Período padrão - 1  Se o Período padrão estiver desativado nas "Configurações de tempo do projeto" --> Período anterior = Período atual - 1  **Período padrão** (padrão) - Essa opção aparece somente se você selecionar a opção **Ativar período padrão** na guia **Projeto** >� [Configurações de tempo](../admin/configure-project-time.htm "(Abre em uma nova guia ou janela)").  Se esse botão de opção estiver ativado, o usuário receberá um e-mail/pdf para o mês padrão definido em "Project Time Settings" (Configurações de tempo do projeto) |
| Com filtros | Em 12.11.11, selecione essa opção para assinar relatórios filtrados por e-mail. |
| Frequência | Selecione uma das opções:  **Diariamente** (padrão)  **Semanal** - Selecione os dias  **Mensal** - Essa é uma seleção padrão. Selecione a data  **Horário de envio** \*: Selecione uma hora na lista suspensa. O padrão é o seu fuso horário atual.  **Dia** \*: Selecione o dia do mês na lista suspensa. |
| Fim da assinatura | Selecione uma das opções:  **Nunca** (padrão) ou  **Em uma data** - insira ou selecione uma data futura, no formato <dd-mm-aaaa>. |
| Gerenciar assinaturas | Selecione esse link para visualizar, editar e excluir as assinaturas de e-mail. |

Depois de inserir valores em todos os campos, selecione o botão **Subscribe (Assinar** ). Uma mensagem de confirmação " *Relatório inscrito com sucesso!* " aparece. A assinatura adicionada aqui estará disponível no pop-up Gerenciar assinaturas.

Observação: Não são permitidas assinaturas duplicadas. Uma assinatura é duplicada se tiver o mesmo nome ou se for para o mesmo relatório no mesmo horário.

## Gerenciar assinaturas

No pop-up Email Subscription (Assinatura de e-mail), selecione o link **Manage Subscriptions (Gerenciar assinaturas** ). A janela pop-up Gerenciar assinaturas é exibida. Você pode

- Visualizar, pesquisar ou editar qualquer uma das assinaturas.
- O ícone **Excluir assinatura(s)** aparece na versão 12.11.11 e posterior.
- Use a opção de paginação para navegar até as assinaturas.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ms-1.jpg)

Marque a caixa de seleção **Visualizar por usuário** para visualizar as assinaturas de todos os usuários que fazem parte das assinaturas.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ms-2.jpg)

Selecione o link **Usuário** para visualizar a lista de relatórios que ele assinou.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ms-3.jpg)

## Ativar/desativar assinaturas de e-mail

Aplica-se a: 12.11.14 e posterior. O recurso permite que os administradores façam o seguinte:

- **Acionamento imediato da assinatura** : Acione (habilite) assinaturas imediatamente após o processo de término mensal (MEP), garantindo atualizações e notificações em tempo hábil.
- **Pausa na assinatura** : Evite a sobrecarga de e-mails ao pausar (desativar) as assinaturas durante períodos específicos, permitindo um melhor gerenciamento de e-mails.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/endisES.png)

Ao selecionar a opção **Enable (Ativar** ), a linha de assinatura é desativada e a mensagem aparece como "*Sua assinatura de e-mail foi pausada. Você não receberá mais e-mails até que ele seja retomado*".

Ao selecionar a opção Disable (Desativar), é exibida uma mensagem como "*Sua assinatura de e-mail foi retomada. Agora você receberá e-mails conforme programado*".

Observação: Os e-mails não serão enviados para assinaturas pausadas.

## Enviar agora

**Aplica-se a** : 12.11.12 e posterior

O recurso Send Now (Enviar agora) permite que os administradores tenham uma maneira conveniente de verificar se a assinatura de e-mail está funcionando como pretendido, garantindo que os assinantes recebam o conteúdo esperado. Ao usar esse recurso, eles podem testar com confiança suas assinaturas de e-mail, facilitando o gerenciamento e a manutenção das assinaturas.

O recurso Send Now pode ser acessado em dois locais:

No pop-up **Manage Subscriptions (Gerenciar assinaturas** ), para cada assinatura de e-mail

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/send-now.jpg)

Na tela de edição de uma assinatura de e-mail individual.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/send-now-1.jpg)

Antes de usar **Send Now (Enviar agora)** na tela de edição, você deve primeiro salvar as alterações feitas nos detalhes da assinatura. Se forem feitas alterações, mas não forem salvas, o botão **Send Now** será desativado até que as alterações sejam salvas. Depois de salvo, você pode selecionar **Send Now (Enviar agora** ) para enviar um e-mail de teste para os assinantes, proporcionando uma maneira rápida e fácil de testar e verificar suas assinaturas de e-mail.

## Definir o corpo do e-mail

Selecione essa opção para alterar o assunto e a descrição do e-mail que é enviado ao assinante.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/email-full.jpg)

O assunto e o corpo do e-mail são personalizáveis. Em 12.11.12, há uma provisão para adicionar variáveis dinâmicas, como nome do relatório, período do relatório e filtros. Essas variáveis são então substituídas pelos valores reais nos e-mails.

Quando você receber a assinatura de e-mail, o

**O assunto do e-mail** aparece como *<Nome do relatório> MMM\_AAAA {filter1 condition = value}; {filter2 condition = value}; { ... }*

**O corpo do e-mail** aparece como

Seu relatório assinado da TBM Apptio está pronto: relatório <Report Name> para o período de <MMM\_YYYY>

- Nome e ID do projeto = XXXX

O **nome do arquivo PDF** ou anexo como *<Report\_Name>\_MMM\_YYYYY*.pdf

O nome do botão no e-mail será exibido como **Exibir relatório completo em Apptio**.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-name.jpg)

## Opção de PDF para relatórios simples

Os administradores podem criar relatórios simples em PDF para assinaturas de e-mail que tenham uma visualização de impressão limpa. Siga as telas abaixo para o processo.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-11.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-10.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-9.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-8.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pf-7.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-6.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-5.jpg)

Observe que:

Se houver uma visualização simples de um relatório, o anexo em PDF incluirá a visualização simples do relatório na assinatura do e-mail.

Se não houver uma visualização simples de um relatório, o anexo em PDF incluirá a "visualização do layout de impressão" do relatório na assinatura do e-mail.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-4.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-3.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-2.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf1.jpg)

## Assinaturas de e-mail com visualização filtrada

Esse recurso permite que os usuários compartilhem relatórios filtrados com destinatários específicos por meio de um sistema de assinatura. O destinatário recebe um hiperlink para acessar o relatório com seleções de segmentação pré-aplicadas, juntamente com a opção de receber um documento PDF anexado. O PDF pode ser configurado para incluir ou excluir a visualização simples vinculada, mantendo as configurações de filtro selecionadas.

Navegue até a janela pop-up Assinatura de e-mail.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/filter-view.jpg)

Deslize o botão de alternância **Filtered Views**. O menu suspenso Filtrar por\* é exibido.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds2.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds3.jpg)

Em 12.11.14, você pode selecionar um valor no menu suspenso ou fazer uma pesquisa parcial inserindo a palavra-chave.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ESsearch.png)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds4.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds-5.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds5.jpg)

Insira valores nos demais campos e selecione o botão **Subscribe (Assinar** ). Uma mensagem de confirmação " *Relatório inscrito com sucesso!* " aparece.

O destinatário receberá um e-mail com o link para o relatório com as exibições filtradas.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds6.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds7.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds8.jpg)

## Assinaturas de e-mail duplicadas

Esse recurso permite que os usuários dupliquem as assinaturas existentes e evitem criá-las do zero. Não é possível duplicar várias assinaturas de uma só vez.

Selecione o link **Manage Subscriptions (Gerenciar assinaturas** ) na janela pop-up Email Subscription (Assinatura de e-mail).

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds-1.jpg)

Selecione qualquer assinatura - o ícone **Duplicar assinatura** aparece no canto superior direito. Esse ícone aparece somente ao selecionar uma única assinatura.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds-2.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/dup-sub1.jpg)

Ao selecionar o ícone Duplicate Subscription (Duplicar assinatura), uma nova janela pop-up aparecerá com todos os campos pré-preenchidos para corresponder à assinatura original.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds-3.jpg)

Faça as alterações apropriadas e, em seguida, selecione o botão **Subscribe (Assinar** ).

## Carregamento de tabela

O recurso de upload de tabelas foi projetado para a distribuição exclusiva de relatórios por e-mail para milhares de destinatários. Esse recurso permite que uma única assinatura de e-mail de relatório inclua várias exibições de relatório exclusivas e filtradas para cada destinatário (ou um grupo de destinatários).

No pop-up Email Subscription (Assinatura de e-mail), deslize o botão de alternância **Bulk Upload XLS**.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bu_toggle.png)

A opção para carregar a tabela é exibida, e os campos **Recipients (Destinatários** ) e **With Filters (Com filtros** ) desaparecem.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bu-2.png)

Você pode fazer uma das seguintes opções:

- Arraste e solte ou anexe o arquivo usando o link **Procurar computador**.
- Clique no link **Blank Template (Modelo em branco** ) para fazer o download do modelo, preencha-o e, em seguida, faça o upload usando o link **Browse Computer (Procurar computador** ). O download da tabela de modelos será feito com base nas colunas filtradas disponíveis.

Se o tipo de arquivo não for válido, será exibida uma mensagem de erro apropriada. O botão **Assinar** será desativado até que o upload do arquivo seja bem-sucedido.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bu-1.png)

Feche a mensagem e carregue novamente o arquivo no formato correto. Uma mensagem de upload bem-sucedido é exibida, conforme mostrado.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bu-3.png)

Após o upload bem-sucedido do arquivo, o link **Arquivo de regras de assinatura** é ativado, indicando que um arquivo/dados já está disponível.

Depois de inserir todos os outros detalhes, clique no botão **Subscribe (Assinar** ). A tabela é validada para garantir a integridade dos dados e a distribuição precisa do relatório. Por exemplo, a coluna de destinatários deve conter endereços de e-mail válidos e não deve ser deixada em branco. Além disso, os nomes das colunas e seus respectivos tipos de dados devem estar alinhados corretamente - um endereço de e-mail não deve ser inserido em uma coluna de dados de cadeia de caracteres e, da mesma forma, dados de cadeia de caracteres não devem ser inseridos em uma coluna que espera valores numéricos ou de data.
