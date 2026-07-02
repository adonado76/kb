---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Caixa de texto HTML"
breadcrumb: []
source_path: "studio/reports/html.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png"
  - "resources/images/studio_images/studioimages/reports/rep146.png"
  - "resources/images/studio_images/studioimages/studio/stu518.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Caixa de texto HTML

**Aplica-se a** : TBM Studio 12.0 e posterior

Você pode adicionar uma caixa contendo texto formatado em HTML. O texto pode apresentar informações que expliquem o relatório ou forneçam outras informações importantes. Um exemplo de caixa HTML é mostrado na imagem a seguir. A sintaxe HTML suportada depende do navegador que você está usando (não da caixa de texto HTML).

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu518.png)

O HTML pode incluir links para outros relatórios e texto dependente do contexto (texto dinâmico), como data ou nome de usuário. Para obter mais informações, consulte [Codificação de links para outros relatórios](coding-links-to-other-reports.html "Aplica-se a: TBM Studio 12.0 e posterior"). O componente HTML é usado com mais frequência para adicionar texto, mas você pode inserir qualquer código HTML formatado corretamente. Por exemplo, você pode adicionar bordas e gráficos ao redor da caixa de texto.

Observação: A caixa de texto HTML não é compatível com JavaScript.

Você pode adicionar um contexto de objeto para o texto dependente de contexto usando o painel **Configuração de HTML**.

As caixas de texto são visíveis para todos os usuários, independentemente da função.

## Adicionar uma caixa de texto HTML

1. Na guia **Relatório**, clique no ícone **HTML**. A caixa de texto é adicionada ao relatório e a caixa de diálogo **Editar conteúdo** é aberta, conforme mostrado na imagem a seguir:![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep146.png)
2. Digite o texto e a codificação HTML na caixa de diálogo.
   - Para adicionar o texto à caixa de texto e deixar a caixa de diálogo **Editar conteúdo** aberta, clique em **Aplicar**.
   - Para adicionar o texto ao objeto de texto e fechar a caixa de diálogo, clique em **OK**.

## Adicionar um contexto de tabela à caixa HTML

Se estiver usando texto dependente de contexto na caixa HTML, você poderá adicionar um contexto de tabela usando o painel **Configuração de HTML**.

1. Selecione a caixa HTML.
2. No painel **Configuração de HTML**, selecione uma tabela no campo na parte superior do painel.
3. Se você tiver adicionado uma métrica no texto, como Custo, arraste o campo de cálculo correspondente para a área **Valores** da caixa de diálogo, conforme mostrado na primeira imagem.

## Editar texto em uma caixa de texto

Para editar o texto em uma caixa de texto:

1. Selecione a caixa de texto.
2. Na guia HTML, clique em **Edit Content (Editar conteúdo** ).

## Inserir texto dependente do contexto no HTML

O aplicativo fornece uma sintaxe de script que pode ser usada para inserir texto dependente do contexto (dinâmico) em caixas de texto HTML e caminhos de dados. Você pode usar essa sintaxe para criar títulos, legendas e cabeçalhos de relatórios personalizados para colunas agrupadas em tabelas. Você também pode usá-lo na caixa de diálogo **Editar caminho**, disponível no painel **Avançado** da caixa de diálogo **Propriedades** de uma tabela.

O texto dinâmico usa a seguinte sintaxe:

`<%=code%>`

Na declaração anterior, *o código* pode ser uma referência de coluna a qualquer tabela, métrica, fórmula ou função.

## Exemplos

O exemplo a seguir exibe o valor atual da métrica Custo:

> `<%=Cost%>`

Os exemplos a seguir mostram duas maneiras de formatar o valor atual da métrica Custo como moeda:

> `<%=Currency(Cost)%>`
>
> `<%=NumberFormat(Table.Column,”$#,###.00”)%>`

O exemplo a seguir faz referência ao conteúdo da coluna Server Name (Nome do servidor) para exibir o nome do servidor atual:

> ```
> <%=Server.Server
>           Name%>
> ```

O exemplo a seguir chama a função LEFT para exibir os três caracteres mais à esquerda do nome do servidor:

> `<%=LEFT(Servers.Server OS,3)%>`

O exemplo a seguir usa a sintaxe dinâmica em um URL para exibir a entrada do CMDB de um servidor:

> ```
> <a
>           href="http://cmdb.company.com/report?server=<%=Server.ServerId%>">
> ```

O exemplo a seguir exibe a data atual no texto:

> `<%=CurrentDate()%>`

O exemplo a seguir exibe o nome da conta de e-mail do usuário:

> `<%=$CurrentUser:Users.Id%>`

O exemplo a seguir exibe o nome completo do usuário:

> `<%=$CurrentUser:Users.Full Name%>`

O exemplo a seguir exibe $0 se o valor retornado estiver em branco:

> ```
> <%=IF(IsNumeric(SRM
>           Debits and Credits),Currency({SRM Debits and
> Credits},"#,###"),"$0")%>
> ```

## Propriedades

Para editar as propriedades de um componente HTML, exiba a caixa de diálogo **Propriedades** executando uma das seguintes ações:

- No canto superior esquerdo do componente, clique no pequeno triângulo ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png) ao lado do nome do componente para exibir o menu **Actions (Ações** ). No menu **Ações**, selecione **Propriedades**.
- Clique com o botão direito do mouse em qualquer lugar dentro das bordas do componente e selecione **Propriedades** no menu pop-up.

## Propriedades gerais

- **Nome** - Digite um nome a ser exibido no cabeçalho da tabela acima do componente. O nome é exibido quando a opção **Show Header** é selecionada.
- **Show Header (Mostrar cabeçalho** ) - O cabeçalho do componente exibe o conteúdo do campo **Name (Nome** ). Selecione essa opção para tornar o cabeçalho do componente visível (o padrão). Quando o cabeçalho está oculto, é possível pausar o ponteiro do mouse no componente para exibi-lo no modo Editar.
- **Show Border (Mostrar borda** ) - Selecione essa opção para exibir uma borda ao redor da tabela. Quando a borda está oculta, é possível exibi-la ao pausar o ponteiro do mouse no componente.
- **Wrap Title (Envolver título** ) - Envolve o texto inserido no campo **Name (Nome** ) para acomodar a largura do componente.
- **Dynamic Text Context (Contexto de texto dinâmico** ) - Especifica o caminho para a fonte que será usada para o texto dinâmico inserido na caixa HTML. Para obter informações sobre texto dinâmico, consulte Inserção de texto dependente do contexto acima.

## Propriedades avançadas

- **Atualização automática quando os cálculos terminam** - Quando o aplicativo exibe um componente HTML, ele o exibe com os dados calculados que estão disponíveis no momento. Em muitos casos, o aplicativo pode estar calculando novos valores em segundo plano. Se você quiser que os resultados sejam exibidos quando os cálculos forem concluídos, marque essa opção. A opção está disponível somente quando a **Política de cálculo** (na caixa de diálogo **Cálculo do projeto** ) de um projeto está definida como **Publicação dinâmica**.

## Adicionar uma barra de rolagem

Se você quiser inserir uma grande quantidade de texto na caixa HTML, mas quiser limitar o tamanho da caixa, poderá adicionar uma barra de rolagem usando o seguinte código HTML:

> ```
> <div
>           style="overflow-y:scroll; height:100%">
> This is
>             a</br>
> test for scroll</br>
> bars</br>
> </div>
> ```
