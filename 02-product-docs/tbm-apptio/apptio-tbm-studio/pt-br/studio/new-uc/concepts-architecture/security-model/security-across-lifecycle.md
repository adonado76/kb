---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Segurança ao longo de todo o ciclo de vida"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
source_path: "studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Segurança ao longo de todo o ciclo de vida

O ciclo de vida de compilação e implantação do TBM Studio (Desenvolvimento → Staging → Produção) traz considerações adicionais de segurança. As próprias configurações de segurança estão sujeitas ao fluxo de trabalho de check-in/check-out e devem ser promovidas entre ambientes, assim como os dados e os modelos.

## Segurança do ambiente de desenvolvimento

O ambiente de desenvolvimento é onde os modelos, relatórios e configurações de segurança são criados e modificados.

- **Acesso:** Requer a permissão " AccessDev ". Normalmente concedido às funções de Administrador e Usuário Avançado.
- **Permissões de edição:** os usuários devem fazer o check-out dos objetos antes de editá-los. O check-out bloqueia o objeto para que outras pessoas não possam editá-lo simultaneamente.
- **Alterações de segurança:** as tabelas de mapeamento RLS, as configurações de filtro e as definições de funções podem ser modificadas no ambiente de desenvolvimento.
- **Testes:** Use filtros de pré-visualização e representação no ambiente de desenvolvimento para validar as configurações de segurança antes da implementação.

- **[Segurança do ambiente de teste](../../../../studio/new-uc/concepts-architecture/security-model/staging-env-sagfety.html)**
- **[Segurança do ambiente de produção](../../../../studio/new-uc/concepts-architecture/security-model/prod-env-security.html)**
- **[Segurança e o fluxo de trabalho de check-in/check-out](../../../../studio/new-uc/concepts-architecture/security-model/security-checkin.html)**
