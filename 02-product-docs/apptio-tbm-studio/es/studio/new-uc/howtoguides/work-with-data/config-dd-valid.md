---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar menús desplegables y validación"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Introducción manual de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/config-dd-valid.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar menús desplegables y validación

**Objetivo:** Añadir restricciones de menús desplegables y reglas de validación a las columnas editables de la tabla para garantizar la calidad y la coherencia de los datos.

## Cuándo se utiliza

- Cualquier columna utilizada como dimensión de informe o factor de asignación
- Campos de clasificación en los que es fundamental que los valores sean coherentes
- Campos con un conjunto conocido de valores válidos
- Esquemas de clasificación de varios niveles (por ejemplo, Torre → Servicio → Subservicio)
- Campos numéricos que requieren validación de rango

Importante: Sin validación, los usuarios introducen datos incoherentes que afectan a la elaboración de informes y a las asignaciones. Una misma entrada puede aparecer como «Servicios de TI», «Servicios de TI», «Tecnología de la información» y «Servicios de TI», cuando en realidad todas deberían ser «Servicios de TI» Los menús desplegables y la validación evitan este problema.

## Requisitos previos

- Una tabla editable (vacía o con datos) ya creada
- Conocimiento de los valores válidos para cada columna
- Para menús desplegables en cascada: tablas de referencia con datos jerárquicos

## Estimación de tiempo

Entre 10 y 30 minutos, dependiendo de la complejidad

## A. Configurar listas desplegables sencillas

1. **Abre tu tabla editable**
   - Accede a **Data Studio**
   - Echa un vistazo a la tabla editable
   - Ve a **Pasos > Configurar columnas**
2. **Selecciona la columna que deseas configurar**
   - Haz clic en el nombre de la columna en la lista de columnas
   - Las propiedades de la columna aparecen a la derecha
3. **Definir los valores posibles**
   - Busca el campo **«Valores posibles»**
   - Introduce una lista de valores permitidos separados por comas
   - Ejemplo: *Desarrollo, Pruebas, Producción*
   - Ejemplo: *Alto, Medio, Bajo*
4. **Configurar el comportamiento del menú desplegable**
   - **Permitir valores que no figuran en la lista de valores posibles:** Desmarcado (recomendado) - Los usuarios deben seleccionar un valor del menú desplegable
   - **No permitir la edición en la celda de valores posibles:** sin marcar (recomendado) - Los usuarios pueden escribir para filtrar o buscar en el menú desplegable

## B. Configurar listas desplegables dinámicas

Los menús desplegables dinámicos extraen valores de otras tablas, lo que permite un mantenimiento centralizado.

1. **Crea una tabla de referencia** (si aún no existe)
   - Crea una tabla de transformación que contenga tu lista de valores válidos
   - Ejemplo: tabla «Torres de TI» con las columnas: ID de la torre, Nombre de la torre, Descripción de la torre
2. **Configurar el menú desplegable basado en fórmulas**
   - En el paso **«Configurar columnas»** de tu tabla editable, selecciona la columna de destino
   - En **«Valores posibles»**, introduzca una fórmula con esta sintaxis:

`%TableName/TableFunction[].ColumnName`

- Ejemplo: `%IT Towers/Distinct[].Tower Name`

## C. Configurar menús desplegables en cascada (dependientes)

Los menús desplegables en cascada se filtran en función de los valores seleccionados en otras columnas.

**Ejemplo de situación:** los usuarios seleccionan Torre → Servicio → Subservicio, donde las opciones de Servicio dependen de la Torre seleccionada.

1. **Configurar la estructura de referencia**
   - Crear una tabla de referencia con relaciones jerárquicas
   - Ejemplo: «Jerarquía de servicios de TI» con las columnas: Torre, Servicio, Subservicio
2. **Configurar el menú desplegable de primer nivel** (Tower)
   - En «**Valores posibles** »: `%IT Service
     Hierarchy/Distinct[].Tower`
3. **Configurar el menú desplegable de segundo nivel** (Servicio)
   - En **«Valores posibles»**, utiliza una fórmula que filtre según la columna «Torre»:

```
%IT Service Hierarchy/Filter[Tower =
        [Tower]]/Distinct[].Service
```

- Establecer **el contexto de valores posibles** en **la fila actual**
  - **Configurar el menú desplegable de tercer nivel** (Subservicio)
- Fórmula similar, filtrando tanto por «Torre» como por «Servicio»:

```
%IT Service Hierarchy/Filter[Tower = [Tower] AND Service =
        [Service]]/Distinct[].Subservice
```

## D. Configurar reglas de validación

1. **Utiliza las opciones de validación integradas**
   - **Valor obligatorio:** marque esta casilla para impedir que se introduzcan valores vacíos
   - **Permitir solo valores únicos:** márcalo para evitar duplicados
   - **Tipo de datos:** al seleccionar «Numérico», se comprueba automáticamente que los valores introducidos sean números
2. **Habilitar la interfaz de usuario de validación** (función beta)
   - Ve a la pestaña **Proyecto** > **Activar funciones**
   - Selecciona **«Habilitar paso de validación para tabla editable (Beta)»**
   - Cuando está activada, los errores de validación aparecen directamente en el campo al introducir los datos

## Errores habituales

|  |  |
| --- | --- |
| **Emitir** | **Solución** |
| **Los valores del menú desplegable no aparecen** | Comprueba que la sintaxis de la fórmula sea correcta. Asegúrate de que la tabla de referencia exista y contenga datos. Comprueba que los nombres de las columnas estén escritos exactamente como aparecen (se distingue entre mayúsculas y minúsculas). |
| **Los menús desplegables en cascada no se filtran correctamente** | El contexto de «Verificar valores posibles» está establecido en «Fila actual». Comprueba la sintaxis de la fórmula del filtro: Filter[ ColumnA = [ ColumnB ]] donde ColumnA se encuentra en la tabla de referencia y ColumnB se encuentra en la fila actual. |
| **Hay demasiadas opciones en el menú desplegable (no se puede utilizar)** | Si el menú desplegable tiene más de 100 valores, plantéate utilizar un enfoque jerárquico (menús desplegables en cascada). O bien, activa la opción «Permitir edición en la celda de valores posibles» para que los usuarios puedan escribir para filtrar. |
| **Los usuarios pueden seguir introduciendo texto libre a pesar del menú desplegable** | Asegúrate de que la opción «Permitir valores que no figuran en la lista de valores posibles» no esté marcada. |

**Tema principal:** [Introducción manual de datos](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
