---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Problemas de compilação e implantação"
breadcrumb:
  - "TBM Studio"
  - "Solução de problemas e suporte"
  - "Problemas comuns e soluções"
source_path: "studio/new-uc/ts-support/bd-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Problemas de compilação e implantação

## A compilação ficou parada no estado "Pendente" ou "Calculando"

Quando as compilações parecerem estar travadas, verifique primeiro a fila de cálculos para entender o estado atual. Vários check-ins podem causar atrasos nas compilações, e grandes alterações na configuração podem exigir um tempo de cálculo considerável.

**Soluções:**

- Verifique a Fila de Cálculos (Compilação > Fila de Cálculos) para analisar o status de todos os ambientes
- Aguarde a conclusão ou coordene as atualizações com os membros da equipe para agrupar as alterações
- Cancele a compilação, se necessário ( v12.3.1+ ) — as alterações pendentes serão incluídas na próxima compilação

## Não é possível fazer a transição para a produção

**Soluções:**

- Verifique se o cálculo da etapa foi concluído — a promoção só é possível após a conclusão de todos os cálculos da etapa
- Verifique o status de bloqueio do ambiente — coordene-se com outros usuários caso o Stage esteja bloqueado
- Verificação de erros de bloqueio no painel Erros
