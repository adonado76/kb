---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Recomendaciones de configuración"
breadcrumb:
  - "TBM Studio"
  - "Solución de problemas y asistencia técnica"
  - "Explicación de los mensajes de error"
source_path: "studio/new-uc/ts-support/em-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recomendaciones de configuración

En esta sección se ofrecen explicaciones y soluciones para los mensajes de error más habituales en TBM Studio. Accede a las recomendaciones a través de TBM Studio > pestaña «Recomendaciones».

|  |  |  |
| --- | --- | --- |
| **Mensaje de error** | **Significado** | **Solución** |
| La tabla de ratios de asignación es demasiado grande | La tabla de ratios de asignación supera los límites de tamaño, lo que afecta al rendimiento | Añadir relación entre datos, añadir filtros «De/A», eliminar las filas de identificadores |
| No hay identificador en el objeto de modelo grande | Un objeto de modelo de gran tamaño carece de identificador, lo que provoca problemas de rendimiento | En el menú desplegable «Filas», seleccione «Usar identificador de objeto» y elija las columnas necesarias |
| Se utiliza la operación de unión del modelo heredado | La asignación utiliza una configuración automática de relaciones de tipo « R11-era » | Desmarcar la casilla de verificación «Relación automática» y establecer columnas explícitas |
| Umbral limitado: Expansión de filas | LookupEx, SplitEx, o Unpivot supera el límite de filas | Reducir las relaciones uno a muchos, limitar la expansión de datos, reducir el número de columnas |
| Se ha superado el número máximo de registros permitido | El proyecto ha alcanzado el número máximo de métricas | Elimina las métricas que no se utilicen a través de Explorador de proyectos > Métricas |
| Se ha superado el número de columnas del paso «Transformar modelo» | La tabla con los pasos del modelo supera el límite de columnas | Añade el paso «Ocultar y renombrar» para ocultar las columnas que no sean necesarias |
