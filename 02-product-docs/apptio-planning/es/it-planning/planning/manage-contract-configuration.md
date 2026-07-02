---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Configurar contratos"
breadcrumb: []
source_path: "it-planning/planning/manage-contract-configuration.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar contratos

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Las dimensiones son las categorías de datos esenciales en las partidas presupuestarias. Muchas dimensiones incorporadas tienen dependencias con otras dimensiones (para más información, véase [Atributo de datos de referencia y dependencias de dimensiones](manage-reference-data.html) ). Puede importar datos de referencia de dimensiones desde un archivo.csv o desde Costing Standard y exportar plantillas de datos de referencia de dimensiones y datos de tablas (véase [Gestionar dimensiones](manage-reference-data.html) ).

![ver icono](../../resources/images/it%20planning_images/icon_video.png)

## Gestionar los datos de referencia del tipo de contrato

Un propietario o administrador del proceso presupuestario puede definir reglas para controlar cómo se contabilizan los tipos de contrato en los presupuestos de OpEx. Puede especificar que un determinado tipo de contrato se acumule siempre en una cuenta OpEx específica con un método de amortización concreto.

1. Habilite las funciones de Contratos e IVA en el Perfil de empresa (véase [Editar el Perfil de empresa.](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.")
2. En el menú de navegación, seleccione Configuración > Datos de referencia > Tipo de contrato.
3. Seleccione ![más icono](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) en la esquina superior derecha de la tabla, seleccione Exportar > Exportar todo.
4. Actualice los valores de la tabla de datos según sea necesario en el archivo.csv:
   - Tipo de contrato - Proporcione un nombre para la combinación de la cuenta del libro mayor y el método de amortización. Unos nombres de tipo de contrato significativos pueden ayudar a los Propietarios de Centros de Coste a asignar sus gastos contractuales a los códigos de cuenta correctos del libro mayor.

     Por ejemplo, los tipos de contrato con nombres significativos para el Propietario del Centro de Coste, como Mantenimiento de Hardware, pueden asignarse todos al mismo código de cuenta del libro mayor de Servicios a Proveedores.
   - Método de amortización del contrato - Especifica cómo se amortizará su contrato a lo largo de la vida del mismo. La amortización de contratos permite repartir los costes a lo largo de la vida de un contrato en lugar de devengar el importe total del contrato en la fecha de inicio del mismo. La Compensación de inicio de amortización retrasa el inicio de la amortización, modifica el número de periodos y mantiene la misma fecha de finalización de los contratos. Al retrasar la fecha de inicio, cambia el número de periodos del plan de amortización. Sin embargo, el periodo final del calendario no cambia. Todos los cálculos para cada día se basan en el calendario gregoriano estándar. Existen los siguientes métodos:
     - Amortización manual : le permite importar, introducir y editar manualmente los importes de gastos amortizados por período para un contrato.
     - Línea recta Períodos pares - (Método por defecto) Amortiza los gastos uniformemente para cada período. El periodo de amortización viene definido por el mes de inicio y fin del contrato.
     - Línea recta por duración - Amortiza los gastos uniformemente por cada periodo. El periodo de amortización se define por el número de meses del contrato.
     - Prorrata lineal primero y último - Amortiza importes iguales para periodos distintos del primero y el último. Para el primer y el último periodo, los importes se prorratean en función del número de días de cada periodo.
     - Línea recta utilizando días naturales - Amortiza los importes individualmente para cada periodo basándose en el número de días naturales de cada periodo.
   - Cuenta - Especifica el código de cuenta del libro mayor donde se devengará el contrato. Las opciones disponibles vienen dadas por los datos de referencia del Plan General de Contabilidad.
5. Ahora, Configuración > Datos de referencia > Tipo de contrato y, a continuación, importe el archivo.csv actualizado

## Ejemplo de amortización de un contrato

El siguiente ejemplo utiliza estos valores iniciales:

- Importe - $ 400.00
- Fecha de inicio - 20 de agosto de 2017
- Fecha de finalización - 19 de diciembre de 2017
- Duración calculada utilizando sólo el mes (utilizado por el método de los periodos pares) - 5 meses
- Duración calculada utilizando el mes y el día (utilizado por el método de la Duración) - 4 meses

| Método de amortización | Ago. | Sept. | Oct. | Nov. | Dic. | Total |
| --- | --- | --- | --- | --- | --- | --- |
| Línea recta Períodos pares | $400 / 5 = $80 | $400 / 5 = $80 | $400 / 5 = $80 | $400 / 5 = $80 | $400 / 5 = $80 | $400 |
| Línea recta por duración | $400 / 4 = $100 | $400 / 4 = $100 | $400 / 4 = $100 | $400 / 4 = $100 |  | $400 |
| Prorrateo en línea recta primero y último | 12 / 122 $400 = $ 39.34 | $ 298.36 / 3 = $ 99.45 | $ 298.36 / 3 = $ 99.45 | $ 298.36 / 3 = $ 99.45 | 19 / 122 $400 = $ 62.30 | $400 |
| Línea recta por días naturales | 12 / 122 $400 = $ 39.34 | 30 / 122 $400 = $ 98.36 | 31 / 122 $400 = $ 101.64 | 30 / 122 $400 = $ 98.36 | 19 / 122 $400 = $ 62.30 | $400 |

Nota:

- Los importes se calculan a valores exactos. Los importes se redondean a la unidad monetaria más próxima (por ejemplo, USD).
- Agregue atributos personalizados para capturar información complementaria sobre los contratos para mejorar sus capacidades de análisis y generación de informes (consulte [agregar atributos personalizados a las dimensiones del contrato)](manage_schema.html "Los esquemas definen la estructura de los datos en Apptio Planning. Especifican las tablas, campos y relaciones que determinan cómo se almacena, vincula y muestra la información en las pestañas de Gastos, como Trabajo, Contratos, Activos y Finanzas.").
- Los métodos de amortización admitidos para los calendarios personalizados son Línea recta período par, Línea recta utilizando días naturales, Amortización manual y Línea recta por duración calendario fiscal personalizado.

## Gestionar los datos de referencia de los tipos del IVA

Una vez que el propietario o administrador del proceso presupuestario activa las funciones de planificación de contratos e IVA, la aplicación Apptio Planning puede calcular el impuesto sobre el valor añadido (IVA), también conocido como impuesto sobre bienes y servicios, para los contratos y gestionar el tipo de IVA. Véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning."). El Tipo de IVA (una dimensión incorporada) especifica el porcentaje gravado que se aplica a cada ubicación. El IVA se basa en la partida contractual Valor de localización en los datos de referencia. Por lo tanto, antes de importar los datos de referencia de los Tipos de IVA, debe actualizar los datos de referencia de la Localización para incluir todas las localizaciones para las que planea introducir un Tipo de IVA. Véase [Dimensiones de los datos de referencia](manage-reference-data.html).
