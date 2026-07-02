---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Ámbito de aplicación del RLS: en qué casos se aplica el RLS"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Seguridad a nivel de fila (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/rls-scope.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ámbito de aplicación del RLS: en qué casos se aplica el RLS

RLS se puede aplicar en múltiples áreas de TBM Studio. Entender en qué casos se aplica —y en cuáles no— es fundamental para garantizar una cobertura de seguridad completa.

|  |  |  |
| --- | --- | --- |
| **Área** | **Comportamiento del síndrome de piernas inquietas** | **Notas** |
| Tablas de transformación ( Data Studio ) | Se aplica mediante un paso del proceso RLS añadido a cada tabla de forma individual | Al añadir un paso RLS, se añade automáticamente un paso de modelado. Solo las tablas modeladas y las tablas editables pueden tener RLS. |
| Objetos de modelo (Model Studio) | Los filtros RLS se transmiten desde las tablas de transformación subyacentes | Cada paso del modelo requiere su propia configuración de RLS. El RLS no se hereda automáticamente entre los pasos del modelo. |
| Informes (Report Studio) | Los informes muestran datos filtrados por RLS. Las agregaciones reflejan la vista filtrada. | Todas las tablas creadas con Ad Hoc Query están censuradas. Es posible que algunas tablas heredadas no lo estén. |
| Tablas editables | Los usuarios solo pueden ver y editar las filas que les permita su configuración de RLS | Las filas ocultas se conservan durante la publicación; no se eliminan ni se sobrescriben. |
| Informes generales sobre modelos | Cada nivel refleja el RLS aplicado a la tabla de ese nivel concreto | Es posible que la suma de los valores de un nivel no coincida con el total que se muestra en los niveles superiores si el RLS se aplica únicamente a los niveles inferiores. |
| Informes de desglose | RLS se aplica a la tabla perforada según la configuración de RLS propia de dicha tabla | La tabla derivada utiliza sus propias reglas RLS, no las de la tabla principal. |

Importante:

**Importante: RLS no se hereda automáticamente**

Las tablas no heredan automáticamente la configuración de RLS. Debes añadir un paso de RLS por cada paso del modelo que requiera seguridad de los datos. Si configura RLS en «Cost Source» pero no en «IT Resource Towers», es posible que los usuarios vean datos sin filtrar al consultar informes basados en «IT Resource Towers».

**Tema principal:** [Seguridad a nivel de fila (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
