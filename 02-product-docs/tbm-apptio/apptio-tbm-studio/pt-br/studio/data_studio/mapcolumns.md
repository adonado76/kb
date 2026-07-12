---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Colunas do mapa"
breadcrumb: []
source_path: "studio/data_studio/mapcolumns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Colunas do mapa

**Aplica-se a** : TBM Studio 12.7 e posterior. Os aplicativos disponíveis em TBM Studio exigem o alinhamento dos dados aos conjuntos de dados mestre. Uma nova etapa do pipeline, **Map Columns**, está disponível para todos os clientes com a versão 12.7.

**As colunas de mapa** podem ser adicionadas a uma tabela de check-out que não sejam os próprios conjuntos de dados mestre. Depois de adicionar a etapa, um destino é solicitado. Qualquer informação mapeada é adicionada à tabela de destino em uma nova etapa "Mapped Tables" (Tabelas mapeadas) nos conjuntos de dados mestre. Os conjuntos de dados mestre são os únicos destinos válidos.

Dica: Depois de carregar uma tabela de dados de origem e transformá-la, se necessário, você pode mapeá-la para uma tabela de dados mestre. Se estiver executando o site TBM Studio 12.7 ou posterior, o site Apptio recomenda o uso do recurso Map Columns (Mapear colunas), descrito aqui, para mapear dados (exceto para o Cloud). Se o Map Columns não for uma opção para você, consulte os métodos alternativos descritos aqui: [Mapear dados para uma tabela de dados mestre](../../cost-transparency/configuration/maptomaster.html "(Abre em uma nova guia ou janela)") e [Mapeamento na nuvem](../../cost-transparency/configuration/cloudmapping.html "(Abre em uma nova guia ou janela)").

**Pré-requisitos**

- Os componentes devem ser instalados para serem mapeados para seus conjuntos de dados mestre.
- Os conjuntos de dados mestre devem estar na versão de conteúdo 104 ou posterior.

## Adicione a etapa do pipeline Map Columns e escolha um destino

1. Criar ou fazer check-out de uma tabela e adicionar dados a ela. Além disso, você pode aplicar etapas transformadoras do pipeline, como Date Partition.
2. Passe o mouse sobre as etapas do pipeline e clique em **+** para adicionar uma nova etapa do pipeline. **Map Columns** fica disponível, a menos que haja uma etapa Model adicionada.![](../../resources/images/studio_images/studioimages/studio_add%20step_map%20columns.png)

   Observação: Se a tabela tiver sido revertida e o upload de dados não, a etapa não estará disponível até que você adicione qualquer outra etapa e, em seguida, adicione Map Columns.
3. Clique em **Map Columns (Mapear colunas** ) e selecione um destino. Se você não vir o conjunto de dados mestre que estava esperando, vá para **Componentes** e instale o componente necessário.![](../../resources/images/studio_images/studioimages/studio_map%20columns_destination.png)

## Mapear para uma coluna do conjunto de dados mestre

1. Revise as Colunas de destino. Essas são as colunas dos conjuntos de dados mestre que podem ser mapeadas. Alguns podem já estar mapeados porque um cabeçalho de coluna em sua tabela corresponde a um valor esperado no destino.
2. Selecione **Selecionar fonte** na coluna Fonte ou, para alterar um mapeamento, selecione um dos outros valores nessa coluna.![](../../resources/images/studio_images/studioimages/studio_map%20columns_cost%20center.png)
3. Selecione um dos nomes de coluna na lista suspensa. Essa lista mostra todas as colunas da tabela com um tipo de coluna correspondente ao destino.

   Observação: A tabela de visualização a seguir não será atualizada até que a alteração seja salva.

   Dica: se você não vir as colunas desejadas na lista suspensa, talvez elas não sejam do tipo de correspondência correto para o destino. Vá para a etapa Importar e altere a opção Type Override conforme necessário. Se a coluna esperada tiver sido criada no pipeline de transformação, use ou altere a etapa Fórmulas.
4. Para inserir uma cadeia de caracteres ou um número para todas as linhas, selecione **Inserir um valor fixo para todas as linhas**. Como resultado, cada linha da tabela mostra o mesmo valor para essa coluna. Essa opção não avalia fórmulas. Para usar uma fórmula, adicione a etapa **Fórmulas** e, em seguida, mapeie a coluna adicional resultante.
5. Insira o valor e clique em **OK**. Agora você mapeou duas colunas adicionais para o conjunto de dados mestre escolhendo uma coluna da sua tabela e inserindo um valor.

## Adicionar uma coluna personalizada ao conjunto de dados mestre

1. Para adicionar uma coluna que não existe no conjunto de dados mestre, clique em **Add Custom Column (Adicionar coluna personalizada** ). Essas adições serão mantidas entre as atualizações sem nenhuma ação especial.
2. Digite o nome da coluna que você deseja adicionar e, em seguida, escolha o tipo. Selecione uma fonte para essa coluna, seja escolhendo outra coluna na tabela ou um valor fixo.
3. Clique em **OK**. As colunas adicionadas são sempre opcionais. Salve a tabela para ver a coluna na visualização.

## Usar Join para mapear colunas

1. Use a etapa **Join** para mapear colunas em que outro conjunto de dados tenha informações adicionais que possam ser combinadas com os dados da tabela mapeada. Para usar esse recurso, clique em **Join**.
2. Clique em **Add Link** e, em seguida, escolha a tabela à qual deseja se unir ou arraste a tabela da seção **Tables (Tabelas** ) do **Project Explorer** e desenhe uma linha até ela. **From Column** e **To Column** representam uma relação de chave em que se espera que os valores correspondam.![](../../resources/images/studio_images/studioimages/studio_map%20columns_add%20link.png)
3. Selecione as colunas apropriadas e clique em **OK**.

   Observação: A visualização não será atualizada até que você clique em **Salvar**.
4. Clique em **Map Columns (Mapear colunas** ) e selecione a coluna que deseja mapear. As colunas recém-mapeadas aparecem na lista suspensa com o nome da tabela, "." e, em seguida, o nome da coluna. As colunas também aparecem na guia **Colunas não mapeadas** :![](../../resources/images/studio_images/studioimages/studio_map%20columns_chart%20of%20accounts%20master%20data.png)
5. Selecione a coluna desejada e, em seguida, salve para atualizar a tabela de visualização.

## Navegar nas colunas do mapa

1. No canto superior direito, use **Search All Fields (Pesquisar todos os campos** ) para pesquisar a coluna Destination (Destino), a coluna Source (Origem) e a coluna Description (Descrição).
2. Clique em cada cabeçalho de coluna para classificar a ordem de cada coluna ou inverter a ordem de classificação de cada coluna.
3. A tabela de visualização mostra os resultados do mapeamento de colunas quando pelo menos uma coluna é mapeada ou a tabela não mapeada se nada for mapeado. Quando algumas colunas, mas não todas, são mapeadas, a guia padrão mostra o que foi mapeado, e "Colunas não mapeadas" está disponível nas guias.

## Visualizar tabelas mapeadas em conjuntos de dados mestre

- Para visualizar todas as tabelas que estão enviando dados para o conjunto de dados mestre, navegue até o conjunto de dados mestre apropriado e selecione **Tabelas mapeadas**.![](../../resources/images/studio_images/studioimages/studio_cost%20source%20master%20data_mapped%20tables.png)
- Na tabela Preview (Visualização), a coluna **Source Table (Tabela de origem)** identifica de qual tabela a linha veio. Use o **filtro Autosearch** para ver todas as linhas de uma fonte.![](../../resources/images/studio_images/studioimages/studio_mapped%20tables_source%20table.png)
- Use a tabela em Mapped Tables para navegar até a tabela de origem e mostrar as seguintes informações:
  - Nome da tabela que contém a etapa correspondente de Map Columns.
  - A última vez que a tabela foi alterada.
  - A contagem de linhas da tabela mapeada.
  - O número de colunas marcadas como Obrigatórias que foram adicionadas.
  - O número de colunas no conjunto de dados mestre que foram mapeadas em geral.
  - O número de colunas que foram adicionadas ao conjunto de dados mestre.
  - A descrição da tabela adicionada ao conjunto de dados mestre. Adicionar uma descrição às suas tabelas garantirá uma manutenção mais fácil e é altamente recomendado para qualquer tabela a ser mapeada para um conjunto de dados mestre com mais de uma tabela mapeada.

## Atualizações de aplicativos e colunas de mapas

Quando um novo conteúdo de aplicativo é lançado, você pode atualizar os projetos para receber as alterações. Para obter mais informações, consulte [Sobre o upgrade da transparência de custos](../../cost-transparency/configuration%20-%20additional/aboutupgradingct.htm "(Abre em uma nova guia ou janela)").

O Map Columns sempre mostra informações para a mesma versão de conteúdo do aplicativo que o conjunto de dados mestre. Se o componente tiver sido atualizado, mas o conjunto de dados mestre for personalizado, não haverá alterações. Pequenas atualizações, como descrições de colunas, podem ocorrer a qualquer momento.

Para atualizar um conjunto de dados mestre, vá para Componentes e selecione o Componente que contém esse conjunto de dados mestre. Role até **Elementos personalizados**. Na lista, localize o nome do conjunto de dados mestre e clique na **seta** à esquerda.

![](../../resources/images/studio_images/studioimages/studio_comp_app%20dev.png)
