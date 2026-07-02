---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Permisos del componente de carga de tablas"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Permisos de informes y componentes"
source_path: "studio/new-uc/concepts-architecture/security-model/table-upload-component-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permisos del componente de carga de tablas

El componente «Table Upload» permite un control de acceso avanzado mediante una tabla editable que asigna tablas específicas a roles concretos o a usuarios individuales. Esto permite a los administradores controlar qué usuarios pueden cargar datos en qué tablas sin necesidad de crear múltiples informes.

**Ejemplo — Configuración del acceso a la carga de tablas:**

|  |  |  |
| --- | --- | --- |
| **Tabla** | **Rol** | **Usuario** |
| Contratos Acme | Usuario avanzado | (cualquier usuario avanzado) |
| Libro mayor de Acme |  | bob@acme.com |
| Libro mayor de Acme |  | sally@acme.com |
| Esquema de la estructura organizativa de Acme IT |  | bob@acme.com |

En esta configuración, Bob ve «Libro mayor general de Acme» y «Asignación de la organización de TI de Acme» en el menú desplegable de carga. Sally tiene acceso a «Acme Contracts» (gracias a su rol de usuaria avanzada) y a «Acme General Ledger». Los usuarios que no figuran en la lista no ven ninguna tabla disponible para cargar.

**Tema principal:** [Permisos de informes y componentes](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
