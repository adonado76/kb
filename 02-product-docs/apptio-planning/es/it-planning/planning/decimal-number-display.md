---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Visualización de números decimales"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/decimal-number-display.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Visualización de números decimales

La visualización de números decimales controla cómo se formatean y muestran los valores numéricos en Apptio Planning. Esta configuración permite a los administradores definir el número de decimales que se utilizan para todos los datos numéricos, lo que garantiza una visualización coherente en todos los planes, informes y exportaciones.

Nota: Solo los usuarios con roles de administrador o propietario del proceso presupuestario pueden realizar estas tareas.

## Controles de visualización de números decimales

Cuando está habilitada, la configuración de visualización decimal se aplica a **todas las columnas numéricas**, incluyendo:

- Valores del año fiscal y del período (importes mensuales, trimestrales y anuales)
- Atributos enteros y numéricos
- Cantidades tales como número de empleados, ETC, horas y porcentajes

Esta configuración **solo** afecta a la visualización; los cálculos siempre conservan toda su precisión en el sistema.

**Cómo habilitar la visualización de números decimales**

1. Vaya a **Configuración (icono de engranaje)** → **Perfil de la empresa**.
2. En la sección **Formato numérico**, habilite **la opción Visualización de números decimales**.
3. Seleccione el número de decimales que desea mostrar (por ejemplo, 0-8).
4. Seleccione **Guardar y salir** para aplicar la configuración.

## Comportamiento predeterminado cuando se desactiva la visualización de números decimales

Cuando **la opción «Visualización de números decimales» está desactivada (configuración predeterminada)**, los valores numéricos se muestran utilizando los valores predeterminados específicos de la vista. Estos valores predeterminados varían según el módulo y el caso de uso para lograr un equilibrio entre la legibilidad y la precisión.

**Vistas que muestran por defecto 0 decimales**

- Vistas de resumen
- Contratos
- Activos
- Otras pestañas no relacionadas con el personal
- Gestión del gasto
- Comparativas (vistas comparativas)

**Vistas que muestran por defecto dos decimales**

- Trabajo
- Actividad laboral (valores en ETC)

**Visualización de decimales en el análisis de desviaciones**

- **Los valores reales** se muestran con **0 decimales**
- **Los totales y los importes de las variaciones** se muestran con **dos decimales.**
