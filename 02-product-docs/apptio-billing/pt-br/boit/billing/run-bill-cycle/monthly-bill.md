---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Processo de faturamento mensal"
breadcrumb:
  - "Billing"
  - "Executando o ciclo de faturamento"
source_path: "boit/billing/run-bill-cycle/monthly-bill.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Processo de faturamento mensal

Cada período de faturamento normalmente segue um conjunto repetível de etapas.

Um padrão comum é o seguinte:

1. **Fechar o período**
   - Alinhe-se com o departamento financeiro quanto ao prazo final do período de faturamento.
   - Congele ou capture os dados de origem quando necessário para que os volumes não sejam alterados na faturação.
2. **Atualizar dados de custo e consumo**
   - Certifique-se de que o departamento de custos recebeu os dados de custos mais recentes para o período.
   - Atualizar feeds de consumo para faturamento:
     - Utilização, bilhetes, dispositivos, utilização da nuvem, métricas do projeto e similares.
3. **Realizar verificações de controle de qualidade**
   - Executar relatórios padrão de controle de qualidade:
     - Mapeamentos ausentes (consumidor, oferta, objetos de domínio).
     - Picos ou quedas de volume.
     - Cargas zero ou negativas que não deveriam existir.
4. **Revisar projetos de lei**
   - Analistas e administradores revisam as cobranças por oferta e consumidor.
   - Os proprietários de serviços ou produtos validam os encargos para suas áreas.
5. **Aplique as correções necessárias**
   - Corrija problemas de dados nos sistemas de origem, tabelas de mapeamento ou tabelas de taxas.
   - Repita as verificações de controle de qualidade.
6. **Aprovar projetos de lei**
   - Após a conclusão do controle de qualidade, obtenha a aprovação dos responsáveis designados:
     - Frequentemente, proprietários de serviços ou produtos e finanças.
7. **Resultados da liberação**
   - Publique/envie por e-mail contas ou relatórios de showback aos consumidores.

Exportar e entregar diários para o departamento financeiro.
