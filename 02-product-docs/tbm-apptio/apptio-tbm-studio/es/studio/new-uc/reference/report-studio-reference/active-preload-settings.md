---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración de «Activo» y «Precarga»"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Propiedades de informe"
source_path: "studio/new-uc/reference/report-studio-reference/active-preload-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración de «Activo» y «Precarga»

Estos ajustes determinan si un informe se incluye en los cálculos del sistema y si se precalcula para agilizar el acceso de los usuarios.

|  |  |
| --- | --- |
| **Valor** | **Descripción e impacto** |
| Activo | Si se marca esta casilla, el informe se incluye en los cálculos del sistema y sus datos se cargan previamente. Si no se marca, el informe se desactiva y no se calcula. Utilice esta opción para desactivar temporalmente un informe sin eliminarlo, o para evitar que se calculen los informes incompletos. |
| Carga previa | Los informes que tienen activada la opción «Activo» tienen los datos precalculados durante la compilación. Si tu dominio está configurado para requerir la precarga, los usuarios no podrán ver los informes que no se hayan precargado. La precarga mejora la experiencia del usuario en los informes con gran volumen de datos, ya que garantiza que los cálculos estén completos antes de que los usuarios accedan al informe. |

**Ubicación:** pestaña «Informe» > grupo «Avanzado» > casilla de verificación «Activo»

**Tema principal:** [Propiedades del informe](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
