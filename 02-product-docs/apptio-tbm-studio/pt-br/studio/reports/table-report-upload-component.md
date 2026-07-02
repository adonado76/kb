---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Componente de upload de tabela"
breadcrumb: []
source_path: "studio/reports/table-report-upload-component.html"
images:
  - "resources/images/studio_images/append-1.png"
  - "resources/images/studio_images/append-2.png"
  - "resources/images/studio_images/append-3.png"
  - "resources/images/studio_images/append-4.png"
  - "resources/images/studio_images/append-5.png"
  - "resources/images/studio_images/append-data-upload.png"
  - "resources/images/studio_images/studioimages/reports/table-upload-component-2.png"
  - "resources/images/studio_images/studioimages/reports/table-upload-component-3.png"
  - "resources/images/studio_images/studioimages/reports/table-upload-component-4.png"
  - "resources/images/studio_images/studioimages/reports/table-upload-component-5.png"
  - "resources/images/studio_images/studioimages/reports/table-upload-component-6.png"
  - "resources/images/studio_images/upload-checkedout.png"
  - "resources/images/studio_images/upload-from-report.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componente de upload de tabela

**Aplica-se a** : TBM Studio 12.9.3 e posterior

O componente Table Upload permite que os usuários finais com as permissões adequadas carreguem diretamente os dados das planilhas para as tabelas sem a necessidade de acesso ao site TBM Studio .

Dica: Para que o componente Table Upload esteja disponível na faixa de opções do relatório, talvez seja necessário ativá-lo usando Enable Features.

[Saiba mais sobre a opção Habilitar recursos.](../admin/enable_features.html "O TBM Studio às vezes contém recursos que ainda não foram liberados para todos os clientes. Esses são recursos da versão beta e podem não funcionar exatamente como foram projetados.")

## Configuração simples

Para usar a opção de configuração simples, faça o seguinte:

1. Adicione um componente Table Upload ao seu relatório.
2. Clique no botão Config no componente de upload da tabela.
3. Arraste as tabelas carregadas para a lista, conforme mostrado no exemplo a seguir.
4. ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/table-upload-component-2.png)

   Observação: Se você escolher a opção Enforce Errors (Aplicar erros), isso executará a validação na tabela. Se forem encontrados erros de validação, eles serão exibidos quando você tentar fazer o upload. Erros de validação, incluindo coisas como colunas ausentes, colunas com cabeçalhos incorretos etc.).
5. Clique em Apply (Aplicar) para salvar a configuração do componente.
6. Na faixa de opções, clique no botão Salvar para salvar o relatório.

Isso fará com que os usuários finais com acesso ao relatório possam selecionar as tabelas e atualizá-las.

Consulte a seção [Interação do usuário](#TableUploadcomponent__Userinteraction), mais adiante neste tópico, para obter detalhes sobre como é a experiência do usuário.

## Configuração avançada

O objetivo da opção de configuração avançada é oferecer suporte a um controle mais granular sobre quais tabelas os usuários ou grupos individuais podem atualizar sem precisar criar vários relatórios.

Para usar a opção de configuração avançada, faça o seguinte:

1. Crie uma tabela editável com as seguintes colunas:
   1. Tabela
   2. Função
   3. Usuário
2. Para fins deste exemplo, chamaremos a tabela editável de "Table Access".
3. Preencha as colunas com dados para especificar o usuário ou a função que deve ter acesso para atualizar uma determinada tabela. Aqui está um exemplo:

   | Tabela | Função | Usuário |
   | --- | --- | --- |
   | Contratos Acme | Usuário avançado |  |
   | Livro-razão geral da Acme |  | bob@acme.com |
   | Livro-razão geral da Acme |  | sally@acme.com |
   | Mapeamento organizacional da Acme IT |  | bob@acme.com |
   | Mapeamento organizacional da Acme IT |  | roxanne@acme.com |

   Considerando a tabela de exemplo acima e sabendo que Sally também é uma Power User, as tabelas que cada usuário verá no menu suspenso do componente Table Upload são as seguintes

   - bob@acme.com verá o Acme General Ledger e o Acme IT Org Mapping.
   - sally@acme.com verá o Acme Contracts (por estar no grupo de usuários avançados) e o Acme General Ledger.
   - roxanne@acme.com verá apenas o Acme General Ledger.
4. Adicione o componente Table Upload ao seu relatório.
5. No componente de upload da tabela, clique no botão Config.
6. Alterne o Tipo de configuração para Avançado.
7. No campo Table: (Tabela:), adicione o nome da sua tabela editável ("Table Access" no nosso exemplo) e, opcionalmente, especifique a correspondência para Roles e Users:
8. ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/table-upload-component-3.png)

   Observação: Se você escolher a opção Enforce Errors (Aplicar erros), isso executará a validação na tabela. Se forem encontrados erros de validação, eles serão exibidos quando você tentar fazer o upload. Erros de validação, incluindo coisas como colunas ausentes, colunas com cabeçalhos incorretos etc.).
9. Clique em Apply (Aplicar) para salvar a configuração do componente.
10. Na faixa de opções, clique no botão Salvar para salvar o relatório.

Isso fará com que os usuários finais com acesso ao relatório e acesso à tabela, conforme especificado na tabela editável descrita acima, possam selecionar as tabelas e atualizá-las.

Consulte a seção [Interação do usuário](#TableUploadcomponent__Userinteraction), mais adiante neste tópico, para obter detalhes sobre como é a experiência do usuário.

## Interação com o usuário

Quando um usuário com acesso ao relatório navegar até ele, verá o componente Upload Table.

Para usá-lo, eles devem fazer o seguinte:

1. Selecione uma das tabelas no menu suspenso.
2. Clique no botão Editar.

   Isso fará com que a tabela seja verificada. Quando a tabela estiver pronta, a página será atualizada.
3. Ao fazer o upload para um slot com dados existentes, você verá essas opções:

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/table-upload-component-4.png)
4. Depois de fazer as edições desejadas, clique em Save (Salvar).
5. Você verá uma caixa de diálogo de check-in. Inclua uma mensagem que descreva a natureza da alteração e clique em Check In.

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/table-upload-component-5.png)

Se você tiver selecionado a opção Enforce Errors (Aplicar erros) durante a configuração e forem detectados erros, será exibido um emblema de erro com menu suspenso.

No exemplo a seguir, uma coluna não estava presente como esperado, uma nova coluna foi adicionada e uma coluna que o sistema esperava que fosse numérica tinha valores de rótulo:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/table-upload-component-6.png)

## Upload de dados em tabelas editáveis

**12.11.3 e posteriores** : O botão **Upload** aparece apenas para a tabela em branco e não para a tabela gerada. Para ver esse botão, ative a opção **Ativar/desativar upload** no pop-up [Propriedades avançadas](tables/set-table-properties.html "Aplica-se a: TBM Studio 12.0 e posterior").

Se você fizer upload de dados para um relatório com check-out, o pop-up de upload não poderá ser fechado. Devido a isso, os botões **Upload** e **Save** permanecerão desativados e o arquivo/dados carregados não serão salvos. Você pode fechar o pop-up apenas atualizando a tabela - clique com o botão direito do mouse na área da tabela e selecione a opção **Atualizar dados**.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/upload-checkedout.png)

No entanto, quando você faz upload de dados em um relatório com check-in, o pop-up de upload tem o ícone de fechar e, portanto, o upload pode ser cancelado ou salvo com êxito.

## Upload de dados por meio de relatórios

Navegue até um relatório de tabela editável e filtre pelo escopo desejado. <clique com o botão direito do mouse> no menu fora da tabela e selecione **Abrir no Excel**.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-1.png)

Faça as alterações desejadas off-line no Excel [Evite o recurso Download ET ou a exportação do Excel da barra de navegação (exportação não filtrada)]

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-2.png)

Faça o upload das alterações selecionando **Upload ET** e arrastando e soltando ou digitando o nome do arquivo.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-3.png)

Você pode optar por substituir os dados existentes ou anexar os dados. O botão **Upload Now** será desativado até que uma opção seja selecionada.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-4.png)

Selecione a opção **Append (Anexar** ) e as novas entradas serão mescladas com as entradas anteriores mais antigas. A opção **Anexar** também funciona com a funcionalidade de integração Validação de dados - Upload de tabela.

Observação: a opção **Overwrite (Sobrescrever** ) é selecionada por padrão para o primeiro upload. Para todos os uploads futuros, o usuário deve selecionar uma das opções, Overwrite (Sobrescrever) ou Append (Anexar).

O arquivo carregado deve ter a mesma configuração que o arquivo carregado existente. Se a configuração não corresponder, será exibida uma janela pop-up restringindo a alteração dos dados de ET.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-5.png)

## Anexar dados após o upload

Em um relatório de tabela editável, clique com o botão direito do mouse para selecionar **Propriedades** > **Avançado** e, em seguida, escolha a opção "Anexar dados no upload".

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-data-upload.png)

Agora, carregue qualquer arquivo para ver o pop-up **Upload Options**.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/upload-from-report.png)

Veja como [a análise aprimorada do Excel](tables/enhanced-excel-parsing.html) funciona em Apptio

- **[Como funciona a análise aprimorada do Excel em Apptio](../../studio/reports/tables/enhanced-excel-parsing.html)**
