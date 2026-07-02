---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Compatibilidad de la función «Vistas»"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
  - "Crear y gestionar vistas"
source_path: "admin/views-feature-compatibility.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Compatibilidad de la función «Vistas»

Aunque las vistas te ofrecen potentes funciones para organizar y controlar cómo se comparten los datos de costes y uso de la nube entre los usuarios de Cloudability, su compatibilidad varía actualmente según las distintas funciones de Cloudability. Algunas funciones son totalmente compatibles con Views, mientras que otras solo lo son parcialmente o tienen limitaciones específicas.

Este documento ofrece una guía de referencia para ayudarte a comprender qué funciones de Cloudability son compatibles con Views, en qué medida, y qué limitaciones o advertencias específicas hay que tener en cuenta al utilizar Views con determinadas funciones. Utiliza esta guía cuando planifiques tu estrategia de Views o resuelvas problemas relacionados con comportamientos inesperados en funciones específicas.

|  |  |  |
| --- | --- | --- |
| **Característica** | **Soporte técnico de Views** | **Limitaciones** |
| Panel de control e informes | Asistencia completa |  |
| TrueCost Explorer | Asistencia completa |  |
| Contenedores  y  Optimización del tamaño de los contenedores | Compatibilidad parcial | Solo se admiten vistas basadas en el ID de cuenta, el nombre de la cuenta, los grupos de cuentas y las dimensiones de proveedor. |
| Contenedor avanzado | No soportado | Pronto ofreceremos compatibilidad parcial (similar a la de los contenedores). |
| Tag Explorer | Asistencia completa |  |
| Detección de anomalías | Compatibilidad parcial | Solo se admiten las vistas basadas en el ID de la cuenta, el nombre de la cuenta, el servicio, la familia de uso y los 5 principales BM (según los detectados por el algoritmo de anomalías). |
| Inventario de recursos | Asistencia completa |  |
| Compromiso | Compatibilidad parcial | Vistas basadas en el ID de cuenta, los grupos de cuentas y las dimensiones de proveedor.  Además, si una vista se genera a través de una asignación empresarial y dicha asignación se basa en una combinación de cuentas o proveedores, sería compatible. |
| Dimensionamiento correcto | Apoyo total, salvo una salvedad → | Advertencia: cuando una vista se basa en una asignación empresarial, el menú desplegable «Cuentas» muestra todas las cuentas, incluidas aquellas que deberían estar restringidas por la vista. También puedes utilizar el filtro basado en grupos de cuentas en Views. |
| ROI de dimensionamiento correcto | Compatibilidad total, salvo una salvedad en la política de RS → | Advertencia: Al crear una política de reajuste (Configuración > Políticas de reajuste), el menú desplegable «Vistas» solo contiene vistas compartidas. |
| Presupuesto | Asistencia completa | Los presupuestos se definen en función de las vistas. La vista seleccionada en la parte superior determina qué presupuestos se muestran. Al seleccionar **«Mostrar todos los datos»,** se muestran los presupuestos de todas las vistas. |
| Previsión | Asistencia completa |  |
| Planes | Asistencia completa |  |
| Tablas de puntuación | Asistencia completa |  |
| Planificación de la carga de trabajo | No soportado | Las vistas no son aplicables a esta función. |
| Gobernabilidad | No soportado | Las vistas no son aplicables a esta función. |

**Tema principal:** [Crear y gestionar vistas](../admin/create-and-manage-views.html)
