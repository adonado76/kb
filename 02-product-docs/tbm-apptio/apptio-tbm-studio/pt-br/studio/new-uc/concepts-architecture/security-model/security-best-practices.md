---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Melhores práticas de segurança"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
source_path: "studio/new-uc/concepts-architecture/security-model/security-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Melhores práticas de segurança

Uma segurança eficaz no TBM Studio requer um planejamento cuidadoso e a aplicação consistente dos princípios de segurança. Esta seção oferece orientações conceituais e padrões comuns para ajudá-lo a projetar uma configuração de segurança robusta.

## Princípio do privilégio mínimo

O princípio do privilégio mínimo consiste em conceder a cada usuário o acesso mínimo necessário para desempenhar suas funções. No TBM Studio, esse princípio se aplica a todas as camadas:

- **Funções:** Atribua a função com o mínimo de privilégios que atenda às necessidades do usuário. Comece com o nível de usuário corporativo e promova-o apenas quando necessário.
- **Funções personalizadas:** Ao criar funções personalizadas, inclua apenas as permissões de que a função realmente necessita. Evite copiar permissões de administrador “por precaução”
- **RLS:** Restringir a visibilidade dos dados ao âmbito mais restrito adequado às responsabilidades de cada usuário.
- **Contas de API:** Crie contas de serviço dedicadas com permissões mínimas para cada integração.
- **Permissões de relatórios:** torne os relatórios visíveis apenas para as funções que precisam deles, em vez de deixar todos os relatórios acessíveis a todos.

- **[Padrões de projeto de segurança](../../../../studio/new-uc/concepts-architecture/security-model/security-design-pattern.html)**
- **[Testes e validação de segurança](../../../../studio/new-uc/concepts-architecture/security-model/security-testing.html)**
