---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Patrones habituales"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes de los informes: tablas editables en los informes"
source_path: "studio/new-uc/reference/report-studio-reference/common-patterns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Patrones habituales

Los siguientes patrones representan implementaciones típicas de componentes de tablas editables.

**Flujo de trabajo de la entrada presupuestaria**

Permitir a los responsables de centros de coste introducir previsiones presupuestarias:

1. Crea una tabla en blanco y editable en Data Studio con columnas para centro de coste, cuenta, período e importe
2. Configure RLS para que cada responsable vea únicamente su propio centro de costes
3. Añadir el componente de tabla editable a un informe de partidas presupuestarias
4. Incluye un validador de fila total para garantizar que los importes se sumen correctamente
5. Configura una programación de publicación periódica para actualizar el modelo a diario

**Flujo de trabajo de enriquecimiento de datos**

Permitir a los usuarios añadir clasificaciones a los datos importados:

1. Crear una tabla enriquecida y editable basada en la transformación de origen (por ejemplo, datos del libro mayor)
2. Añadir columnas editables para los campos de clasificación (por ejemplo, Solución, Categoría, Subcategoría)
3. Configurar menús desplegables en cascada para garantizar que solo se muestren combinaciones válidas
4. Establezca las columnas de origen como de solo lectura para conservar los datos originales
5. Los usuarios enriquecen los datos sin modificar la importación original

**Integración del flujo de trabajo de aprobación**

Seguimiento del estado de aprobación y de los comentarios:

1. Añadir las columnas «Estado» y «Responsable de la aprobación» con valores desplegables (Pendiente, Aprobado, Rechazado)
2. Configure el permiso «Editar fila» para restringir la aprobación a los roles autorizados
3. Utiliza la función «Mostrar cambios» para saber quién tomó las decisiones de aprobación
4. Habilita las columnas «.Username» y «.EditDate » para que muestren información de auditoría

**Tema principal:** [Componentes de los informes: Tablas editables en los informes](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
