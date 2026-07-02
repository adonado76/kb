---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Taxas de configuração e carregamento"
breadcrumb:
  - "Billing"
  - "Configurando os fundamentos do faturamento (implementação)"
source_path: "boit/billing/config-be/configure.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Taxas de configuração e carregamento

As taxas convertem unidades em encargos monetários.

Passos:

1. **Definir estratégia de taxas**
   - Para cada oferta, determine se a taxa será:
     - Baseado em custos, custo acrescido, preço, orçamento ou híbrido.
   - Decida com que frequência as taxas podem mudar:
     - Anualmente, trimestralmente ou ad hoc com governança.
2. **Crie o layout da tabela de taxas**
   - No mínimo:
     - Apresentando documento de identificação.
     - Período ou data de vigência.
     - Valor da taxa.
     - Moeda.
   - Opcional:
     - Tipo de taxa (padrão, com desconto, interna).
     - Notas ou comentários.
3. **Taxas iniciais de carga**
   - Preencha as taxas para:
     - O primeiro período de cobrança.
     - Um horizonte futuro definido (por exemplo, o ano fiscal completo).
4. **Validar resolução**
   - Execute um relatório de teste ou uma execução de modelo para confirmar:
     - Cada oferta faturada no período resulta em uma taxa única e inequívoca.
     - Nenhuma oferta está faltando taxas.

Dica de governança:

- Trate as alterações nas taxas como eventos controlados, com documentação e aprovação claras, especialmente no meio do ano.
