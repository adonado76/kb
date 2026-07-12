---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Anexar dados"
breadcrumb: []
source_path: "studio/data_studio/append-data.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu001.png"
  - "resources/images/studio_images/studioimages/studio/stu005.png"
  - "resources/images/studio_images/studioimages/studio/stu006.png"
  - "resources/images/studio_images/studioimages/studio/stu007.png"
  - "resources/images/studio_images/studioimages/studio/stu008.png"
  - "resources/images/studio_images/studioimages/studio/stu010.png"
  - "resources/images/studio_images/studioimages/studio/stu011.png"
  - "resources/images/studio_images/studioimages/studio/stu511.png"
  - "resources/images/studio_images/studioimages/studio/stu512.png"
  - "resources/images/studio_images/studioimages/studio/stu660.png"
  - "resources/images/studio_images/studioimages/studio/stu661.png"
  - "resources/images/studio_images/studioimages/studio/stu662.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Anexar dados

**Aplica-se a** : TBM Studio 12.0 e posterior

Você pode adicionar dados de uma ou mais tabelas de origem a uma tabela de destino usando a etapa de transformação de dados **Append**. A etapa **Append** sempre adiciona linhas da tabela de origem à tabela de destino.

Quando você anexa dados:

- Quando os dados são anexados à tabela de destino, os dados anexados são adicionados como novas linhas na tabela de destino. As linhas das tabelas de origem e de destino nunca são combinadas. Para combinar linhas, use uma etapa de transformação de dados **Join**.
- As colunas em uma tabela de origem podem ser mapeadas para colunas existentes na tabela de destino.
- As colunas em uma tabela de origem podem ser adicionadas à tabela de destino como novas colunas.
- Os acréscimos se aplicam à versão atual da tabela. Quando um período fora do intervalo de datas da tabela versionada é selecionado, o acréscimo é bloqueado.

Se quiser mesclar dados em tabelas sem criar novas linhas, você deve usar uma etapa [Join](join-data.htm "(Abre em uma nova guia ou janela)"). Além disso, você pode criar novas colunas na tabela de destino e extrair dados das tabelas de origem usando a função **Lookup**. Para obter mais informações, consulte [as funções Lookup e Lookup\_Wild](../formulas-and-functions/functions/lookupandlookup_wild.htm "(Abre em uma nova guia ou janela)").

## Exemplo

Suponha que você tenha as duas tabelas a seguir com colunas correspondentes:

Tabela 1

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu660.png)

Tabela 2

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu661.png)

Se você anexar a Tabela 2 à Tabela 1, obterá a seguinte tabela:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu662.png)

As etapas gerais para executar um append estão descritas abaixo:

- Confira a tabela de alvos.
- Adicione a etapa **Append** à transformação de dados.
- Selecione uma tabela de origem.
- Mapear colunas na tabela de origem para colunas na tabela de destino ou usar fórmulas.
- Opcionalmente, adicione colunas da tabela de origem.

## Confira a tabela de alvos

A tabela de destino aceitará dados de uma ou mais tabelas de origem. A tabela de destino deve ser uma tabela de transformação.

Para verificar o conjunto de dados de destino:

1. Na seção **Tabelas** do **Project Explorer**, clique na tabela de destino.
2. Adicione a etapa **Append** ao pipeline de transformação.

## Selecione um conjunto de dados de origem

1. Clique em **Append Data Source (Anexar fonte de dados** ).

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu511.png)
2. Clique no nome da tabela de origem e, em seguida, clique em **Next**. A caixa de diálogo **Append** é exibida conforme mostrado na imagem a seguir:

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu005.png)

## Colunas do mapa

Os principais elementos da caixa de diálogo de mapeamento mostrados na imagem anterior são descritos a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu006.png)

A coluna à esquerda exibe as colunas de destino. Os ícones e as cores indicam o tipo de coluna: chave, rótulo, data, numérica. Um asterisco indica que a coluna foi marcada como obrigatória. Nesse contexto, *necessário* significa que a coluna é necessária para iluminar totalmente os modelos e relatórios baseados nos dados. No entanto, você pode fazer o append sem mapear a coluna.

Uma marca de seleção verde indica que a coluna foi mapeada.

Você pode filtrar a coluna à esquerda selecionando um tipo de coluna na legenda no canto superior direito da caixa de diálogo. Por padrão, todas as colunas são exibidas.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu007.png)

A coluna à direita exibe colunas da tabela de origem. Se um nome de coluna na tabela de origem corresponder a um nome de coluna na tabela de destino, o nome da coluna de destino será exibido. A correspondência não diferencia maiúsculas de minúsculas.

A coluna à direita contém listas suspensas para selecionar colunas de origem. As colunas exibidas na lista são baseadas no tipo de coluna de destino. Por exemplo, se a lista for para uma coluna-chave, somente as colunas-chave no conjunto de dados de origem serão listadas:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu008.png)

É possível inserir fórmulas nos campos suspensos, começando com =. Talvez você queira usar uma fórmula se a coluna que deseja mapear na tabela de origem não corresponder ao tipo de coluna na tabela de destino. Se você inserir uma coluna com um nome que inclua caracteres especiais, coloque o nome da coluna entre colchetes { }.

Para ajudá-lo a combinar colunas, as tabelas de destino e de origem são exibidas na parte inferior da caixa de diálogo em guias separadas:

![](../../resources/images/studio_images/studioimages/studio_append%20data_acme%20gl.png)

Para mapear uma coluna:

1. Se houver muitas colunas na tabela e você quiser limitar as colunas exibidas, selecione um tipo de coluna na chave no canto superior direito da caixa de diálogo.
2. Abra a lista suspensa na coluna à direita e selecione uma fonte column.If a coluna que você deseja mapear na tabela de origem não corresponde ao tipo de coluna na tabela de destino, insira uma fórmula.

   **Exemplos** :`={column name}`

   ```
   =If({Cost
                   Pool} IN ("FTE Labor","Depreciation"),"Fixed","Variable")
   ```

   ```
   =Lookup(ACCOUNT,Chart of Accounts,ACCOUNT,Cost
                 Pool)
   ```

   Você pode mapear colunas-chave para colunas de rótulos e vice-versa.

Para adicionar uma ou mais colunas de origem à tabela de destino:

1. Clique no link **Selecionar coluna de origem adicional** abaixo das colunas de destino e origem.
2. Na caixa de diálogo **Select Columns (Selecionar colunas** ), selecione as colunas que deseja adicionar e clique em **OK**.

## Revisar fontes de dados

Depois que você anexar um ou mais conjuntos de dados de origem a uma tabela de destino, eles serão listados no painel de etapas. O painel exibe informações sobre os conjuntos de dados anexados, incluindo o número de colunas necessárias no conjunto de dados de origem que foram mapeadas para o conjunto de dados de destino. Se não houver colunas obrigatórias, a coluna **Colunas obrigatórias** não será exibida. Na imagem abaixo, não há colunas obrigatórias:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu512.png)

Há várias ações que você pode executar no painel:

- **Edit** - Editar o mapeamento de acréscimo
- **Remove** - Remove o conjunto de dados anexado
- **Anexar fonte de dados** - Anexar outra fonte de dados

## Anexar exemplo 1

Suponha que você tenha as duas tabelas a seguir com colunas correspondentes:

Tabela 1

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu660.png)

Tabela 2

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu661.png)

Se você anexar a Tabela 2 à Tabela 1, obterá a seguinte tabela:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu662.png)

## Anexar exemplo 2

Suponha que você tenha as duas tabelas mostradas abaixo. Você deseja combiná-las em uma única terceira tabela chamada **Machine CMDB**, preservando a coluna **RAM** no conjunto de dados Virtual Machines. Além disso, você deseja mapear a coluna **Virtual ID** para a coluna **Asset Tag**.

Máquinas virtuais

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu010.png)

Máquinas físicas

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu001.png)

Quando terminar, o conjunto de dados anexado deverá se parecer com o seguinte:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu011.png)

Para realizar a anexação:

1. Faça uma cópia da tabela **Virtual Machines** para criar a tabela **Machine CMDB**.
2. Confira a tabela **Machine CMDB** e adicione uma etapa de transformação **Edit Columns (Editar colunas** ).
3. Defina todas as colunas como **Label**, exceto a coluna **Hostname**. A coluna **Hostname** deve ser **Key**.
4. Adicione uma etapa **Append** à transformação após a etapa **Edit Columns**.
5. Clique em **Append Data Source**, clique no conjunto de dados Physical Machines e clique em **Next**. Observe que as colunas **Hostname** e **Virtual Type** são mapeadas automaticamente.
6. A coluna **Asset Tag** na tabela **Physical Machines** é *numérica*, mas o campo **Virtual ID** no conjunto de dados **Machine CMDB** é um *rótulo*. **A Asset Tag** não será listada na lista suspensa porque é um tipo de coluna diferente do campo **Virtual ID**. Para mapear a coluna **Asset Tag** para a coluna **Virtual ID** no conjunto de dados **Machine CMDB**, adicione o prefixo pm- inserindo a seguinte fórmula no campo da lista suspensa: `="pm-"&{Asset Tag}`
7. Clique em **Salvar**.
