---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Planificación de contratos"
breadcrumb:
  - "Planning"
  - "Planificación de contratos"
source_path: "it-planning/planning/manage-contracts.html"
images:
  - "resources/images/it_planning_images/vatinfo.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planificación de contratos

El módulo de planificación de contratos le permite presupuestar, prever y gestionar los contratos de proveedores y vendedores dentro de su modelo de planificación financiera de TI. Al modelizar los contratos -su compromiso, devengo de costes y amortización- se obtiene una mayor visibilidad de las obligaciones fijas y recurrentes, lo que permite tomar mejores decisiones sobre renovaciones, compromisos de gasto y calendario de gastos.

**Por qué es importante**

- Los contratos suelen constituir una parte importante del gasto operativo de TI.
- Sin modelizar los contratos, la planificación puede omitir compromisos a largo plazo u ocultar obligaciones futuras hasta el momento de la renovación.
- Con Planificación de contratos puede:
  - Capturar las fechas de inicio y finalización del contrato, los importes y la metodología de amortización
  - Prever cómo afectarán los gastos del contrato a lo largo del tiempo (no sólo en el momento de la compra)
  - Adaptar las obligaciones contractuales a los centros de costes, cuentas, departamentos y planes financieros

## Configurar la planificación de contratos

Nota: Para realizar estas tareas se requieren los roles de Administrador o Propietario de Proceso Presupuestario.

Antes de empezar a introducir partidas individuales de contratos, deberá activar los Contratos y configurar los datos de referencia para que los contratos se comporten de forma coherente en su modelo.

Al activar la planificación de contratos se activan las tablas de Datos de Referencia relacionadas y se añade la pestaña **Contratos** a la tabla Gastos.

Pasos de configuración

1. Vaya a **Ajustes** (icono de engranaje) **→ Perfil de empresa**.
2. Habilite **los Contratos** y haga clic en **Guardar y Salir**.
3. Vaya a **Configuración → Datos de referencia → Tipo de contrato**.
4. Exporte la plantilla y rellene los campos clave:
5. **Tipo de contrato -** Clasificación o etiqueta utilizada para identificar la categoría o naturaleza del contrato.
6. **Método de amortización del contrato** (por ejemplo, línea recta por periodos pares, línea recta por días naturales, línea recta prorrateando el primero y el último, línea recta por duración, amortización manual). Consulte [Métodos de amortización](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-amortization-methods "(se abre en una pestaña o una ventana nueva)").
7. **Cuenta** - la cuenta de mayor en la que se devengará el coste del contrato
8. Importe el CSV actualizado y **publique** los cambios para que estén disponibles para los nuevos planes.

## Configurar el Impuesto sobre el Valor Añadido (IVA)

Nota: Para realizar estas tareas se requieren los roles de Administrador o Propietario de Proceso Presupuestario.

Apptio La planificación puede calcular automáticamente **el impuesto sobre el valor añadido (IVA)** -también conocido como impuesto sobre bienes y servicios- para las partidas de los contratos.

Para activar los cálculos del IVA, vaya a **Configuración → Perfil de empresa** y active la opción **Incluir impuesto sobre el valor añadido (IVA)**. Al activar esta opción, se creará automáticamente una tabla de datos de referencia **de tipos de IVA**.

El IVA se calcula en función de la **Localización** seleccionada en cada partida del contrato:

- Cuando se introduce una partida contractual y se especifica una **Ubicación**,
- Apptio Planificación buscará **el tipo de IVA** en la tabla de datos de referencia,
- Y calcular automáticamente el **Importe con IVA**.
- El IVA no se amortiza: sólo se utiliza para la amortización el importe original (antes del IVA).

Consulte el [Impuesto sobre el Valor Añadido](value-added-tax.html "Apptio La planificación admite la modelización del Impuesto sobre el Valor Añadido (IVA) para las partidas de los contratos, lo que permite a las organizaciones representar con precisión el gasto total de los contratos, con o sin impuestos. El IVA es un impuesto sobre el consumo que se aplica a bienes y servicios y, dependiendo de las políticas contables de su organización, puede ser recuperable o no recuperable.") para más detalles

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/vatinfo.png)

**Pasos de configuración**

**Antes de importar los tipos de IVA**, asegúrese de que sus **datos de referencia de ubicación** incluyen todas las ubicaciones pertinentes en las que debe aplicarse el IVA.

1. Vaya a **Ajustes** (icono de engranaje) **→ Perfil de empresa**.
2. Active **Incluir el Impuesto sobre el Valor Añadido (IVA)** y haga clic en **Guardar y Salir**.
3. Navegue hasta **Configuración → Datos de referencia → Tipos de IVA**.
4. Exporte la plantilla y rellene los campos clave:
5. **Localización** - El identificador de localización utilizado para determinar el tipo de IVA aplicable.
6. **Tipo de IVA** - El tipo impositivo a aplicar, introducido como decimal (por ejemplo, introduzca 0.20 para un 20%).
7. Importar el CSV actualizado
8. Haga clic en el **menú Elipses** y **Publique** los cambios para que estén disponibles para los planes.

![imagen del impuesto sobre el valor añadido](../../../../../03-media/apptio-planning/resources/images/it_planning_images/vatinfo.png)

## Introducción y gestión de partidas contractuales

- Abra su plan y navegue hasta la pestaña **Contratos** dentro de la página **Gastos**.
- Añade un nuevo contrato:
  - Utilizando la **fila vacía** de la parte inferior de la tabla, o bien
  - **Haga clic con el botón derecho** y seleccione **Insertar fila**
- Proporcione la información requerida para cada contrato:
  - **Tipo de contrato** - La categoría o clasificación del contrato, que determina las normas contables por defecto, como el método de amortización.
  - **Centro de costes-** **El** centro de costes responsable financieramente del coste y la amortización del contrato.
  - **Proveedor** (opcional) - Proveedor o parte externa que presta el servicio contratado. Útil para la elaboración de informes y el análisis de gastos de proveedores.
  - **Ubicación** (opcional) - Se utiliza para determinar el tipo de IVA aplicable si el IVA está activado. El IVA se calcula en función de este lugar.
  - **Importe del contrato -** El valor total del contrato comprometido que se amortizará a lo largo del plazo del contrato seleccionado.
  - **Fecha de inicio** - Fecha en la que el contrato se activa y comienza el reconocimiento de gastos (amortización).
  - **Fecha de finalización** - Fecha en la que finaliza la vigencia del contrato y cesa el reconocimiento de gastos.
  - **Método de amortización:** método utilizado para distribuir el coste del contrato a lo largo de periodos de tiempo. Se rellena automáticamente en función del tipo de contrato, pero puede modificarse si es necesario.
  - **Amortizar** (casilla de verificación) -
    - Activado (verdadero): Distribuye uniformemente el importe del contrato a lo largo de toda la duración del mismo.
    - Desactivado (falso): Reconoce el importe total del contrato en el primer periodo de la fecha de inicio del contrato.
- Revise el plan de amortización generado por el sistema y compruebe que se ajusta a sus expectativas (p. ej., el coste se distribuye entre los meses como corresponde).

Una vez introducido el contrato, Apptio Planning calcula automáticamente el gasto de amortización en función de los detalles del contrato y del método de amortización seleccionado. A continuación, el gasto se distribuye entre las columnas de periodos de tiempo de la pestaña Contratos.

En la pestaña **Resumen**, Apptio Planning genera el asiento financiero correspondiente al gasto de amortización utilizando la **Cuenta de Amortización** configurada.

## Delegar gastos de contrato a un centro de coste diferente

Si el gasto de amortización debe cargarse a un centro de coste distinto del que posee el contrato, puede rellenar los campos **Centro de coste de delegación** y **Fecha de inicio de la delegación**. Esto redirige el gasto a otro centro de coste a partir de la fecha especificada.

Esto es útil en escenarios como cuando un contrato es adquirido por un centro de coste de Proyecto, pero los costes en curso deben ser cargados a un centro de coste operativo diferente.

En esta configuración, el contrato sigue perteneciendo al centro de costes original, pero el impacto financiero se aplica al centro de costes delegado.
