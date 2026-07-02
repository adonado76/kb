---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Gerencie despesas com nuvem (sem integração com CFP)"
breadcrumb:
  - "Planning"
  - "Integrações"
  - "Conecte-se a Cloudability Financial Planning"
source_path: "it-planning/planning/manage-cfp-wo-int.html"
images:
  - "resources/images/it_planning_images/managecfp.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gerencie despesas com nuvem (sem integração com CFP)

Importante: Disponível com *a assinatura* ***do Padrão de Planejamento*** Apptio

Lembre-se: a Nova Visualização está ativada.

A guia **Nuvem** na visualização **Despesas** pode ser usada independentemente, sem a integração CFP, para gerenciar e acompanhar os gastos com nuvem dentro dos orçamentos e previsões.

Para adicionar ou atualizar despesas com nuvem:

1. Abra seu plano e navegue até a guia **Nuvem** na página **Despesas**.
2. Adicione uma nova despesa de nuvem de uma das seguintes maneiras:
   - Usando a **linha vazia** na parte inferior da tabela, ou
   - **Clique com o botão direito do mouse** e selecione **Inserir linha**
   - **Importando** os dados usando um arquivo CSV e no menu Ações no nível da tabela ( *botão com três pontos*) → opção **Importar linhas da nuvem**.
3. Forneça as informações necessárias para cada linha de despesas com nuvem:
   - **Centro de custos (obrigatório)** – Identifica o departamento ou unidade organizacional financeiramente responsável pelos gastos com a nuvem.
   - **Conta (obrigatório)** – A conta contábil na qual a despesa com nuvem será registrada.
   - **Fornecedor (opcional)** – Provedor ou fornecedor de serviços em nuvem. Este campo é útil para relatórios ao nível do fornecedor e análise de gastos.
   - **Localização (opcional)** – A localização geográfica onde os gastos com a nuvem foram incorridos.
   - **Tipo de custo (opcional)** – Disponível quando o Planejamento integrado de investimentos está ativado. Classifica os gastos como **Construção** ou **Operação**. Se deixado em branco, o sistema atribui automaticamente **Executar** como padrão.
   - **Projeto (opcional)** – Disponível quando o Planejamento integrado de investimentos está ativado. Use este campo para associar os gastos com a nuvem a um projeto específico para acompanhamento e relatórios.
   - **Descrição e comentário** – Contexto adicional ou metadados sobre a linha de despesas com nuvem.

Uma vez inserido, o Planejamento do Apptio gera automaticamente o lançamento financeiro correspondente para cada despesa de nuvem na guia **Resumo**. As linhas da guia Nuvem inseridas manualmente podem coexistir perfeitamente com as linhas de despesas na nuvem importadas do Cloud Financial Planning (CFP).

![gerenciar cf sem integração](../../../../../03-media/apptio-planning/resources/images/it_planning_images/managecfp.png)

**Tópico principal:** [Conecte-se a Cloudability Financial Planning](../../it-planning/planning/connect-cfp.html)
