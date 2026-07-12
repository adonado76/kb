---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Seguridad y cumplimiento normativo"
breadcrumb:
  - "TBM Studio"
  - "Administración"
source_path: "studio/new-uc/admin/sec-comp.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Seguridad y cumplimiento normativo

**Tipo de contenido:** Conceptual / Guía práctica

**Destinatarios:** Administradores, responsables de seguridad

**Requisitos previos:** rol de administrador, conocimientos sobre los requisitos de seguridad de los datos

TBM Studio ofrece múltiples capas de seguridad para proteger los datos financieros confidenciales y garantizar el cumplimiento de las políticas de la organización. En esta sección se tratan los ajustes de seguridad de los dominios, la seguridad a nivel de fila y las prácticas de gobernanza de datos.

## Configuración de seguridad del dominio

La configuración de seguridad del dominio controla las políticas de autenticación, los requisitos de contraseña y la gestión de sesiones para todos los usuarios del entorno de Apptio.

**Para acceder a la configuración de seguridad del dominio:**

1. Ve a la pestaña «**Proyecto** ».
2. Haz clic **en «Seguridad del dominio** ».
3. Configure las políticas de contraseñas, los ajustes de sesión y las opciones de autenticación.

**Configuración de la política de contraseñas**

|  |  |
| --- | --- |
| **Valor** | **Descripción** |
| Longitud mínima de la contraseña | Número mínimo de caracteres requerido para las contraseñas |
| Antigüedad mínima de la contraseña | El número de días que deben transcurrir antes de poder cambiar una contraseña. El valor de « -1 » significa «ilimitado». |
| Antigüedad máxima de la contraseña | Días que faltan para que caduque la contraseña y haya que cambiarla. El valor de « -1 » significa «ilimitado». |
| Historial de contraseñas | Número de contraseñas anteriores que no se pueden volver a utilizar |

## Seguridad a nivel de fila (RLS)

La seguridad a nivel de fila garantiza que los usuarios solo vean los datos a los que tienen autorización para acceder. RLS filtra los datos a nivel de fila en función de los atributos de los usuarios, lo que permite que un mismo informe muestre datos diferentes a distintos usuarios.

**Ámbito de aplicación del RLS:**

- **Tablas de transformación** : filtran las filas visibles antes de que los datos se incluyan en los informes
- **Tablas editables** : restringe los datos que los usuarios pueden ver y modificar
- **Informes** : las agregaciones reflejan únicamente la vista filtrada de cada usuario

**Nota:** *Al publicar tablas editables con RLS habilitado, las filas que el usuario no puede ver se conservan, no se sobrescriben. Esto evita la pérdida de datos cuando los usuarios publican sus cambios.*

## Prácticas de gobernanza de datos

Una gestión eficaz de los datos garantiza la calidad, la seguridad y el cumplimiento normativo de los datos. TBM Studio ofrece varias funciones para facilitar los flujos de trabajo de gobernanza.

## Periodos de cierre

Los periodos cerrados impiden la modificación de datos, aunque permiten seguir generando informes. Utilice períodos cerrados para los ejercicios fiscales ya finalizados a fin de mantener la integridad de los datos.

## Normas sobre la actualidad de los datos

Las reglas de actualidad de los datos supervisan cuándo se actualizan las tablas y envían notificaciones si los datos quedan obsoletos. Esto contribuye a garantizar que los datos se carguen a tiempo y evita que los informes se basen en información desactualizada.

**Para crear una regla de actualización de datos:**

1. Ve a **Proyecto > Reglas de actualización de datos**.
2. Haz clic en **«Crear regla»** y especifica la frecuencia de actualización deseada.
3. Configura las notificaciones por correo electrónico para las actualizaciones que te hayas perdido.
4. Asociar las reglas a una o varias tablas.

## Linaje de datos

El linaje de datos realiza un seguimiento del flujo de datos a lo largo de tu proyecto de TBM Studio, mostrando de dónde proceden los datos, cómo se han transformado y dónde se utilizan. El historial es fundamental para el análisis de impacto y la resolución de problemas.

**Casos de uso de Lineage:**

- **Análisis de impacto** : comprender qué se vería afectado al modificar o eliminar una columna o una tabla
- **Limpieza** : identificar tablas huérfanas o métricas calculadas que no se utilizan
- **Protección de datos** : localiza dónde se encuentran y están expuestos los datos confidenciales

**Para acceder al árbol genealógico:**

- Haz clic con el botón derecho del ratón en cualquier entidad del Explorador de proyectos y selecciona **«Rastrear linaje» para este documento**
- Haz clic con el botón derecho del ratón en la pestaña del documento situada en la parte inferior del espacio de trabajo y selecciona **«Rastrear linaje».**
