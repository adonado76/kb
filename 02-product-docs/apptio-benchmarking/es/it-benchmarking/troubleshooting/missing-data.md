---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Datos faltantes o incompletos"
breadcrumb:
  - "Benchmarking"
  - "Informes comparativos"
  - "Solución de problemas y preguntas frecuentes"
source_path: "it-benchmarking/troubleshooting/missing-data.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Datos faltantes o incompletos

**Los gráficos o tablas completos están en blanco.**

Síntoma  
: Se carga una vista, pero todos los valores de su organización aparecen en blanco.   
Causas probables

- No hay datos sobre costes informáticos ni perfiles para el año seleccionado
- El benchmarking apunta al año equivocado o al proyecto de cálculo de costes
- La configuración de grupos de pares excluye a tu organización u oculta la métrica
- Dominio (industria/ OpEx /infraestructura) no habilitado por completo

Qué hay que comprobar

1. Confirme que el perfil de su organización y los datos de costes existen para ese año.
2. Compruebe la configuración de Benchmarking para el año activo y el proyecto de cálculo de costes.
3. Relaja los filtros (sector, tamaño, región) para ver si la métrica vuelve a aparecer.
4. Confirma que el dominio correspondiente está habilitado y no se encuentra en estado de error.

Respuesta breve que puede enviar  
: Este gráfico está en blanco porque no hay datos comparables para nosotros en el año y el grupo de referencia seleccionados. Una vez que actualicemos los datos subyacentes o ajustemos el grupo de referencia, aparecerán los valores.

**Faltan algunos gastos de torres de recursos o fondos comunes.**

Síntoma  
: Sabes que hay gastos en ciertas torres de recursos o grupos de costes en Costing, pero no aparecen en Benchmarking.   
Posibles causas

- Esos costes se asignan a torres de recursos personalizadas o grupos de costes que no se ajustan a las categorías estándar de TBM
- El gasto se encuentra en un proyecto de cálculo de costes que Benchmarking no está utilizando
- El conjunto de datos de referencia no admite esa torre de recursos para el grupo de pares seleccionado

Qué hay que comprobar

1. En Costing, confirme que esas torres de recursos/grupos de costes tienen un coste distinto de cero para el año seleccionado.
2. Verificar la correspondencia entre las estructuras locales y los grupos de costes/torres de recursos estándar utilizados por Benchmarking.
3. Comprueba qué proyecto de cálculo de costes está configurado para utilizar la evaluación comparativa y si el gasto se encuentra en ese proyecto.

Respuesta breve que puede enviar  
: La torre de recursos o el grupo de costes no se muestran porque están asignados a una categoría no estándar que no se ajusta a la taxonomía de referencia, o porque se encuentran en un proyecto de cálculo de costes que Benchmarking no utiliza. Una vez que alineemos el mapeo y la fuente, se mostrará en las vistas de referencia.

**Las métricas de infraestructura no aparecen, pero sí aparece « OpEx ».**

Síntoma: Las vistas  
 de Industria y TI ( OpEx ) muestran datos, pero las vistas de Infraestructura están vacías.   
Posibles causas

- Faltan datos sobre el volumen o la capacidad de las subtorres de recursos relacionadas con la infraestructura
- Las subtorres de recursos no se asignan correctamente a las definiciones de referencia

Qué hay que comprobar

1. Verificar los datos de coste **y** volumen de los recursos de infraestructura de las subtorres (servidores, almacenamiento, red, etc.).
2. Comprueba las unidades (por ejemplo, TB frente a GB, servidores físicos frente a virtuales).

Respuesta breve que puede enviar: Los puntos de   
referencia de Infra aún no están disponibles porque no hemos completado el mapeo de costes y volúmenes para las torres de recursos de infraestructura. Una vez que esté en su lugar, se completarán las métricas de costo unitario de infraestructura.
