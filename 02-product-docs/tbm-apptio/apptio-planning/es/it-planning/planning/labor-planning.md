---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Panorama de la planificación laboral"
breadcrumb:
  - "Planning"
  - "Planificación laboral"
source_path: "it-planning/planning/labor-planning.html"
images:
  - "resources/images/it_planning_images/glf.png"
  - "resources/images/it_planning_images/lca-1.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Panorama de la planificación laboral

El módulo de Planificación Laboral permite a las organizaciones planificar y presupuestar los gastos relacionados con la mano de obra, incluidos los salarios, las prestaciones, los impuestos y las asignaciones de costes asociadas. Le ayuda a modelar las necesidades de personal, asignar costes a los departamentos y alinear la estrategia de personal con las prioridades empresariales.

**Por qué utilizar la planificación laboral**

- Proporciona visibilidad de la plantilla, los costes de los empleados y los gastos a nivel de funciones en todos los departamentos y proyectos.
- Permita que Finanzas y RR.HH. colaboren de forma más eficaz en la planificación de la capacidad, la contratación y la optimización de los costes de mano de obra.
- Configure las reglas de asignación de mano de obra para calcular automáticamente el coste total de cada plantilla, incluidos salarios, prestaciones y gastos generales.

## Configurar la planificación de la mano de obra

Nota: Para realizar estas tareas se requieren los roles de Administrador o Propietario de Proceso Presupuestario.

Antes de empezar a introducir partidas de mano de obra, tendrá que activar Mano de obra y configurar los datos de referencia para que las asignaciones de mano de obra se comporten de forma coherente en su modelo.

Al activar la planificación de la mano de obra, se activan las tablas de Datos de referencia relacionadas y se añade la pestaña **Mano de obra** a la tabla Gastos.

**Permitir la planificación laboral**

1. Vaya a **Ajustes** (icono de engranaje) **→ Perfil de empresa**.
2. Habilitar la **mano de obra**
3. **Configurar método de resumen de rec** uentos: determina cómo se calculan y muestran los totales de recuentos en los KPI:
4. **Media** - Calcula la media de efectivos a lo largo del periodo seleccionado.
5. **Inicio del periodo** - Utiliza el recuento al inicio del periodo.
6. **Fin de periodo** - Utiliza los efectivos al final del periodo.
7. **Seleccione Configuración de Resumen de Mano de Obra** - Elija las dimensiones por las que se resumirán las finanzas de mano de obra generadas en la pestaña **Resumen**.
8. Las dimensiones disponibles incluyen cualquier dimensión compartida entre los esquemas **Laboral** y **Financiero**. Consulte *[Resumir las finanzas laborales](labor-summarization.html "La función Resumir datos financieros de mano de obra le permite determinar cómo se agregan y presentan los datos de costes de mano de obra en la pestaña Resumen. Controla qué dimensiones (por ejemplo, centro de coste, cuenta, ubicación) se utilizan para agrupar y desglosar las líneas de costes laborales, garantizando que se obtiene el nivel adecuado de visibilidad y confidencialidad de las finanzas laborales.")* para obtener más detalles.
9. **Habilitar ajustes de remuneración variable** *(requiere nueva vista)* - Permite modelar los cambios mensuales de la remuneración base.
10. Para más detalles, véase *[Ajustes de las retribuciones](plan-labor-compensation.html "Los Ajustes de Remuneración Laboral permiten a las organizaciones modelizar los aumentos (o disminuciones) de remuneración a lo largo del tiempo dentro de Apptio Planning. Esta función ofrece una forma estructurada de contabilizar los ajustes salariales previstos, como aumentos por méritos, ajustes de mercado, ascensos o cambios en el coste de la vida.")* laborales.
11. Haga clic en **Guardar y salir**.

**Establecer roles laborales**

1. Vaya a **Configuración → Datos de referencia → Rol.**
2. **Exporte** la plantilla y rellene los campos obligatorios:
3. **Código** - Identificador único de la función.
4. **Nombre** - Nombre o título del puesto.
5. **Importa** el archivo « CSV » actualizado y **publica** los cambios para que los roles estén disponibles en los planes.

*Consejo:* Puede personalizar el esquema **Rol** en **Esquema → Dimensiones estándar** para incluir atributos adicionales.

**Establecer tarifas laborales**

Definir tasas de compensación base por defecto para cada rol laboral para estandarizar el modelado de costes. Las reglas pueden utilizar combinaciones de **Tipo de empleado**, **Función**, **Ubicación** y **Proveedor**. Cuando una partida de mano de obra coincide con estos atributos, se aplica automáticamente la tarifa por defecto correspondiente.

1. Vaya a **Configuración → Datos de referencia → Tarifas de mano de obra.**
2. **Exporte** la plantilla y rellene los campos clave:
3. **Tipo de empleado** - *Interno* o *externo*
4. **Rol** - El código de rol de la tabla de Roles Laborales
5. **Localización** - El código de localización de los datos de referencia de localización
6. **Vendedor** - El código de vendedor de los datos de referencia del vendedor
7. **Moneda** - Código de moneda para la tarifa
8. **Base Rate** - Remuneración anual por el puesto
9. **Importa** el archivo « CSV » actualizado y **publica** los cambios para que las tarifas estén disponibles en los planes.

**Establecer normas de asignación de mano de obra**

Las reglas de asignación de mano de obra definen cómo se distribuyen los costes de mano de obra entre los departamentos y las cuentas de mayor. Cada partida de mano de obra en Apptio Planning comienza con una tarifa base, y las reglas de asignación aplican automáticamente la lógica de distribución, ya sea como un porcentaje de la tarifa base o un valor fijo. Esto garantiza la exactitud de los costes de mano de obra "totalmente cargados" y su correcta asignación a los departamentos y cuentas del Libro Mayor apropiados.

1. Vaya a **Configuración → Reglas de asignación de mano de obra.**
2. Exporte una plantilla o introduzca los siguientes campos directamente en la interfaz de usuario:
   1. **Cuenta** - El código de cuenta de los datos de referencia de la cuenta. Esto genera una entrada de gastos para cada línea de trabajo que cumpla las condiciones de la regla.
   2. **Tipo de valor de salida** - Define cómo se calcula el coste:
      1. **Valor fijo** - Aplica un importe anual fijo.
      2. **Porcentaje de la tarifa** base - Calcula un porcentaje de la tarifa laboral base.
      3. **Porcentaje de otra tarifa** - Calcula un porcentaje de la tarifa de Otra mano de obra.
   3. **Excluir del Cálculo de Mano de Obra** - Determina si este coste se incluye en el total del Año Fiscal mostrado en la pestaña Mano de Obra:
      1. **Verdadero (marcado)** - Excluye el coste del total (por ejemplo, para gastos cruzados o costes no gravados).
      2. **Falso (sin marcar)** - Incluye el coste en el total del Año Fiscal.
   4. **Valor** - El porcentaje o importe fijo a aplicar en función del Tipo de Valor de Salida.
   5. **Método** de amortización de mano de obra: define cómo se distribuye el coste a lo largo de los periodos de tiempo (consulte *[las reglas de asignación de mano de obra](manage-labor-allocation-rules.html)* para obtener más detalles):
      1. **Línea recta Períodos pares** - Reparte el coste uniformemente entre todos los períodos.
      2. **Línea recta utilizando días naturales** - Distribuye el coste proporcionalmente al número de días de cada periodo.
      3. **Línea recta utilizando días labor** ables - Utiliza el calendario laboral definido para ponderar la distribución de costes.
3. **Importe** el archivo « CSV » ya completado y **publique** los cambios para que las reglas de asignación estén disponibles para su uso en los planes.

**Reglas de asignación de mano de obra por tiempo efectivo a nivel de plan**

Las reglas de asignación de mano de obra se pueden configurar a nivel de plan con **valores vigentes en el tiempo**, lo que permite que los costes de mano de obra varíen a lo largo del horizonte de planificación sin modificar los datos de referencia globales de las reglas de asignación de mano de obra.

Esta función resulta útil para simular cambios en los costes laborales, como prestaciones, bonificaciones, formación y otros componentes que pueden aumentar o disminuir con el tiempo dentro de un plan concreto.

Cada plan mantiene su propio calendario de reglas de asignación de mano de obra, independiente de los datos de referencia globales. Durante el cálculo de los ingresos por mano de obra, el sistema aplica la tarifa correspondiente a nivel de plan en función de la fecha de inicio de la mano de obra y del ejercicio fiscal que se esté calculando. Si no existe ningún valor a nivel de plan para un período, se utiliza el valor correspondiente de la regla global de asignación de mano de obra.

***Aspectos clave a tener en cuenta***

- Selecciona el **plan** y, a continuación, ve a **«Configuración del plan» → «Reglas de asignación de mano de obra»** para configurar los valores de las reglas específicas del plan.
- Utilice las fechas **de «Válido a partir de»** para definir cuándo entra en vigor cada tarifa dentro del plan.
- Los cambios en las reglas de asignación de mano de obra a nivel de plan se reflejan inmediatamente en el plan actual; no es necesario publicarlos.
- Las reglas de asignación de mano de obra a nivel de plan muestran los atributos de la versión global correspondiente de la regla de asignación de mano de obra en modo de solo lectura, al tiempo que permiten añadir y actualizar las tarifas por hora de cada regla.
- Los plazos de las reglas de asignación de mano de obra a nivel de plan se conservan al crear un plan a partir de una línea de base.
- Los ajustes salariales y los cálculos del coste total de la mano de obra utilizan automáticamente la tarifa aplicable a nivel de plan correspondiente al período en cuestión.
- Si no se define ninguna tarifa a nivel de plan para un período, el sistema recurre al valor correspondiente de la regla global de asignación de mano de obra.
- Las reglas de asignación de mano de obra a nivel de plan también admiten la importación a través de un archivo. CSV.

## Introducción y gestión de partidas de mano de obra

1. Abra su plan y navegue hasta la pestaña **Mano de Obra** dentro de la página de **Gastos**.
2. Añade una nueva línea de trabajo
   1. Utilizando la **fila vacía** de la parte inferior de la tabla, o bien
   2. **Haga clic con el botón derecho** y seleccione **Insertar fila**
3. **Proporcione la información requerida** para cada línea laboral:
   1. **Centro de coste** - Unidad organizativa responsable del coste laboral.
   2. **Rol** - El cargo o título laboral asociado al recurso laboral (por ejemplo, Desarrollador, Gestor de proyectos).
   3. **Tipo de empleado** - Indica si la mano de obra es **Interna** (empleado) o **Externa** (contratista).
   4. **Ubicación** - Lugar de trabajo o región del recurso laboral; se utiliza para aplicar tarifas basadas en la ubicación.
   5. **Proveedor** - El proveedor o la empresa de contratación que proporciona el recurso (si procede).
   6. **Nombre del empleado -** El nombre de la persona; útil para el seguimiento pero no obligatorio.
   7. **Remuneración base** - La remuneración base anual o el coste per cápita antes de aplicar asignaciones o ajustes.
   8. **Otra retribución** - Componentes adicionales de la retribución anual (por ejemplo, primas, incentivos, asignaciones) utilizados en las reglas de asignación que aplican un cálculo del Porcentaje de Otra Tasa.
   9. **Cantidad** - Número de recursos (efectivos) que representa esta partida.
   10. **Fecha de inicio / Fecha de finalización** - Periodo durante el cual el recurso está activo o presupuestado.
   11. **Descripción** - Una breve explicación o notas sobre el elemento de trabajo (por ejemplo, asignación de proyecto, tipo de función).
   12. **Calendario laboral** - Define los días laborables utilizados para calcular las distribuciones de costes entre periodos de tiempo.
4. El sistema genera automáticamente un plan de recuento basado en la Cantidad, la Fecha de inicio y la Fecha de finalización. Revise el plan generado para confirmar que la distribución de los efectivos entre los periodos se ajusta a sus expectativas.
5. Modifique la distribución si es necesario editando los campos mensuales o periódicos directamente en la tabla.
6. Las líneas de mano de obra que coinciden con la función, el proveedor, la ubicación y el tipo de empleado configurados aplican automáticamente la tarifa de mano de obra y las reglas de asignación correctas.
7. Puede anular las tarifas de mano de obra en partidas específicas cuando sea necesario, por ejemplo, para reflejar la remuneración real de una persona en lugar de una tarifa predeterminada.
8. La columna "**Total del ejercicio** " muestra el **coste anual total de** cada línea laboral.
   1. Si **los ajustes variables de mano de obra** están activados, puede modelar los cambios mensuales de la remuneración base y ver las imputaciones de costes detalladas por cuenta de mayor.
   2. Para más información, consulte *[«Ajustes en la remuneración laboral](plan-labor-compensation.html "Los Ajustes de Remuneración Laboral permiten a las organizaciones modelizar los aumentos (o disminuciones) de remuneración a lo largo del tiempo dentro de Apptio Planning. Esta función ofrece una forma estructurada de contabilizar los ajustes salariales previstos, como aumentos por méritos, ajustes de mercado, ascensos o cambios en el coste de la vida.")* ».

![imagen del ajuste de la compensación laboral](../../../../../03-media/apptio-planning/resources/images/it_planning_images/lca-1.png)

## Comportamiento importante: Cantidad de efectivos

- **La cantidad de efectivos no se prorratea** en función de la **fecha de inicio** o **finalización** del empleado.

  Por ejemplo, si un recurso laboral comienza el **15 de enero**, seguirá contando como **1 ETC** para el mes de enero por defecto.
- Los métodos de amortización **lineal por días naturales** y **lineal por días laborables** **tienen** en cuenta el prorrateo de las fechas de inicio y fin a la hora de calcular **el coste**, pero no los efectivos.
  - Por ejemplo, si ajusta manualmente el recuento de un mes parcial a **0.5** el sistema aplicará el prorrateo de costes correspondiente (por ejemplo, 0.5 × 15 días en enero = 7.5 días de coste, o aproximadamente una cuarta parte del gasto del mes).
- **La línea recta por periodos pares** **no** realiza el prorrateo por fechas: los costes se reparten uniformemente entre todos los meses en los que el recurso laboral está activo.
  - Por lo tanto, solo ajuste **el número de empleados a FTE parcial (por ejemplo, 0.5 )** cuando utilice **Línea recta por períodos pares** para representar una contratación a mitad de mes o un recurso a tiempo parcial.
- **Los métodos de amortización determinan** cómo se distribuyen **los costes** a lo largo del tiempo (por ejemplo, por periodo, días naturales o días laborables), pero **no alteran el recuento de efectivos** en los informes o los indicadores clave de rendimiento.

Sugerencia: Si su organización necesita representar recuentos parciales de meses, puede modelar los recuentos parciales directamente en las columnas periódicas o ajustar el campo de cantidad cuando utilice **Línea recta por periodos pares**.

## Ver las finanzas de la mano de obra generada

- La pestaña Resumen agrega los costes totales de mano de obra por departamento, proporcionando una visibilidad clara de cómo se distribuyen los gastos de mano de obra en toda la organización.
- Cada partida de mano de obra genera un asiento financiero para cada regla de imputación de mano de obra que se aplique. El número de líneas resumidas mostradas en la pestaña Resumen depende de las Opciones de integración de mano de obra, que definen las dimensiones de agrupación utilizadas para el rollup. Esta estructura garantiza una asignación detallada a la vez que salvaguarda la confidencialidad de los salarios individuales al resumir los costes a nivel agregado en lugar de exponer los datos individuales de remuneración. Consulte *[«Ocultar datos confidenciales sobre mano de obra»](hide-sensitive-labor-data.html "Los administradores pueden restringir la visibilidad de columnas específicas en la pestaña Mano de obra -como el nombre del empleado, el salario u otros detalles de compensación- para que los usuarios sin el permiso requerido puedan ver las entradas de mano de obra sin ver los campos sensibles.")* para obtener más información.

![imagen de las finanzas laborales generadas](../../../../../03-media/apptio-planning/resources/images/it_planning_images/glf.png)
