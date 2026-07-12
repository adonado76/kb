---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Normas de asignación de mano de obra"
breadcrumb:
  - "Planning"
  - "Planificación laboral"
source_path: "it-planning/planning/manage-labor-allocation-rules.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Normas de asignación de mano de obra

Nota: Se requieren roles de administrador o responsable del proceso presupuestario para configurar las reglas de asignación de mano de obra.

Las Reglas de Asignación de Mano de Obra le permiten definir cómo se distribuyen los costes de mano de obra base (salario, beneficios, carga) entre departamentos, centros de coste y cuentas de mayor. Cuando una línea de trabajo cumple los requisitos de una regla, el sistema crea el asiento (o asientos) financiero correspondiente aplicando la lógica de la regla.

Estas reglas ayudan a modelar el **coste de la mano de obra totalmente cargada** y garantizan que el gasto se asigna al Departamento, Centro de Coste y Cuenta correctos, en lugar de basarse en la plantilla prevista.

## Métodos de amortización

|  |  |  |
| --- | --- | --- |
| **Método** | **Qué hace** | **Ejemplo** |
| **Línea recta Períodos pares** | Reparte el coste uniformemente entre todos los periodos en los que el recurso está activo o presupuestado. | Una regla genera 12.000 $ anuales; durante 12 meses cada periodo = 1.000 $. |
| **Línea recta por días naturales** | Reparte el coste proporcionalmente en función de los días naturales por periodo. | 12.000 $ en 12 meses, febrero tiene 28 días → coste de febrero = (28/365)\*12.000 ≈ 920 $. |
| **Línea recta en días laborables** | Reparte el coste utilizando el calendario laboral definido (por ejemplo, excluyendo fines de semana/vacaciones). | 12.000 $ anuales si 260 días laborables → coste diario = 46.15 $; marzo tiene 22 días laborables → 1.015 $. |
| **Línea recta utilizando días naturales en un periodo fijo** | Distribuye los costes en función del número de días naturales de cada período fiscal en relación con el ejercicio fiscal completo, sin prorratear las fechas de inicio o finalización del contrato de trabajo. | Una cantidad anual **de** 12 000 dólares repartida a lo largo de un año de 365 días: febrero tiene 28 días, por lo que el coste de febrero es **= (28 / 365) × 12 000 ≈ 920 dólares**, independientemente de las fechas de inicio o finalización del contrato a lo largo del año. |
| **Línea recta utilizando días laborables en un período fijo** | Distribuye los costes en función del número de días laborables de cada ejercicio fiscal utilizando el calendario laboral configurado, sin prorratear las fechas de inicio o finalización del contrato. Vuelve a una distribución uniforme por periodos cuando los calendarios de trabajo son fijos. | Una cantidad anual **de** 12 000 dólares, repartida entre **260 días laborables,** supone un coste diario de aproximadamente **46.15 dólares**. Si marzo tiene **22 días laborables**, el coste asignado para marzo = **22 × 46.15 ≈ 1.015 $**, independientemente de las fechas de inicio o finalización del contrato a lo largo del año. |

## Comportamiento importante: Recuento de personal y prorrateo de los costes laborales

**Número de empleados**

La cantidad de personal **no** se prorratea en función de **la fecha de inicio** o **la fecha de finalización** de un recurso laboral.

- Si un recurso comienza o finaliza a mitad de mes, se seguirá contando como **un FTE e 1.0 e para todo ese periodo de forma predeterminada**.
- Por ejemplo, un recurso laboral que comience el **15 de** enero contará como **1 ETC para todo el mes de enero**, a menos que se ajuste manualmente el número de empleados.

**Cálculo de costes frente a número de empleados**

Los métodos de amortización afectan a cómo se distribuyen los costes laborales a lo largo del tiempo, pero no afectan a las cantidades de personal en la pestaña «Labor».

- **El coste laboral** siempre se calcula como: **Número de empleados mensual × Tarifa mensual**
- El prorrateo de los costes laborales solo se aplica cuando se utilizan los métodos de amortización «Línea recta por días naturales» o «Línea recta por días laborables».

**Comportamiento del método de amortización**

- **Línea recta por períodos iguales**
  - **No** realiza el prorrateo basado en la fecha al calcular el costo de mano de obra
  - El número de empleados se establece por defecto en **1 ETC para el periodo**, independientemente de la fecha de inicio o finalización.
  - Los costes laborales se calculan como **el número de empleados mensual × la tarifa mensual.**
  - Los costes se distribuyen de manera uniforme entre todos los periodos en los que el recurso laboral está activo.
  - Ejemplo: Un recurso laboral comienza el 15 de enero con una tarifa mensual de 10 000 $. Usando la línea recta por períodos pares, el recurso se contabiliza como 1.0 FTE para enero y los $10 000 completos se asignan a enero.

    Si desea que enero refleje un coste parcial del mes, debe ajustar manualmente el número de empleados (por ejemplo, a un ETC de 0.5 ), lo que daría como resultado un coste laboral de 5000 $ para enero.
- **Línea recta por días naturales** y **línea recta por días laborables**
  - Estos métodos **tienen** en cuenta el prorrateo de la fecha de inicio y finalización al calcular el coste laboral.
  - El recuento de personal sigue siendo por defecto **un FTE** (equivalente a tiempo completo) de 1.0 para el periodo, independientemente de la fecha de inicio o finalización.
  - El coste laboral se prorratea en función de los días activos del recurso dentro del periodo.
  - Ejemplo: utilizando el mismo recurso que comienza el 15 de enero con una tarifa mensual de 10 000 $, la opción «Línea recta por días naturales» o «Línea recta por días laborables» calcula el coste de mano de obra en función de los días activos del recurso en enero.

    Con 16 días activos, el coste laboral de enero es de aproximadamente 5161 dólares, aunque la plantilla sigue siendo de 1.0 FTE para el periodo.

Nota: Si su organización necesita representar el número de empleados parciales por mes al utilizar el método de amortización lineal por períodos iguales, puede modelar el número de empleados parciales directamente en las columnas periódicas.

## Establecer normas de asignación de mano de obra

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
   5. **Método de amortización de mano de obra** : define cómo se distribuye el costo a lo largo de los períodos de tiempo (consulte *Métodos de amortización de mano de obra* para obtener más detalles):
   6. **Línea recta Períodos pares** - Reparte el coste uniformemente entre todos los períodos.
   7. **Línea recta utilizando días naturales** - Distribuye el coste proporcionalmente al número de días de cada periodo.
   8. **Línea recta utilizando días labor** ables - Utiliza el calendario laboral definido para ponderar la distribución de costes.
3. **Importa** el archivo « CSV » ya completado y **publica** los cambios para que las reglas de asignación estén disponibles para su uso en los planes.

## Ejemplos

**Ejemplo A: Valor fijo (anual), sin reglas de nivel de plan**

Este ejemplo muestra cómo se distribuye el mismo valor anual (2.000 $) utilizando diferentes métodos de amortización.

Valor fijo (anual) = 2.000 $, **Fecha de inicio:** 15 enero

1. **Método de amortización = Línea recta Periodos pares**

   Tarifa mensual: 2.000 $ ÷ 12 meses = 166.67 $ al mes

   Asignación mensual:

   |  |  |  |  |
   | --- | --- | --- | --- |
   | **Mes** | **Cant.** | **Cálculo** | **Importe** |
   | Enero | 1 | ( 2.000 $ ÷ 12 meses) × 1 ETC | $166.67 |
   | Febrero | 1 | ( 2.000 $ ÷ 12 meses) × 1 ETC | $166.67 |
   | Marzo | 1 | ( 2.000 $ ÷ 12 meses) × 1 ETC | $166.67 |
2. **Método de amortización = Línea recta por días naturales**

   Tarifa diaria: 2.000 $ ÷ 365 días = 5.48 $ al día

   Asignación mensual:

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Mes** | **Cant.** | **días** | **Cálculo** | **Importe** |
   | Enero | 1 | 31 | ((31 - 14 días) × $ 5.48 ) × 1 ETC | $93.16 |
   | Febrero | 1 | 28 | (28 días × $ 5.48 ) × 1 ETC | $153.44 |
   | Marzo | 1 | 31 | (31 días × $ 5.48 ) × 1 ETC | $169.88 |
3. **Método de amortización = Línea recta por días laborables**

   Definición del calendario laboral: 260 días laborables

   Tarifa diaria: 2.000 $ ÷ 260 días = 7.69 $ al día

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Mes** | **Cant.** | **Días laborables** | **Cálculo** | **Importe** |
   | Enero | 1 | 21 | ((21 - 8 días) × $ 7.69 ) × 1 ETC | $161.49 |
   | Febrero | 1 | 19 | (19 días × $ 7.69 ) × 1 ETC | $146.11 |
   | Marzo | 1 | 21 | (21 días × $ 7.69 ) × 1 ETC | $161.49 |

**Ejemplo B: porcentaje del tipo básico, sin reglas de nivel de plan**

Un empleado tiene un **salario base** de **120.000 dólares al año**, y una regla de asignación aplica **el 10% del salario base** como coste adicional (por ejemplo, beneficios o gastos generales).

Asignación anual: 120.000 $ × 10% = 12.000 $ al año, **Fecha de inicio:** 15 de enero

1. **Método de amortización = Línea recta Periodos pares**

   Fórmula: 12.000 $ ÷ 12 meses = 1.000 $ al mes

   |  |  |  |  |
   | --- | --- | --- | --- |
   | **Mes** | **Cant.** | **Cálculo** | **Importe** |
   | Enero | 1 | (12.000 $ ÷ 12 meses) × 1 ETC | 1000 dólares |
   | Febrero | 1 | (12.000 $ ÷ 12 meses) × 1 ETC | 1000 dólares |
   | Marzo | 1 | (12.000 $ ÷ 12 meses) × 1 ETC | 1000 dólares |
2. **Método de amortización = Línea recta por días naturales**

   Fórmula: 12.000 $ ÷ 365 días = 32.88 $ al día

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Mes** | **Cant.** | **días** | **Cálculo** | **Importe** |
   | Enero | 1 | 31 | ((31 - 14 días) × $ 32.88 ) × 1 ETC | $558.96 |
   | Febrero | 1 | 28 | (28 días × $ 32.88 ) × 1 ETC | $920.64 |
   | Marzo | 1 | 31 | (31 días × $ 32.88 ) × 1 ETC | $1, 019.28 |
3. **Método de amortización = Línea recta por días laborables**

   Definición del calendario laboral: 260 días laborables

   Fórmula: 12.000 $ ÷ 260 días = 46.15 $ al día

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Mes** | **Cant.** | **Días laborables** | **Cálculo** | **Importe** |
   | Enero | 1 | 21 | ((21 - 8 días) × $ 46.15 ) × 1 ETC | $599.95 |
   | Febrero | 1 | 19 | (19 días × $ 46.15 ) × 1 ETC | $876.85 |
   | Marzo | 1 | 21 | (21 días × $ 46.15 ) × 1 ETC | $969.15 |

## Reglas de asignación de mano de obra por tiempo efectivo a nivel de plan

Nota: Para configurar las reglas de asignación a nivel de plan, es necesario tener el rol de administrador o de responsable del proceso presupuestario.

Por defecto, las reglas de asignación de mano de obra se gestionan como datos de referencia globales, y todos los planes utilizan los mismos valores de regla al generar partidas de gastos de mano de obra. Las reglas de asignación de mano de obra con efecto temporal a nivel de plan permiten que cada plan mantenga sus propios calendarios de tarifas, lo que facilita la planificación de escenarios y la simulación de cambios en las hipótesis sobre los costes de mano de obra a lo largo del horizonte de planificación, al tiempo que se mantienen las definiciones de las reglas globales subyacentes.

***Capacidades clave***

- **Ampliar las reglas globales con plazos específicos para cada plan** : heredar las reglas globales de asignación de mano de obra y definir entradas adicionales con efectos temporales a nivel del plan sin modificar los datos de referencia compartidos.
- **Definir los valores** de «Válido a partir de»: controla exactamente cuándo entra en vigor un cambio en el valor de una regla dentro del período del plan. Se pueden definir varias entradas de tarifas dentro del mismo mes.
- **Aplicación automática de tarifas** : durante la generación de costes de mano de obra, el sistema selecciona el valor efectivo a nivel de plan cuya fecha de inicio de vigencia sea la fecha más tardía igual o anterior a la fecha relevante que se está evaluando. Si ninguna tarifa a nivel de plan cubre ese periodo, el sistema recurre al valor de la regla global.
- **Modelización de escenarios plurianuales** : aplica diferentes tasas de prestaciones, porcentajes de bonificación o costes de formación en los distintos años de un plan plurianual sin necesidad de crear reglas globales independientes.

**Configurar reglas de asignación a nivel de plan**

- Abre tu **plan** y, en el menú de navegación de la izquierda, selecciona «**Configuración del plan** ».
- Selecciona **«Regla de asignación de mano de obra»** en el menú de configuración del plan. La tabla «**Reglas de asignación de** mano de obra: periodos de tiempo» recoge todas las reglas globales que se pueden anular.
- Busca la regla que quieras ampliar y haz clic en **«Ver reglas»** en la columna **«Reglas avanzadas»** para desplegar las filas de reglas avanzadas.
- En el panel **«Tarifas avanzadas»**, haz clic en **«+ Añadir tarifa»** para añadir una entrada con validez temporal.
- Especifique el **valor** (porcentaje o importe fijo) y la fecha **de entrada en vigor a partir de** la cual se aplicará dicho valor.
- Añade entradas de tipos adicionales para reflejar las variaciones de valor a lo largo de los distintos periodos. Cada entrada debe tener una fecha de inicio única.
- Utiliza el botón **«Ordenar por fecha»** para ordenar las entradas de tarifas cronológicamente y facilitar su revisión.
- Haz clic en **«Guardar»** para guardar los cambios.

**Generación de datos financieros de mano de obra para reglas a nivel de plan**

El sistema siempre selecciona la tarifa cuya fecha **de inicio de vigencia** sea la más reciente, incluida o anterior a la fecha que se está evaluando. El comportamiento clave según el método de amortización es:

- **Períodos lineales:** En el **mes de inicio**, la tarifa vigente en la **fecha de inicio del contrato** se aplica a todo el mes. Para todos **los meses completos siguientes**, se aplicará la tarifa vigente el día **1 de dicho mes**. No se aplican los cambios de tarifa que se producen a mitad de mes dentro de un mismo mes natural.
- **Línea recta con días naturales:** El coste diario se vuelve a calcular para cada **segmento de tarifa** dentro del mes. En el **primer mes**, solo se tienen en cuenta los días a partir de la fecha de inicio del contrato, y a esos días se les aplica la tarifa vigente en dicha fecha (y así sucesivamente hasta el siguiente cambio de tarifa ). En **los meses siguientes**, cada segmento de tarifas contribuye con una parte proporcional del coste de ese mes, calculada en función de los días naturales.
- **Línea recta con días laborables:** Su lógica es idéntica a la de «Días naturales», pero en cada segmento de tarifa solo se contabilizan **los días laborables** (tal y como se definen en el calendario laboral configurado).
- Si no existe una tarifa a nivel de plan para un período determinado, el sistema **recurre al valor de la regla global**.

Nota: Las reglas de asignación a nivel de plan y sus calendarios de tasas se copian automáticamente al crear un plan a partir de una línea de base. La sincronización de datos de referencia (Actualizar datos de referencia) añadirá nuevas reglas globales al plan y eliminará las que se hayan borrado, conservando al mismo tiempo las entradas de tarifas a nivel de plan que hayas configurado.

**Ejemplos con reglas de eficiencia temporal a nivel de plan**

Los siguientes ejemplos **(C, D y E)** amplían **el ejemplo B** (porcentaje de la tarifa base, $120,000/year, Cantidad = 1 ETC, **Fecha de inicio = 15 de enero** ) añadiendo tarifas efectivas por tiempo a nivel de plan. Los tres ejemplos utilizan la misma cronología de tarifas a nivel de plan, en la que las tarifas varían mensualmente y también **a mitad de mes** en enero y febrero.

*Cronología de tarifas por plan (común a los ejemplos C, D y E)*

|  |  |  |
| --- | --- | --- |
| **Válido desde** | **Porcentaje (% de la base)** | **Notas** |
| 1 de enero de 2026 | 10 % | Inicio del plan |
| 15 de enero de 2026 | 11 % | Cambio a mediados de enero — coincide con la fecha de inicio del contrato |
| 1 de febrero de 2026 | 12% | Cambios en febrero |
| 10 de febrero de 2026 | 13% | Cambio a mediados de febrero |
| 1 de marzo de 2026 | 14 % | Cambio de marzo |

**Tarifa base:** $120,000/year │ Cantidad **:** 1 ETC │ **Fecha** de inicio: 15 de enero

**Ejemplo C: Periodos uniformes lineales con reglas a nivel de plan**

En el caso de **los períodos uniformes lineales**, se aplica la tarifa vigente en la **fecha de inicio** del contrato (15 de enero) durante todo el mes de inicio. Para los meses completos siguientes, se aplica la tarifa vigente a partir del día **1 de cada mes**. **No** se aplican los cambios de tipo de interés que se producen a mediados de mes dentro de un mismo mes (por ejemplo, 10/02 → 13 %); solo se tiene en cuenta el tipo de interés vigente el día 1 de dichos meses.

**Tipos de interés aplicables:** enero → 11 % (tipo vigente a partir del 15 de enero), febrero → 12 % (tipo vigente a partir del 1 de febrero), marzo → 14 % (tipo vigente a partir del 1 de marzo)

|  |  |  |  |
| --- | --- | --- | --- |
| **Mes** | **Cant.** | **Cálculo** | **Importe** |
| Enero | 1 | ((120 000 $ × 11 %) ÷ 12) × 1 ETC | 1.100 dólares |
| Febrero | 1 | ((120 000 $ × 12 %) ÷ 12) × 1 ETC | 1.200 dólares |
| Marzo | 1 | ((120 000 $ × 14 %) ÷ 12) × 1 ETC | 1.400 dólares |

Nota: Para el **mes de inicio (enero)**, el sistema utiliza el tipo de interés vigente en la **fecha de inicio** del contrato (15/01 → 11 %), y no el tipo de interés vigente el día 1 del mes (01/01 → 10 %). Para los meses completos siguientes, solo se aplica el tipo vigente el día 1 del mes; los cambios que se producen a mitad de mes, como el del 10 de febrero al 13 %, no se aplican a los periodos pares.

**Ejemplo D: Amortización lineal utilizando días naturales con reglas a nivel de plan**

Con **el método lineal basado en días naturales**, los costes se calculan **por segmento de tarifa** dentro de cada mes. En el **mes de inicio (enero)**, solo están activos los días a partir de la fecha de inicio del trabajo (15 de enero).

**Enero (17 días naturales: del 15 al 31 de enero)**

El tipo de interés vigente a partir de la fecha de inicio del contrato (15 de enero) es **del 11 %**. No habrá más cambios en las tarifas antes del 1 de febrero, por lo que todos los días activos de enero se regirán por esta tarifa.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Tasa** | **Tarifa diaria** | **días** | **Coste por segmento** |
| Segmento 1 | 15 de enero | 31 de enero | 11 % | (120 000 $ × 11 %) ÷ 365 = 36.16 $ | 17 | $614.79 |

**Febrero (28 días naturales)**

El mes de febrero presenta dos tramos de tarifas debido al cambio de tarifas que entra en vigor el 10 de febrero.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Tasa** | **Tarifa diaria** | **días** | **Coste por segmento** |
| Segmento 1 | 1 de febrero | 9 de febrero | 12% | (120 000 $ × 12 %) ÷ 365 = 39.45 $ | 9 | $355.07 |
| Segmento 2 | 10 de febrero | 28 de febrero | 13% | (120 000 $ × 13 %) ÷ 365 = 42.74 $ | 19 | $812.05 |
| **Total de febrero** |  |  |  |  | **28** | **1, 167.12** |

**Marzo (31 días naturales)**

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Tasa** | **Tarifa diaria** | **días** | **Coste por segmento** |
| Segmento 1 | 1 de marzo | 31 de marzo | 14 % | (120 000 $ × 14 %) ÷ 365 = 46.03 $ | 31 | 1, 426.85 |
| **Total de marzo** |  |  |  |  | **31** | **1, 426.85** |

**Resumen – Ejemplo D (Días naturales)**

|  |  |  |  |
| --- | --- | --- | --- |
| **Mes** | **Cant.** | **Segmentos** | **Total mensual** |
| Enero | 1 | 1 (11 %, días 15-31) | $614.79 |
| Febrero | 1 | 2 (12 % + 13 %) | 1, 167.12 |
| Marzo | 1 | 1 (14 %) | 1, 426.85 |

**Ejemplo E: Método lineal utilizando días laborables con reglas a nivel de plan**

En el caso de la opción «**Línea recta con días laborables** », la lógica es idéntica a la de «Días naturales», pero en cada segmento de tarifa solo se contabilizan **los días laborables** (excluidos los fines de semana y los días festivos).

Al igual que con los días naturales, en el **mes de inicio (enero)**, solo están activos los días laborables a partir del 15 de enero, y a todos ellos se les aplica la tarifa vigente a partir de la fecha de inicio ( **11 % a partir del 15/01** ).

Calendario laboral: **261 días laborables al año en 2026**

**Fórmula de la tarifa diaria:** Tarifa diaria = (Tarifa base × Tarifa del plan) ÷ 261

**Distribución estimada de días laborables para cada segmento de tarifa:**

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Tasa** | **Días laborables** |
| Ene – Seg. 1 | 15 de enero | 30 de enero | 11 % | 6 |
| Febrero – 1.ª semana | 2 de febrero | 9 de febrero | 12% | 6 |
| Febrero – Seg. 2 | 10 de febrero | 27 de febrero | 13% | 14 |
| Mar – Lun 1 | 1 de marzo | 31 de marzo | 14 % | 22 |

**Enero (12 días laborables: del 15 al 31 de enero)**

El tipo de interés vigente a partir de la fecha de inicio del contrato (15/01) es del 11 %. Los 12 días laborables de enero se incluyen en este segmento de tarifa única.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Tasa** | **Tarifa diaria** | **Días laborables** | **Coste por segmento** |
| Segmento 1 | 15 de enero | 31 de enero | 11 % | (120 000 $ × 11 %) ÷ 261 = 50.77 $ | 6 | $606.90 |
| **Total de enero** |  |  |  |  | **6** | **$606.90** |

**Febrero (20 días laborables)**

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Tasa** | **Tarifa diaria** | **Días laborables** | **Coste por segmento** |
| Segmento 1 | 2 de febrero | 9 de febrero | 12% | (120 000 $ × 12 %) ÷ 261 = 55.17 $ | 6 | $331.03 |
| Segmento 2 | 10 de febrero | 27 de febrero | 13% | (120 000 $ × 13 %) ÷ 261 = 59.77 $ | 14 | $836.78 |
| **Total de febrero** |  |  |  |  | **20** | **1, 167.82** |

**Marzo (22 días laborables)**

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segmento** | **De** | **Para** | **Tasa** | **Tarifa diaria** | **Días laborables** | **Coste por segmento** |
| Segmento 1 | 1 de marzo | 31 de marzo | 14 % | (120 000 $ × 14 %) ÷ 261 = 64.37 $ | 22 | 1, 416.09 |
| **Total de marzo** |  |  |  |  | **21** | **1, 416.09** |

**Resumen – Ejemplo E (Días laborables)**

|  |  |  |  |
| --- | --- | --- | --- |
| **Mes** | **Cant.** | **Segmentos** | **Total mensual** |
| Enero | 1 | 1 (11 %, días laborables 15-30) | $606.90 |
| Febrero | 1 | 2 (12 % + 13 %) | 1, 167.82 |
| Marzo | 1 | 1 (14 %) | 1, 416.09 |
