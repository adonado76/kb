---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar los controladores para las asignaciones"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Crear asignaciones"
source_path: "studio/new-uc/howtoguides/build-cost-model/config-drivers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar los controladores para las asignaciones

**Objetivo:** Crear factores de asignación que controlen con precisión cómo se transfieren los costes de las tablas de origen a las de destino mediante condiciones de coincidencia y columnas de ponderación.

**Cuándo utilizarlo: cuando** se necesita un control detallado sobre el comportamiento de la asignación, lo que incluye asignar costes a filas de destino específicas en función de atributos compartidos (como el ID de proveedor o la cuenta) y aplicar una lógica de ponderación personalizada.

**Tiempo estimado:** 20-30 minutos

## Comprender los factores determinantes

Los factores determinantes marcan las pautas de la distribución de los costes. Hay dos tipos:

**Controladores de unidad:** definen cómo se introducen los valores en un objeto del modelo a partir de sus datos subyacentes. Los controladores de unidad hacen referencia a las columnas de la tabla de origen.

**Factores de asignación:** definen cómo fluye el valor de un objeto del modelo a otro. Los controladores de asignación especifican la lógica de emparejamiento y el comportamiento de ponderación.

## Paso a paso: Configuración de un controlador de asignación con coincidencia

**Escenario:** Asignar los costes de los proveedores a los servicios tecnológicos, emparejándolos por ID de proveedor y cuenta, ponderados según la columna «Ponderación de asignación».

1. **Abre el paso «Modelo» de la tabla de origen**
   - Ve a la tabla de origen (por ejemplo, «Proveedores») en el Explorador de proyectos.
   - Haz clic en el paso «Modelo» del proceso de transformación.
2. **Crear o modificar la asignación**
   - Haz clic en «Añadir asignación» o selecciona una asignación existente para editarla.
   - Configuración: Asignar = Coste, Utilizar = Valor ponderado, A = Servicios tecnológicos.
3. **Configurar condiciones de coincidencia (relación entre datos)**
   - En «Relación de datos», haz clic para añadir columnas coincidentes.
   - Añade los siguientes pares: ID de proveedor → ID de proveedor, Cuenta → Cuenta, Tipo de gasto → Tipo de gasto.

   Nota: Ambas columnas deben existir en sus respectivas tablas. Los valores deben coincidir exactamente para que se puedan asignar los costes.
4. **Establecer la columna de ponderación**
   - En «Peso según», selecciona «Tabla».
   - Seleccione la columna de ponderación (por ejemplo, «Ponderación de asignación»).
   - Asegúrate de que esta columna contenga valores numéricos, sin valores nulos ni negativos.
5. **Previsualizar y verificar**
   - Haga clic en «Vista previa» para examinar los resultados de la asignación.
   - Revisa si hay filas sin asignar (filas sin destinos correspondientes).
6. **Guardar la configuración del controlador**
   - Haz clic en «Guardar» para confirmar la asignación.
   - Comprueba la tabla cuando se hayan completado todas las asignaciones.

## Prácticas recomendadas para la configuración de controladores

**Mantén las tablas de controladores breves y ordenadas**

- Incluye solo las columnas necesarias para la comparación y la ponderación.
- Elimina las columnas que no se utilicen para mejorar el rendimiento.
- Documenta el propósito del controlador para futuros mantenedores.

**Utiliza la coincidencia explícita en lugar de la automática**

- La coincidencia automática (función heredada) puede dar lugar a resultados inesperados.
- Especifica siempre de forma explícita los pares de columnas de origen y destino.
- Si ves la casilla «Relación automática», desmárcala y configura claves explícitas.

**Comprueba que los tipos de datos coincidan**

- Las columnas que se van a emparejar deben tener el mismo tipo de datos (texto con texto, número con número).
- La búsqueda de texto distingue entre mayúsculas y minúsculas.
- Elimina los espacios en blanco de las columnas de texto en Data Studio si la coincidencia falla de forma inesperada.

## Referencia de tipos de controladores

|  |  |  |
| --- | --- | --- |
| **Tipo de controlador** | **Definición** | **Ejemplo de caso de uso** |
| **Columna** | Valor extraído de una columna de la tabla | Número de servidores, superficie, número de usuarios |
| **Métrica** | Valor tomado de otra métrica del modelo | Utilizar la métrica de costes para ponderar la asignación presupuestaria |
| **Fórmula** | Valor calculado mediante una fórmula personalizada | Lógica de ponderación compleja, distribución condicional |

**Tema principal:** [Crear asignaciones](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
