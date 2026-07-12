---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Visão geral do gerenciamento de despesas"
breadcrumb:
  - "Planning"
  - "Gerenciamento de despesas"
source_path: "it-planning/planning/spend-management.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Visão geral do gerenciamento de despesas

O Spend Management permite que você gerencie dados reais importando transações mensais para o Apptio Planning. Ao integrar os dados reais, você pode alinhar seus modelos de planejamento e previsão com o desempenho real, permitindo melhor visibilidade, rastreamento de variações e tomada de decisões.

## Fontes de dados reais

- **Importação de CSV** - Faça upload de transações reais por meio de arquivos CSV (por exemplo, do seu sistema ERP ou GL).
- **Apptio Integração de custos** - Importe transações reais automaticamente do site Apptio Costing, se configurado.
- Independentemente da fonte, os dados importados entram no Gerenciamento de despesas e podem ser usados para criar planos de previsão.

## Etapas para importar dados reais via CSV

1. Vá para **Spend Management → Transactions (Gerenciamento de despesas → Transações** ) na navegação à esquerda.
2. Use a **barra de navegação superior** para selecionar o período de tempo para o qual você deseja importar dados reais.
3. Clique em **Actions → Import Actuals...** ou selecione **Export Template (Exportar modelo** ) para fazer download de um modelo CSV.
4. Escolha um **tipo de importação** :
   1. **Replace All Data (Substituir todos os** dados) - substitui todos os dados existentes no período selecionado.
   2. **Append Data (Anexar dados** ) - adiciona novas linhas sem excluir os dados existentes.
5. Carregue seu **arquivo CSV contendo** os campos obrigatórios.
6. Clique em **Importar** e, em seguida, escolha **Importar** ou **Importar com problemas** para finalizar o upload.
7. As transações importadas aparecerão imediatamente na **tabela Transactions (Transações** ).

## Etapas para importar dados reais do site Apptio Costing

1. Verifique se a conexão de dados está configurada em **Settings** (ícone de engrenagem) **→ Apptio Costing Integration**.
2. Navegue até Spend **Management → Transactions (Gerenciamento de despesas → Transações).**
3. Use a **barra de navegação superior** para selecionar o período de tempo para o qual você deseja importar dados reais.
4. Clique em **Actions → Import from Apptio Costing...**
5. Clique em **Import**.
6. As transações importadas aparecerão na **tabela Transactions (Transações** ).

   Para obter mais informações, consulte [Importar dados reais](import-publish-actuals.html)

## Gerenciamento de despesas Estados do período

Cada período contábil no Gerenciamento de despesas tem um dos seguintes estados: **Novo**, **Aberto** ou **Final**.

**Abrir um período**

1. Clique em **Open Month** no canto superior direito.
2. O status do período muda de **New → Open**.

**Finalizar um período**

1. Clique em **Close Month (Fechar mês** ) no canto superior direito.
2. O status do período muda de **Aberto → Final**.

**Reabrir um período**

1. Clique em **Reopen Month (Reabrir mês** ) no canto superior direito.
2. O status do período muda de **Final → Novo**.

***Notas de comportamento***

- Os estados **Novo** e **Aberto** funcionam da mesma forma: os dados podem ser importados ou modificados.
- Quando um período é marcado como **Final**, nenhuma outra importação ou edição é permitida - inclusive os dados importados automaticamente fromApptio Costing.
- Os proprietários do orçamento podem visualizar as transações de qualquer departamento ao qual tenham acesso, independentemente do estado do período.
- Após importar dados para um período, se houver dados de referência (por exemplo, contas, centros de custo, etc.) for atualizado, você deve clicar em **Update Reference Data (Atualizar dados de referência)** para aplicar essas alterações ao período.
- A estrutura da **tabela Transactions** pode ser gerenciada em **Configuration → Schema → Actuals**.
