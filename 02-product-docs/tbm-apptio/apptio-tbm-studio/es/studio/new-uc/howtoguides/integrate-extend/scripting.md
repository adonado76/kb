---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Programación"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Integrar y ampliar"
source_path: "studio/new-uc/howtoguides/integrate-extend/scripting.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Programación

|  |  |
| --- | --- |
| **Tipo de contenido** | Guía práctica |
| **Destinatarios** | Analistas de negocios, desarrolladores |
| **Requisitos previos** | Conocimientos básicos de TBM Studio y comprensión del funcionamiento de las tablas editables |

ApptioScript es el lenguaje de programación de TBM Studio para crear aplicaciones empresariales interactivas. Te permite automatizar operaciones con datos, implementar lógica de negocio y crear procesos basados en flujos de trabajo que van más allá de las funciones integradas de TBM Studio.

Esta sección contiene dos guías prácticas: la primera presenta los conceptos básicos de « ApptioScript » y te muestra cómo escribir [tus primeros scripts](htg-write-as.html), mientras que la segunda aborda [patrones habituales](htg-use-common-pattern.html) que puedes adaptar a tus situaciones empresariales. Para consultar la documentación completa de la función, véase la sección « 5.6: » en la referencia de ApptioScript.

**Qué puedes hacer con « ApptioScript »**

- **Automatizar la introducción y actualización de datos** : añadir, editar o eliminar filas en tablas editables mediante programación
- **Implementar flujos de trabajo empresariales** : crear procesos de aprobación, cambios de estado y notificaciones automáticas
- **Controla la experiencia del usuario** : configura las celdas como obligatorias o de solo lectura según las condiciones, e implementa menús desplegables en cascada
- **Crear registros de auditoría** : realiza un seguimiento automático de quién ha editado los datos y cuándo
- **Copiar y transformar datos** : mover datos entre tablas, proyectos o periodos de tiempo
- **Enviar notificaciones** : activa el envío de correos electrónicos cuando se cumplan determinadas condiciones

## Cuándo utilizar « ApptioScript » frente a las funciones integradas

TBM Studio ofrece numerosas funciones integradas. Utiliza « ApptioScript » cuando necesites un comportamiento que vaya más allá de la configuración estándar.

|  |  |  |
| --- | --- | --- |
| **Situación** | **Función integrada** | **¿Cuándo utilizar « ApptioScript »?** |
| Listas desplegables sencillas | Columna: Valores posibles | Utiliza este script para crear menús desplegables en cascada con lógica compleja |
| Validación de datos | Reglas de validación en la configuración de la columna | Utilizar un script para la validación entre campos |
| Valores calculados | Métricas calculadas | Utiliza el script para realizar cálculos a nivel de fila en tablas editables |
| Notificaciones al usuario | No disponible | Utilizar la función ` SendEmail( )` |
| Cambios en el estado del flujo de trabajo | No disponible | Utilizar « EditRows( )» con acciones de botones |
| Registros de auditoría | Registro de auditoría del sistema | Utilizar un script para el seguimiento de las modificaciones visibles para el usuario en las tablas |

- **[Guía práctica: Cómo escribir fórmulas en ApptioScript](../../../../studio/new-uc/howtoguides/integrate-extend/htg-write-as.html)**
- **[Guía práctica: Cómo utilizar patrones de script habituales](../../../../studio/new-uc/howtoguides/integrate-extend/htg-use-common-pattern.html)**
