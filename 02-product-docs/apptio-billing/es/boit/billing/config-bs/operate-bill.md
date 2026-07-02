---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Puesta en práctica de la norma de facturación"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/operate-bill.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Puesta en práctica de la norma de facturación

Tras su puesta en marcha, la norma de facturación pasa a formar parte del ciclo de facturación recurrente descrito en la sección 9, con responsabilidades de dominio añadidas.

Elementos clave que deben documentarse y entregarse:

- **Runbook**
  - Secuencia de actualización de datos para cada dominio (nube, infraestructura, aplicaciones, proyectos).
  - Orden de ejecución del modelo y dependencias.
  - Pasos de control de calidad y aprobación por dominio y a nivel de resumen.
- **Propiedad**
  - ¿Quién es el propietario de los datos maestros de cada dominio?
  - ¿Quién es el propietario de los servicios, los precios y las definiciones de las unidades?
  - ¿Quién es el propietario de los informes y quién es responsable de responder a las preguntas?
- **Control de calidad específico del dominio**
  - Informes de control de calidad de dominio para:
    - Cobertura de etiquetas en la nube.
    - Asignaciones de aplicaciones.
    - Servidor y grupos de almacenamiento.
    - Asignaciones de proyectos.
    - Expectativas de cierre mensual por dominio.

Una vez implementado, Billing Standard puede admitir conversaciones más completas (optimización de tarifas unitarias, análisis de variaciones, precios de transferencia) sin sacrificar la trazabilidad ni la estabilidad operativa.
