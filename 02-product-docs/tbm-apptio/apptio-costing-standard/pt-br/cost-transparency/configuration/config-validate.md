---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Validar alocações do modelo"
breadcrumb:
  - "Costing Standard"
  - "Configuração"
source_path: "cost-transparency/configuration/config-validate.html"
images:
  - "resources/images/studio_images/da.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Validar alocações do modelo

Use a visualização da tabela do modelo para validar o fluxo de valor em um modelo. Depois de carregar e mapear os dados de origem para a tabela de dados mestre apropriada, as tabelas modeladas associadas devem começar a mostrar os impulsionadores unitários e as alocações.

Uma tabela modelada pelo Padrão de Custeio é uma tabela à qual foi adicionada uma etapa Modelo. A tabela modelada é uma transformação de uma tabela de dados mestre. Por exemplo, a tabela Origem de custos é uma transformação da tabela Dados mestre de origem de custos. Não é possível adicionar etapas adicionais ao pipeline de transformação às tabelas modeladas pelo Padrão de Custeio. As únicas etapas de transformação exibidas para tabelas modeladas são **Origem** e **Modelo**.

**Diagrama de alocação de motoristas**

Se você clicar em uma tabela de modelo no **Project Explorer** e, em seguida, clicar na etapa Model no pipeline de transformação, um diagrama de alocação de driver será exibido, conforme mostrado abaixo. Use o diagrama para verificar o fluxo de valor de e para a tabela.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/da.png)

O diagrama mostra o fluxo de valor para a métrica do modelo selecionada no campo **Selecionar uma métrica** acima do diagrama. Na Figura A acima, a métrica é Custo. Você pode selecionar qualquer uma das métricas do modelo definidas para o projeto.

**Faça alterações**

Você pode fazer alterações nas alocações no modelo padrão de cálculo de custos. Você pode modificar as alocações existentes e adicionar novas alocações. Antes de fazer alterações em um modelo, você deve entender completamente como criar e modificar modelos.

Para obter informações sobre como trabalhar com modelos, consulte [Sobre o Model Studio.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-about-model-studio "(Abre em uma nova guia ou janela)")
