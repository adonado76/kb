---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración del enlace de datos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: filtros y segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/data-binding-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración del enlace de datos

**Configuración del campo de origen**

Los filtros se rellenan a partir de los campos de las vistas. El tipo de campo determina el comportamiento del filtro:

|  |  |
| --- | --- |
| **Tipo de campo** | **Comportamiento del cortador** |
| Texto/Etiqueta | Crea un filtro de lista con valores seleccionables |
| Numérico | Crea un filtro deslizante con controles de rango |
| Fecha | Crea un filtro de lista con orden cronológico |
| Campo bloqueado | Ofrece resultados más predecibles; imprescindible para las cortadoras compactas de uso general |
| Campo desbloqueado | , Ofrece resultados satisfactorios |

**Para añadir un filtro:**

1. En la pestaña «Informe», haz clic en «Filtro de filas»
2. Arrastra un campo desde una perspectiva al área «Cortar por»
3. Configura el aspecto y el comportamiento en la pestaña «Slicer»

**Opciones de ordenación de valores**

Los valores del filtro se pueden ordenar de dos maneras mediante las opciones de ordenación de la pestaña «Filtro»:

|  |  |
| --- | --- |
| **Opción de ordenación** | **Comportamiento** |
| Por estado | Agrupa los valores por estado (Seleccionados → Relacionados → No relacionados) y, a continuación, los ordena alfabéticamente dentro de cada grupo |
| abc/123 | Ordena todos los valores alfabéticamente, independientemente del estado |

**Orden predeterminado por tipo de datos:**

- Texto: Por orden alfabético
- Números: Ascendente
- Fechas: por orden cronológico

Nota: Los usuarios que consultan el informe no pueden modificar la opción de ordenación, ya que esta la establece el diseñador del informe.

**Tema principal:** [Componentes de los informes: Filtros y segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
