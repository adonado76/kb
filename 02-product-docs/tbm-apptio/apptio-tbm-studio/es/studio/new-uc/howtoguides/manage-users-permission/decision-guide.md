---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía para la toma de decisiones: cómo elegir el sistema de control de acceso adecuado"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Gestionar usuarios y permisos"
  - "Control de accesos"
source_path: "studio/new-uc/howtoguides/manage-users-permission/decision-guide.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía para la toma de decisiones: cómo elegir el sistema de control de acceso adecuado

Utilice este marco de decisión para determinar qué mecanismo de control de acceso (o combinación de ellos) se adapta mejor a sus necesidades:

**Cuándo utilizar los permisos de informes**

- Quieres ocultar informes o paneles completos a determinados roles
- Los distintos roles necesitan acceso a diferentes conjuntos de informes
- Necesitas vistas específicas para cada rol de los mismos datos subyacentes (utilizando la visibilidad de los componentes)
- Desea restringir las funciones de creación de informes según el rol

**Cuándo utilizar la seguridad a nivel de fila**

- Los usuarios solo deben ver los datos relevantes para su ámbito organizativo (unidad de negocio, región, centro de coste)
- Varios inquilinos o divisiones comparten la misma instancia de TBM Studio
- Las restricciones de datos deben aplicarse de manera uniforme en todos los informes y tablas
- Necesitas un filtrado de datos muy preciso basado en la identidad del usuario

**Cuándo utilizar los permisos de tabla editable**

- Los equipos distribuidos deben gestionar sus propios datos (por ejemplo, los responsables de centros de coste que introducen los presupuestos)
- Quieres restringir quién puede introducir datos en tablas concretas
- Cada usuario debe editar las tablas editables que le correspondan en función de su rol
- Necesitas un control de auditoría sobre las actividades de introducción de datos

## Combinación de controles de acceso

Para garantizar una seguridad integral, combina varias medidas de protección. Una configuración empresarial típica podría incluir:

- **Permisos de informes** para controlar a qué paneles de control puede acceder cada rol
- **RLS** se encargará de que los directores de las unidades de negocio solo vean sus propios datos de costes
- **Permisos para editar las tablas,** de modo que cada equipo pueda gestionar sus propias tablas de correspondencias

Importante: RLS no protege los datos frente a los usuarios con privilegios de administrador. Los administradores tienen acceso al modo Studio y pueden crear informes que eludan el RLS, añadirse a las tablas de asignación del RLS o desactivar el RLS por completo. Diseña tu modelo de seguridad teniendo en cuenta esta limitación.

**Tema principal:** [Control de acceso](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
