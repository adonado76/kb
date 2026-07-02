---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Lista de verificação administrativa de faturamento"
breadcrumb:
  - "Billing"
  - "Executando o ciclo de faturamento"
source_path: "boit/billing/run-bill-cycle/admin-checklist.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Lista de verificação administrativa de faturamento

Esta lista de verificação resume as tarefas recorrentes para cada período de faturamento. Pode ser adaptado para um manual operacional mais detalhado.

**Antes do encerramento do período**

- Confirme o calendário de faturamento e as datas de corte para o próximo período.
- Valide se os sistemas de origem estão prontos para fornecer dados de consumo dentro do prazo.
- Verifique se as tabelas de taxas estão atualizadas para o próximo período.

**Após o encerramento do período**

- Atualizar os dados de custos para o período.
- Carregue ou atualize os feeds de consumo necessários para o faturamento.
- Execute os modelos de faturamento no ambiente apropriado (primeiro no ambiente de teste e, depois, no ambiente de produção após a promoção).

**Validação**

- Execute relatórios de controle de qualidade estruturais, de volume e de taxa.
- Reconcilie os totais de faturamento com os custos e, se aplicável, com o plano ou orçamento.
- Resolva quaisquer problemas de dados ou configuração e execute novamente os modelos, se necessário.

**Liberação da conta**

- Gerar relatórios detalhados e faturas para o período.
- Confirme se os relatórios são renderizados corretamente e se a segurança está funcionando conforme o esperado.
- Disponibilize os relatórios para os públicos apropriados e notifique-os.

**Integração de diários e finanças**

- Prepare e valide as exportações do diário.
- Entregar ou carregar diários no sistema Financeiro.
- Confirme a publicação e registre quaisquer IDs de referência.

**Serviço de limpeza**

- Arquivar os resultados de faturamento do período.
- Registre quaisquer problemas conhecidos, ajustes manuais ou tratamentos pontuais.
- Atualize a documentação ou as notas que serão relevantes no próximo ciclo de planejamento anual.
