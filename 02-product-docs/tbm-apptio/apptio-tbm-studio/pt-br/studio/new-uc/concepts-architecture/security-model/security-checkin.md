---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Segurança e o fluxo de trabalho de check-in/check-out"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Segurança ao longo de todo o ciclo de vida"
source_path: "studio/new-uc/concepts-architecture/security-model/security-checkin.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Segurança e o fluxo de trabalho de check-in/check-out

Os objetos relacionados à segurança (como configurações de RLS, permissões de relatórios e configurações de visibilidade de componentes baseadas em funções) seguem o mesmo fluxo de trabalho de check-in/check-out que os demais objetos do TBM Studio. Isso significa que:

- É necessário fazer o check-out de uma tabela para adicionar ou modificar sua etapa RLS.
- A consulta à tabela modificada aciona um recálculo que aplica as novas regras de RLS.
- Os outros usuários só verão a configuração de segurança atualizada após a conclusão do cálculo.
- As tabelas de mapeamento do RLS no projeto Row-Level Security também seguem o padrão de check-out/check-in.

Nota:

**Melhores práticas: Gestão de mudanças de segurança**

Trate as alterações de segurança com o mesmo rigor com que trata as alterações no modelo. Documente o que foi alterado e por quê, realize testes exaustivos nos ambientes de desenvolvimento e de teste antes de implementar na produção e verifique os resultados após a implementação. Uma regra RLS mal configurada pode expor dados confidenciais ou ocultar dados de que os usuários precisam para realizar seu trabalho.

**Conceitos relacionados:** Para obter uma explicação detalhada sobre o ciclo de vida da compilação e da implantação, [consul](../build-deployment.html) te Ciclo de vida da compilação e da implantação. Para obter procedimentos passo a passo sobre como gerenciar usuários e configurar a segurança, consulte as seções “ 3.4 : Gerenciamento de usuários e permissões” e “[Gerenciamento de usuários](../../admin/user-management.html) e [segurança e conformidade](../../admin/sec-comp.html) ”.

**Tópico principal:** [Segurança ao longo do ciclo de vida](../../../../studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html)
