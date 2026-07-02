---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Check-out, check-in e criação de construções"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
  - "Ambientes e gerenciamento de versões"
source_path: "boit/billing/environ-relnmgmt/checkin-checkout.html"
images:
  - "resources/images/boit_images/chckin.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Check-out, check-in e criação de construções

As alterações de configuração para Faturamento seguem o mesmo padrão do Cálculo de Custos:

1. **Check-out**
   - Os administradores ou analistas verificam os itens relevantes em Desenvolvimento:
     - Modelos relacionados com o faturamento.
     - Conjuntos de dados, tabelas ou métricas dos quais o faturamento depende.
     - Relate definições ou modelos para faturamento.
2. **Editar**
   - As alterações são feitas em Desenvolvimento:
     - Ajustando a lógica nos modelos.
     - Adicionar ou modificar tabelas e campos.
     - Atualização de layouts de relatórios ou novos relatórios.
3. **Efetuar check-in**
   - Quando as alterações estiverem concluídas, os itens serão verificados.
   - O sistema automaticamente:
     - Cria uma nova **compilação em desenvolvimento**.
     - Cria uma **compilação de preparação** correspondente com base nas mesmas alterações.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/chckin.png)

Fig. #: Verificação no relatório “Conta de TI”

Dicas práticas:

- Agrupe as alterações em um pequeno número de conjuntos de check-in para que sejam mais fáceis de rastrear e testar.
- Use notas de compilação significativas no check-in para que fique claro quais compilações contêm quais alterações de faturamento.
