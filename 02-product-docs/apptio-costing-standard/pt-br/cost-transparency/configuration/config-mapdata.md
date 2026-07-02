---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Mapear dados para dados mestres"
breadcrumb:
  - "Costing Standard"
  - "Configuração"
source_path: "cost-transparency/configuration/config-mapdata.html"
images:
  - "resources/images/studio_images/ad1.png"
  - "resources/images/studio_images/ad6.png"
  - "resources/images/studio_images/map3.png"
  - "resources/images/studio_images/mapcol2.png"
  - "resources/images/studio_images/master2.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mapear dados para dados mestres

Depois de carregar uma tabela de dados de origem e transformá-la, se necessário, você pode mapeá-la para uma tabela de dados mestre. Use as instruções a seguir para mapear dados para uma tabela de dados mestre.

Existem dois métodos disponíveis para mapear dados para conjuntos de dados mestres:

- Colunas do mapa (preferencial)
- Anexar tabelas

**Colunas do mapa**

O método principal (e preferencial) para mapear dados é usar o recurso Map Columns.The O recurso Map Columns destina-se a transformar seu conjunto de dados de origem.

Se os dados forem reutilizados para vários conjuntos de dados mestres, crie uma nova tabela usando a fonte da tabela existente para cada conjunto de dados mestres e, em seguida, adicione colunas de mapeamento.

**Adicione a etapa do pipeline Map Columns e escolha um destino**

1. Crie ou verifique uma tabela e adicione dados à tabela. Além disso, você pode aplicar etapas de pipeline transformadoras, como Partição por data.
2. Passe o cursor sobre as etapas do pipeline e clique **em +** para adicionar uma nova etapa ao pipeline. **As colunas do mapa** ficam disponíveis, a menos que haja uma etapa Modelo adicionada.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/mapcol2.png)

   Observação: se a tabela foi revertida e o upload de dados não, a etapa não estará disponível até que você adicione qualquer outra etapa e, em seguida, adicione Mapear Colunas.
3. Clique em **Colunas do mapa** e selecione um destino. Se você não encontrar o conjunto de dados mestre que esperava, vá para **Componentes** e instale o componente necessário.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/map3.png)

## Mapeie para uma coluna do conjunto de dados mestre

1. Revise as colunas de destino. Estas são as colunas nos conjuntos de dados mestres que podem ser mapeadas. Alguns podem já estar mapeados porque um cabeçalho de coluna na sua tabela corresponde a um valor esperado no destino.
2. Selecione **Escolher fonte** na coluna Fonte ou, para alterar um mapeamento, selecione um dos outros valores nessa coluna.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/master2.png)
3. Selecione um dos nomes das colunas na lista suspensa. Esta lista mostra todas as colunas da tabela com um tipo de coluna correspondente ao destino.

   Observação: a tabela de pré-visualização a seguir não será atualizada até que a alteração seja salva.

   Dica: se você não encontrar as colunas desejadas na lista suspensa, elas podem não ser do tipo compatível com o destino. Vá para a etapa Importar e altere a opção Substituição de tipo conforme necessário. Se a coluna esperada foi criada no pipeline de transformação, use ou altere a etapa Fórmulas.
4. Para inserir uma sequência de caracteres ou um número para todas as linhas, selecione **Insira um valor fixo para todas as linhas**. Como resultado, todas as linhas da tabela mostram o mesmo valor para essa coluna. Esta opção não avalia fórmulas. Para usar uma fórmula, adicione a etapa **Fórmulas** e, em seguida, mapeie a coluna adicional resultante.
5. Insira o valor e clique **em OK**. Agora você mapeou duas colunas adicionais para o conjunto de dados mestre, selecionando uma coluna da sua tabela e inserindo um valor.

**Adicionar uma coluna personalizada ao conjunto de dados mestre**

1. Para adicionar uma coluna que não existe no conjunto de dados mestre, clique em **Adicionar coluna personalizada**. Essas adições serão mantidas entre as atualizações sem nenhuma ação especial.
2. Digite o nome da coluna que deseja adicionar e escolha o tipo. Selecione uma fonte para essa coluna, escolhendo outra coluna na tabela ou um valor fixo.
3. Clique em **OK**. As colunas adicionadas são sempre opcionais. Salve a tabela para ver a coluna na pré-visualização.

**Anexar dados**

Este método é menos preferível porque personaliza o conjunto de dados mestres, o que aumenta o tempo de atualizações para receber novos conteúdos.

1. No **Project Explorer**, clique na tabela de dados mestre desejada.
2. Confira a tabela.
3. No pipeline de transformação, clique na etapa **Anexar**.
4. Clique em **Anexar tabela** na área de detalhes.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ad1.png)
5. Selecione uma tabela de dados de origem e clique em **Avançar.**
6. Mapeie as colunas de origem para as colunas do conjunto de dados mestre usando o seguinte **Adicionar a...** Imagem dos dados mestres.

   Observação: um asterisco (\*) na coluna Dados Mestres indica que o campo é obrigatório para preencher completamente os relatórios relacionados a esse conjunto de dados. O mapeamento parcial é permitido. Se você não tiver todos os dados necessários, poderá mapear um subconjunto dos campos obrigatórios, embora isso possa resultar na perda de dados em um ou mais relatórios.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ad6.png)
7. Clique em Save.
