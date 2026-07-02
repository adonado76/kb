---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Métricas calculadas"
breadcrumb:
  - "Cloudability Premium"
  - "Configuración"
  - "Organiza tus gastos en la nube"
source_path: "admin/calculated_metrics.html"
images:
  - "images/calculated-metric-add-button.png"
  - "images/calculated-metric-create-modal.png"
  - "images/calculated-metric-delete-dropdown.png"
  - "images/calculated-metric-delete-message.png"
  - "images/calculated-metric-details-page.png"
  - "images/calculated-metric-edit-dropdown.png"
  - "images/calculated-metric-update-modal.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Métricas calculadas

## ¿Qué son las métricas calculadas?

Las métricas calculadas son métricas personalizadas y reutilizables que puedes crear en Cloudability utilizando métricas estándar, métricas de negocio, constantes y operaciones aritméticas básicas.

A diferencia de las métricas proporcionadas por los proveedores, las métricas calculadas ofrecen flexibilidad para definir indicadores clave de rendimiento (KPI) específicos para cada negocio y medidas de rentabilidad por unidad que se ajusten a los requisitos particulares de tu organización.

Las métricas calculadas admiten las siguientes operaciones aritméticas:

- Suma (`+`)
- Resta (`-`)
- Multiplicación (`*`)
- División (`/`)

Estas métricas ayudan a adaptar los informes de « Cloudability » a los casos de uso empresariales y financieros específicos de su organización. Las métricas calculadas permiten a los equipos crear indicadores clave de rendimiento (KPI) reutilizables que pueden emplearse de forma coherente en todos los paneles de control e informes sin necesidad de volver a crear las fórmulas una y otra vez.

## ¿Cómo funcionan las métricas calculadas?

Evaluado en el momento de la consulta

Cuando se carga un panel o un informe, Cloudability evalúa las métricas calculadas en función del conjunto de resultados agregados. Esto significa que los cálculos se realizan sobre los datos agregados finales, en lugar de sobre las partidas de costes individuales, durante la importación de datos.

Este enfoque ofrece varias ventajas:

- Las métricas están disponibles inmediatamente después de su creación
- No es necesario volver a procesar los datos
- Los informes históricos reflejan automáticamente las actualizaciones de las fórmulas
- Los cambios se aplican al instante en todos los informes y paneles de control

Aplicado a los resultados agregados

Las métricas calculadas se aplican a datos agregados tras su agrupación y resumen. Esto significa que la fórmula se aplica a los totales, las medias u otros valores agregados, en lugar de a las filas individuales.

Consejos para crear métricas calculadas

Elige un nombre claro

Cada métrica calculada debe tener un nombre único. Elige un nombre que transmita claramente su finalidad, ya que aparecerá en los informes y en todo el sitio web Cloudability. El nombre debe ser único dentro de tu organización y no puede coincidir con los nombres de medidas básicas ya existentes.

Selecciona la fuente de datos adecuada

Elige entre «Coste» o «Uso» como fuente de datos. Todas las medidas a las que se hace referencia en tu fórmula deben coincidir con el tipo de fuente de datos seleccionado.

Definir una fórmula clara

Crea fórmulas utilizando nombres de medidas válidos, constantes y operadores aritméticos. Asegúrate de utilizar correctamente los paréntesis para controlar el orden de las operaciones.

Añadir una descripción

Proporcione una descripción clara que explique la finalidad de la métrica y su lógica de cálculo. Esto ayuda a otros usuarios a comprender y aplicar correctamente la métrica en sus informes.

## Trabajar con métricas calculadas

Listado y revisión de métricas calculadas

Desde la página «Asignaciones de negocio», puedes ver todas las métricas calculadas que hayas creado. La lista muestra el nombre de la métrica, la descripción, la fuente de datos y los detalles de creación.

Creación de nuevas métricas calculadas

Para crear una nueva métrica calculada:

1. Ve a **«Organizar» → «Asignaciones empresariales»**
2. Selecciona **«Nueva métrica calculada»** en el menú desplegable **«Nueva dimensión empresarial».**

   ![Nuevo botón «Métrica calculada»](../../../../03-media/cloudability-premium/images/calculated-metric-add-button.png)
3. Introduce un **nombre** para la métrica
   - El nombre debe ser único dentro de tu organización
   - No se pueden encontrar nombres de medidas base que coincidan
4. Añadir una **descripción**
   - La descripción aparece como una información emergente cuando se utiliza la métrica en los paneles de control o en los informes
   - Ayuda a otros usuarios a comprender la finalidad de la métrica
5. Selecciona un **tipo de medida** (formato numérico)
   - **Número** : formato predeterminado para valores numéricos generales
   - **Importe** : para valores monetarios o de coste
   - **Porcentaje** : para cálculos de proporciones o porcentajes
6. Selecciona la **fuente de datos**
   - **Coste** : utiliza métricas relacionadas con el coste (por ejemplo, «unblended\_cost», «amortized\_cost»)
   - **Uso** : utiliza métricas de utilización (por ejemplo, avg\_cpu\_utilization, memory\_usage)
   - Todas las medidas de tu fórmula deben coincidir con la fuente de datos seleccionada
7. Define la **fórmula**
   - Utiliza nombres de medidas válidos de la fuente de datos seleccionada
   - Incluye constantes (números) según sea necesario
   - Aplica los operadores aritméticos: +, -, \*, /
   - Utiliza paréntesis para controlar el orden de las operaciones

   ![Crear ventana modal «Métrica calculada»](../../../../03-media/cloudability-premium/images/calculated-metric-create-modal.png)
8. Haz clic en **«Guardar»** para crear la métrica

Una vez guardada, la métrica calculada queda disponible de inmediato en todos los informes de « Cloudability ».

Edición de métricas calculadas

Para actualizar una métrica calculada ya existente:

1. Ve a **«Organizar» → «Asignaciones empresariales»**
2. Busca en la lista la **métrica calculada** que quieras editar
3. Haz clic en el icono con forma de engranaje y selecciona **«Editar métrica»** en el menú desplegable

   ![Editar el menú desplegable de métricas](../../../../03-media/cloudability-premium/images/calculated-metric-edit-dropdown.png)
4. Rellena los campos según sea necesario:
   - Descripción
   - Formato de los números
   - Fórmula
   - Origen de datos

   ![Actualizar la ventana modal «Métrica calculada»](../../../../03-media/cloudability-premium/images/calculated-metric-update-modal.png)
5. Haz clic en **«Guardar»** para aplicar los cambios

Eliminación de métricas calculadas

Para eliminar una métrica calculada:

1. Ve a **«Organizar» → «Asignaciones empresariales»**
2. Busca en la lista la **métrica calculada** que deseas eliminar
3. Haz clic en el icono con forma de engranaje y selecciona **«Eliminar métrica»** en el menú desplegable

   ![Eliminar el menú desplegable de métricas](../../../../03-media/cloudability-premium/images/calculated-metric-delete-dropdown.png)
4. Haz clic en **«Aceptar»** en el mensaje de confirmación «Eliminar métrica calculada»

   ![Mensaje de confirmación de eliminación](../../../../03-media/cloudability-premium/images/calculated-metric-delete-message.png)

**Importante:** Una métrica calculada solo se puede eliminar si en ese momento no aparece referenciada en ningún informe, panel de control o widget guardado. Si la métrica está en uso, debes eliminar esas referencias antes de borrarla.

Visualización de los detalles de las métricas calculadas

Para ver los detalles de una métrica calculada concreta:

1. Ve a **«Organizar» → «Asignaciones empresariales»**
2. Busca en la lista la **métrica calculada** que quieras ver
3. Haz clic en el **nombre** de la métrica
4. Consulta toda la información en la página de detalles de la métrica

   ![Página de detalles de la métrica calculada](../../../../03-media/cloudability-premium/images/calculated-metric-details-page.png)

La página de detalles muestra:

- Nombre y descripción completos del indicador métrico
- Expresión completa
- Marcas de tiempo de creación y modificación
- Información sobre el creador y el último modificador

## Casos de uso habituales

**Compara los modelos de costes de la nube**

Comprender la diferencia entre el coste original de la nube y el coste efectivo amortizado de la nube para evaluar el impacto financiero de los compromisos, los descuentos y los precios negociados.

**Ejemplo:**

```
Cost (List) - Cost (Amortized)
```

Este cálculo muestra el ahorro total conseguido gracias a las optimizaciones de precios.

**Analizar la eficiencia del ahorro**

Mide la eficacia con la que las optimizaciones de precios reducen los costes en los distintos proveedores, servicios, equipos y unidades de negocio.

**Ejemplo:**

```
(Cost (List) - Cost (Amortized)) / Cost (List)
```

Este porcentaje indica la proporción del precio de catálogo que se ha ahorrado gracias a las optimizaciones.

**Desarrollar la economía de la unidad**

Crea indicadores clave de rendimiento (KPI) operativos para evaluar la escalabilidad y la eficiencia operativa.

**Ejemplos:**

- Coste por recurso: `unblended_cost / usage_quantity`
- Coste por clúster: `unblended_cost / cluster_count`
- Coste por entorno: `unblended_cost / environment_count`
- Coste por carga de trabajo: `unblended_cost / workload_count`

**Aplicar descuentos o recargos**

Simula diferentes escenarios de precios aplicando ajustes porcentuales.

**Ejemplos:**

- 20 % de descuento: `unblended_cost * 0.8`
- Margen del 10 %: `unblended_cost * 1.1`
- Precios por niveles: `(unblended_cost + 100) / 2`

**Calcular los márgenes de utilización**

Añade márgenes de seguridad a los indicadores de utilización para la planificación de la capacidad.

**Ejemplo:**

```
avg_cpu_utilization * 1.1
```

Esto añade un margen del 10 % a la utilización de la CPU con fines de planificación.

## Permisos

Las métricas calculadas admiten tres niveles de permisos que controlan el acceso y las capacidades de los usuarios.

**Acceso completo**

**Autorización:** `CalculatedMetricsFeatureFullAccess`

Los usuarios con acceso completo pueden:

- Ver todas las métricas calculadas
- Crear nuevas métricas calculadas
- Actualizar cualquier métrica calculada
- Eliminar cualquier métrica calculada

**Acceso de edición propio**

**Autorización:** `CalculatedMetricsFeatureOwnEditAccess`

Los usuarios con acceso para editar sus propios contenidos pueden:

- Ver todas las métricas calculadas
- Crear nuevas métricas calculadas
- Actualizar únicamente las métricas que ellos mismos hayan creado
- Eliminar únicamente las métricas que ellos mismos hayan creado

**Acceso solo de lectura**

**Autorización:** `CalculatedMetricsFeatureViewOnlyAccess`

Los usuarios con acceso de solo lectura pueden:

- Ver todas las métricas calculadas
- Ver definiciones y fórmulas de las métricas
- Utilizar métricas en informes y paneles de control
- No se pueden crear, editar ni eliminar métricas

## ¿Cuál es la diferencia entre las métricas calculadas y las métricas empresariales?

| **Característica** | **Métricas calculadas** | **Métricas de negocio** |
| --- | --- | --- |
| Calendario de evaluación | Se evalúa en el momento de la consulta | Evaluado en el momento de la ingestión |
| Nivel de procesamiento | Aplicado a los resultados agregados | Se aplica a cada fila por separado |
| Lógica condicional | Sin expresiones condicionales | Admite expresiones de coincidencia |
| Disponibilidad | Disponible de inmediato | Requiere un nuevo procesamiento de los datos |
| Límites métricos | Ilimitado | Hasta 5 indicadores empresariales |
| Complejidad de las fórmulas | Solo operaciones aritméticas | Admite lógica condicional compleja |
| Datos históricos | Las actualizaciones se aplican con carácter retroactivo | Es necesario volver a procesar los datos históricos |

## Reglas de expresión y validación

**Operadores compatibles**

- `+` Adición
- `-` Resta
- `*` Multiplicación
- `/` División

**Reglas de validación**

- **Nombre:** Debe ser único dentro de la organización y no puede coincidir con los nombres de medidas básicas ya existentes
- **Expresión:** Debes utilizar operadores y nombres de medidas válidos para tu organización
- **Tipo de fuente:** Todas las medidas de la expresión deben coincidir con el «source\_type» especificado (coste o consumo)
- **Paréntesis:** deben estar correctamente equilibrados en las expresiones
- **Nombres de medidas:** pueden contener letras, dígitos y guiones bajos
- **Decimales:** Utiliza el punto (.) para los números decimales

**Ejemplos de uso**

**Métricas de costes:**

```
unblended_cost * 0.8
(unblended_cost + 100) / 2
business_metric9 / total_adjusted_amortized_cost * bytes_transferred
```

**Métricas de uso:**

```
avg_cpu_utilization * 1.1
burst_balance * 100
avg_running_instances_per_hour / business_metric9
```

## Preguntas frecuentes (FAQ)

¿Cuándo se evalúan las métricas calculadas?

Las métricas calculadas se evalúan en el momento de la consulta. Esto significa que los cálculos se realizan al cargar un panel de control o un informe, y no durante la importación de los datos de facturación.

En consecuencia:

- Las métricas están disponibles inmediatamente después de su creación
- Los informes históricos reflejan automáticamente las actualizaciones de las fórmulas
- No es necesario volver a procesar los datos
- Los cambios se aplican al instante en todos los informes

¿Qué tipos de fórmulas son compatibles?

Las métricas calculadas admiten fórmulas creadas mediante:

- Métricas estándar (indicadores de costes y uso)
- Métricas empresariales
- Valores constantes (números)
- Suma (`+`)
- Resta (`-`)
- Multiplicación (`*`)
- División (`/`)
- Paréntesis para el orden de las operaciones

**Ejemplo:**

```
(Cost (List) - Cost (Amortized)) / Cost (List)
```

¿Pueden las métricas calculadas utilizar lógica condicional?

Núm. Las métricas calculadas no admiten:

- Lógica «SI/ENTONCES»
- CASE declaraciones
- Condiciones booleanas
- Expresiones coincidentes

Para la lógica condicional o basada en reglas, utiliza en su lugar «Business Metrics» o «Business Mappings».

¿Las métricas calculadas requieren un nuevo procesamiento de los datos?

Núm. Las métricas calculadas están disponibles inmediatamente después de su creación o modificación y no requieren un nuevo procesamiento de los datos de facturación. Los cambios en las fórmulas se aplican automáticamente a todos los datos históricos cuando se generan los informes.

¿Hay algún límite en el número de métricas calculadas?

Núm. Cloudability Admite un número ilimitado de métricas calculadas por organización.

¿Pueden las métricas calculadas hacer referencia a otras métricas calculadas?

Núm. Las métricas calculadas están diseñadas para utilizar métricas estándar, métricas empresariales, constantes y operaciones aritméticas. Actualmente no se admiten las métricas calculadas anidadas o encadenadas (en las que una métrica calculada hace referencia a otra).

¿Qué ocurre si elimino una métrica calculada que está en uso?

No puedes eliminar una métrica calculada si actualmente aparece como referencia en algún informe, panel de control o widget guardado. Para poder eliminar la métrica, primero debes eliminar todas las referencias a ella. Esto evita que se produzcan errores en los informes y paneles de control existentes.

¿Cómo puedo utilizar la API para gestionar las métricas calculadas?

Puedes utilizar las API de « Cloudability » para crear, leer, actualizar y eliminar métricas calculadas mediante programación. La documentación de la API para gestionar las métricas calculadas está disponible en el apartado «[Punto de conexión de métricas calculadas](../api-v3/calculated_metrics_end_point.html) ».

**Tema principal:** [Organiza tu gasto en la nube](../admin/tag-data.html)
