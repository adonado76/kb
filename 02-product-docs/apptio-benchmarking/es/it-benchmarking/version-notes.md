---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Apéndice B: Notas sobre la versión y la compatibilidad"
breadcrumb:
  - "Benchmarking"
  - "Cómo empezar"
source_path: "it-benchmarking/version-notes.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Apéndice B: Notas sobre la versión y la compatibilidad

Este apéndice explica cómo IBM Apptio Benchmarking se alinea con las versiones de TBM y cómo interactúa con Costing.

Úsalo cuando alguien te pregunte:

- «¿Qué versión estamos usando?»
- «¿Por qué cambiaron las cosas después de la última actualización?»
- «¿Podemos reutilizar nuestra antigua configuración de Benchmarking?»

## Alineación de la taxonomía TBM

IBM Apptio El benchmarking utiliza la taxonomía y las estructuras de TBM para interpretar sus datos y compararlos con referencias externas.

Selección de la versión de TBM

En la configuración de Interactive Benchmarking, seleccione una versión de la taxonomía TBM ( ATUM ) (correspondiente a la versión de la taxonomía TBM con la que se alinean sus datos). Esa elección controla:

- ¿Qué grupos de costes, torres de recursos y subtorres de recursos existen?
- Cómo se agrupan y etiquetan las métricas de infraestructura
- ¿Qué definiciones y asignaciones de referencia están disponibles?

Directrices:

- Haga coincidir la versión de ATUM con la versión de TBM que utiliza su proyecto de cálculo de costes.
- Si está migrando a una nueva versión..
  - Confirm Interactive Benchmarking es compatible con la nueva versión de TBM.
  - Si es compatible, complete la migración en el lado de Costing antes de cambiar las versiones de Interactive Benchmarking ( configuration.Changing ) sin coordinación, ya que esto romperá las comparaciones y confundirá las tendencias.

Impacto en las métricas y la estructura

Los cambios de versión pueden:

- Añadir, eliminar o renombrar torres de recursos y subtorres de recursos
- Mover elementos de coste entre torres de recursos o grupos de costes
- Cambiar las métricas disponibles para cada área

Desde la perspectiva del usuario:

- Antes del cambio, las métricas se basaban en la estructura anterior
- Tras el cambio, las métricas se basan en la nueva estructura
- En algunos casos, no existe una traducción exacta entre ambos

Implicación práctica:

- Marca el año del cambio de versión como nueva referencia.
- No pretendas que los valores previos al cambio y posteriores al cambio son directamente comparables sin reexpresarlos.

## Relación con el cálculo de costes

El benchmarking y el cálculo de costes están estrechamente relacionados, pero no son lo mismo.

**Con integración de costes**

Cuando el benchmarking interactivo se integra con el cálculo de costes:

- La evaluación comparativa interactiva extrae el coste anual de TI de un proyecto de cálculo de costes seleccionado.
- Ese proyecto debe utilizar grupos de costes y torres de recursos de TBM que se ajusten a la versión de TBM seleccionada.
- Los puntos de referencia de infraestructura dependen de las asignaciones a nivel de subtorre de recursos si se desean métricas de coste unitario.

Ventajas:

- Obtienes cifras coherentes entre el cálculo de costes y la evaluación comparativa.
- Puede profundizar desde las diferencias en los puntos de referencia hasta las cuentas, los proveedores, las aplicaciones o los servicios.
- Puede mantener un único sistema de registro para los costes de TI.

Riesgos si no está alineado correctamente:

- Los puntos de referencia reflejarán una visión parcial o distorsionada del coste de las TI.
- Las conversaciones ejecutivas se estancarán en la reconciliación en lugar de en las decisiones.

**Sin integración de costes**

Puede utilizar Benchmarking sin costes cargando los costes anuales manualmente o mediante un archivo.

Aún puedes:

- Utilice los puntos de referencia de la industria y TI OpEx
- Utilice algunos puntos de referencia de Infra si proporciona el coste y el volumen por subtorre de recursos

Limitaciones:

- Sin retroceso a GL, proveedores o servicios dentro de Costing
- La actualización de datos es más manual y requiere más tiempo
- Más margen para inconsistencias en el alcance y la asignación

Este enfoque puede estar bien para un piloto. Para un uso prolongado, es muy recomendable la integración con Costing.

**Mantener la sincronización entre el benchmarking y el cálculo de costes**

Cuando los cambios en los costes afectan a la evaluación comparativa:

- Torres nuevas o reestructuradas
- Reclasificaciones importantes
- Cambios en el alcance (por ejemplo, añadir la nube, las telecomunicaciones o nuevas unidades de negocio)

Debes:

- Revisar la configuración y las asignaciones de benchmarking.
- Revalidar un pequeño conjunto estándar de vistas de referencia.
- Documentar que se produjo un cambio de modelo para ese año.

Si omite esto, verá saltos inexplicables en las vistas de referencia que en realidad son cambios en el modelo, no cambios operativos.
