---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Trabalhar com relatórios mestre"
breadcrumb: []
source_path: "studio/reports/master-reports.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu631.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Trabalhar com relatórios mestre

**Aplica-se a** : TBM Studio 12.0 e posterior

Se quiser que um conjunto de relatórios tenha o mesmo layout, você pode criar um relatório mestre e aplicá-lo a cada um dos relatórios. Um relatório mestre pode incluir todos os componentes de um relatório normal, como botões, caixas de grupo e itens de ação. O conceito é semelhante ao dos slides mestres em aplicativos de apresentação. Os relatórios mestre, por padrão, são sempre relatórios de nível superior. Para criar um relatório mestre, crie um novo relatório e clique na opção **Relatório mestre** no grupo **Avançado** da guia **Relatório**.

## Relatórios mestre padrão

O aplicativo inclui muitos relatórios mestre padrão. Eles estão listados no menu suspenso **Mestres** na guia **Relatório**. Você pode usar esses relatórios mestre como estão ou modificá-los e salvá-los usando a opção **Salvar como**. Não é possível excluir relatórios mestre padrão.

## Relatórios mestre como papel de parede

Pense nos relatórios mestre como papel de parede. Quando aplicados a um relatório personalizado, os componentes de um relatório mestre não podem ser editados em um relatório personalizado. Eles são estáticos. Os componentes adicionados a um relatório personalizado ficam na parte superior do papel de parede. Por exemplo, se o mestre incluir uma caixa de grupo, você poderá posicionar os componentes de modo que eles apareçam dentro da caixa de grupo, mas não sejam anexados a ela.

Se você adicionar um componente com abas a um relatório mestre, as abas funcionarão quando você aplicar o relatório mestre a um relatório. No entanto, evite colocar qualquer componente na parte superior do componente com guias no relatório personalizado, pois eles serão exibidos na parte superior de todas as guias. Novamente, pense no componente com abas como um papel de parede.

## Criar e excluir relatórios mestre

Para criar um relatório mestre:

1. Verifique o relatório que você deseja usar como mestre.
2. No grupo **Avançado** da guia **Relatório**, clique na opção **Relatório mestre**.
3. Salve o relatório.

Para excluir um relatório mestre:

1. No modo Edição de relatório, clique na seção **Relatórios** no **Project Explorer**. Filtre a lista de relatórios por **Relatórios mestre**.

   ![Relatórios mestre](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu631.png)
2. Verifique o relatório que você deseja excluir.
3. Clique em **Excluir** na guia **Início**.
4. Verifique no relatório.

Observação: Só é possível excluir relatórios mestre de clientes. Não é possível excluir os relatórios mestre padrão que acompanham o produto.

## Aplicar um relatório mestre

Para aplicar um relatório mestre a um relatório personalizado:

1. Confira o relatório personalizado no modo de edição.
2. Na guia **Relatório**, abra a lista suspensa **Mestres** e clique no relatório mestre que deseja aplicar.

Você pode aplicar relatórios mestre a outros relatórios mestre, mas isso não é recomendado.

## Remover um relatório mestre

Para remover um relatório mestre de um relatório personalizado:

1. Selecione a guia **Relatório**.
2. Abra a lista suspensa **Mestre** e selecione **Nenhum** na parte inferior da lista.

## Práticas recomendadas do relatório mestre

Abaixo estão várias práticas recomendadas para a criação de relatórios mestre.

1. Os relatórios mestre são auxílios de layout. Em geral, você deseja criar contêineres, como caixas de grupo, nos quais colocará componentes, como gráficos e tabelas.
2. Se você adicionar um componente com abas a um relatório mestre, certifique-se de adicionar componentes a cada uma das abas. Não será possível adicionar componentes às guias individuais no relatório personalizado em que você aplicar o mestre. Os componentes adicionados na parte superior de um componente com guias serão exibidos na parte superior de todas as guias.
3. As caixas de grupo adicionadas a um relatório mestre perdem suas habilidades de agrupamento quando o mestre é aplicado a um relatório personalizado. Use caixas de grupo como uma borda visual ao redor dos componentes.
4. Se você adicionar um botão a um relatório mestre que usa texto Wiki e não tiver especificado um Data URL para o botão, o aplicativo usará o relatório atual como contexto.
