---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Visão geral do relatório - Qualidade da marcação"
breadcrumb:
  - "Costing Standard"
  - "Relatório detalhado"
  - "Layouts da versão anterior"
  - "Relatórios na nuvem"
source_path: "cost-transparency/reports-v104/taggingquality.html"
images:
  - "resources/images/ct_images/8091_1.png"
  - "resources/images/ct_images/8091_10.png"
  - "resources/images/ct_images/8091_11.png"
  - "resources/images/ct_images/8091_12.png"
  - "resources/images/ct_images/8091_2.png"
  - "resources/images/ct_images/8091_3.png"
  - "resources/images/ct_images/8091_4.png"
  - "resources/images/ct_images/8091_5.png"
  - "resources/images/ct_images/8091_6.png"
  - "resources/images/ct_images/8091_7.png"
  - "resources/images/ct_images/8091_8.png"
  - "resources/images/ct_images/8091_9.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Visão geral do relatório - Qualidade da marcação

## Visão geral do relatório - Qualidade da marcação

Observação: Aplica-se a: Apptio Costing Standard ou Apptio Cloud Cost Management em execução em TBM Studio v12.3.3 ou posterior.

O relatório de nuvem pública em Apptio 's Costing Standard inclui uma visão da qualidade da marcação da nuvem. Em termos gerais, a qualidade da marcação na nuvem pública ajuda você das seguintes maneiras:

- Use os relatórios de qualidade de marcação para descobrir omissões de marcação e valores inválidos
- Localizar o número de tags vazias ou inválidas pelos consumidores de serviços em nuvem
- Filtrar por consumidores específicos e exportar linhas com valores em branco ou inválidos para enviar a esses consumidores

A análise da qualidade da marcação é baseada em atributos no site Apptio que são mapeados a partir de tags na fatura da nuvem. Certifique-se de mapear as tags corretamente para utilizar totalmente esse relatório.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_1.png)

## Totalidade

- A guia **Completude** permite que o usuário identifique o número de registros que não têm valores em campos específicos.
- O gráfico na parte superior mostra a contagem de registros em branco pelo campo aplicável. Esse gráfico também pode ser manipulado para mostrar qualquer campo específico e o número de registros em branco por mês.
- A tabela de detalhes oferece uma visão mais orientada por dados e mostra o nome da coluna específica e o número de campos nessa coluna que estão com valores ausentes.
- O último componente da guia é o próprio conjunto de dados real. O usuário pode usar as segmentações **Show Blanks** para manipular os dados e visualizar os campos em branco em relação ao conjunto de dados.
- Há também seletores ao lado de **Show Additional Details** que permitem que o usuário manipule os dados e visualize apenas colunas específicas, se necessário.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_2.png)
- Se você clicar em **Exibir** na coluna Tx, poderá ver os **Detalhes de qualidade de marcação** para o item de linha aplicável.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_3.png)

## Validade

- A guia **Validade** permite que o usuário identifique o número de registros que têm valores inválidos em campos específicos.
- O gráfico na parte superior mostra a contagem de registros inválidos pelo campo aplicável. Esse gráfico também pode ser manipulado para mostrar qualquer campo específico e o número de registros inválidos por mês.
- A tabela de detalhes lhe dá uma visão mais orientada por dados e mostra o nome da coluna específica e o número de campos nessa coluna que têm valores inválidos.
- O último componente da guia é o próprio conjunto de dados real. O usuário pode usar os slicers **Show Invalid** para manipular os dados e visualizar os campos inválidos em relação ao conjunto de dados.
- Há também seletores ao lado de **Show Additional Details** que permitem que o usuário manipule os dados e visualize apenas colunas específicas, se necessário.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_4.png)
- Se você clicar em **Exibir** na coluna Tx, poderá ver os **Detalhes de qualidade de marcação** para o item de linha aplicável.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_5.png)

## Configurar relatório de validade

Embora a guia **Completude** indique automaticamente os valores em branco na fatura, a guia **Validade** precisa ser configurada com dados de comparação dos valores esperados com base na marcação usada. Isso é feito anexando dados à tabela **Cloud Validity**. Essa tabela é então usada como referência para determinar quais campos da fatura de nuvem são valores válidos. Você pode configurar isso fazendo o seguinte:

- Entre em **TBM Studio** e abra a tabela **Cloud Validity**. Selecione a etapa **Table (Tabela** ) e clique em **Export (Exportar** ) e, em seguida, em **Excel**.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_6.png)
- Exclua a coluna **Valid** da planilha. Use esta planilha como modelo para seus dados de validade. Preencha a planilha com os dados apropriados, conforme correlacionados aos campos da fatura (por exemplo, coloque " Amazon Web Services, Inc." na coluna Provider (Provedor) e preencha as colunas restantes à medida que forem mapeadas para Apptio a partir da fatura da nuvem).

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_7.png)
- Depois que os dados forem preenchidos, salve a planilha.
- Em Apptio, clique em **New (Novo** ) e selecione **Table (Tabela** ). Digite o nome e a categoria da tabela e clique em **OK**.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_8.png)
- Selecione **File Upload**. Carregue a planilha que você criou no Excel. Isso será usado como referência para valores válidos. Após o upload, se for necessária uma configuração adicional, você poderá fazer alterações na etapa **de importação** ou adicionar outras etapas (fórmula, filtro etc.) para configurar conforme necessário.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_9.png)
- Selecione **Cloud Validity** novamente e clique em **Check Out**. Selecione a etapa **Append**. Anexe a tabela que você acabou de criar e mapeie as colunas para o **Cloud Validity** de acordo com a marcação da sua conta.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_10.png)

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_11.png)
- Clique em **Check In** e faça o check-in dos dois documentos.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_12.png)

A tabela **Cloud Validity** agora será usada para comparar esses campos com os campos na fatura da nuvem. Todos os valores inconsistentes com essa tabela serão registrados como um valor inválido na guia **Validity (Validade** ) do relatório **Tagging Quality (Qualidade da marcação)**.
