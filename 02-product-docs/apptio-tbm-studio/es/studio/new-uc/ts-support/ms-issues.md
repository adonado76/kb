---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Problemas con Model Studio"
breadcrumb:
  - "TBM Studio"
  - "Solución de problemas y asistencia técnica"
  - "Problemas habituales y soluciones"
source_path: "studio/new-uc/ts-support/ms-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Problemas con Model Studio

## La asignación no funciona como se esperaba

**Síntomas:**

- Los costes no se ajustan a los objetivos previstos
- Costes no asignados restantes tras la asignación
- Valores nulos en los objetos de destino

**Soluciones:**

1. **Comprueba la cobertura de los datos del controlador** : abre la tabla de controladores y comprueba que contenga valores para todas las entidades de destino. Considera la posibilidad de añadir un fondo residual para cubrir las deficiencias.
2. **Comprueba las relaciones entre los datos** : abre el paso de asignación y comprueba que la columna de origen y la columna de destino estén correctamente asignadas.
3. **Soluciona los problemas de asignación heredados** : si ves que la casilla «Relación automática» está marcada, desmárcala y configura manualmente las columnas de origen y destino.

Advertencia: Una vez que se registren los cambios para sustituir una asignación heredada, no se podrá volver a habilitar la configuración heredada. Prueba a fondo el código en el entorno de desarrollo antes de integrarlo.

## El cálculo del modelo tarda demasiado

**Síntomas:**

- Las compilaciones tardan horas en completarse
- El entorno de pruebas suele estar desactualizado
- Los usuarios notan que los informes tardan en cargarse

**Soluciones:**

1. **Analizar la complejidad del modelo** : utilice el componente «Revisión del rendimiento» para identificar las áreas problemáticas. Céntrate en reducir las asignaciones en los niveles inferiores del modelo.
2. **Añadir identificadores a objetos de gran tamaño** : ve al objeto del modelo marcado. En el menú desplegable «Filas», selecciona «Usar identificador de objeto».
3. **Reducir el tamaño de la tabla de ratios de asignación** : añadir relaciones entre datos para limitar el alcance de la asignación. Añade filtros «De» o «A».
4. **Elimina los elementos que no se utilizan** : borra las métricas que no se utilizan a través del panel «Recomendaciones». Elimina las asignaciones que no se utilicen y desactiva los informes que no se utilicen.
