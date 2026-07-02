---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cómo interactúan los permisos de los informes y RLS"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Permisos de informes y componentes"
source_path: "studio/new-uc/concepts-architecture/security-model/report-permission-rls-interact.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cómo interactúan los permisos de los informes y RLS

Los permisos de los informes y RLS funcionan como capas complementarias:

1. Los permisos del informe determinan si el usuario puede acceder al informe.
2. Si el usuario puede acceder al informe, RLS filtra los datos que se muestran en él.
3. La visibilidad de los componentes permite ajustar aún más lo que el usuario ve en la interfaz del informe.

**Situación habitual:** el informe «Resumen de costes» está disponible para todos los roles. Un directivo tiene acceso a todas las unidades de negocio (sin restricciones de RLS). Un jefe de departamento solo ve los datos de su departamento (RLS filtra por unidad de negocio). Ambos ven diferentes distribuciones de los componentes (visibilidad de los componentes según el rol). Todo esto se consigue con una sola definición de informe.

Nota:

**Error habitual: falta de RLS en los objetivos de perforación**

Si un usuario pasa de una tabla de resumen protegida a una tabla de detalle que no tiene configurado el RLS, es posible que vea datos sin filtrar en la vista detallada. Asegúrate siempre de que RLS esté configurado en todas las tablas a las que se pueda acceder mediante la navegación de desglose.

**Tema principal:** [Permisos de informes y componentes](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
