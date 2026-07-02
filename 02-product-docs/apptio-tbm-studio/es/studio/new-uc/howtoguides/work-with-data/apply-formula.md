---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Aplicar fórmulas para transformar datos"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Transformar y enriquecer los datos"
source_path: "studio/new-uc/howtoguides/work-with-data/apply-formula.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Aplicar fórmulas para transformar datos

## Objetivo

Crea columnas calculadas, transforma los tipos de datos y aplica la lógica de negocio a tus datos antes de que pasen a la capa de modelado.

## Cuándo utilizar esto

Utiliza fórmulas cuando sea necesario:

- Crear columnas derivadas (por ejemplo, «Coste total = Coste unitario × Cantidad»)
- Convertir tipos de columna (de numérico a etiqueta, de etiqueta a numérico)
- Aplicar lógica condicional (instrucciones IF, categorización)
- Enriquecer los datos con consultas a otras tablas
- Estandarizar valores o dar formato al texto

## Requisitos previos

- Tabla de origen con datos importados
- Comprensión de la sintaxis de las fórmulas de TBM Studio
- Nombres y tipos de columnas identificados

## Estimación de tiempo

Entre 10 y 15 minutos por columna de fórmula

## Pasos

1. Echa un vistazo a la tabla en **el Explorador de proyectos**.
2. Añade un paso **de fórmulas** al proceso de transformación.
3. Haz clic en «**Añadir una nueva columna** ».
4. Configura la nueva columna:
   - **Tipo** : Selecciona el tipo de columna (Clave, Etiqueta, Numérico, Fecha)
   - **Nombre** : Introduce un nombre descriptivo para la columna
   - **Fórmula** : Introduce tu fórmula empezando por =
5. Crea tu fórmula utilizando la sintaxis de TBM Studio:
   - Para hacer referencia a columnas existentes, utiliza llaves: *{Column Name}*
   - Utiliza los operadores: +, -, \* y / para operaciones matemáticas, y «&» para concatenar texto
   - Aplica funciones como: IF(), Lookup(), Value(), NumberFormat(, etc.
6. Haz clic en **«Guardar»** para añadir la columna.
7. Revisa la vista previa para comprobar que la fórmula da los resultados esperados.
8. (Opcional) Para editar una columna de fórmula existente, selecciónela en el menú desplegable «**Seleccionar columna para editar** », realice los cambios y haga clic en «**Guardar** ».

## Ejemplos comunes de fórmulas

|  |  |
| --- | --- |
| **Caso de uso** | **Ejemplo de fórmula** |
| Calcular el coste total | `={Unit Cost} * {Quantity}` |
| Clasificar los gastos | ``` =IF({Cost Pool} IN ("FTE                 Labor&","Depreciation&"),"Fixed&","Variable&") ``` |
| Convertir un número en texto | `=NumberFormat({Account},"#,###&")` |
| Búsqueda en otra tabla | ``` =Lookup({Account}, Chart of Accounts,                 Account,   Cost Pool) ``` |
| Añadir un prefijo al ID | `="pm-&"&{Asset Tag}` |

## Resultados previstos

Las nuevas columnas de fórmulas aparecen en la parte superior de la lista de columnas del panel de edición. Las columnas originales de la tabla se mantienen en la parte inferior. La vista previa muestra los valores calculados según la lógica de la fórmula.

## Errores habituales

- **Error «No se encuentra la columna...»:** comprueba que los nombres de las columnas coincidan exactamente (se distingue entre mayúsculas y minúsculas cuando están entre llaves). Si el nombre de la columna contiene caracteres especiales, debe escribirse entre llaves.
- **Discrepancia de tipos en las búsquedas:** cuando utilices la función Lookup(), asegúrate de que las columnas de clave de búsqueda tengan los mismos tipos. Si es necesario, convierte el valor utilizando la función `Value()` o ` NumberFormat( ()`.
- **La fórmula hace referencia a columnas del paso «Fórmulas» actual:** la mayoría de las fórmulas solo pueden hacer referencia a columnas de pasos anteriores del proceso, no a columnas creadas en el mismo paso «Fórmulas». Crea varios pasos de «Fórmulas» si necesitas basarte en columnas calculadas.

**Tareas relacionadas**

- Referencia de fórmulas y funciones (Sección 5.4 )
- [Combinar datos de varias fuentes](join-data.html)
- [Datos limpios y cartográficos](clean-map.html)

**Tema principal:** [Transformar y enriquecer datos](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
