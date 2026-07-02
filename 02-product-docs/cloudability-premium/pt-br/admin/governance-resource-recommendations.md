---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Recomendações de recursos"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
source_path: "admin/governance-resource-recommendations.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Recomendações de recursos

A governança fornece recomendações para novos recursos EC2 e RDS que estão sendo implantados quando uma configuração semelhante (com requisitos de CPU e memória correspondentes) está disponível a um custo menor. As recomendações são postadas como comentários na solicitação pull (PR).

**Se a governança não identificar um recurso mais econômico, nenhuma recomendação será publicada.**

**Exemplo:** Faça upgrade da instância RDS de db.m5.8xlarge para db.m6g.8xlarge para economizar custos e manter o desempenho.
