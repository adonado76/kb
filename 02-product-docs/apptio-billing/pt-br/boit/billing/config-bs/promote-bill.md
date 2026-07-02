---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Promoção para produção e primeira execução completa do padrão de faturamento"
breadcrumb:
  - "Billing"
  - "Configurando o padrão de faturamento (implementação)"
source_path: "boit/billing/config-bs/promote-bill.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Promoção para produção e primeira execução completa do padrão de faturamento

Após o faturamento, o conteúdo padrão e o comportamento do ponto final são validados no Staging:

1. **Bloqueio de preparação**
   - Evite novos check-ins e mantenha a compilação testada estável.
2. **Executar o controle de qualidade final no ambiente de teste**
   - Confirmar:
     - Todos os principais serviços e consumidores têm custos.
     - Os relatórios de domínio são preenchidos conforme o esperado.
     - A variação e os resultados da taxa unitária parecem razoáveis.
3. **Promova a compilação para produção**
   - Promova a compilação de estágio validada para o projeto Padrão de Custeio.
   - Isso também atualiza efetivamente o conteúdo do endpoint Padrão de Faturamento.
4. **Executar modelos padrão de faturamento na produção**
   - Execute os modelos de faturamento para o período alvo na produção.
   - Validar:
     - Resultados principais e específicos.
     - Relatórios importantes para o período.
5. **Abra o endpoint Padrão de faturamento para atingir o público-alvo**
   - Confirme que:
     - Os usuários pretendidos podem ver o ponto final.
     - Os relatórios são apresentados corretamente.

Os filtros de segurança funcionam conforme o esperado.
