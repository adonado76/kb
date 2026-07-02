---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Instalando os componentes do Billing Essentials"
breadcrumb:
  - "Billing"
  - "Configurando os fundamentos do faturamento (implementação)"
source_path: "boit/billing/config-be/install-be.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Instalando os componentes do Billing Essentials

O Billing Essentials é fornecido como componentes que são instalados no projeto Costing Essentials existente.

Etapas de alto nível:

1. Abra o **projeto Costing Essentials** no TBM Studio.
2. Navegue até a área onde os componentes são gerenciados.
3. Localize e instale:
   - Faturamento – Cobrança
   - Faturamento – Relatório de cobranças
4. Confirme a instalação:
   - Cria os modelos e conjuntos de dados esperados.
   - Adiciona a coleção de relatórios “Faturamento” ao projeto.

Verificações pós-instalação:

- Verifique se os modelos de faturamento são compilados sem erros em Desenvolvimento.
- Confirme se as novas tabelas e métricas aparecem no modelo de dados do projeto.
- Confirme se a coleção de relatórios “Faturamento” aparece na árvore de relatórios (mesmo que ainda não tenha sido publicada na Produção).
