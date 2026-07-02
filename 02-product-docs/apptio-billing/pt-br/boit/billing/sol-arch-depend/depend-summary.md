---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Resumo das dependências"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
  - "Arquitetura da solução e dependências"
source_path: "boit/billing/sol-arch-depend/depend-summary.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Resumo das dependências

A tabela abaixo resume as principais dependências para cada edição.

|  |  |  |
| --- | --- | --- |
| **Área** | **Fundamentos de faturamento** | **Padrão de faturamento** |
| **Requisito de cálculo de custos** | Projeto Costing Essentials implementado | Projeto de Padrão de Custeio implantado |
| **Modelo de componente** | Versão 200 | Versão 120 e anteriores |
| **Componentes de faturamento** | Cobrança – Cobrança, Relatórios de cobrança | Vários componentes (Fundação, Unidades, Aplicações, Nuvem, etc.) |
| **Terminal** | Sem ponto final de faturamento separado; usa o Costing Essentials | Ponto final de faturamento separado, além do padrão de custos |
| **Ponto de entrada frontal** | Fundamentos de custos front-end, coleta de relatórios de faturamento | Aplicativo/ponto de extremidade padrão de faturamento dedicado |
| **Dependência do TBM Studio** | O mesmo projeto que Fundamentos de Cálculo de Custos | Mesmo projeto que o Padrão de Custeio |

Essa arquitetura e visão de dependências devem ser verificadas antes de qualquer trabalho de configuração ou solução de problemas. Se um dos pré-requisitos estiver faltando ou estiver desalinhado, o comportamento de faturamento nas seções posteriores do guia não corresponderá ao descrito.
