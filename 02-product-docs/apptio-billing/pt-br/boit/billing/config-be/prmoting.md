---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Promoção para produção e primeira execução ao vivo"
breadcrumb:
  - "Billing"
  - "Configurando os fundamentos do faturamento (implementação)"
source_path: "boit/billing/config-be/prmoting.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Promoção para produção e primeira execução ao vivo

Quando o Billing Essentials funcionar conforme o esperado no ambiente de teste:

1. **Bloqueio de preparação**
   - Evite que novos check-ins alterem a compilação de preparação em teste.
2. **Executar o controle de qualidade final no ambiente de teste**
   - Confirmar:
     - Todas as ofertas exigidas têm taxas.
     - Todos os consumidores necessários têm encargos.
     - Não aparecem valores zero ou negativos inesperados onde não deveriam.
3. **Promova a compilação para produção**
   - Promova a compilação de estágio validada para produção, seguindo o processo padrão do ambiente.
4. **Executar modelos de faturamento em produção**
   - Execute os modelos do Billing Essentials na produção para o período alvo.
   - Confirme se as saídas são preenchidas corretamente.
5. **Publique relatórios para públicos-alvo**
   - Certifique-se de que a coleta de relatórios de faturamento esteja visível para administradores, analistas e outras funções específicas.

Execute um conjunto final de testes de fumaça nos relatórios de produção.
