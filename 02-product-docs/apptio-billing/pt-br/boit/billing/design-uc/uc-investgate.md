---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Investigue um aumento repentino na taxa unitária"
breadcrumb:
  - "Billing"
  - "Padrões de Design e Casos de Uso"
source_path: "boit/billing/design-uc/uc-investgate.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Investigue um aumento repentino na taxa unitária

**Problema**

Um interessado relata que a taxa para um determinado serviço “aumentou” este mês. Você precisa explicar o motivo.

**Entradas**

- Dados históricos da taxa unitária do serviço
- Resultados de custos para esse serviço (se disponíveis)
- Volumes de consumo ao longo do tempo
- Histórico da tabela de taxas

**Passos**

1. Abra o **relatório de análise da taxa unitária** do serviço:
   - Filtre pelo serviço, período atual e pelo menos três períodos anteriores.
2. Compare:
   - Unidades por período
   - Taxas por período
   - Taxa unitária por período
3. Determine qual driver foi alterado:
   - As unidades movimentaram-se significativamente com custos estáveis: provavelmente impulsionado pelo volume.
   - Custo por unidade alterado: provável alocação ou alteração do fator de custo no Cálculo de custos.
   - Alteração explícita da taxa: verifique a tabela de taxas.
4. Verifique a **tabela de taxas** :
   - Confirme se uma alteração de taxa foi configurada para o período.
   - Se sim, verifique se a alteração foi aprovada e documentada.
5. Se o custo estiver disponível em Cálculo de custos:
   - Compare **o custo por unidade** com **o preço por unidade** ao longo dos períodos.
6. Resuma as conclusões em termos simples:
   - “A taxa unitária aumentou porque o volume caiu X% em uma base de custos principalmente fixos.”
   - “A taxa unitária aumentou porque a taxa foi alterada de A para B por unidade.”
   - “A taxa unitária mudou porque a alocação de custos subjacente mudou no Cálculo de Custos.”

**Relatórios importantes**

- Relatório de tendências da taxa unitária para o serviço
- Histórico de taxas (visualização da tabela de taxas)
- Visualização da comparação entre custo e preço (se configurado)
