---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar asignaciones sencillas (uno a uno)"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Crear asignaciones"
source_path: "studio/new-uc/howtoguides/build-cost-model/setup-sa.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar asignaciones sencillas (uno a uno)

**Objetivo:** Distribuir los costes de una tabla de origen a una tabla de destino utilizando un método de distribución sencillo.

**Cuándo utilizarlo:** Es necesario distribuir los costes en función de un atributo cuantificable, como el número de empleados, el número de servidores, el número de usuarios o la superficie. Este es el patrón de asignación más habitual y sirve de base para modelos de costes más complejos.

**Tiempo estimado:** 15-20 minutos

## Comprender los tipos de asignación

Antes de crear una asignación, elija el tipo que mejor se adapte a su caso:

|  |  |  |
| --- | --- | --- |
| **Tipo de asignación** | **Cuándo utilizarlo** | **Ejemplo** |
| **Valor ponderado** | Distribuir los costes proporcionalmente en función de una columna numérica | Asignar los costes del centro de datos en función del uso de la CPU |
| **Consumo** | Comparar el consumo real con la capacidad disponible | Imputar los costes de los servicios en función de las unidades consumidas |
| **Valor predeterminado** | La tabla de objetivos contiene la cantidad exacta que se debe asignar | Asignar los costes fijos cuando el objetivo especifique el importe en dólares |
| **Incluso** | Distribución equitativa entre todas las filas de destino | Repartir los gastos compartidos a partes iguales entre los departamentos |

## Paso a paso: cómo crear una asignación de valores ponderada

Este procedimiento muestra el patrón de asignación más habitual: distribuir los costes de forma proporcional basándose en una columna de ponderación.

**Situación:** Asignar 500 000 dólares en gastos del centro de datos a cinco aplicaciones en función del número de servidores de cada una.

**Pasos**

1. **Echa un vistazo a ambas tablas**
   - En el Explorador de proyectos, haz clic con el botón derecho del ratón en la tabla de origen (por ejemplo, «Costes del centro de datos») y selecciona «Desproteger».
   - Repite el proceso para la tabla de destino (por ejemplo, «Aplicaciones»).
2. **Abre el paso «Modelo» de la tabla de origen**
   - Haz clic en la tabla de origen en el Explorador de proyectos.
   - En el flujo de transformación, haz clic en el paso «Modelo».
   - Se abre el espacio de trabajo del modelo, mostrando el diagrama de Sankey.
3. **Añadir una nueva asignación**
   - En el diagrama de Sankey, haz clic en «Añadir asignación» debajo del encabezado «Asignaciones».
4. **Configurar los ajustes de asignación**
   - **Asignar:** Selecciona las métricas a las que se aplica esta asignación (por ejemplo, Coste, Presupuesto).
   - **Procedimiento:** Seleccione «Valor ponderado» como tipo de asignación.
   - **A:** Selecciona la tabla de destino (por ejemplo, «Aplicaciones»).
5. **Configurar la ponderación**
   - En «Peso según», selecciona «Tabla» (la opción más habitual).
   - Selecciona la columna que contiene los valores de ponderación (por ejemplo, «Número de servidores»).

   Consejo: La columna de ponderación debe contener únicamente valores numéricos. Los valores no numéricos hacen que se ignore la ponderación, lo que da lugar a una distribución uniforme.
6. **Ver un avance de la asignación**
   - Haz clic en «Vista previa» para ver cómo se distribuirán los costes.
   - Revisa la tabla de vista previa para comprobar que los porcentajes de asignación se ajustan a lo que esperabas.

   |  |  |  |
   | --- | --- | --- |
   | **Aplicación** | **Número de servidores** | **Importe de la asignación** |
   | Aplicación A | 50 | 125 000 dólares (25 %) |
   | Aplicación B | 80 | 200 000 dólares (40 %) |
   | Aplicación C | 30 | 75 000 $ (15 %) |
   | Aplicación D | 25 | 62 500 $ ( 12.5 %) |
   | Aplicación E | 19 | 37 500 $ ( 7.5 %) |
   | **Total** | **200** | **500 000 dólares** |
7. **Guardar la asignación**
   - Haz clic en «Guardar» para añadir la asignación a tu modelo.
   - El diagrama de Sankey se actualiza para mostrar la línea de asignación que conecta el origen con el destino.

## Resultados previstos

Después de guardar:

- El diagrama de Sankey muestra una línea que va de la tabla de origen a la tabla de destino.
- El grosor de la línea es proporcional a la cantidad asignada.
- Al pasar el cursor por encima de la línea de asignación, se muestra el valor total asignado.
- La tabla de destino contiene ahora los costes asignados que pueden transferirse a tablas posteriores.

## Explicación de las opciones de distribución

**Distribución uniforme (predeterminada)**

- Distribuye los costes de manera equitativa entre todas las filas de destino.
- Úsese cuando no exista ningún factor de ponderación o cuando se pretenda una distribución equitativa.
- Ejemplo: 100 000 dólares repartidos entre 5 solicitudes = 20 000 dólares cada una.

**Peso por**

- Distribuye los costes de forma proporcional en función de una columna de la tabla, una métrica u otro factor determinante.
- Ejemplo: 100 000 dólares asignados a las solicitudes, ponderados según el número de usuarios.

**Relación entre datos**

- Distribuye los costes entre las filas correspondientes en función de los pares de valores de las columnas.
- Úsalo cuando la fuente y el destino compartan una clave común (por ejemplo, región, departamento).
- Ejemplo: Los costes del centro de datos regional se asignan únicamente a las aplicaciones de la misma región.

## Errores habituales

|  |  |  |
| --- | --- | --- |
| **Emitir** | **Síntoma** | **Solución** |
| Columna de ponderación no numérica | Los costes se reparten de manera uniforme, en lugar de según el peso | Comprueba si la columna de ponderación contiene valores de texto, espacios en blanco o caracteres especiales |
| Valores de ponderación negativos | La asignación falla y se produce un error | Los valores negativos impiden la asignación. Utiliza valores absolutos o separa los datos. |
| Ponderación cero para todas las filas | Se produce una distribución uniforme | Asegúrate de que al menos algunas filas del conjunto objetivo tengan valores de ponderación distintos de cero |
| La mesa no está reservada | No se puede guardar la asignación | Comprueba las tablas de origen y destino antes de realizar la configuración |

**Tema principal:** [Crear asignaciones](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
