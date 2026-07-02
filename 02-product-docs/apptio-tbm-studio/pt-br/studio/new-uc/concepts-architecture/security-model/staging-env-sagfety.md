---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Segurança do ambiente de teste"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Segurança ao longo de todo o ciclo de vida"
source_path: "studio/new-uc/concepts-architecture/security-model/staging-env-sagfety.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Segurança do ambiente de teste

O ambiente de teste funciona como uma porta de validação entre o desenvolvimento e a produção.

- **Acesso:** Requer a permissão " AccessStg ". Normalmente concedido às funções de Administrador e Usuário Avançado.
- **Objetivo:** Verificar se as configurações de segurança funcionam corretamente com dados reais antes da implantação em produção.
- **Testes:** Execute cálculos de simulação e verifique se os filtros RLS produzem os resultados esperados. Use a função de suplantar identidade para realizar testes na perspectiva de usuários específicos.

**Tópico principal:** [Segurança ao longo do ciclo de vida](../../../../studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html)
