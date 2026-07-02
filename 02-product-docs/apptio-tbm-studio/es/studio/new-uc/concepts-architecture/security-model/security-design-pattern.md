---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Patrones de diseño de seguridad"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Buenas prácticas de seguridad"
source_path: "studio/new-uc/concepts-architecture/security-model/security-design-pattern.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Patrones de diseño de seguridad

Los siguientes patrones abordan situaciones habituales relacionadas con la seguridad en TBM Studio. Utilícelos como punto de partida y adáptelos a las necesidades específicas de su organización.

**Modelo 1: Acceso basado en roles según la función laboral**

|  |  |
| --- | --- |
| **Aspecto** | **Detalles** |
| Situación | Los distintos equipos necesitan distintos niveles de acceso: los analistas financieros elaboran modelos, los jefes de departamento consultan informes y los ejecutivos consultan paneles de control con resúmenes. |
| Implementación | Crea tres roles: «Creador de modelos» (usuario avanzado + permisos de modelos), «Visor de informes» (usuario empresarial + acceso a una colección específica de informes) y «Ejecutivo» (usuario empresarial + acceso a una colección de paneles ejecutivos). |
| RLS | No es necesario si todos los roles deben tener acceso a todos los datos. Aplica RLS solo si hay roles que deban tener acceso a datos restringidos. |
| Permisos del informe | Asigna colecciones de informes a roles específicos. Utiliza la visibilidad de los componentes para mostrar diferentes diseños de gráficos a los ejecutivos y a los analistas. |

**Modelo 2: Jerarquía organizativa**

|  |  |
| --- | --- |
| **Aspecto** | **Detalles** |
| Situación | Los jefes de equipo deben ver los datos de sus equipos, los directores deben ver los de sus departamentos y los vicepresidentes deben ver los de sus divisiones. |
| Implementación | Crea tablas de correspondencias que reflejen la jerarquía de la organización. El mapa de cada responsable incluye los centros de coste de su equipo. Las asignaciones de los directores incluyen todos los centros de coste de sus departamentos. |
| RLS | Aplica el filtrado RLS por centro de coste o unidad organizativa. Si es necesario, utiliza varias tablas de correspondencias para gestionar la jerarquía de forma clara. |
| Acceso completo | Crea una tabla de asignación independiente con acceso completo para los vicepresidentes y ejecutivos que necesiten ver todos los datos, utilizando el patrón de indicador «Is Admin». |

**Patrón 3: Datos multitenant**

|  |  |
| --- | --- |
| **Aspecto** | **Detalles** |
| Situación | Varias unidades de negocio comparten una única instancia de TBM Studio, pero solo deben ver sus propios datos. |
| Implementación | Crear tablas de correspondencias de RLS ordenadas por unidad de negocio. Cada usuario está asignado a una o varias unidades de negocio. Aplica RLS a todas las tablas que contengan datos de la unidad de negocio. |
| Exhaustividad del RLS | Importante: RLS debe aplicarse a TODAS las tablas del modelo que contengan datos específicos de las unidades de negocio, incluidos los destinos de desglose. Si falta un RLS en cualquier tabla, se produce una fuga de datos. |
| Pruebas | Utilice el filtro de vista previa y la suplantación de identidad para comprobar que los usuarios de cada unidad de negocio solo vean sus propios datos en todos los informes y rutas de desglose. |

**Tema principal:** [Prácticas recomendadas de seguridad](../../../../studio/new-uc/concepts-architecture/security-model/security-best-practices.html)
