---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Pull Requests - Fluxo de trabalho de aprovação"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
source_path: "admin/governance-pull-requests-and-approval-workflow.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Pull Requests - Fluxo de trabalho de aprovação

A governança se integra ao site GitHub para gerenciar as aprovações de RP. Como lembrete, os PRs que não estão em conformidade com o nível de aplicação "Gated" são bloqueados, mas podem ser desbloqueados por usuários com a função **" Cloudability Governance PR Approver"**.

Configuração do GitHub

GitHub o proprietário do repositório precisa criar uma regra de proteção de ramificação que exija que as execuções de verificação de governança sejam aprovadas antes da mesclagem.

Aprovação de PRs

1. Navegue até a guia "Pull Requests" no painel de governança e revise os PRs que precisam de aprovação. Somente os PRs "abertos" e com status "reprovado" podem ser aprovados.
2. Selecione o PR e clique em "Approve" (Aprovar)
3. Em GitHub,, o status de execução da verificação do PR é atualizado para "Aprovado", permitindo que o engenheiro de nuvem faça a fusão dessa alteração.
