---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Analisar e validar ATUM pools de custos"
breadcrumb: []
source_path: "it-benchmarking/start-here/analyze-validate.html"
images:
  - "resources/images/it_benchmarking_images/analyze-validate-1.jpg"
  - "resources/images/it_benchmarking_images/analyze-validate-2.jpg"
  - "resources/images/it_benchmarking_images/analyze-validate-3.jpg"
  - "resources/images/it_benchmarking_images/analyze-validate-4.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Analisar e validar ATUM pools de custos

**Resumo**

Você pode usar o site Benchmarking para analisar e validar a distribuição do pool de custos para uma fonte de custos alinhada ao ATUM ou como uma análise independente no benchmarking interativo.

**Além do benchmarking**

O produto Benchmarking pode ser aproveitado de várias maneiras distintas, começando com uma introdução ao Apptio, passando pelo processo de implementação e continuando nas operações diárias, como ajudar a defender seu orçamento de TI. Este artigo se concentra no aspecto de validação do pool de custos do ATUM ao usar o Interactive Benchmarking.

**Uso do site interativo Benchmarking para validação do pool de custos**

É possível usar o site interativo Benchmarking para apoiar a confirmação das alocações de pool de custos. Ao comparar o mapeamento de contas de uma organização com os pools de custos em relação ao Apptio Community Data (ACD), um TBMA pode demonstrar que os mapeamentos estão bem alinhados com o ATUM ou identificar áreas em que as alocações do modelo talvez precisem ser aprimoradas.

**Validação do pool de custos**

Usando um relatório de pool de custos do Interactive Benchmarking (veja a imagem abaixo), alguns pools de custos neste exemplo estão acima ou abaixo do retângulo colorido. O retângulo representa do primeiro ao terceiro quartil, compreendendo 50% dos dados. Embora o valor destacado, hardware, não esteja fora do intervalo (um indicador claro de que o mapeamento provavelmente está errado), ele ainda está na faixa mais alta de todos os valores.

![img4](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/analyze-validate-1.jpg)

Com base no valor elevado em comparação com o intervalo do pool de custos de hardware, a próxima etapa é navegar até o relatório Cost Transparency Cost Pool Analysis. O subelemento Details é selecionado (veja a imagem abaixo) para visualizar o pool de custos de hardware para análise. Observe que "Depreciação e amortização" e "Suporte e manutenção" são as duas áreas com o maior gasto.

![img4](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/analyze-validate-2.jpg)

O usuário, ao investigar esses custos, pode selecionar Hardware no relatório Summary by Cost Pool (Resumo por pool de custos) (veja a imagem abaixo) para estudar os custos de itens de linha. O usuário pode estudar os detalhes para saber se há um mapeamento impreciso do pool de custos ou se os custos estão simplesmente acima da faixa.

![img4](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/analyze-validate-3.jpg)

O usuário pode selecionar o item de linha para o detalhe do razão geral na visualização da transação OpEx. Em seguida, o usuário pode observar que há uma cobrança significativa por depreciação. Isso completa a análise sobre o motivo pelo qual o valor é mais alto. O valor mais alto não está relacionado a um problema de mapeamento, mas sim aos custos reais que são mais altos do que a maioria. A etapa seguinte, que está fora do escopo deste artigo, é aproveitar outros relatórios de transparência de custos para completar o quadro de custos.

![img4](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/analyze-validate-4.jpg)

**Conclusão**

Usando o produto Benchmarking , o usuário pode empregar os recursos do Interactive Benchmarking para validação do mapeamento do pool de custos do Cost Transparency. Ao comparar os valores mapeados e alocados com o conjunto de Apptio Community Data (ACD), o cliente pode analisar e validar a precisão de seus mapeamentos e examinar mais detalhadamente os detalhes para fornecer evidências de apoio.
