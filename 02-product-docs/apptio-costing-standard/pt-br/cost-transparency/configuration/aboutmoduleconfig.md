---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Sobre a configuração do Costing Standard Foundation Module"
breadcrumb: []
source_path: "cost-transparency/configuration/aboutmoduleconfig.html"
images:
  - "resources/images/ct_images/6834_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Sobre a configuração do Costing Standard Foundation Module

Quando você cria um projeto Costing Standard , o módulo Costing Standard Foundation é instalado.

## Introdução

O módulo é baseado no modelo de custo mostrado na Figura A abaixo. Em geral, o valor é trazido para o modelo no nível do objeto Fonte de custos. Para facilitar a geração de relatórios sobre mão de obra e ativos fixos, o valor é alocado para os objetos Labor, Fixed Asset Ledger e Other Cost Pools. Para facilitar a geração de relatórios com base nas torres de recursos de TI, o valor é agregado ao objeto Torres de recursos de TI. Esse modelo serve de base para os outros dois módulos do aplicativo Costing Standard : Aplicativos e serviços e Unidades de negócios.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6834_1.png)

## Etapas de configuração

Para fornecer as métricas básicas, os modelos de cálculo e os relatórios para Costing Standard, você executará as seguintes etapas:

- Crie o projeto Costing Standard
- Configurar o tempo para o projeto
- Carregar tabelas de dados no aplicativo
- Adicionar colunas às tabelas para prepará-las para o mapeamento das tabelas de dados mestre
- Anexar e mapear as tabelas para as tabelas de dados mestre

## Funções

Os usuários que acessarão a página inicial Costing Standard com o objetivo de visualizar os relatórios devem ser atribuídos à função View Only. Eles não podem ser atribuídos às funções de gerente de projeto ou proprietário de unidade de negócios.

Os usuários que configurarão o aplicativo precisarão ser atribuídos à função Admin.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
