---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Preencha a guia Dados de custo"
breadcrumb: []
source_path: "it-benchmarking/configuration/interactive-benchmarking/cost-data.html"
images:
  - "resources/images/it_benchmarking_images/interactive-1.jpg"
  - "resources/images/it_benchmarking_images/interactive-10.jpg"
  - "resources/images/it_benchmarking_images/interactive-11.jpg"
  - "resources/images/it_benchmarking_images/interactive-2.jpg"
  - "resources/images/it_benchmarking_images/interactive-3.jpg"
  - "resources/images/it_benchmarking_images/interactive-4.jpg"
  - "resources/images/it_benchmarking_images/interactive-5.jpg"
  - "resources/images/it_benchmarking_images/interactive-6.jpg"
  - "resources/images/it_benchmarking_images/interactive-7.jpg"
  - "resources/images/it_benchmarking_images/interactive-8.jpg"
  - "resources/images/it_benchmarking_images/interactive-9.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Preencha a guia Dados de custo

A guia Cost Data (Dados de custo) destina-se à entrada manual de informações do modelo Cost Transparency (Transparência de custos).

Há 3 seções na guia Dados de custo:

- Dados anuais de custos de TI
- Dados do pool de custos anuais
- Dados anuais das torres/subtorres de recursos de TI

**Dados anuais de custos de TI**

Benchmarking calcula valores com base na métrica de custo anual. Para obter detalhes adicionais, consulte a própria fórmula da métrica encontrada na guia Métricas. A fórmula calcula os 12 meses anteriores de rolagem. Ao inserir dados manualmente no Interactive Benchmarking, selecione o mês após o mês final que representa o fim do período anual para as comparações desejadas.

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-1.jpg)

Por exemplo, selecionar Jan FY17 exibirá o valor do mês de janeiro anterior FY16-Dec FY16. A seleção de junho do ano fiscal de 17 exibirá o valor anual do mês de junho anterior FY16-MayFY17.

Em seguida, filtre por "anual" na pesquisa de métricas. Selecione **Annual Cost (Custo anual** ) e, em seguida, selecione **Cost Source (Fonte de custo** ) no menu Properties (Propriedades), conforme mostrado abaixo na Fig. 1.

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-2.jpg)

(Fig. 1)

Após selecionar a **fonte de custo**, confirme a data e anote o total da coluna de custo anual (Fig. 2) e insira esse valor na entrada Annual Cost (Custo anual) no site Interactive Benchmarking (Fig. 3):

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-3.jpg)

(Fig. 2)

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-4.jpg)

(Fig. 3)

Repita esse processo para a depreciação anual selecionando a métrica de **custo anual** e o objeto **do Ledger de ativos fixos**. Copie o total da coluna **Custo anual** do modelo Transparência de custos para o campo **Depreciação anual** no site interativo Benchmarking.

Por fim, repita esse processo para o Annual CapEx selecionando a métrica **Annual CapEx** no modelo Cost Transparency, o objeto **Cost Source** na seção Properties e anotando o total do Annual CapEx.

**Dados do pool de custos anuais**

Os valores do pool de custos também estão disponíveis na mesma guia Métricas na Transparência de custos. Confirme se a métrica **Custo anual** está selecionada e se **a Fonte de custo** está selecionada nas Propriedades. Em seguida, clique com o botão direito do mouse e exiba/oculte as colunas para mostrar a coluna Pool de custos dos dados mestre de origem de custos (consulte a Fig. 4).

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-5.jpg)

(Fig. 4)

Com a coluna Pool de custos visível, filtre por cada Pool de custos e observe o total da coluna **Custo anual**. Copie esse valor para o site interativo Benchmarking.

Por exemplo, para Hardware, filtre por Hardware e copie o total da coluna Custo anual da Transparência de custos para o site interativo Benchmarking (Fig. 5).

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-6.jpg)

(Fig. 5)

Continue esse processo para cada pool de custos ATUM ™.

**Dados anuais das torres/subtorres de recursos de TI**

Esse processo é idêntico ao do Pool de custos, mas, em vez de selecionar Custo anual na Origem de custos e trazer a coluna Pool de custos, selecione o objeto **Torre de recursos de TI** e selecione as colunas **Torre** e **Subtorre**.

Alterne para o modo Studio e navegue até a guia **Metrics (Métricas** ). Selecione a métrica de **custo anual**. Em seguida, selecione o objeto **IT** Resource Tower para examinar o custo de cada IT Resource Tower e Sub-Towers (consulte a Fig. 6).

![img5](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-7.jpg)

(Fig. 6)

Nessa tela, clique com o botão direito do mouse e selecione **Show/Hide Columns** (veja a Fig. 7).

![img4](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-8.jpg)

(Fig. 7)

Selecione as colunas **IT Resource Tower** e **Sub Tower** na caixa de diálogo e clique em OK (veja a Fig. 8).

![img3](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-9.jpg)

(Fig. 8)

Depois de selecionar as colunas, filtre a combinação de **Torre de Recursos de TI** e **Subtorre** para encontrar o Custo Anual (veja a Fig. 9).

![img2](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-10.jpg)

(Fig. 9)

Copie o valor na tela de entrada de dados do benchmark interativo (consulte a Fig. 10).

![img1](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-11.jpg)

(Fig. 10)

Conclua esse processo para cada Torre e Subtorre de recursos de TI filtrando cada valor respectivo na guia Métrica de transparência de custos.
