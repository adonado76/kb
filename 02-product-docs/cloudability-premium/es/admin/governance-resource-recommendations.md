---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Recomendaciones de recursos"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
source_path: "admin/governance-resource-recommendations.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Recomendaciones de recursos

La gobernanza ofrece recomendaciones para los nuevos recursos EC2 y RDS que se implementan cuando hay disponible una configuración similar (que cumple los requisitos de CPU y memoria) a un coste menor. Las recomendaciones se publican como comentarios en el pull request (PR).

**Si Gobernanza no identifica un recurso más rentable, no se publicará ninguna recomendación.**

**Ejemplo:** Actualizar la instancia RDS de db.m5.8xlarge a db.m6g.8xlarge para ahorrar costes manteniendo el rendimiento.
