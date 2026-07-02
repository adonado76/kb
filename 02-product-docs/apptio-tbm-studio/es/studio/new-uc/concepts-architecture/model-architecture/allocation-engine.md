---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "El motor de asignación"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura del modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/allocation-engine.html"
images:
  - "resources/images/studio_images/allocation-pattern.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# El motor de asignación

La asignación es la operación fundamental que hace posible la modelización de costes. En esencia, la asignación es el proceso de distribuir los costes desde un objeto de origen a uno o varios objetos de destino según unas reglas definidas. En esta sección se explica cómo funciona el motor bajo el capó.

## Conceptos básicos de la asignación

Cada asignación sigue el mismo patrón básico:

![Motor de asignación](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/allocation-pattern.png)

El conductor decide las proporciones. La fuente indica el importe total. El destinatario recibe su parte. Este es el mecanismo fundamental que subyace a todas las asignaciones en TBM Studio.

## Tipos de asignación

TBM Studio ofrece cinco tipos de asignación, cada uno de ellos adecuado para distintos escenarios de distribución de costes. Es fundamental saber cuándo utilizar cada tipo.

**Asignación de valores ponderados**

El tipo de asignación más habitual. El valor ponderado distribuye los costes de forma proporcional en función de la proporción de los valores de una columna de la tabla de destino.

**Cómo funciona:** cada fila de destino recibe una parte del coste de origen igual a su peso dividido por el peso total de todas las filas de destino.

**Fórmula:** *Importe asignado = Total de la fuente × (Peso de la fila / Peso total)*

**Ejemplo práctico: Costes del centro de datos ponderados por servidor**

Supongamos que tu centro de datos cuesta 100 000 dólares y quieres distribuir los costes en función del número de servidores:

|  |  |  |  |
| --- | --- | --- | --- |
| **Unidad de negocio** | **Número de servidores** | **Relación de pesos** | **Coste asignado** |
| Ventas | 50 | 50 / 200 = 25 % | 25 000 dólares |
| Ingeniería | 100 | 100 / 200 = 50 % | 50 000 dólares |
| Marketing | 30 | 30 / 200 = 15 % | 15 000 dólares |
| Soporte | 20 | 20 / 200 = 10 % | 10 000 dólares |
| **Total** | **200** | **100 %** | **100 000 dólares** |

**Opciones de distribución en «Valor ponderado»:**

- **Incluso:** El valor predeterminado. Si no se selecciona ninguna columna de ponderación, los costes se reparten a partes iguales entre todas las filas de destino.
- **Ponderación por:** Los costes se reparten proporcionalmente según una columna de la tabla de destino (como se muestra arriba). La columna de ponderación debe contener valores numéricos no negativos.
- **Relación entre datos:** los costes se distribuyen en categorías en función de la coincidencia de los valores de las columnas entre la fuente y el destino. Cada cubeta se asigna de forma independiente. Esto evita tener que utilizar muchas líneas de asignación individuales.

Nota:

**Peso según los escollos**

**Valores no numéricos:** si la columna de ponderación contiene aunque sea un solo valor no numérico, la ponderación se ignora sin aviso y los costes se distribuyen de manera uniforme. Comprueba siempre los datos de ponderación.

**Valores negativos:** la ponderación con números negativos provoca que la asignación falle. TBM Studio aplica un mecanismo de protección para evitar problemas de cálculo derivados de pesos negativos.

**Distribución del consumo**

La asignación por consumo distribuye los costes en función de la relación entre las unidades consumidas y la capacidad disponible. Esto resulta ideal para simular el uso real de los servicios de TI.

**Cómo funciona:** Se especifica una columna de consumo (del destino) y una columna de capacidad (del origen). La asignación distribuye los costes de origen en función de la parte de la capacidad disponible que cada destino ha consumido realmente.

**Cuándo utilizarlo:** cuando se dispone de datos de uso reales; por ejemplo, para distribuir los costes de computación en la nube en función de las horas de CPU consumidas por cada aplicación.

**Asignación de valores estándar**

La asignación de valor estándar distribuye un valor igual al que ya existe en la tabla de destino. Se trata de una asignación de mapeo directo.

**Cómo funciona:** si la tabla de destino indica que la aplicación A cuesta 10 000 $, se asignan 10 000 $ a la aplicación A. Si la fuente tiene más o menos que el total de la tabla de destino, la fuente tendrá un remanente o se le habrá asignado un importe excesivo.

**Cuándo utilizarlo:** cuando se dispone de datos de costes directos para cada objetivo y se desea asignar esos importes conocidos en lugar de distribuir un fondo común. Se suele utilizar para los costes de personal cuando se conocen los salarios exactos por persona o por proyecto.

**Fórmula de asignación**

La asignación mediante fórmulas te ofrece un control total a través de fórmulas personalizadas. Puedes escribir una expresión que determine cómo recibe cada fila de destino su parte.

**Cómo funciona:** Introduzca una fórmula utilizando el lenguaje de cálculo de TBM Studio. La fórmula puede hacer referencia a la palabra clave SOURCE (valor total de la fuente), a los valores de las columnas, al operador ~ (tilde) para sumas agregadas y a la función Ratio.

**Fórmula de ejemplo:** *=FUENTE \* Ratio( {Servers.Size}, ~ {Servers.Size} )*

Esta fórmula reproduce el comportamiento del valor ponderado: cada fila recibe una proporción equivalente a su valor de «Tamaño» en relación con el total. La función Ratio gestiona el caso extremo en el que todos los valores son cero recurriendo a una distribución uniforme.

**Asignación recursiva**

La asignación por recursividad se aplica a situaciones en las que los costes circulan entre servicios interconectados; por ejemplo, cuando los servicios de TI se prestan apoyo mutuo, además de prestar apoyo a las unidades de negocio.

**Cómo funciona:** La asignación se ejecuta de forma iterativa. En cada iteración se transfiere una parte de los costes del origen al destino. Los costes que vuelven a la fuente se reasignan en la siguiente iteración. Esto continúa hasta que el importe restante sea inferior a un umbral de precisión o se alcance el número máximo de iteraciones.

**Cuándo utilizarlo:** cuando los servicios tienen dependencias mutuas (por ejemplo, el servicio de asistencia técnica da soporte a los servidores y los servidores dan soporte al servicio de asistencia técnica) y es necesario resolver el flujo circular de costes.

Nota:

**Nota sobre el rendimiento de la recursividad**

Las asignaciones recursivas requieren una potencia de procesamiento considerablemente mayor que las asignaciones estándar. Utiliza un número limitado de asignaciones recursivas por modelo, mantén bajo el número de iteraciones y establece el umbral de precisión lo más alto posible.

## Resumen de tipos de asignación

|  |  |  |
| --- | --- | --- |
| **Tipo de asignación** | **Ideal para** | **Complejidad** |
| Valor ponderado | La mayoría de las distribuciones de costes (reparto proporcional basado en los datos de los conductores) | Bajo |
| Consumo | Asignaciones basadas en el uso (consumo frente a capacidad) | Medio |
| Valor predeterminado | Asignaciones de costes directos en las que se conocen los valores objetivo | Bajo |
| Fórmula | Lógica personalizada no contemplada en los tipos estándar | Alto |
| Recursividad | Interdependencias entre áreas de servicio | Alto |
