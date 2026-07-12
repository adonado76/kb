---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar uma tabela a partir de uma tabela editável"
breadcrumb: []
source_path: "studio/data_studio/create-table-from-et.html"
images:
  - "resources/images/studio_images/aftr-chkin.jpg"
  - "resources/images/studio_images/df-disable.jpg"
  - "resources/images/studio_images/df-enable.jpg"
  - "resources/images/studio_images/et-table.jpg"
  - "resources/images/studio_images/et-tbl1.jpg"
  - "resources/images/studio_images/et-tbl2.jpg"
  - "resources/images/studio_images/et-upload.png"
  - "resources/images/studio_images/ps-ddf.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar uma tabela a partir de uma tabela editável

Você pode criar uma tabela a partir de uma tabela editável existente usando as etapas a seguir:

Em TBM Studio, acesse a guia **Início** >� **Novo** menu suspenso > selecione **Tabela**.

Na janela pop-up Create Table (Criar tabela), digite um nome para a tabela e selecione Ok.

Selecione o bloco **Tabela editável**.

![Tabela editável](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-table.jpg)

Selecione um valor no menu suspenso Tabela editável.

![Menu suspenso Tabela editável](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-tbl2.jpg)

Escolha o método de upload e selecione a programação de publicação recorrente

![programação de publicação recorrente](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-tbl1.jpg)

Salve e faça o check-in da mesa.

## Desativar o fluxo de dados na transformação enriquecida

Se você configurar uma tabela editável enriquecida e depois alterar as informações na tabela de transformação de origem no estágio de desenvolvimento, os dados não fluirão automaticamente para a tabela editável enriquecida. Somente quando a tabela for publicada, os dados fluirão da tabela de origem para a tabela editável enriquecida.

Para ativar esse recurso, acesse TBM Studio > Project Settings e selecione a opção **Disable Data Flow in Enriched Transform**.

![Desativar o fluxo de dados](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ps-ddf.jpg)

Se o recurso estiver desativado, o fluxo de dados será o mostrado abaixo.

![Upload de tabelas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-disable.jpg)

Se o recurso estiver ativado, o fluxo de dados será o mostrado abaixo.

![Recurso ativado](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-enable.jpg)

Depois de verificar as alterações, os dados serão exibidos conforme mostrado.

![Dados](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/aftr-chkin.jpg)

Para o fluxo atual da tabela editável enriquecida, considere três tabelas envolvidas:

- Table\_1 - tabela de transformação de fontes
- EET\_Table\_2 - tabela editável enriquecida criada a partir de Table\_1
- Trf\_Table\_3 - tabela de transformação criada em ET\_Table\_2.

Os valores mostrados em Trf\_Table\_3 são provenientes de duas tabelas:

- Table\_1 tem as linhas de origem originais, e
- EET\_Table\_2 tem os registros de sobreposição que modificam as células nas linhas de origem originais de Table\_1, e podem incluir novas linhas adicionadas. (Ele não pode excluir nenhuma linha existente em Table\_1 ).

Quando você fizer upload de um novo conjunto de dados para Table\_1, as alterações serão vistas imediatamente em EET\_Table\_2 e Trf\_Table\_3, mesmo que você NÃO tenha publicado alterações de EET\_Table\_2 para Trf\_Table\_3. EET\_Table\_2 tem apenas os registros de sobreposição para as linhas de origem de Table\_1.

Esse novo recurso lhe dá a opção de controlar qual comportamento você prefere e é controlado por meio de uma nova configuração de projeto: "Disable Data Flow in Enriched Transforms" (Desativar fluxo de dados em transformações enriquecidas)

- Desativado (padrão) - a tabela de transformação receberá atualizações da tabela de origem ( Table\_1 ) imediatamente (comportamento atual)
- Ativado - a tabela de transformação só verá as atualizações da tabela de origem ( Table\_1 ) quando o upload da tabela for "registrado"

Observação: as tabelas editáveis agora são específicas da filial, permitindo que o trabalho em cada filial não afete o tronco principal. Ou seja, a criação de uma ramificação terá sua própria cópia das tabelas editáveis e as modificações no tronco não serão visíveis na ramificação.

## Upload e publicação de dados em uma tabela de transformação

O recurso Transform Table permite que os administradores façam upload e publiquem dados de uma tabela editável no pipeline de dados.

**Correção de erros em alterações de tabelas editáveis**

Você pode corrigir erros em alterações de tabelas editáveis que foram publicadas em um período anterior. Suponha que você tenha publicado alterações em uma tabela editável em janeiro, mas depois descobriu que havia erros nos dados. Você pode fazer o download dos dados da Transform Table para janeiro, fazer as correções necessárias e, em seguida, carregar os dados corrigidos diretamente na Transform Table. Isso corrigirá os erros no modelo de custo e garantirá que os dados sejam precisos e atualizados.

Observação: esse recurso é aplicável somente para ET em branco e não para ET enriquecida

1. Navegue até a etapa do pipeline de dados e selecione a Transform Table para a qual você deseja fazer upload de dados.
2. **Faça o download** dos dados da tabela para um período específico.
3. Faça as alterações necessárias no arquivo baixado. Os dados devem estar no mesmo formato - só podem ser modificados, as linhas/colunas não podem ser excluídas nem adicionadas.
4. **Carregue** os dados corrigidos diretamente na Transform Table para o período específico. Isso substituirá os dados originais e corrigirá os erros no modelo de custo.

![Correção de erros em alterações de tabelas editáveis](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-upload.png)

**Tópico principal:** [Editar configurações do projeto](../../studio/admin/edit-project-settings.html "Aplica-se a: TBM Studio 12.0 e posterior. Algumas configurações estão disponíveis em versões posteriores do TBM Studio, conforme indicado abaixo.")

**Tópico principal:** [Carregar dados](../../studio/data_studio/upload-data.html "Aplica-se a: TBM Studio 12.0 e posterior")
