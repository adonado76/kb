---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Configurar o conector Coupa DataLink"
breadcrumb:
  - "Costing Standard"
  - "Integrações tecnológicas"
  - "Informações sobre fornecedores Coupa"
  - "Informações sobre fornecedores Coupa Introdução"
source_path: "cost-transparency/technology-integration/configure_the_datalink_coupa_connector.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configurar o conector Coupa DataLink

◆ Aplica-se a: Datalink (Classic)4.8.7 e posteriores

[Visão geral](#overview "(Abre em uma nova guia ou janela)")

[Pré-requisitos](#prerequisites "(Abre em uma nova guia ou janela)")

[Instruções](#instruction_overview "(Abre em uma nova guia ou janela)")

- [Tarefa 1: Configurar o conector](#task_1:_configure_the_connector "(Abre em uma nova guia ou janela)")
- [Tarefa 2: Definir as informações da consulta](#task_2:_define_the_query_information "(Abre em uma nova guia ou janela)")
- [Tarefa 3: Definir as propriedades](#_task_3:_define_the_properties "(Abre em uma nova guia ou janela)")
- [Tarefa 4: Configurar o conector Coupa Apptio Configurações de destino](#task_4:_configure_the_coupa_connector__apptio_destination_settings "(Abre em uma nova guia ou janela)")
- [Tarefa 5: Configurar notificações por e-mail do conector](#task_5:_configure_connector__email_notifications "(Abre em uma nova guia ou janela)")
- [Tarefa 6: Testar o conector](#task_6:_test_the_connector_ "(Abre em uma nova guia ou janela)")
- [Tarefa 7: Salvar a configuração do conector](#task_7:_save_the_connector__configuration "(Abre em uma nova guia ou janela)")
- [Tarefa 8: Executar ou cancelar a execução do conector](#task_8:_execute_or_cancel_the_connector__run "(Abre em uma nova guia ou janela)")
- [Tarefa 9: Visualizar o histórico de execução](#task_9:_view_execution_history "(Abre em uma nova guia ou janela)")
- [Tarefa 10: Validar a saída em TBM Studio](#task_10:_validate_output_in_tbm_studio "(Abre em uma nova guia ou janela)")

[Resolva problemas com o conector](#troubleshoot_issues_with_the_connector_ "(Abre em uma nova guia ou janela)")

[Apêndice](#appendix "(Abre em uma nova guia ou janela)")

- [Melhores práticas do modo de recuperação](#retrieval_mode_best_practices "(Abre em uma nova guia ou janela)")
- [Recomendação para opções de recuperação](#recommendation_for_retrieval_options "(Abre em uma nova guia ou janela)")
- [Propriedades JSON e objetos Coupa](#json_propteries_and_coupa_objects "(Abre em uma nova guia ou janela)")
- [Aviso sobre colunas de segmento de conta em tabelas](#warning_about_account_segment_columns_in_tables "(Abre em uma nova guia ou janela)")

**Visão geral**

Use o Conector Coupa do Datalink (Classic) para exportar dados do Coupa e, em seguida, importe-os para sua instância do Apptio para gerar relatórios no ApptioVendor Insights .

**Instruções**

**Tarefa 1: Configurar o conector**

1. Abra o Agente do Datalink (Classic) e clique em Novo Conector.
2. Clique no Conector Coupa.
3. Digite um Nome do Conector.   
      
    **Exemplo** : Coupa – Dados iniciais – Linha de pedido   
    de compra
4. Opcionalmente, selecione Adicionar este conector a um grupo de conectores.   
      
    **Exemplo de nome** : Coupa – Dados iniciais   
     
    Para obter informações sobre grupos de conectores, consulte [Agrupar vários conectores](../../datalink-classic/datalink/group-connectors.html "(Abre em uma nova guia ou janela)").

**Tarefa 2: Definir as informações da consulta**

Para obter informações sobre como definir a consulta e, especificamente, sobre autenticação, consulte [Definir as informações da consulta](../../datalink-classic/datalink/connectorguides/c-coupa.html).

**Tarefa 3: Definir as propriedades**

1. Selecione um Modo de recuperação.   
    Se você selecionar Dados iniciais (Dados a partir de), forneça informações adicionais sobre o Mês inicial e o Ano inicial.

   **Exemplos**

   - Modo de recuperação: Dados iniciais (Dados a partir de)
   - Mês de início: janeiro
   - Ano de início: 2019

   **Opções do modo de recuperação**

   As etapas de configuração diferem para cada modo de recuperação:
   - **Dados iniciais (todos os dados)** - Recupera todos os dados até a data de execução do conector. Esta transformação de destino está configurada para substituir os dados anteriores.
   - **Dados iniciais (Dados a partir de)** - Recuperar dados a partir de um mês e ano definidos até a data de execução do conector (>= [mês inicial] / 01 / [ano inicial]). Esta transformação de destino está configurada para substituir os dados anteriores.
   - **Dados Delta (a partir do início do mês passado)** - Recuperar dados desde o início do mês anterior até a data de execução do conector (>=[mês do mês passado] / 01 / [ano do mês passado]). Essa transformação de destino está configurada para anexar os novos dados aos dados anteriores.   
        
      Consulte [o Apêndice: Melhores práticas do modo de recuperação](#retrieval_mode_best_practices "(Abre em uma nova guia ou janela)") para obter mais informações.
2. Selecione um objeto Coupa. Você pode acessar e importar os seguintes tipos de dados da API Coupa e critérios de filtro (além do intervalo de dados do Modo de Recuperação ) para sua instância do Apptio :

   | Objeto Coupa | Filtro de status padrão |
   | --- | --- |
   | Fornecedores | ativo, inativo |
   | Contratos | publicado, inativo |
   | Ordens de Compra | Todos os status |
   | Linhas de ordem de compra | Todos os status |
   | Contas de linha de ordem de compra | Todos os status |
   | Faturas | aprovado, anulado |
   | Linhas da fatura | aprovado, anulado |
   | Contas de linhas de fatura | aprovado, anulado |

   Observação: as linhas da fatura e as contas das linhas da fatura são filtradas pelo status da fatura principal.
3. Selecione um filtro de status

**Tarefa 4: Configurar o conector Coupa Apptio Configurações de destino**

Conecte seu conector ao seu destino no Apptio. No conector, clique em “ Apptio **” (Destino)** no menu à esquerda para acessar essas configurações. Se o conector fizer parte de um grupo de conectores, as  Apptio  **Destino**   configurações para  Apptio Instância  ,  Projeto  Domínio  , e  Filial  serão desativadas e, em vez disso, herdadas das configurações do grupo.

| Campo | Descrição | Exemplo |
| --- | --- | --- |
| Apptio **Versão** | Selecione R12 com porta frontal. | R12 com porta da frente |
| Apptio **Instância** | Selecione na lista de aplicativos válidos da Administração de Acessos. | Costing Standard (https://acme.apptio.com) |
| **Domínio** | Digite o nome de domínio da instância do Apptio de destino. | acme.com |
| Projeto | Digite o nome do projeto de destino. | Costing Standard |
| **Tabela** | Insira o nome da tabela de destino.   Este é apenas o nome da tabela. Não é a informação do caminho ou do diretório ( URL ). Se a tabela não existir, ela será criada. | Coupa Raw – Inicial – Linha PO |
| **Sistema de origem** | Insira **Coupa** como o nome do sistema de origem dos dados. | Coupa |
| **Período de tempo** | Selecione **Hora específica**. | **Hora específica** |
| **Período específico** | Selecione o Mês específico, o Tipo de calendário e o Ano específico.     Recomenda-se usar um dos modos de recuperação **de Dados Iniciais** na seção **Definir as propriedades** para preencher sua instância do Apptio com dados históricos. Esses dados são colocados no período de tempo especificado nas configurações de Hora específica. | Desmarcar |
| Validação | Selecione esta caixa de seleção para validar os dados carregados usando o conjunto de dados existente. | Selecionar |

Se as colunas não corresponderem, os dados carregados serão mantidos em uma área de preparação, mas não serão adicionados ao conjunto de dados. Um e-mail é enviado aos usuários administradores do Datalink (Classic) notificando-os de que o upload não passou na validação. Nesse caso, o administrador pode acessar a guia TBM Studio Dados e aprovar manualmente o upload. É uma boa prática validar os dados antes de enviá-los.

**Opções avançadas**

| Campo | Descrição | Exemplo |
| --- | --- | --- |
| Codificação de dados | Selecione a codificação de caracteres a ser usada nas consultas.     Esta opção está disponível apenas quando a instância de destino do Apptio é R12. | **Detecção automática** |
| Categoria | Insira uma categoria para a tabela.     Esta opção está disponível apenas quando a instância de destino do Apptio é R12. | z\_Coupa Raw |
| Filial | Se você estiver usando o recurso de ramificação em TBM StudioR12, insira um nome de ramificação para carregar os dados nessa ramificação.     Para obter mais informações, consulte [Projetos de ramificação](../../studio/admin/bp-branching-projects.htm "(Abre em uma nova guia ou janela)").  - Este recurso requer o R12.5 ou posterior. Se estiver usando uma versão anterior do R12, a configuração será ignorada e os dados serão carregados no tronco. - Se o nome do branch estiver incorreto ou não existir mais (por exemplo, o branch foi fechado e uma compilação subsequente foi concluída), um erro será relatado. |  |
| Transformação | 1. Selecione um valor adequado para o modo de recuperação que você selecionou:  - Dados iniciais (Todos os dados) - Defina como Sobrescrever os dados anteriores. - Dados iniciais (Dados a partir de) - Defina como Sobrescrever os dados anteriores. - Dados Delta (a partir do início do mês passado) - Defina para anexar os novos dados aos dados anteriores. | **Substituir** |

  

**Tarefa 5: Configurar notificações por e-mail do conector**

Depois de configurar as notificações por e-mail para o seu Agente Datalink (Classic), você pode configurar notificações por e-mail para cada conector. Se você não configurou suas definições SMTP, consulte [Configurar notificações por e-mail do agente](../../datalink-classic/datalink/config-datalink-agents.html#agentemail "(Abre em uma nova guia ou janela)"). Você pode especificar que uma notificação por e-mail seja enviada quando um conector for bem-sucedido ou falhar.

1. Clique em Notificar ou Notificar e arquivar no menu à esquerda para acessar as configurações de e-mail. Caso contrário, role para baixo até a seção Notificar ou Notificar e arquivar.
2. Selecione suas preferências de e-mail.
3. Na caixa Para, insira um ou mais endereços de e-mail, separados por vírgula ou ponto e vírgula.
4. Digite um assunto na caixa Assunto.

**Tarefa 6: Testar o conector**

Clique em Teste no canto superior direito para testar o conector.

Se houver um erro, ele será sinalizado e você poderá ir diretamente para essa parte da definição do conector. Clicar em Testar salva todas as alterações feitas no conector.

**Tarefa 7: Salvar a configuração do conector**

Clique em Salvar no canto superior direito para salvar o conector.

Se houver informações faltando na configuração, elas serão sinalizadas para você.

**Tarefa 8: Executar ou cancelar a execução do conector**

- Para executar o conector, abra o Datalink (Classic) Agente, clique  Ações  em ao lado do conector e, em seguida, clique  Corra agora  em.
- Para cancelar um conector em execução, abra o Datalink (Classic) Agent, clique em Ações ao lado do conector e, em seguida, clique em Cancelar execução.

**Tarefa 9: Visualizar o histórico de execução**

Visualize um relatório dos resultados da execução que lista as fontes, o destino, o período alvo, a hora de início e término da execução, uma explicação dos resultados e o número de bytes carregados para cada execução do conector.

1. Abra o Datalink (Classic) Agent, clique em Ações ao lado do conector e, em seguida, clique em Exibir histórico de execução.   
      
    **NOTA** : Por padrão, o Histórico de Execução exibe informações de execução dos últimos três meses.
2. (Opcional) Altere os valores nos campos  De   Até  e e clique em  Obter registros de execução  para visualizar até 12 meses de histórico.

**Tarefa 10: Validar a saída em TBM Studio**

Certifique-se de que a tabela com o nome especificado foi criada com sucesso.

**Resolva problemas com o conector**

Se o Conector falhar durante a execução, tente desmarcar a caixa de seleção Validação. Execute o Conector e, em seguida, marque novamente a caixa de seleção Validação para futuras execuções.

**NOTA** : Para Datalink (Classic) 4.8.8 (compilação new-master-12000 ) e posteriores, o não `execution ID`  está presente nos arquivos de log.

**Apêndice**

**Melhores práticas do modo de recuperação**

Ao configurar pela primeira vez a integração do Coupa com o Apptio, é recomendável usar um modo de recuperação de dados iniciais para preencher o Apptio com os dados históricos necessários. Os dados iniciais preencherão o período de tempo especificado usando as opções de Hora específica na configuração Período de tempo do destino Apptio. Para saber mais, consulte [Configurar as definições de destino](#task_4:_configure_the_coupa_connector__apptio_destination_settings "(Abre em uma nova guia ou janela)") do Apptio.

A opção Delta Data foi projetada para ser o modo de recuperação para execuções programadas do Connector. Esta opção serve para recuperar registros que foram atualizados no Coupa e, em seguida, anexá-los à mesma tabela no mesmo período. Nesse caso, você pode usar o recurso TBM Studio Remover Duplicatas para garantir que apenas a versão mais recente de um determinado registro seja usada em Apptio.

**NOTA** : A Coupa recomenda usar a opção Dados Iniciais (Definir Data de Início) para carregamentos de dados iniciais, a fim de evitar a transferência de volumes de dados desnecessários. Embora os Dados Iniciais (Todos os Dados) possam ser adequados para Fornecedores e Contratos.

Valores esperados

A tabela a seguir mostra os valores esperados ao extrair dados do Coupa:

| Objeto Coupa | Puxada inicial - filtro de dados | Filtro de status padrão | Período inicial de atração - destino | Puxada inicial -   onde colocar os dados (transformação) | Delta pull - filtro de dados | Delta pull - período de tempo de destino | Delta pull - onde colocar os dados (transformação) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Fornecedor | Dados iniciais (todos os dados) | ativo, inativo | Primeiro período do ano corrente | Sobrescrever | Dados delta (a partir do início do mês passado) | Período anterior | Anexo |
| Contrato | Dados iniciais (todos os dados) | publicado, inativo | Primeiro período do ano corrente | Sobrescrever | Dados delta (a partir do início do mês passado) | Período anterior | Anexo |
| PO, Linha PO, Conta da Linha PO | Dados iniciais (todos os dados) | Todos os status | Primeiro período do ano corrente | Sobrescrever | Dados delta (a partir do início do mês passado) | Período anterior | Anexo |
| Fatura, Linha da fatura, Conta da linha da fatura | Dados iniciais (dados a partir de) | aprovado, anulado | Período anterior | Sobrescrever | Dados delta (a partir do início do mês passado) | Período anterior | Anexo |

**Recomendação para opções de recuperação**

Recomenda-se que você use um dos modos de recuperação de dados iniciais para preencher sua instância do Apptio com dados históricos. Esses dados são colocados no período de tempo especificado nas configurações de Hora específica. Para saber mais, consulte [Definir as propriedades](#_task_3:_define_the_properties "(Abre em uma nova guia ou janela)").

**Exemplo** : Hora específica

**Exemplo** : Período específico: Jan:FY2019

**Propriedades JSON e objetos Coupa**

As propriedades JSON serão extraídas em relação ao objeto Coupa que está sendo consultado. Para os objetos Conta da linha do pedido de compra e Conta da linha da fatura, o objeto raiz para cada registro será a alocação de conta, se a conta fornecida for membro de uma alocação de conta. Caso contrário, o objeto raiz será conta.

**Exemplo** : O campo adicional “Nome do campo adicional: some.path ” para um objeto “Conta de linha de fatura” obteria seu valor de `invoice.invoice-lines.account-allocations` “para contas que são membros de uma alocação de conta” e `invoice.invoice-lines.account` “para contas que não são membros de uma alocação de conta”.

**Aviso sobre colunas de segmento de conta em tabelas**

Em Datalink (Classic)4.8.15 e posteriores, as colunas do segmento de conta nas tabelas carregadas pelo Conector Coupa Datalink (Classic) para Contas de Linha de Pedido de Compra e Contas de Linha de Fatura seguem as seguintes novas convenções de nomenclatura:

- O segmento da conta 01-09 permanece o mesmo (um 0 precede os números 1-9)
- O segmento de conta 010 e acima não requer mais um 0 antes do número.   
    
   **Exemplo** : a conta 010 agora é a conta 10, e a conta 011 agora é a conta 11

Ao anexar a uma tabela que utilizava a convenção de nomenclatura anterior (Conta 010 em vez de Conta 10), as novas colunas renomeadas dos segmentos da conta são adicionadas à tabela. Os registros da tabela que existiam antes de Datalink (Classic) 4.8.15 continuam a armazenar dados do segmento da conta usando a convenção de nomenclatura anterior.
