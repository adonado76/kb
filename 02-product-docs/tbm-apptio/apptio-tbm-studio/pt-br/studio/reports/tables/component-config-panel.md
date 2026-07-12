---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "O painel Configuração de componentes"
breadcrumb: []
source_path: "studio/reports/tables/component-config-panel.html"
images:
  - "resources/images/studio_images/nc-shoiw.jpg"
  - "resources/images/studio_images/new-column.jpg"
  - "resources/images/studio_images/show-pk-column.png"
  - "resources/images/studio_images/show-pk.png"
  - "resources/images/studio_images/studioimages/studio/stu536.png"
  - "resources/images/studio_images/studioimages/studio/stu537.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# O painel Configuração de componentes

**Aplica-se a** : TBM Studio 12.0 e posterior

O painel **Configuração de componentes** é exibido quando você insere uma tabela ou um gráfico em um relatório. Ele inclui um seletor de tabelas e áreas em que você arrasta campos para criar tabelas e gráficos:

![configuração de componentes](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu537.png)

Há duas versões do painel **Configuração de componentes** : Usuário avançado e Analista. A versão que um usuário vê é controlada pela função atribuída a ele. As duas versões são descritas a seguir:

- **Usuário avançado** - Visualiza todos os recursos no painel de configuração e pode criar perspectivas personalizadas disponíveis para o analista. Essa exibição está disponível para usuários com a função Admin ou equivalente. A função deve ter a permissão **Editar modelos**.
- **Analista** - Visualiza apenas as perspectivas personalizadas, a perspectiva **de tempo** e o painel **Configuração de componentes**. Essa visualização está disponível para usuários com a função de Usuário Comercial ou equivalente.

Quando você insere um componente de relatório e seleciona uma tabela modelo na lista suspensa, a tabela selecionada determina os campos disponíveis nas perspectivas no **Project Explorer**. Todos os conjuntos de dados e métricas vinculados à tabela selecionada por meio do mecanismo de inferência estarão disponíveis.

As seções no **Project Explorer** organizam os campos que podem ser arrastados para as áreas de configuração para criar uma tabela. As dimensões padrão estão descritas abaixo:

- **Tables (Tabelas** ) - Exibe os nomes das tabelas vinculadas pelo **Apptio Inference Engine** ao objeto selecionado.
- **Métricas** - Exibe as métricas modeladas e calculadas.
- **Time (Tempo** ) - Exibe os períodos de tempo disponíveis.
- **Perspectivas** - Para aumentar as seções padrão, é possível criar perspectivas personalizadas na seção **Perspectivas**. As perspectivas personalizadas contêm campos selecionados de outras seções que você deseja disponibilizar para os analistas. Para obter mais informações sobre perspectivas, consulte [Criação de perspectivas personalizadas](../creating-custom-perspectives.html "Aplica-se a: TBM Studio 12.0 e posterior").

Para criar uma tabela, arraste os campos do **Project Explorer** para as áreas na parte inferior do painel **Configuração de componentes**. Vários campos podem ser adicionados a todas as áreas, exceto na área **Colunas**. Se um campo não puder ser aplicado a uma área, será exibida uma mensagem de aviso.

Para remover um campo de uma área, arraste-o para fora da área ou clique com o botão direito do mouse no campo e selecione **Remove (Remover** ).

As quatro áreas estão descritas abaixo.

- **Rows (Linhas** ) - Fornece entradas para a primeira coluna da tabela. Se houver entradas duplicadas na fonte, as entradas serão agrupadas e será exibida uma única entrada para cada valor exclusivo. Se você adicionar mais de um campo à área, os subgrupos serão criados na primeira coluna da tabela.
- **Columns** - Fornece cabeçalhos de coluna para a tabela. Arraste um campo aqui a partir de uma perspectiva. Somente um campo pode ser colocado na área **Columns (Colunas** ).
- **Valores** - Fornece os dados exibidos no corpo da tabela. Você pode ocultar um valor clicando com o botão direito do mouse no valor e selecionando **Hide (Ocultar** ).
- **Filtros** - Filtra as entradas em uma coluna da tabela. Arraste os campos para cá a partir de perspectivas e outras áreas. Se você usar uma métrica, poderá clicar com o botão direito do mouse na métrica e definir o intervalo de números.

## Exibir/ocultar a coluna.pk

**Aplica-se a** : R12.11.2 e posterior

O administrador do Apptio agora pode mostrar (e ocultar) a coluna.pk para tabelas editáveis brutas em um componente de relatório de tabela editável e também classificar os valores por ela. A coluna.pk será incluída por padrão nas colunas incluídas assim que o usuário arrastar qualquer coluna para as colunas incluídas, mas ficará oculta por padrão. O usuário pode mostrar/ocultar a coluna pk em um relatório passando o cursor sobre a coluna.PK e clicando com o botão direito do mouse para abrir o menu Adicionar aos filtros. Verifique se a coluna.PK está oculta por padrão e se o botão Show está ativado. Ao selecionar "**Show** ", a coluna.PK será exibida e poderá ser movida para qualquer ordem de coluna desejada.

![mostrar pk](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/show-pk.png)

Se a coluna.pk estiver visível no relatório e uma nova linha for adicionada, seu valor não será visível até que a linha seja salva. Isso foi feito para manter o padrão do índice pk oculto para o usuário. O usuário final pode usar esse recurso para oferecer suporte a várias células consistentes, copiar/colar, classificar a coluna PK on-line/planilha do Excel e copiar/colar começando com o intervalo correto.

![mostrar pk](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/show-pk-column.png)

## Mostrar/ocultar as colunas.Username e .EditDate

**Aplica-se a** : 12.11.11 e posterior

O administrador do Apptio agora pode mostrar (e ocultar) as colunas.Username e .EditDate em um componente de relatório de tabela editável e também classificar os valores por elas. A coluna.Username mostrará quem fez a última alteração e .EditDate mostrará quando a última alteração foi feita. Essas duas colunas serão incluídas por padrão nas colunas incluídas assim que o usuário arrastar qualquer coluna para as colunas incluídas.

![mostrar nome de usuário](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/new-column.jpg)

O usuário pode mostrar/ocultar essas colunas em um relatório passando o cursor sobre elas, clicando com o botão direito do mouse para abrir o menu **Add to Filters (Adicionar aos filtros** ). Ao selecionar "**Show** ", as colunas serão exibidas e poderão ser movidas para qualquer ordem de coluna desejada. Ambas as colunas são somente leitura e nenhuma alteração pode ser feita nelas.

![mostrar data de edição](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/nc-shoiw.jpg)

## Alterar a ordem dos campos nas caixas de área

Para alterar a ordem dos campos em uma caixa de área, arraste os campos para cima ou para baixo na lista. A ordem dos campos determina a ordem das colunas correspondentes na tabela.

## Limpar todos os campos

Para limpar todos os campos das áreas, clique no botão **Limpar** na parte inferior do painel.

## Adiar atualizações

Por padrão, as alterações feitas no painel **Ad Hoc Query Configuration** afetam imediatamente os dados exibidos na tabela. Se estiver trabalhando com grandes conjuntos de dados, pode levar algum tempo para que os dados sejam atualizados na tabela. Para evitar atrasos, você pode mudar para atualizações manuais desmarcando a opção **Update Results Immediately (Atualizar resultados imediatamente** ) na parte inferior da caixa de diálogo. Quando essa opção não estiver selecionada, as atualizações serão feitas somente quando você clicar no botão **Update (Atualizar** ).

## Minimizar o painel

Para minimizar o painel **Configuração**, clique na seta no canto superior direito.

## Filtrar campos em uma seção

Se houver uma longa lista de campos em uma seção, é possível filtrar a lista inserindo texto na caixa de filtro automático na parte superior da seção. À medida que você insere caracteres, a lista é filtrada:

![campos de filtro](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu536.png)
