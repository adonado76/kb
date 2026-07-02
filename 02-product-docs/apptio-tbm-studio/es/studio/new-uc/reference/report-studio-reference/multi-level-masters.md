---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Másteres multinivel"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Informes principales"
source_path: "studio/new-uc/reference/report-studio-reference/multi-level-masters.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Másteres multinivel

TBM Studio te permite aplicar informes maestros a otros informes maestros, creando así una posible jerarquía. Sin embargo, **no se recomienda esta práctica**.

**Por qué no se recomienda cursar másteres de varios niveles**

- **Complejidad** : los múltiples niveles de herencia dificultan saber qué elementos proceden de qué plantilla principal
- **Carga de mantenimiento** : cualquier cambio en un elemento principal de la cadena puede tener efectos en cadena
- **Dificultad para la resolución de problemas** : los problemas visuales resultan más difíciles de diagnosticar cuando hay varias capas de herencia
- **Consideraciones sobre el rendimiento** : las capas de representación adicionales pueden afectar a los tiempos de carga de los informes

Nota: Si necesitas plantillas de varios niveles, plantéate rediseñar la estructura de las plantillas para utilizar un único informe maestro completo que incluya todos los elementos necesarios.

**Tema principal:** [Informes maestros](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
