---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Códigos externos"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/external-unique-identifier.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Códigos externos

Cuando importas o actualizas datos de gastos (por ejemplo, mano de obra, actividad laboral, contratos, activos) desde sistemas externos (sistemas de RR. HH., bases de datos de proveedores, etc.), Necesita un identificador único y coherente para hacer coincidir las líneas de su plan con los registros del sistema de origen.

De forma predeterminada, Apptio utiliza sus propios identificadores internos ( [códigos de línea](line-item-codes.html) ), pero estos no coinciden con los sistemas externos. La función **Código externo** resuelve esta deficiencia. Cuando está habilitada, cada línea de gastos puede llevar un identificador único definido externamente (como el ID de empleado, el ID de proveedor, el ID de puesto, etc.). Esto garantiza que los datos importados o actualizados se asignen correctamente a las líneas existentes, evitando duplicados, registros perdidos o discrepancias en los datos.

## Habilitar código externo

Nota: *Para realizar esta tarea se requieren los roles de administrador o responsable del proceso presupuestario.*

1. Ve a **Configuración (icono del engranaje) → Perfil de la empresa**.
2. Marque la casilla **Habilitar código externo**.
3. Haga clic en **Guardar y salir**.

   Después de habilitarla, la columna Código externo estará disponible en las tablas de gastos.

## Cómo funcionan los códigos externos

- Aparece una nueva columna**, Código externo,** en las pestañas de gastos (Mano de obra, Actividad laboral, Contratos, Activos, Otros). Puede estar oculto por defecto, pero puedes mostrarlo en la vista.
- En la pestaña **Resumen**, verás nuevas columnas: **Código externo** y **Código externo de origen.**
- Los valores **de los códigos externos** introducidos en las pestañas de gastos (Mano de obra, Actividad de mano de obra, Contratos, Activos, Otros) se resumirán en la columna «**Código externo** » de la pestaña «**Resumen** ».
- Puede cambiar el nombre de la columna Código externo en **Configuración → Esquema**, pero esto se aplica a todos los planes.
- El código externo puede hacerse **obligatorio** en el esquema si se desea garantizar que cada línea tenga una referencia externa única.
- Al crear un nuevo plan a partir de una línea de base, se transfieren los valores de código externo existentes.

Nota: Dado que el «Código externo» se utiliza para agregar los datos financieros generados en la pestaña «Resumen», la restricción de unicidad para el «Código externo» no se aplica en las pestañas «Resumen» y «Otros». En el resto de pestañas, el sistema exige que los datos de «Código externo» tengan identificadores únicos.

**Códigos externos de origen**

**Un** código externo de origen identifica el código externo de la partida original cuando se crea una línea a partir de otra fuente, como por ejemplo:

- **Delegaciones** (para contratos o activos) creadas por la partida original
- **Datos financieros generados** (para activos, contratos, mano de obra y actividad laboral)

Los códigos externos aparecen cuando una partida no se crea manualmente. El código «Fuente externa» remite a la partida original.

Si [la función de resumen de horas de trabajo](labor-summarization.html "La función Resumir datos financieros de mano de obra le permite determinar cómo se agregan y presentan los datos de costes de mano de obra en la pestaña Resumen. Controla qué dimensiones (por ejemplo, centro de coste, cuenta, ubicación) se utilizan para agrupar y desglosar las líneas de costes de mano de obra, garantizando que se obtiene el nivel adecuado de visibilidad y confidencialidad para las finanzas de mano de obra.") está activada:

- Una sola línea financiera resumida puede provenir de múltiples líneas laborales
- En este caso, tanto el código externo como el código fuente externo pueden mostrar **«varía».**

## Permisos para editar código externo

- Solo los usuarios con el **canEditExternalCode** permiso correspondiente pueden añadir o modificar valores de código externo. De forma predeterminada, los usuarios con roles de administrador y propietario del proceso presupuestario tienen este permiso.
- Si desea restringir la edición, asigne este permiso de forma selectiva. Esto evita que se realicen cambios no autorizados o se utilicen identificadores incorrectos.

## Uso de código externo con importaciones de datos

Al importar datos de gastos a través de CSV :

- Utilice el modo **Actualizar datos** (no Reemplazar todo), ya que permite la coincidencia de filas basada en el código externo (o el código de partida individual, si está presente).
- Lógica de emparejamiento:
  - Si una línea de la carga coincide con un código de partida existente, las actualizaciones se realizan en función de ello.
  - Si falta el código de partida, pero el código externo coincide, el sistema se actualiza basándose en el código externo.
- Los códigos externos deben ser **únicos para cada tipo de línea de gasto** dentro de un plan. Las importaciones serán rechazadas si se encuentran duplicados.

## Sincronización de datos reales y previsiones mediante código externo

Los datos reales se importan a « Apptio » desde sistemas ERP externos, mientras que los presupuestos y las previsiones se crean dentro de « Apptio ». Esta separación puede dificultar la conciliación de los datos reales con las partidas del pronóstico o del presupuesto.

La función **«Código externo»** resuelve este problema al permitir definir identificadores únicos específicos para cada usuario que pueden utilizarse de forma coherente en todos los sistemas. Por ejemplo, si se utiliza un *ID de activo* como código externo en las líneas del presupuesto o de las previsiones, y ese mismo ID de activo existe en los datos reales del sistema ERP, esto permite alinear con precisión los datos reales con las previsiones utilizando este identificador común.

**Pasos para habilitar y utilizar código externo para la alineación**

1. Active la función **«Código externo»** en el perfil de la empresa.
2. Habilitar [la configuración de resumen real](actual-summarization.html "Esta función describe cómo se desglosan las partidas de datos reales, en función de las columnas seleccionadas para la agregación.") **mediante código externo**.
3. Asigne códigos externos a las partidas de gastos de su plan.
4. Asegúrese de que los mismos códigos externos figuren en los datos reales de su sistema ERP.
5. En el Plan de previsión, ve a **Gastos > Resumen** y agrupa las partidas por la columna «Código externo» para ver la comparación entre la previsión y los datos reales.

## Códigos externos en el historial de cambios

Los códigos externos aparecen en el **registro de eventos,** en la columna **Detalles,** cuando se modifica una línea con un código externo.

Cuando una línea se origina a partir de otra línea (por ejemplo, generada a partir de mano de obra, activos o contratos), se muestra el código externo de origen, que enlaza con la línea original.

Para obtener más información, consulta [el historial de cambios](change-history.html "El historial de cambios proporciona un registro de auditoría de las acciones clave realizadas en su entorno de planificación. Permite a las organizaciones mantener la transparencia, cumplir con los requisitos normativos y resolver problemas de planificación mediante el seguimiento de quién ha cambiado qué, cuándo y cómo.").
