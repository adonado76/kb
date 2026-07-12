---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Editar propriedades de tabelas"
breadcrumb: []
source_path: "studio/reports/tables/edit-properties-tables.html"
images:
  - "resources/images/studio_images/apply-filters.png"
  - "resources/images/studio_images/checkbox-del-row.png"
  - "resources/images/studio_images/default-slicer.png"
  - "resources/images/studio_images/delete-all-rows-popup.png"
  - "resources/images/studio_images/disable-edits.png"
  - "resources/images/studio_images/export-et.png"
  - "resources/images/studio_images/fr-uneditablecolumn.png"
  - "resources/images/studio_images/permission-dialog.png"
  - "resources/images/studio_images/properties-1.png"
  - "resources/images/studio_images/r-notes/et-export_907x507.png"
  - "resources/images/studio_images/r-notes/et-permission_232x359.png"
  - "resources/images/studio_images/row-slicer.png"
  - "resources/images/studio_images/sel-chkbox-et.png"
  - "resources/images/studio_images/studioimages/reports/rep169.png"
  - "resources/images/studio_images/studioimages/reports/rep170.png"
  - "resources/images/studio_images/suppress-et.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Editar propriedades de tabelas

**Aplica-se a** : TBM Studio 12.0 e posterior

Você controla como os usuários interagem com as tabelas editáveis com as propriedades Editing (Edição). Observe que essas propriedades também se aplicam às tabelas geradas. Para saber mais sobre as propriedades de edição, consulte [Definir propriedades da tabela](set-table-properties.html "Aplica-se a: TBM Studio 12.0 e posterior").

Também é possível controlar como os usuários interagem com as tabelas editáveis com as propriedades Editing (Edição) na barra da faixa de opções TBM Studio . Observe que essas propriedades também se aplicam às tabelas geradas:

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/properties-1.png)

## Fazer upload

Você pode carregar uma tabela editável de uma das seguintes maneiras:

- Selecione **Upload** na faixa de opções Editable Tables (Tabelas editáveis).
- Selecione o botão Upload na parte inferior da tabela. Esse botão aparece somente quando você ativa a opção **Ativar/desativar upload** no pop-up [Propriedades avançadas](set-table-properties.html "Aplica-se a: TBM Studio 12.0 e posterior").

Para saber mais sobre as opções de upload, consulte o [componente Table Upload.](../table-report-upload-component.html "Aplica-se a: TBM Studio 12.9.3 e posterior")

## Baixe aqui

Esse botão está disponível por padrão para todas as tabelas editáveis. Ao selecionar esse botão, a seguinte janela pop-up é exibida.

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/export-et.png)

Faça a escolha apropriada e selecione o botão **Exportar**.

## Ativar a caixa de diálogo Adicionar linha

Selecione o botão **Enable Add Row Dialog** para configurar e adicionar uma nova linha com dados pré-preenchidos.

Clique no botão **Add Row (Adicionar linha** ) para ver a caixa de diálogo que contém a coluna e os dados e, em seguida, selecione a linha a ser adicionada ao relatório atual.

## Desativar edições

Esse campo usa uma expressão de texto dinâmica. Se a expressão for avaliada como verdadeira, a edição será desativada para a tabela. No exemplo abaixo, o usuário ddavis não poderá editar a tabela.

> `{$CurrentUser:Users.ID}="ddavis@ABCCompany.com"`

Para obter mais informações sobre texto dinâmico, consulte [Inserir texto dependente do contexto no HTML](../html.html "Aplica-se a: TBM Studio 12.0 e posterior").

Em 12.11.6, o botão **Delete All Rows (Excluir todas as linhas)** será exibido mesmo quando a expressão for "true" (verdadeira).

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/disable-edits.png)

## Colunas não editáveis

Aplica-se a 12.10.10 e posterior

Esse campo permite que você torne uma coluna não editável. Expanda a opção **Uneditable Tables (Tabelas não editáveis** ) para ver a lista de colunas que podem ser tornadas não editáveis.

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fr-uneditablecolumn.png)

## Script

ApptioScript é a linguagem de script usada para criar aplicativos de negócios interativos com base na plataforma Apptio.

ApptioScript pode ser usado para realizar muitas operações, como editar tabelas, enviar e-mails, fazer a transição de estados no fluxo de trabalho ou programar o que acontece quando o usuário clica em um botão. Veja [Sobre ApptioScript](../../apptioscript/about.html "ApptioScript é a linguagem de script usada para criar aplicativos de negócios interativos com base na plataforma Apptio.") e [Exemplos de ApptioScript](../../apptioscript/apptioscript_examples.html "Use os exemplos a seguir para revisar os usos de ApptioScript.").

## Validar total

Validador de coluna total
:   Usado para validar os totais das linhas. Por exemplo, você pode querer que uma linha de números some 100. Ou você pode verificar os valores que estão entre um valor baixo e um valor alto. Quando esse recurso é usado, uma coluna de totais é adicionada ao lado direito da tabela. Os valores que estão fora dos parâmetros são destacados em vermelho.

    Para definir os validadores, clique no ícone à direita do campo. A caixa de diálogo **Total Column Validator** é exibida conforme mostrado abaixo. Selecione **Total** no primeiro campo, selecione um qualificador no segundo campo e digite um valor no terceiro campo. Você pode adicionar várias entradas para especificar os valores mínimo e máximo. Para adicionar uma segunda entrada, clique no sinal + abaixo da primeira entrada.

    ![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep169.png)

Validador de linha total
:   Usado para validar os totais das linhas. Por exemplo, você pode querer que uma coluna de porcentagens seja somada a 100%. Ou você pode verificar os valores que estão entre um valor baixo e um valor alto. Quando esse recurso é usado, uma linha **de totais** é adicionada à parte inferior da tabela. Os valores que estão fora dos parâmetros são destacados em vermelho.

    Para definir os validadores, clique no ícone à direita do campo. A caixa de diálogo **Total Row Validator** é exibida como mostrado abaixo. Selecione **Total** no primeiro campo, selecione um qualificador no segundo campo e digite um valor no terceiro campo. Você pode adicionar várias entradas para especificar os valores mínimo e máximo. Para adicionar uma segunda entrada, clique no sinal + abaixo da primeira entrada.

    ![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep170.png)

## Permissões

Esta seção permite conceder/negar permissões para as seguintes ações em uma linha. A permissão padrão para **Delete All Rows Permission** é *admin e partner*, enquanto o restante das permissões tem *todos* como valor padrão.

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/et-permission_232x359.png)

## Adicionar permissão de linha

Especifica as funções que poderão adicionar linhas à tabela. As opções são *Everyone (Todos* ) e *Selected Roles (Funções selecionadas* ). Para especificar as funções, clique no ícone **Selecionar funções** e escolha a(s) função(ões) no menu suspenso.

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/permission-dialog.png)

## Permissão de linha duplicada

Especifique as funções que poderão duplicar as linhas em uma tabela.

## Permissão para excluir linha

Especifique as funções que poderão excluir linhas da tabela.

## Permissão para publicar linha

Especifique as funções que poderão publicar linhas na tabela.

## Permissão de edição de linha

Especifique as funções que poderão editar as linhas da tabela.

## Permissão de download

Especifique as funções que poderão fazer o download da tabela.

## Permissão de upload

Especifique as funções que poderão fazer upload da tabela.

## Mostrar permissões de histórico

Especifica as funções que poderão ver o histórico das alterações feitas na tabela.

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/et-export_907x507.png)

## Permissão Delete All Rows (Excluir todas as linhas)

Especifique as funções que poderão excluir todas as linhas de uma tabela editável.

## Excluir todas as linhas

Esse botão aparece somente quando você ativa a opção **Excluir todas as linhas** no pop-up [Propriedades avançadas](set-table-properties.html "Aplica-se a: TBM Studio 12.0 e posterior"). Ao selecionar esse botão, o pop-up de aviso é exibido conforme mostrado.

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/delete-all-rows-popup.png)

Digite "delete" e, em seguida, selecione o botão **OK**. A tabela está em branco, mas todas as alterações são capturadas na seção Show Changes (Mostrar alterações).

Observação: se você inserir qualquer valor diferente de "delete", o botão **OK** permanecerá desativado.

Se todas as células do conjunto filtrado de linhas visíveis estiverem bloqueadas, todos os botões (Adicionar linha, Excluir linha e Duplicar linha) serão desativados, mas o botão Excluir todas as linhas permanecerá ativado.

## Ativar coluna de caixa de seleção

**12.11.5 e posteriores** : A coluna de seleção de caixa de seleção aparece somente quando você ativa a opção **Ativar coluna de caixa de seleção** no pop-up [Propriedades avançadas](set-table-properties.html "Aplica-se a: TBM Studio 12.0 e posterior"). Filtre valores específicos e, em seguida, use o botão ApptioScript para editar o valor da célula ou excluir a linha.

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/sel-chkbox-et.png)

Selecione ou arraste o cursor por várias linhas. clique com o botão direito do mouse e selecione a opção **Excluir linha**.

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/checkbox-del-row.png)

A partir de **12.11.6** em diante, você pode fazer o seguinte:

- Em valores filtrados, selecione uma ou mais linhas específicas e edite o valor da célula ou exclua essa(s) linha(s) usando o botão ApptioScript.

## Publicar

Selecione esse botão para publicar os dados das tabelas geradas nas tabelas pai. Para obter mais informações, consulte [Publicar alterações manualmente na superfície de relatório](../../data_studio/table-update-schedule.html "Aplica-se a: TBM Studio 12.6 e posterior").

## Suprimir

Esse recurso permite que você suprima/oculte dados em tabelas editáveis extensas e grandes.

**12.11.5 e posteriores** : O relatório de tabela editável é suprimido somente quando você ativa a opção **Suprimir solicitação de dados inicial** no pop-up [Propriedades avançadas](set-table-properties.html "Aplica-se a: TBM Studio 12.0 e posterior").

Se a opção **Suprimir solicitação de dados iniciais** estiver selecionada, todos os dados serão ocultados na tabela. É exibida uma mensagem "*Selecione seu filtro preferido para recuperar os dados. Observação: O carregamento automático do relatório foi desativado.*".

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/suppress-et.png)

Para ver os dados de sua escolha, você deve aplicar [slicers compactos](../compact-slicers.html "Aplica-se a: TBM Studio 12.0 e posterior") ou filtros de linha.

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/default-slicer.png)

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/apply-filters.png)

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/row-slicer.png)

Como alternativa, você pode atualizar os dados manualmente, automaticamente ou selecionando **Update Data (Atualizar dados)** no menu do botão direito do mouse.
