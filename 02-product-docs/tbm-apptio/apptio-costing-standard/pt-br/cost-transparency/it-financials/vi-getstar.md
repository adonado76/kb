---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Informações sobre fornecedores Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financeiro"
  - "Fornecedor"
source_path: "cost-transparency/it-financials/vi-getstar.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Informações sobre fornecedores Introdução

O Vendor Insights fornece análises e suporte à tomada de decisões em todo o ciclo de vida da gestão de fornecedores, incluindo visibilidade dos gastos com fornecedores, controles de pedidos de compra, análise de contratos e monitoramento de ARC/RRC. O Vendor Insights é fornecido por meio de componentes modulares que podem ser instalados de forma incremental, com base no nível de insight necessário.

Antes de ativar os relatórios do Vendor Insights, certifique-se de que os componentes básicos necessários estejam instalados e que os fornecedores, contas a pagar e conjuntos de dados relacionados estejam disponíveis e mapeados corretamente.

## Pré-requisitos

- **CTF – Fonte de Custos**
- Fornece dados financeiros reais e orçamentários básicos necessários para a análise de gastos com fornecedores.
- **CTF – Fornecedor**
- Permite o registro dos dados principais do fornecedor e a atribuição dos gastos por fornecedor.

Os componentes adicionais do Vendor Insights se baseiam nessa estrutura e introduzem recursos de relatórios mais avançados.

**Componentes do Vendor Insights**

Os componentes do Vendor Insights são instalados de forma incremental, com cada componente ativando um conjunto específico de relatórios e análises.

## Informações sobre fornecedores – Fundação

O componente **Vendor Insights Foundation** oferece visibilidade dos gastos com fornecedores e recursos de racionalização. Permite a análise da distribuição de fornecedores, tendências de gastos e concentração do portfólio.

Principais recursos habilitados:

- Informações sobre fornecedores (painel)
- Resumo do fornecedor
- Detalhes do fornecedor
- Despesas com fornecedores por tipo de fornecedor e grupo de custos
- Análise da qualidade dos dados entre fornecedores e contas a pagar

Este componente requer:

- Dados de contas a pagar (faturas e detalhes de gastos)
- Dados mestre do fornecedor (nomes dos fornecedores, hierarquia, categorização)

## Informações sobre fornecedores – Ordens de compra (PO)

O componente **PO** do Vendor Insights amplia a análise do fornecedor para a visibilidade e os controles do pedido de compra.

Principais recursos habilitados:

- PO Burndown
- Gastar sem ordens de compra
- Detalhes do pedido de compra
- Análise da relação entre PO e AP

Este componente requer:

- Dados da ordem de compra
- Dados de mapeamento AP-PO

**Observação:** O componente Foundation deve estar totalmente instalado e configurado antes de instalar o componente PO.

## Informações sobre fornecedores – Contratos

O componente **Contratos** do Vendor Insights permite a análise em nível de contrato e o planejamento de renovações.

Principais recursos habilitados:

- Resumo do contrato
- Expiração do contrato
- Notificação de expiração do contrato
- Contrato para Aplicações
- Detalhes do contrato

Este componente requer:

- Dados mestre do contrato
- Mapeamento de PO para contrato
- Mapeamento de contratos para aplicações
- Dados mestre da aplicação

**Observação:** O componente PO deve ser instalado antes de habilitar os Contratos.

## Informações sobre fornecedores – ARC/RRC

O componente **ARC/RRC** oferece suporte à análise de contratos com fornecedores baseados no consumo, com cobranças adicionais por recursos e créditos reduzidos por recursos.

Principais recursos habilitados:

- Resumo do ARC RRC
- ARC RRC RU Reconciliação
- Análise do consumo e dos preços das unidades de recursos

Este componente é instalado após os Contratos e requer dados específicos do ARC/RRC relativos a contratos e unidades de recursos.

## Fontes comuns de dados

O Vendor Insights normalmente integra dados de sistemas financeiros, de compras e de gestão de contratos. As aplicações de origem comuns incluem:

- **Contas a pagar/Sistemas financeiros:** SAP ECC/AP, Oracle Finanças, NetSuite
- **Sistemas de aquisição:** SAP Ariba, Coupa, Oracle Nuvem de aquisição
- **Gestão de fornecedores e contratos:** ServiceNow Gestão de fornecedores, SAP ERP, Oracle

O escopo e a qualidade dos dados de origem determinam os atributos disponíveis para relatórios, como nomes de fornecedores, categorias, valores gastos, ordens de compra, contratos, aplicativos suportados e métricas ARC/RRC.

## Conjuntos de dados principais

Dependendo dos componentes instalados, o Vendor Insights utiliza os seguintes conjuntos de dados principais:

- **Dados mestre do fornecedor** – Atributos, hierarquia e categorização do fornecedor
- **Dados mestres de contas a pagar** – Gastos e atribuição ao nível da fatura
- **Dados mestre de ordens de compra** – valores, status e compromissos das ordens de compra
- **Dados mestre dos contratos** – Termos contratuais, vencimento, compromissos
- **Contratos para dados mestre de aplicativos** – Mapeamento de contratos para aplicativos compatíveis
- **Dados mestres ARC/RRC** – Quantidades, limites e preços das unidades de recursos

Esses conjuntos de dados devem ser carregados e mapeados corretamente para garantir relatórios e análises precisas dos fornecedores em todos os relatórios do Vendor Insights.
