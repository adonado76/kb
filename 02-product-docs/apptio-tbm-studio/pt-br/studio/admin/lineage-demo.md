---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Demonstração de linhagem"
breadcrumb: []
source_path: "studio/admin/lineage-demo.html"
images:
  - "resources/images/studio_images/demo-lineage-10.png"
  - "resources/images/studio_images/demo-lineage-11.png"
  - "resources/images/studio_images/demo-lineage-2.png"
  - "resources/images/studio_images/demo-lineage-3.png"
  - "resources/images/studio_images/demo-lineage-4.png"
  - "resources/images/studio_images/demo-lineage-5.png"
  - "resources/images/studio_images/demo-lineage-6.png"
  - "resources/images/studio_images/demo-lineage-7.png"
  - "resources/images/studio_images/demo-lineage-8.png"
  - "resources/images/studio_images/demo-lineage-9.png"
  - "resources/images/studio_images/r-notes/demo-lineage-1.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Demonstração de linhagem

O recurso Lineage não está ativo por padrão. Um administrador pode ativá-lo navegando até a guia **Projeto** > **Ativar recursos** e, em seguida, selecionar **Mostrar linhagem**. Em seguida, ele pode ser acessado de diferentes entidades, como tabelas, colunas em tabelas, tabelas editáveis e relatórios de métricas.

Vamos analisar um exemplo para demonstrar o poder da linhagem: pegue o projeto Apptio One Cost (historicamente chamado de Cost Transparency) e extraia um conjunto de dados simples em um modelo simples apenas para começar.

Considere o conjunto de dados Apptio Value Explorer >>Value Master. Aqui, no pipeline de dados, você tem a etapa de anexação com algumas tabelas conectadas, uma etapa de fórmula que inclui uma pesquisa em outra tabela. Você também vê a etapa Join, que mostra vários relacionamentos entre tabelas. Esses são alguns dos relacionamentos que você pode identificar rapidamente aqui.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/demo-lineage-1.png)

Para explorar a linhagem dessa tabela, navegue até o explorador de projetos, clique com o botão direito do mouse e selecione **Trace Lineage for this document**. Uma nova guia para linhagem é exibida com um diagrama bastante complexo.

A cor azul representa os objetos relacionados ao modelo (AVE) e a cor marrom representa os relatórios.

A visualização inicial é limitada a uma profundidade de 1 e mostrará as dependências posteriores, pois estamos começando com uma tabela que pode ser aumentada com base na complexidade dos relacionamentos da entidade selecionada. À medida que o projeto se torna muito complexo, você pode obter mais profundidade para detalhar os relacionamentos. Você também pode alternar entre dependências downstream, que é o padrão se você escolher uma tabela, ou dependências upstream, que é o padrão se você escolher um relatório.

Você também pode incluir ou excluir os subcomponentes ou subtipos associados a tabelas, objetos de modelo ou relatórios. Marque a caixa de seleção do subtipo que deseja ver em seu diagrama de linhagem. Os números de cada subtipo indicam a contagem total de entidades presentes no diagrama. Você também pode Selecionar todos/Desmarcar todos os subtipos usando a alternância de subtipos.

Informações adicionais sobre qualquer entidade estão disponíveis ao passar o mouse sobre elas. Se você clicar na seta vermelha para cima, ela mostrará a lista de entidades a serem adicionadas acima do objeto selecionado no gráfico.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/demo-lineage-2.png)

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/demo-lineage-3.png)

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/demo-lineage-4.png)

Da mesma forma, clique na seta vermelha Downside para ver as entidades downstream.

Agora, remova todos os subtipos e selecione **Aplicar**. Você pode ver uma tabela no nível superior entrando em um modelo. Agora, aumente a profundidade e aplique para ver mais informações com essas duas entidades em foco.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/demo-lineage-5.png)

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/demo-lineage-6.png)

Aqui, uma **linha sólida** significa que há uma dependência direta entre as duas entidades e você pode ver qual é essa dependência passando o mouse sobre a linha. A **linha pontilhada** significa que há uma dependência indireta: provavelmente outras entidades intermediárias entre as duas no diagrama. Você pode clicar duas vezes na linha pontilhada para ver quais são essas dependências intermediárias.

Você também notará que a profundidade de escolha é aumentada até o nível 5, o que significa que incrementamos apenas algumas camadas de cada vez. Isso é feito para manter o mesmo desempenho em cada iteração e retornar mais informações. Ao escolher a profundidade máxima, você perceberá que a tabela está associada a dois modelos diferentes, que estão fornecendo informações para vários relatórios.

Agora, com cada clique com o botão direito do mouse na entidade, você tem opções para:

- **Show Direct Dependencies (Mostrar dependências diretas** ): traz o foco para as entidades selecionadas para ver as dependências diretas.
- **Hide This** : removerá a entidade do gráfico.
- **Abrir documento** : abrirá o documento em uma guia diferente.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/demo-lineage-7.png)

Agora que você já sabe como o Lineage funciona, vamos a outro caso de uso em que você deseja examinar uma coluna e entender o impacto se a alterarmos.

Vamos pegar a tabela Benchmark Tower Spend Transform e supor que estamos interessados em uma coluna específica: % Tower Spend. Você pode clicar com o botão direito do mouse na coluna e clicar em **Trace Lineage (Rastrear linhagem) para essa coluna**.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/demo-lineage-8.png)

Na dependência downstream, fica claro que essa coluna de métrica está associada à tabela e ao relatório conhecido como Resumo de Benchmarking. Ao aumentar a profundidade para o máximo, vemos o seguinte:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/demo-lineage-9.png)

Portanto, essa visualização nos fornece informações sobre todos os relatórios e tabelas aos quais a coluna está associada. Você também pode querer ver de quais entidades a coluna dele depende (upstream) e pode alternar para "The focused entity depends on" no painel direito. De modo geral, isso o ajudará a identificar o impacto para se livrar dessa coluna.

## Linhagem por meio de um relatório

Esse é outro caso de uso da linhagem. Navegue até **Relatórios**, selecione **Vendor Insights Spends without POs**, clique com o botão direito do mouse e escolha **Trace Lineage for this document**. O gráfico de linhagem aparece como mostrado. Agora, alterne os subtipos e aumente a profundidade para ver que há mais tabelas e relacionamentos, e você pode ver a tabela de contas a pagar e o conjunto de dados mestre, com alguns relatórios associados a eles.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/demo-lineage-10.png)

Se você se aprofundar ainda mais, verá que há mais tabelas e relacionamentos. O plano de contas está alimentando o pedido de compra, devido à conta que está associada ao pedido de compra. O mapeamento organizacional provavelmente se deve aos centros de custo e às responsabilidades organizacionais associadas a essa tabela e, por fim, aos relatórios. Novamente, você pode navegar pelas tabelas, por uma coluna, por uma métrica calculada ou por um relatório.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/demo-lineage-11.png)
