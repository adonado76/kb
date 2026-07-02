---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Como fazer: Fonte Data Management Configuração e tabela de erros do projeto"
breadcrumb: []
source_path: "cost-transparency/configuration-additional/howtosourcedatamanagement.html"
images:
  - "resources/images/ct_images/4826_1.png"
  - "resources/images/ct_images/4826_2.png"
  - "resources/images/ct_images/4826_3.png"
  - "resources/images/ct_images/4826_4.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Como fazer: Fonte Data Management Configuração e tabela de erros do projeto

*Guia Relatórios (Projeto SDM/Dados promocionais)*

**Aplicativo** : O projeto SDM é usado para copiar dados de um projeto para outro dentro da mesma instância. No entanto, a configuração adequada é necessária para garantir que os dados corretos sejam copiados/colados de e para o projeto específico. A tabela "Project Errors" (Erros de projeto) do menu suspenso do projeto é uma ótima ferramenta para ajudar a solucionar problemas de configuração.

**Configuração do SDM:**

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/4826_1.png)

Para acessar as propriedades de um botão, você precisará estar no modo de edição, clicar com o botão direito do mouse e escolher propriedades. Isso abrirá a visualização de Propriedades mostrada abaixo. Essa visualização permitirá que você escolha Ações no visualizador e examine o código-fonte.

Nota:

Certifique-se de clicar apenas com o botão direito do mouse no botão, pois clicar com o botão esquerdo forçará o botão a executar a cópia do destino de origem/destino selecionado.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/4826_2.png)

**Tabela de erros do projeto:**

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/4826_3.png)

A mensagem de erro será exibida depois que o botão copiar tabela for pressionado se o código-fonte não estiver correto. Conforme mostrado abaixo, o erro em questão é que a tabela de apoio não foi encontrada. O código precisa incluir a tabela de apoio "Mainframe Storage Mapping" para que o botão seja executado corretamente.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/4826_4.png)

Há vários tipos de erros, mas todos serão identificados na tabela de erros do projeto, na coluna de erros.
