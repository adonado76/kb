---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar la multidivisa"
breadcrumb: []
source_path: "studio/admin/configure-multi-currency.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar la multidivisa

Se aplica a: TBM Studio v12.1 y posteriores

Si su empresa tiene oficinas en más de un país, debe configurar la multidivisa. Como mínimo, debe introducir los tipos de cambio anuales. Si necesita cifras más actualizadas, puede utilizar los tipos de cambio trimestrales o mensuales.

- Cuando se configura la multidivisa para un proyecto, se activan las siguientes funciones:
- El Admin selecciona una moneda base y una configuración regional para un proyecto (utilice la pestaña **Proyecto**, grupo **Configuración del proyecto**, comando **Configuración del proyecto** ).
- El administrador puede introducir tipos de cambio para cualquier otra divisa (pestaña Datos > Tabla de tipos de cambio).
- Todos los valores monetarios de los informes se muestran en función de los tipos de cambio.
- Al definir una métrica, puede seleccionar un tipo de tarifa multidivisa por defecto. Por ejemplo: si hay dos tipos de tarifa, Plan y Real, podría elegir Plan o podría elegir Real.

  Nota: En el caso de los productos multidivisa de Apptio Cloud, los valores de la columna Tipo de los datos que cargue en la tabla Cambio de divisas deben estar etiquetados como Real en los datos sin procesar para que funcione la función multidivisa.
- Los usuarios pueden seleccionar una moneda y una configuración regional para su perfil (haga clic en el nombre de usuario de la cabecera).
- Los usuarios pueden seleccionar una moneda para un informe específico y todos los valores de los componentes Ad Hoc del informe se mostrarán en dicha moneda (haga clic en la lista multidivisa de la barra de herramientas del informe).![](../../resources/images/studio_images/studioimages/studio_report%20toolbar_multi-currency.png)
- En el modo TBM Studio , los valores se muestran siempre en la moneda base.
- Las divisas se convierten a partir de la divisa base.
- Todos los informes temporales utilizan el tipo de cambio del mes correspondiente o el tipo de cambio anual. Utilizando el tipo de cambio mensual, las variaciones de los valores pueden vincularse a las variaciones de los tipos de cambio.
- Puede añadir columnas a las tablas Ad Hoc y seleccionar la moneda y el tipo de cambio para la columna. Una tabla puede tener columnas que muestren valores en distintas monedas.

Para obtener información adicional relacionada con el uso de múltiples monedas para productos de Apptio Cloud, consulte [Configurar múltiples monedas para Cloud](../../cost-transparency/configuration/multicurrency.html "(se abre en una pestaña o una ventana nueva)").

## Divisas y localizaciones admitidas

La divisa determina el símbolo de la divisa (por ejemplo, g.: €/$) y el código internacional de tres letras de la divisa (por ejemplo, g.: EUR/USD) que se muestra con los valores. La configuración regional determina el formato de los números. Ambos son independientes entre sí. La configuración regional determina la colocación y el espaciado de los símbolos monetarios, pero no mediante una interpretación literal de la plantilla de formato de gráfico. Así, $#,### se interpreta como "mostrar como moneda", con separadores de "miles", precisión cero y el símbolo de moneda colocado (prefijo frente a sufijo, espaciado) en función de la configuración regional.

La aplicación admite todos los códigos de moneda que figuran en la lista de códigos ISO 4217 de la Organización Internacional de Normalización. La aplicación admite las siguientes configuraciones regionales. Los códigos de moneda correspondientes y los formatos de configuración regional aparecen junto a cada configuración regional.

> Argentina | ARS | #.##0,##
>
> Australia | AUD | ##0.##
>
> Austria | EUR | #.##0,##
>
> Bélgica (neerlandés) | EUR | #.##0,##
>
> Bélgica (francés) | EUR | #.##0,##
>
> Botsuana | BWP | #,##0.##
>
> Brasil | BRL | #.##0,##
>
> Canadá (francés)| CAD | #.##0,##
>
> Canadá (inglés) | CAD | #,##0.##
>
> China (continental) | CNY | #,##0.##
>
> Colombia | COP | #.##0,##
>
> República Checa | CZK | #.##0,##
>
> Dinamarca | DKK | #.##0,##
>
> Ecuador | USD (antes ECS) | #,##0.##
>
> Etiopía | ETB | #,##0.##
>
> Finlandia | EUR | #.##0,##
>
> Francia | EUR | #.##0,##
>
> Alemania | EUR | # ##0,##
>
> Ghana | GHS | #,##0.##
>
> Honduras | HNL | #,##0.##
>
> Hungría | HUF | # ##0,##
>
> Irlanda (inglés) | EUR | #.##0,##
>
> Irlanda (irlandés) | EUR | #.##0,##
>
> Italia | EUR | #.##0,##
>
> Japón | JPY | #,##0
>
> Kenia | KES | #,##0.##
>
> Luxemburgo (francés) | EUR | #.##0,##
>
> Luxemburgo (alemán) | EUR | #.##0,##
>
> Malaui | MWK | #,##0.##
>
> Mauricio | MUR | #,##0
>
> México | MXN | #,##0.##
>
> Mozambique | MZN | #.##0,##
>
> Países Bajos | EUR | #.##0,##
>
> Nigeria | NGN | #,##0.##
>
> Noruega (Bokmal) | NOK | # ##0,##
>
> Noruega (Nynorsk) | NOK | # ##0,##
>
> Panamá | PAB | #,##0.##
>
> Perú | PEN | #,##0.##
>
> Polonia | PLN | # ##0,##
>
> Portugal | EUR | #.##0,##
>
> Rumanía | RON | #.##0,##
>
> Eslovaquia | EUR | #.##0,##
>
> Sudáfrica | ZAR | ##0.##
>
> Corea del Sur | KRW |#,##0 (añadido en R11.8.1.5 )
>
> España (catalán) | EUR | #.##0,##
>
> España (Español) | EUR | #.##0,##
>
> Suazilandia | SZL | #,##0.##
>
> Suecia | SEK | # ##0,##
>
> Suiza (francés) | CHF | #'##0.##
>
> Suiza (alemán) | CHF | #'##0.##
>
> Suiza (italiano) | CHF | #'##0.##
>
> Tanzania | TZS | #,##0.##
>
> Uganda | UGX | #,##0.##
>
> Emiratos Árabes Unidos | AED | #,##0.##
>
> Reino Unido | GBP | #.##0,##
>
> Estados Unidos | USD | #,##0.##
>
> Vietnam | VND | #,##0

## Restricciones

La multidivisa tiene las siguientes restricciones:

- En los informes, sólo los valores basados en métricas modeladas de los tipos Cálculo de costes y Determinación de precios pueden mostrarse en la moneda elegida por los usuarios. Todos los demás valores se mostrarán en la moneda base o en la moneda a la que se hayan convertido.
- La multidivisa sólo se aplica a las tablas y gráficos Ad Hoc. No se aplica a las tablas y gráficos heredados.
- Las tablas editables se muestran en la moneda asignada al conjunto de datos y no pueden modificarse.
- No se aplica a la antigua aplicación de Presupuestos y Previsiones.
- Los gráficos en cascada siempre se muestran en la moneda base establecida para el proyecto.
- En el modo TBM Studio , la moneda de la sesión pasa a ser la moneda base.

## Configurar la multidivisa

Pasos clave para configurar la multidivisa:

1. Introduzca los tipos de cambio en la tabla **Cambio de divisas** de la categoría **Otros**. Si la tabla no está en la categoría **Otros**, establezca el Filtro en **Oculto** para mostrar el nombre de la tabla.![](../../resources/images/studio_images/studioimages/studio_project%20explorer_currency%20exchange.png)
2. Asigne tipos de tarifa por defecto a cada métrica de costes y precios.
3. Seleccione una moneda (y configuración regional) para el proyecto.

   Nota: La divisa determina el símbolo de la divisa (e. g.: €/$) y el código de divisa internacional de tres letras (e. g.: EUR/USD) que se muestra con los valores. La configuración regional determina el formato de los números. Ambos son independientes entre sí.

## Introducir tipos de cambio

Introduzca los tipos de cambio en la tabla Cambio de divisas. La moneda base siempre se fija en 1. El **código de moneda** debe ser uno de los códigos de moneda internacionales estándar de tres letras. El tipo debe ser un multiplicador de conversión del tipo de la moneda base. El tipo es una breve descripción del tipo de cambio. Dos descripciones comunes son Plan para valores anuales y Actual para valores mensuales. En la siguiente imagen se muestra un ejemplo de tabla de cambio de divisas:

![](../../resources/images/studio_images/studioimages/studio_currency%20exchange_table.png)

Debe introducir los mismos tipos de cambio para cada moneda. Por ejemplo, si define tipos de cambio Plan y Real para la moneda EUR, también deberá definir tipos de cambio Plan y Real para todas las demás monedas.

Nota: La moneda base no tiene tipo y puede aparecer en cualquier lugar de la tabla. No tiene por qué ser la primera entrada de la tabla.

Si introduce un código de moneda que no coincide con ninguna configuración regional, se mostrará el código de moneda de tres letras en lugar del símbolo de moneda. Por ejemplo: CNL59,000.

## Asignar un tipo de interés por defecto a cada métrica monetaria

Para que los informes se muestren correctamente, debe definir un tipo de tarifa para cada métrica modelada de costes y precios. Los tipos de tarifa más comunes son Plan, Real, Mensual y Semanal. Para asignar un tipo de tarifa por defecto:

1. En el Explorador de proyectos, haga clic en la métrica.
2. En el campo **Tipo de cambio multidivisa por defecto**, seleccione un tipo de cambio.![](../../resources/images/studio_images/studioimages/studio_cost%20ytd_formula%20metric.png)
3. Compruebe que el campo **Formato de tabla** (véase más arriba) tiene una entrada =Divisa.

## Seleccione una moneda (y configuración regional) para el proyecto

1. Abra la pestaña **Proyecto** y haga clic en **Configuración del proyecto**.
2. Seleccione una moneda en el campo **Moneda base**.
   - Esto controla el símbolo de moneda (e. g.: €/$) y el código de moneda internacional de tres letras (e. g.: EUR/USD) que se muestra con los valores.

     Nota: Cuando los usuarios trabajan en TBM Studio, todos los valores se mostrarán en la moneda base, independientemente de las preferencias de moneda que el usuario haya seleccionado.
   - Si selecciona Moneda única, la multidivisa no estará activa para el proyecto.
3. Seleccione una configuración regional en el campo **Configuración regional**. La configuración regional determina el formato de los números. La localización es independiente de la moneda. Ejemplo de locales:
   - Estados Unidos: 12, 345.67
   - Francia: 12 345,67
   - Alemania: 12.345,67

## Convertir los datos en tarifa base

Si importa datos en varias monedas que desea combinar en un único conjunto de datos, primero debe convertir los datos a la moneda base del proyecto. Por ejemplo, puede importar valores de varios libros mayores.

1. Importe el conjunto de datos.
2. Añada una columna al conjunto de datos de transformación utilizando el botón [ConvertCurrencyToBase](../formulas-and-functions/functions/convertcurrencytobase.htm "(se abre en una pestaña o una ventana nueva)") function.This la columna contendrá los valores de la moneda base.
3. Añade el conjunto de datos al conjunto de datos fusionados.

   Nota: También existe una función.
