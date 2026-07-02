---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Pull Requests - Flujo de aprobación"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
source_path: "admin/governance-pull-requests-and-approval-workflow.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Pull Requests - Flujo de aprobación

Governance se integra con GitHub para gestionar las aprobaciones de relaciones públicas. Como recordatorio, los RP que no cumplen con el nivel de aplicación "Gated" se bloquean, pero pueden ser desbloqueados por usuarios con el rol **" Cloudability Governance PR Approver"**.

Configuración de GitHub

GitHub el propietario del repositorio necesita crear una regla de protección de rama que requiera que las comprobaciones de Gobernanza pasen antes de fusionar.

Aprobación de los RP

1. Vaya a la pestaña "Pull Requests" del panel de control de Gobernanza y revise los PR que requieren aprobación. Sólo se pueden aprobar los PR que están "abiertos" y que tienen un estado "fallido".
2. Seleccione el RP y haga clic en "Aprobar"
3. En GitHub,, el estado de ejecución de la comprobación de PR se actualiza a "Pass", lo que permite al ingeniero de la nube fusionar ese cambio.
