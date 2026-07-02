---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Validação das contas do período atual"
breadcrumb:
  - "Billing"
  - "Executando o ciclo de faturamento"
source_path: "boit/billing/run-bill-cycle/validating.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Validação das contas do período atual

A validação é onde a maioria dos problemas de faturamento é detectada antes de chegar aos consumidores.

Validações típicas:

1. **Verificações estruturais**
   - Confirme que:
     - Cada consumidor que espera receber uma fatura tem pelo menos uma cobrança.
     - Os consumidores novos ou aposentados são tratados corretamente.
     - As ofertas marcadas como faturáveis aparecem efetivamente.
2. **Verificações de volume**
   - Compare as unidades do período atual com:
     - Períodos anteriores.
     - Eventos comerciais conhecidos, como migrações, novos lançamentos ou aposentadorias.
   - Investigar:
     - Grandes picos ou quedas.
     - Grandes mudanças entre as ofertas.
3. **Verificações de taxas**
   - Confirme que:
     - A taxa correta é aplicada para o período atual.
     - Tarifas especiais ou descontos são aplicados quando acordados.
     - Não são utilizadas taxas padrão ou provisórias onde não devem ser utilizadas.
4. **Razoabilidade da cobrança**
   - Verifique o total das cobranças:
     - Por consumidor.
     - Ao oferecer ou prestar serviços.
   - Compare com:
     - Orçamento ou plano.
     - Resultados de custos para implementações baseadas em custos.

1. **Reconciliação com custos**
   - Para cenários de estorno, confirme que:
     - Os encargos totais de faturamento aproximam-se da visão de custos recuperáveis.
     - Qualquer diferença entre o custo e os encargos é entendida e documentada como variação planejada.

Para o Padrão de Faturamento, algumas validações podem ser feitas no nível do domínio (por exemplo, nuvem, servidores, projetos) em vez de apenas no nível da oferta. Os mesmos princípios se aplicam.
