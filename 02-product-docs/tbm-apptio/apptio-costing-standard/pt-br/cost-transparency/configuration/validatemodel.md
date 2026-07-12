---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Validar alocações de modelos"
breadcrumb: []
source_path: "cost-transparency/configuration/validatemodel.html"
images:
  - "resources/images/ct_images/6872_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Validar alocações de modelos

Use a visualização da tabela de modelos para validar o fluxo de valor em um modelo. Depois de fazer o upload e mapear os dados de origem para a tabela de dados mestre apropriada, suas tabelas modeladas associadas devem começar a mostrar os drivers de unidade e as alocações.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

## Demostrações

Assista a estes vídeos de demonstração:

- [TBM Studio Configuração de alocação](https://community.apptio.com/videos/2038 "(Abre em uma nova guia ou janela)")
- [Vídeo: Aprimoramentos de usabilidade do modelador na versão 12.4.1](https://community.apptio.com/videos/1953 "(Abre em uma nova guia ou janela)")

Confira o [catálogo completo de vídeos dos produtos Apptio](https://community.apptio.com/docs/DOC-7714 "(Abre em uma nova guia ou janela)")

## Tabelas modeladas

Uma tabela modelada Costing Standard é uma tabela à qual foi adicionada uma etapa de modelo. A tabela modelada é uma transformação de uma tabela de dados mestre. Por exemplo, a tabela Origem do custo é uma transformação da tabela Dados mestre da origem do custo. Etapas adicionais do pipeline de transformação não podem ser adicionadas às tabelas modeladas do site Costing Standard . As únicas etapas de transformação exibidas para tabelas modeladas são **Source** e **Model**.

## Diagrama de alocação de drivers

Se você clicar em uma tabela de modelo no **Project Explorer** e, em seguida, clicar na etapa Modelo no pipeline de transformação, será exibido um diagrama de alocação de drivers, conforme mostrado abaixo. Use o diagrama para verificar o fluxo de valor de e para a tabela.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6872_1.png)

O diagrama mostra o fluxo de valor para a métrica do modelo selecionada no campo **Selecionar uma métrica** acima do diagrama. Na Figura A acima, a métrica é Custo. Você pode selecionar qualquer uma das métricas de modelo definidas para o projeto.

## Fazer alterações

Você pode fazer alterações nas alocações no modelo Costing Standard . Você pode modificar as alocações existentes e adicionar novas alocações. Antes de fazer alterações em um modelo, você deve entender bem como criar e modificar modelos. Para obter informações sobre como trabalhar com modelos, consulte [Sobre o Model Studio](https://community.apptio.com/docs/DOC-4891.html "(Abre em uma nova guia ou janela)").

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
