---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Códigos de partida"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/line-item-codes.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Códigos de partida

Nota: *Se requieren roles de administrador o responsable del proceso presupuestario para gestionar los códigos de partidas.*

**Los códigos de partida** proporcionan un identificador único para cada partida creada en las tablas de planificación clave. Estos códigos facilitan el seguimiento de los cambios, la resolución de problemas en las actualizaciones y la consulta de líneas específicas en los planes enviados, las instantáneas y el historial del registro de eventos.

Los códigos se aplican a las siguientes tablas de partidas:

- **Finanzas** (pestañas Resumen y Otras)
- **Activo**
- **Contrato**
  - **Trabajo**
- **Actividad laboral**

## Cómo funcionan los códigos de partida individual

Cada código de línea se compone de dos partes:

1. **Prefijo** : identifica el tipo de partida individual
2. **Código numérico** : un número único generado por el sistema dentro del plan

Apptio La planificación asigna automáticamente la parte numérica cuando se crea una nueva partida.

Planes de referencia

Al crear un nuevo plan a partir de uno ya existente:

- Puede copiar todos los códigos de partida del plan de origen, o
- Generar nuevos códigos de partida individual

Para obtener más información sobre la creación de planes, consulte [Creación de planes](create-plan.html).

## Prefijos predeterminados

Cada tipo de partida tiene su propio prefijo predeterminado:

|  |  |
| --- | --- |
| **Tipo de partida** | **Prefijo predeterminado** |
| Finanzas | **F-** |
| Activo | **A-** |
| Contrato | **C-** |
| Trabajo | **L-** |
| Actividad laboral | **LAP-** |

## Cambiar el prefijo del código de una partida individual

Los cambios en los prefijos de los códigos de las partidas individuales se aplican a todos los planes.

1. Vaya a **Configuración** → **Prefijo del código de línea de artículo**.
2. Seleccione el **tipo de partida** que desea actualizar.
3. Se abre el cuadro de diálogo **Editar prefijo**.
4. Introduzca un nuevo prefijo siguiendo estas reglas:
   1. Debe tener **entre 1 y 10 caracteres.**
   2. No puede contener **dígitos.**
   3. No puede estar **vacío**
5. Selecciona **Guardar**.

Los cambios surten efecto inmediatamente en todos los planes del inquilino.

## Códigos de las partidas de origen

**Un código de partida de origen** identifica la partida de origen cuando una partida se crea a partir de otra fuente, como por ejemplo:

- **Delegaciones** (para contratos o activos) creadas por la partida original
- **Datos financieros generados** (para activos, contratos, mano de obra y actividad laboral)

Los códigos de partida de origen aparecen cuando una partida no se ha creado manualmente. Los datos financieros generados en la pestaña Resumen no reciben códigos de partida individual, pero muestran un código de partida individual de origen que remite a la partida individual original.

Si [la opción Resumir finanzas laborales](labor-summarization.html "La función Resumir datos financieros de mano de obra le permite determinar cómo se agregan y presentan los datos de costes de mano de obra en la pestaña Resumen. Controla qué dimensiones (por ejemplo, centro de coste, cuenta, ubicación) se utilizan para agrupar y desglosar las líneas de costes laborales, garantizando que se obtiene el nivel adecuado de visibilidad y confidencialidad de las finanzas laborales.") está habilitada:

- Una sola línea financiera resumida puede provenir de múltiples líneas laborales
- En este caso, el código de partida de origen puede mostrar **«varía».**

## Fuente Plan

El **plan de origen** identifica el plan desde el que se copió una partida individual.

Ejemplo:

- El plan B se crea a partir del plan A
- El Plan C se crea a partir del Plan B

Para las partidas creadas originalmente en **el Plan A**, el Plan de origen seguirá mostrando **el Plan A** tanto en el Plan B como en el Plan C.

## Códigos de partida en el historial de cambios

Los códigos de línea aparecen en el **registro de eventos**, en la columna **Detalles**, lo que le permite realizar un seguimiento de la línea exacta que se ha modificado en un plan.

El registro de eventos muestra el **prefijo utilizado en el momento en que se produjo el evento** :

- Los eventos **anteriores** a un cambio de prefijo muestran el prefijo *antiguo.*
- Los eventos **posteriores** al cambio muestran el *nuevo* prefijo

Esto significa que dos partidas del mismo tipo pueden mostrar prefijos diferentes dependiendo de cuándo se modificaron.

Para obtener más información, consulte [el historial de cambios](change-history.html "El historial de cambios proporciona una pista de auditoría de las acciones clave realizadas en su entorno de planificación. Permite a las organizaciones mantener la transparencia, respaldar los requisitos de cumplimiento y solucionar problemas de planificación mediante el seguimiento de quién ha cambiado qué, cuándo y cómo.").
