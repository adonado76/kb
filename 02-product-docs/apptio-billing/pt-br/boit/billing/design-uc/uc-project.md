---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Visão do projeto de gastos com tecnologia"
breadcrumb:
  - "Billing"
  - "Padrões de Design e Casos de Uso"
source_path: "boit/billing/design-uc/uc-project.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Visão do projeto de gastos com tecnologia

Observação: **aplica-se apenas ao padrão de faturamento.**

**Problema**

As equipes de portfólio ou PMO querem entender os custos de tecnologia por projeto para um determinado período ou ano.

**Entradas**

- Dados mestre do projeto (ID, nome, proprietário, tipo)
- Mapeamentos de custos/uso para projetos (mão de obra, infraestrutura, nuvem, etc.)
- Configuração de faturamento que:
  - A Bills projeta diretamente, ou
  - Tags cobranças com atributos do projeto

**Passos**

1. Verifique **os mapeamentos do projeto** :
   - Confirme se a mão de obra, a infraestrutura e o uso da nuvem estão vinculados aos projetos, quando relevante.
2. Execute os modelos padrão de faturamento para o período.
3. Abra o **relatório de faturamento do projeto** :
   - Filtrar para o período atual.
   - Veja os encargos por projeto e serviço.
4. Aplique filtros adicionais conforme necessário:
   - Patrocinador, portfólio, tipo de projeto.
5. Exportar ou dividir ainda mais:
   - Principais projetos por gastos com tecnologia.
   - Custos do projeto por unidade de negócios ou consumidor.

**Relatórios importantes**

- Resumo do faturamento do projeto (Projeto × Serviço × Período)
- Relatório detalhado do projeto (com colaboradores subjacentes)
- Painel do portfólio destacando os principais projetos por gasto
