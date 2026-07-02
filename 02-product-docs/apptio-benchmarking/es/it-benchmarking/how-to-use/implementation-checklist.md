---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Lista de verificación de implementación"
breadcrumb:
  - "Benchmarking"
  - "Cómo utilizar esta guía"
source_path: "it-benchmarking/how-to-use/implementation-checklist.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Lista de verificación de implementación

Antes de empezar

**Antes de empezar**

- Confirmar que los productos son visibles en Frontdoor
  - La evaluación comparativa es visible.
  - El cálculo de costes es visible, si planeas integrarlo (muy recomendable).
- Si se integra con Costing, identifique el proyecto Costing del sistema de registro
  - Seleccione qué proyecto de cálculo de costes actuará como fuente para el gasto real en TI.
  - La propiedad y el control de los cambios del proyecto de cálculo de costes están claros.
- Asignar roles
  - Se ha identificado al responsable del programa TBM/ITFM.
  - TBMA primario / analista designado como propietario de la evaluación comparativa.
  - Apptio Administrador de la plataforma identificado.
  - Se identificaron los propietarios de los recursos clave (por ejemplo, computación, almacenamiento, red, etc.).

**Preparación de datos**

- Datos del perfil organizativo disponibles
  - Últimos **ingresos** anuales completos para el ámbito de su organización de TI que se está evaluando.
  - Último **FTE** (equivalente a tiempo completo) anual para ese mismo ámbito.
  - Clasificación **industrial** acordada asociada con su organización de TI.
  - **Región** acordada (global frente a región específica) y lógica de rango de tamaño.
- Datos sobre gastos en TI disponibles para al menos un año completo
  - Gasto anual en TI asignado a **los grupos de costes** de TBM.
  - Gasto anual en TI asignado a **las torres de recursos** de TBM.
- Volúmenes de infraestructura (si se utilizan puntos de referencia de infraestructura)\*
  - Recuento de dispositivos/capacidad por subtorre, por ejemplo:
    - Servidores (físicos/virtuales según sea necesario)
    - Almacenamiento (TB de capacidad útil)
    - Red (puertos, dispositivos o unidades relevantes)
  - Recuento de FTE para funciones de infraestructura importantes, si se prevé utilizar métricas de eficiencia de FTE.

\* *Si no puede marcar todos los elementos de infraestructura, puede comenzar con los puntos de referencia de Industria y OpEx y añadir la infraestructura más adelante.*

**Entorno y configuración**

- Acceso verificado
  - Los administradores de TBMA pueden iniciar sesión en **IBM Apptio Benchmarking**.
  - Si se integra Costing, TBMA/los administradores pueden iniciar sesión en el proyecto **Costing** elegido.
  - Los consumidores clave pueden ver, como mínimo, los informes de evaluación comparativa que se espera que utilicen.
- Conjunto de versiones de taxonomía
  - Versión de TBM seleccionada en Benchmarking para ajustarse al proyecto de cálculo de costes.
  - Cualquier torre de recursos/grupo de costes no estándar asignado a equivalentes estándar o excepciones documentadas.
- Perfil organizativo configurado en Benchmarking
  - Los ingresos y el número de empleados introducidos coinciden con el alcance de la organización de TI.
  - La industria y la región están configuradas correctamente.
  - Cualquier factor adicional que aumente la complejidad, si está disponible.
- Datos de costes conectados o cargados
  - Si se integra con Costing:
    - El benchmarking apunta al proyecto de cálculo de costes correcto.
    - Año fiscal/período correcto seleccionado para los puntos de referencia.
  - Si no está integrado:
    - Gasto anual en TI por grupo de costes y torre de recursos cargado manualmente.
    - Moneda y año fiscal claramente definidos.
- Datos de infraestructura configurados (si procede)
  - Coste de infraestructura asignado a subtorres alineadas con la taxonomía de referencia.
  - Datos de volumen/capacidad cargados para esas subtorres.
  - Unidades de medida validadas (GB frente a TB, físicas frente a virtuales, etc.)
- Valores predeterminados del grupo de pares definidos
  - Grupo de referencia predeterminado seleccionado (sector, rango de tamaño, región).
  - Cualquier política de filtrado adicional acordada (por ejemplo, cuándo restringir o ampliar).
  - Grupo de pares predeterminado documentado para su reutilización en informes ejecutivos.

**Validación y primer uso**

- Prueba de humo: vistas principales
  - Métricas del sector:
    - Gasto en TI frente a ingresos y frente a empleados.
  - OpEx: de TI
    - Distribuciones del fondo común de costes y la torre de recursos.
  - Infraestructura:
    - Al menos una métrica de coste unitario (si se han configurado los datos de infraestructura).
- Comprobaciones de validez superadas
  - Los totales de gastos en TI concuerdan con los datos financieros del año seleccionado.
  - No hay valores atípicos evidentes ( 10x ) debidos a errores unitarios o mapeo incorrecto.
  - Todas las principales torres de recursos y reservas de costes que esperas están presentes y son distintas de cero.
  - El grupo de pares y el año que se muestran coinciden con lo que usted pretende discutir.
- Paquete inicial para las partes interesadas preparado
  - 3-5 gráficos seleccionados:
    - 1 Perspectiva del sector
    - 1 Distribución de la tecnología de la información ( OpEx )
    - 1-2 Vistas de infraestructura (si procede)
  - Breve narrativa redactada para cada uno:
    - Dónde estamos en la fila.
    - En qué nos diferenciamos.
    - Dónde tenemos previsto investigar más a fondo.
- Sesión introductoria con el patrocinador celebrada
  - El responsable de TBM y el responsable de TBMA acompañan al patrocinador (CIO/VP/Finanzas) a través de:
    - ¿Qué es el benchmarking?
    - Con quién nos comparamos.
    - Principales conclusiones iniciales.
  - Decisiones documentadas:
    - Métricas que supervisaremos.
    - Torres de recursos / áreas en las que nos centraremos.
    - Con qué frecuencia volveremos a visitarlo.

**Gobernanza y operaciones en curso**

- Cadence aceptó
  - Anual:
    - Actualización completa de datos y puntos de referencia alineados con el ciclo de planificación.
    - Revisión y confirmación por parte de un grupo de pares.
  - Trimestral:
    - Revisión de los indicadores clave de referencia y las deficiencias de la Torre de Recursos en la revisión trimestral de negocios (QBR) / dirección.
  - Ad hoc:
    - Utilizar puntos de referencia para los principales casos de negocio e iniciativas de Resource Tower.
- Cambiar las políticas definidas
  - Se requiere aprobación (responsable de TBM) para:
    - Cambio de la versión de TBM en Benchmarking.
    - Cambio del proyecto de cálculo de costes principal.
    - Cambiar las selecciones predeterminadas del grupo de pares.
    - Añadir o eliminar categorías de costes importantes del alcance del benchmark.
  - Permitir la discreción de TBMA (con documentación) para:
    - Correcciones menores en el mapeo.
    - Vistas experimentales con grupos de pares alternativos claramente etiquetados.
- Documentación disponible
  - Documento de una página guardado que recoge lo siguiente:
    - Proyecto de cálculo de costes utilizado
    - Versión TBM
    - Grupo de pares predeterminado
    - Cadencia de actualización de datos
  - Notas de mapeo para cualquier decisión de ámbito no obvia, por ejemplo:
    - «El gasto en telecomunicaciones se incluye en la torre de red»
    - «El servicio compartido X se asigna íntegramente a la gestión de TI»
  - Enlace a esta guía de ayuda sobre evaluación comparativa compartida con TBMA, propietarios de torres de recursos y socios financieros clave.

Si se cumplen todas las condiciones anteriores, el benchmarking no solo está configurado técnicamente, sino que es realmente utilizable, explicable y regulado.
