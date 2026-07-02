---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar um driver de unidade a uma tabela em um modelo"
breadcrumb: []
source_path: "studio/model_studio/add-unit-driver-to-table.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu605.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar um driver de unidade a uma tabela em um modelo

**Aplica-se a** : TBM Studio 12.0 e posterior

Há duas maneiras de agregar valor a uma tabela em um modelo:

- Use uma coluna de valor na tabela. Isso é conhecido como driver de unidade. Os drivers de unidade geralmente são usados na camada mais baixa de um modelo.
- Atribuir valor à tabela a partir de outra tabela. Isso é conhecido como alocação. As alocações são usadas, na maioria das vezes, para fluir o valor de um nível em um modelo para outro.

Na imagem a seguir, a tabela **Cost Source Actuals** tem dois drivers de unidade: **OpEx Variável** e **OpEx Fixo**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu605.png)

As informações abaixo descrevem como adicionar um driver de unidade. Para obter informações sobre alocações, consulte **[Criar uma alocação](allocate-value-in-model.htm "(Abre em uma nova guia ou janela)")**.

Para adicionar um driver de unidade a uma tabela:

1. Clique na tabela no **Project Explorer** e verifique a tabela.
2. Adicionar uma etapa **de Modelo**.
3. Clique na etapa **Modelo**.
4. No espaço de trabalho **Modelo**, clique em **Adicionar driver de unidade** na coluna **Drivers**.
5. Em **Add To (Adicionar a** ), clique nas métricas às quais o driver será aplicado.
6. Em **Usando**, clique no tipo de driver (veja abaixo uma explicação dos tipos de driver).
7. Complete a definição do motorista com base no tipo de motorista que você selecionou:
   - **Coluna** : selecione uma coluna
   - **Métrica** : selecione uma métrica
   - **Fórmula** : insira uma fórmula

Opcionalmente, em **Notas**, insira informações sobre o driver.

As guias **Source (Origem** ) e **Destination (Destino** ) na tabela do lado direito da caixa de diálogo mostram linha por linha como o valor está sendo distribuído.

## Tipos de drivers

Há três tipos de motoristas.

- **Coluna** - O valor é obtido de uma coluna na tabela. Esse é o tipo mais comum de motorista.
- **Métrica** - O valor é obtido de outra métrica do modelo.
- **Fórmula** - Uma equação gera o valor. A equação pode incluir valores da tabela ou de outras tabelas.

## Excluir um driver

1. Clique no driver no diagrama Sankey.
2. Clique em **Excluir** na parte inferior do painel.
