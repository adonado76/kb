---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Asignaciones"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
source_path: "studio/new-uc/reference/model-studio-reference/allocations.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Asignaciones

Las asignaciones son el mecanismo fundamental para distribuir el valor entre los objetos del modelo. Determinan cómo los costes, los presupuestos y otros indicadores se transfieren de los objetos de origen a los de destino según reglas configurables.

## Tipos de asignación

TBM Studio ofrece cinco tipos de asignación para adaptarse a diferentes necesidades de distribución.

**Asignación de valores ponderados**

**Descripción:** Distribuye los valores en función de la proporción (tamaño relativo) de los valores de una columna seleccionada de la tabla de destino. Este es el tipo de asignación más habitual.

**Parámetros de configuración**

|  |  |  |  |
| --- | --- | --- | --- |
| **Parámetro** | **Obligatorio** | **Valores** | **Descripción** |
| Asignar (Métricas) | Sí | Coste, presupuesto, previsión | Qué métricas asignar |
| Para (Destinatario) | Sí | Objeto modelo | Objeto del modelo de destino |
| Distribución | Sí | Igual, Peso por, Relación de datos | Cómo se distribuye el valor |
| Peso por | Condicional | Tabla, sistema métrico, otro conductor | Fuente de ponderación (si se ha seleccionado «Ponderar por») |
| Relación entre datos | Condicional | Pares de columnas | Columnas coincidentes (si se ha seleccionado) |

**Opciones de distribución**

|  |  |  |
| --- | --- | --- |
| **Opción** | **Comportamiento** | **Ejemplo** |
| Incluso | Se distribuye por igual entre todas las filas de destino | $100K / 5 aplicaciones = $20K cada una |
| Peso por – Tabla | Distribuye en función de las proporciones de las columnas en el destino | Columna «Peso por número de usuarios» |
| Peso en – Sistema métrico | Distribuye en función de los valores de otra métrica | Distribución del peso por costes |
| Peso según: otro conductor | Se adapta al estilo de conducción de otro conductor | Ajustar el patrón de asignación de mano de obra |
| Relación entre datos | Se distribuye entre las filas en las que coinciden las columnas | Hacer coincidir el ID del proveedor entre tablas |

**Nota:** Las opciones «Peso por – Métrico» y «Peso por – Otro conductor» están disponibles en TBM Studio 12.5 y versiones posteriores.

**Ejemplo: Asignación de valores ponderados**

Asignar 100 000 dólares a cinco solicitudes, ponderadas en función del número de usuarios:

|  |  |  |
| --- | --- | --- |
| **Aplicación** | **Número de usuarios** | **Asignación** |
| Aplicación A | 50 | 25 000 $ (50/200 × 100 000 $) |
| Aplicación B | 80 | 40 000 $ (80/200 × 100 000 $) |
| Aplicación C | 30 | 15 000 $ (30/200 × 100 000 $) |
| Aplicación D | 25 | 12 500 $ (25/200 × 100 000 $) |
| Aplicación E | 19 | 7.500 $ (15/200 × 100.000 $) |

**Errores habituales**

Advertencia: Ponderación con valores no numéricos: si la columna de ponderación contiene algún valor no numérico, se ignorará la ponderación y la asignación se realizará por defecto de forma equitativa.

Nota: Ponderación con valores negativos: las asignaciones fallan si los valores de ponderación incluyen números negativos. Consulte la sección «Acerca de la ponderación y los números negativos» para conocer las soluciones alternativas.

Consulte [«Crear asignaciones ponderadas» para ver el procedimiento paso a paso.](../../howtoguides/build-cost-model/create-allocation.html)

**Distribución del consumo**

**Descripción:** Realiza la asignación en función de las unidades consumidas realmente en comparación con la capacidad total disponible. Se utiliza cuando se dispone de datos de consumo específicos que indican cuánto consume cada destinatario de un servicio o recurso.

**Parámetros de configuración**

|  |  |  |  |
| --- | --- | --- | --- |
| **Parámetro** | **Obligatorio** | **Valores** | **Descripción** |
| Columna de consumo | Sí | Distancia desde el objetivo | Número de unidades consumidas |
| Columna de capacidad | Sí | Columna de la fuente | Capacidad total disponible |
| Distribución | Sí | Igual, Peso por, Relación de datos | Lógica de distribución adicional |

**Casos de uso**

- Consumo de servicios en la nube (GB de almacenamiento consumidos frente al total asignado)
- VM asignación (máquinas virtuales utilizadas por cada unidad de negocio frente al total disponible)
- Plazas de servicio (licencias utilizadas frente al total adquirido)

**Asignación de valores estándar**

**Descripción:** Asigna un valor igual al que ya figura en la tabla de destino, independientemente del importe de origen. Esto da lugar a una transferencia directa del valor actual del objetivo.

**Comportamiento clave**

- Si el destino tiene 10 000 $ y el origen tiene 15 000 $: se asignan 10 000 $ y quedan 5 000 $ en el origen
- Si el destino tiene 10 000 $ y el origen tiene 5 000 $: sobreasignación del 200 %
- El valor de origen no limita la asignación; el valor de destino determina la cantidad

Advertencia: Las asignaciones de valores estándar pueden dar lugar a situaciones de sobreasignación. Supervise los porcentajes de asignación para garantizar la integridad del modelo.

**Fórmula de asignación**

**Descripción:** Utiliza una fórmula personalizada para controlar la distribución de la asignación. Ofrece la máxima flexibilidad para situaciones de asignación complejas que los métodos estándar no pueden abordar.

**Palabras clave especiales**

|  |  |
| --- | --- |
| **Palabra clave** | **Descripción** |
| ORIGEN | Representa la cantidad de dinero que se asigna desde el objeto de origen |
| ~ (operador tilde) | Obtiene el valor total de una columna en todas las filas coincidentes (similar a SUM, pero respeta las relaciones entre los datos) |

**Fórmulas de ejemplo**

|  |  |
| --- | --- |
| **Finalidad** | **Fórmula** |
| Asignación ponderada (equivalente a «Ponderar por») | =SOURCE\*Ratio( {Servers.Size},~ {Servers.Size} ) |
| Valor directo de la columna (como el valor estándar) | =Servers.Size |
| Asignación basada en porcentajes | =FUENTE\*( {Table.Percent} /100) |

**Nota:** Las asignaciones mediante fórmulas no pueden reproducir el comportamiento de las asignaciones por consumo o recursivas.

Consulte «Fórmulas y funciones» en 5.4: para ver la sintaxis completa de las fórmulas

**Asignación recursiva**

**Descripción:** Gestiona patrones de asignación circulares en los que los servicios se reparten los costes entre sí. Procesa las asignaciones de forma iterativa hasta alcanzar un umbral de precisión o el número máximo de iteraciones.

**Parámetros de configuración**

|  |  |  |  |
| --- | --- | --- | --- |
| **Parámetro** | **Obligatorio** | **Valor predeterminado** | **Descripción** |
| Precisión | Sí | Varía | Valor mínimo para continuar con la iteración |
| Número máximo de iteraciones | Sí | Varía | Número máximo de ciclos de asignación |
| Utilizar el modo incremental | Nee | Sin marcar | Añade el valor de iteración a la fuente |

**Requisitos**

- Las tablas de origen y destino deben tener las mismas unidades
- Después de cada iteración debe quedar algún valor en las unidades de destino
- Las asignaciones de recursión múltiple no deben solaparse

Advertencia: Las asignaciones recursivas requieren una potencia de procesamiento considerablemente mayor. Úsalo con moderación y con el menor número posible de iteraciones.

*→ Consulte [«Configurar asignaciones recursivas» para obtener información detallada sobre la configuración](../../howtoguides/build-cost-model/config-drivers.html)*

- **[Todas las opciones de configuración de asignación](../../../../studio/new-uc/reference/model-studio-reference/allocation-config.html)**
- **[Orden y prioridad de asignación](../../../../studio/new-uc/reference/model-studio-reference/allocation-order.html)**
- **[Comportamiento del cálculo de la asignación](../../../../studio/new-uc/reference/model-studio-reference/allocation-calc-behaviour.html)**
