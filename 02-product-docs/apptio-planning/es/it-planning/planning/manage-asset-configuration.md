---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Configurar activos"
breadcrumb: []
source_path: "it-planning/planning/manage-asset-configuration.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar activos

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Vea este vídeo de Apptio Education Services: [Configuración de datos de referencia: Dimensiones de contratos y activos](https://community.apptio.com/videos/1994 "(se abre en una pestaña o una ventana nueva)").

O vea todos los [vídeos y recursos de formación de Apptio Planning](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(se abre en una pestaña o una ventana nueva)") .

Las dimensiones son las categorías de datos esenciales en las partidas presupuestarias. Muchas dimensiones incorporadas tienen dependencias con otras dimensiones (para más información, véase [Atributo de datos de referencia y dependencias de dimensiones](manage-reference-data.html) ). Puede importar datos de referencia de dimensiones desde un archivo.csv o desde Costing Standard y exportar plantillas de datos de referencia de dimensiones y datos de tablas (véase [Gestionar dimensiones](manage-reference-data.dital "(se abre en una pestaña o una ventana nueva)") ).

Los datos de referencia de la clase de activos controlan cómo se contabilizan las compras de activos de capital y la depreciación en los presupuestos de OpEx y CapEx. Por ejemplo, puede especificar que una determinada clase de activo siempre se acumule en una cuenta de compras CapEx específica y en una cuenta de depreciación OpEx.

1. Habilitar Activos (véase [Editar el perfil de la empresa](edit-company-profile.dita "(se abre en una pestaña o una ventana nueva)") ).
2. En el menú de navegación, seleccione Configuración > Datos de referencia > Clase de activos.
3. Seleccione ![](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) en la esquina superior derecha de la tabla, seleccione Exportar > Exportar todo.
4. Abra el archivo.csv descargado y actualice los valores de los datos según sea necesario:
   - Clase de activos - Identificador único del nombre de la categoría de la clase de activos
   - Cuenta de depreciación - OpEx cuenta que acumula el gasto de depreciación de la clase de activo seleccionada
   - Método de depreciación - Modelo utilizado para predecir la pérdida de valor a lo largo del tiempo de la clase de activos. Para más información, véase Planificar la disminución del valor de los activos fijos con métodos de amortización.
   - Cuenta de compras - La cuenta CapEx que acumula los gastos de compra de la clase de activos seleccionada
   - Vida útil del activo (meses) : la vida útil de depreciación estándar de la clase de activo
   - Valor residual % - Porcentaje del precio de compra que se calculará como valor residual para la clase de activos
   - Tasa de saldo (%) - La tasa de saldo decreciente que se aplicará para la depreciación anual de saldo decreciente. En este método de depreciación, el coeficiente de equilibrio se aplicará al valor del activo cada año. Por ejemplo, un activo con un precio de compra de 100.000 dólares que se deprecia con una tasa de equilibrio del 40% depreciaría 40.000 dólares en su primer año.
5. Ahora, Configuración > Datos de referencia > Clase de activo e importe el archivo.csv actualizado.

Consejo: Puede añadir atributos personalizados a las dimensiones de los activos para capturar información complementaria sobre los activos y mejorar sus capacidades de análisis e informes. Para obtener más información, consulte [Añadir y gestionar atributos personalizados de datos de referencia (dimensiones y tablas de partidas individuales)](manage_schema.dita "(se abre en una pestaña o una ventana nueva)").

## Fórmulas para calcular la amortización para cada uno de los métodos de amortización enumerados

**La línea recta utiliza la fórmula**

- Importe de la amortización = (Precio del activo \* (1 - Valor residual)) / Vida útil del activo
- Vida útil del activo = Duración en meses o días

**El doble declive utiliza la fórmula:**

- Importe de la amortización = 2 \* ( 1 / Vida útil del activo) \* Valor contable del período inicial
- Vida útil del activo = Duración en meses o días
- Valor contable al inicio del período = Precio del activo - Amortización acumulada

**El Saldo Decreciente utiliza la Tasa de Saldo para calcular cada periodo:**

- Importe de la amortización = Saldo de activos \* Tasa de saldo / 12
- Nuevo cálculo al principio de cada año: Saldo Activo = Saldo Activo - Saldo Activo \* ( Tasa Saldo / 12 ) \* # Meses Amortizados en el año anterior

## Ejemplo

Precio de los activos = $40K

Vida útil = 12 meses

Fecha de entrada en servicio = 15/1/2024

Línea recta ( P1 FY24 ) = $40K \* (1 - 0) / 12 = $3333

Doble decreciente ( P1 FY24 ) = 2 \* (1/12) \* ( $40K - $0) = $6667

Doble descenso ( P2 FY24 ) = 2 \* (1/12) \* ( $40K - $6666) = $5556 (editado)

Nota: La doble depreciación calcula el valor contable al principio de cada período en lugar de al principio del año. Por lo tanto, si desea modelar un Saldo Decreciente Doble estándar (el doble de la tasa de la línea recta), deberá utilizar Saldo Decreciente con una Tasa de Saldo = 200%.
