---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Alocar valor em um modelo"
breadcrumb: []
source_path: "studio/model_studio/allocate-value-in-model.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu573.png"
  - "resources/images/studio_images/studioimages/studio/stu578.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Alocar valor em um modelo

**Aplica-se a** : TBM Studio 12.0 e posterior

Um dos recursos mais avançados do site TBM Studio são os esquemas de alocação usados para modelar o fluxo de dinheiro e outras métricas de uma tabela em um modelo para outras tabelas. Os modelos permitem relacionar despesas, ativos e mão de obra a aplicativos, plataformas e transações. O resultado é um custo detalhado e informações estatísticas para a TI e as unidades de negócios que ela atende.

## Diagrama Sankey

As alocações são exibidas em um diagrama Sankey, como o mostrado na imagem a seguir. A largura das linhas de alocação no diagrama é proporcional ao valor.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu573.png)

## Tabelas e alocações

Em um modelo, uma tabela contém dados associados a um elemento da organização. Os exemplos incluem servidores, redes, contabilidade geral, instalações, data centers, e-mail, SAP e unidades de negócios. Uma tabela agrupa dados para análise. Em um modelo, as tabelas são exibidas como retângulos. No modelo de custo mostrado na imagem anterior, a tabela **Cost Source Actuals** é a tabela de origem. Ele deriva seu valor de drivers de duas unidades com base nas colunas da tabela **Cost Source Actuals** : **OpEx Variável** e **OpEx Fixo**. Ele aloca valores a três tabelas de destino: Dados **reais de mão de obra**, **Dados reais de instalações** e **Dados reais de ativos fixos**. As tabelas de destino podem então alocar seu valor para outras tabelas, conforme mostrado na imagem a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu578.png)

Para alocar valor:

1. Verifique as tabelas de origem e destino.
2. Clique na tabela de origem no **Project Explorer**.
3. Clique na etapa **Modelo** no pipeline de transformação.
4. No diagrama Sankey, clique em **Add Allocation (Adicionar alocação** ) sob o título **Allocations (Alocações** ).
5. Se houver mais de uma métrica, na seção **Alocar**, clique nas métricas às quais a alocação será aplicada.
6. Na seção **Uso**, selecione o tipo de alocação (consulte [Tipos de alocação](#Allocatevalueinamodel__Allocationtypes) para obter uma descrição de cada um).
7. Na seção **To (Para** ), selecione a tabela de destino.
8. Com base no tipo de alocação, preencha as informações restantes.

## Tipos de alocação

Há cinco tipos de alocações: **Valor ponderado**, **Consumo**, **Valor padrão**, **Fórmula** e **Recursão**. Cada tipo de alocação é descrito nos subtópicos a seguir.

- [Alocações de valor ponderado](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-weighted-value-allocations "(Abre em uma nova guia ou janela)")
- [Alocações de consumo](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-consumption-allocations "(Abre em uma nova guia ou janela)")
- [Alocações de valor padrão](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-standard-value-allocations "(Abre em uma nova guia ou janela)")
- [Alocações de fórmula](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-formula-allocations "(Abre em uma nova guia ou janela)")
- [Alocações de recursão](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-recursion-allocations "(Abre em uma nova guia ou janela)")
