---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Itinerarios de aprendizaje para administradores"
breadcrumb:
  - "TBM Studio"
  - "Itinerarios de aprendizaje (basados en funciones)"
source_path: "studio/new-uc/learning-path/lp-admin.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Itinerarios de aprendizaje para administradores

**Objetivo:** Configurar, proteger, optimizar y mantener TBM Studio para su organización

**A quién va dirigido:** Administradores de TBM Studio, gestores de la plataforma y cualquier persona responsable de la configuración del sistema, la gestión de usuarios y el soporte técnico en producción

## Fundamentos (1 hora)

**Lo que** aprenderás: Responsabilidades del administrador y conceptos básicos de la plataforma

**Objetivos de aprendizaje:**

- Comprender las funciones y responsabilidades del administrador
- Conoce el modelo de roles y permisos de usuario
- Comprender el ciclo de vida del desarrollo (Desarrollo → Prueba → Producción)
- Navegar por las interfaces administrativas
- Reconocer los conceptos clave de la plataforma

**Temas que hay que completar:**

1. **Resumen de las responsabilidades del administrador** (15 min) *→ Sección 6.1*
2. **Roles y permisos de usuario** (15 min) *→ Sección 6.2*
3. **Ciclo de vida del desarrollo** (20 min) *→ Sección 4.5*
4. **Arquitectura de la plataforma** (10 min) *→ Sección 4.2, 4.3*

**Requisitos previos:** Conocimientos básicos de TBM Studio (se recomienda completar el tutorial de inicio rápido)

## Habilidades básicas (4 horas)

**Lo que** aprenderás: Tareas administrativas cotidianas, como la gestión de usuarios, los permisos, las compilaciones y la seguridad

**Objetivos de aprendizaje:**

- Crear y gestionar usuarios y roles
- Configurar los ajustes del proyecto
- Ejecutar los procesos de registro y compilación
- Gestionar el flujo de trabajo desde el desarrollo hasta la producción
- Implementar la seguridad a nivel de fila (RLS)
- Supervisar y solucionar problemas en las compilaciones

**Temas que hay que completar:**

1. [Gestionar usuarios y roles (45 min)](../howtoguides/manage-users-permission/manage-up-intro.html)
2. **Configurar proyectos** (30 min) *→ Sección « 6.1 »*
3. **Flujo de trabajo de registro principal** (45 min) *→ Sección 4.5*
4. **Proceso de compilación y promoción** (60 min) *→ Sección 4.5*
5. [Implementar la seguridad a nivel de fila](../howtoguides/manage-users-permission/implement-rls.html) (45 min)
6. **Supervisar el estado del sistema** (15 min) *→ Sección 6.4*

**Requisitos previos:** haber completado el curso básico y disponer de acceso de administrador a un proyecto

**Tiempo estimado de práctica:** suma entre 2 y 3 horas de práctica en el entorno de desarrollo

## Avanzado (6 horas)

**Lo que** aprenderás: optimización del rendimiento, escenarios de seguridad complejos, recuperación ante desastres y optimización de plataformas

**Objetivos de aprendizaje:**

- Optimizar el rendimiento de la compilación y los tiempos de cálculo
- Gestionar componentes y dependencias
- Resolver problemas complejos relacionados con la compilación
- Gestionar la recuperación ante desastres y la reversión
- Configurar funciones avanzadas de actualización de datos y automatización
- Aplicar estrategias de ramificación
- Optimizar la plataforma para obtener un rendimiento óptimo

**Temas que hay que completar:**

1. **Optimización del rendimiento** (90 min) *→ Sección 6.4*
2. **Gestión de componentes** (45 min) *→ Sección 6.1*
3. **Solución avanzada de problemas de compilación** (60 min) *→ Sección 7.1, 7.3*
4. **Recuperación ante desastres y reversión** (45 min) *→ Sección 4.5*
5. **Actualización avanzada de datos** (30 min) *→ Sección 6.4*
6. **Estrategias de ramificación** (45 min) *→ Sección 4.5*
7. **Refuerzo de la seguridad** (45 min) *→ Sección 6.3*

**Requisitos previos:** haber completado el curso de «Habilidades básicas» y contar con experiencia práctica en soporte de producción

**Retos habituales:**

- **Compilaciones lentas:** utiliza Calc Explorer, simplifica los modelos y revisa la complejidad de las transformaciones
- **RLS no funciona:** comprueba la exactitud de la tabla de asignaciones y revisa las asignaciones de roles
- **Errores en la promoción:** comprueba minuciosamente en Stage y verifica si hay diferencias entre entornos
- **Quejas de los usuarios sobre el acceso:** revisar los permisos de forma sistemática y utilizar la suplantación de identidad para verificar
