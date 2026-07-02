---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Executando o cálculo do Billing Essentials"
breadcrumb:
  - "Billing"
  - "Configurando os fundamentos do faturamento (implementação)"
source_path: "boit/billing/config-be/running.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Executando o cálculo do Billing Essentials

Com ofertas, consumidores, consumo e taxas definidos, o cálculo do Billing Essentials pode ser executado em Desenvolvimento e Preparação.

Passos:

1. **Executar modelos de faturamento em desenvolvimento**
   - Execute o(s) modelo(s) de cálculo de faturamento primário(s) criado(s) pelo componente Faturamento – Cobrança.
   - Confirme se a execução foi concluída com sucesso.
2. **Inspecionar saídas**
   - Analise a tabela de saída de faturamento:
     - Certifique-se de que existem linhas para todos os consumidores e ofertas esperados.
     - Verifique aleatoriamente unidades, taxas e encargos.
3. **Publique e teste relatórios em Desenvolvimento/Preparação**
   - Abra relatórios de faturas e detalhes da coleção de relatórios de faturamento.
   - Validar:
     - Totais por consumidor e oferta.
     - Principais casos de uso (por exemplo, uma grande unidade de negócios, um grande serviço).
4. **Realizar controle de qualidade formal na preparação**
   - Assim que o comportamento inicial for confirmado, passe para a fase de preparação e:
     - Reexecute os modelos de faturamento com dados mais completos.
     - Execute relatórios de controle de qualidade que destacam mapeamentos ausentes ou anomalias.

Somente após esse ciclo estar estável no ambiente de teste é que uma compilação deve ser promovida para o ambiente de produção.
