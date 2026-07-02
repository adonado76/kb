---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Servicio multidivisa en Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
source_path: "admin/multi-currency-cldy.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Servicio multidivisa en Cloudability

El servicio «Multi-Currency» ofrece una plataforma centralizada para gestionar las tablas de cambio de divisas de tus productos de Apptio. El servicio simplifica la gestión y elimina la necesidad de mantener tablas independientes para cada producto. Puedes cargar las tablas de cambio de divisas desde una interfaz común y configurar los distintos productos de Apptio para que utilicen las mismas tablas en los cálculos de divisas.

Para obtener más información, consulta [https://www.ibm.com/docs/en/apptio-platform/multi-currency-service/saas?topic=multi-currency-service](https://www.ibm.com/docs/en/apptio-platform/multi-currency-service/saas?topic=multi-currency-service "(se abre en una pestaña o una ventana nueva)").

El servicio multidivisa te permite utilizar una moneda común en todo Cloudability, independientemente del proveedor de servicios en la nube o de la moneda en la que se facture. Las organizaciones pueden operar y comunicarse en la moneda que prefieran sin necesidad de realizar conversiones de divisas fuera de Cloudability.

El contacto de facturación de Cloudability de una organización puede designar una moneda preferida para que los usuarios vean los informes y los paneles de control, así como definir los tipos de cambio que se utilizan para la conversión de divisas.

Solo los usuarios con el rol **« Cloudability » (Administrador de facturación)** o a los que se les haya asignado el permiso « **OrgCurrencyFeatureAccess** » (Configurar preferencias de moneda) en su rol pueden configurar las preferencias de moneda

**Cómo habilitar la configuración multidivisa en Cloudability**

En Cloudability, la configuración multidivisa solo puede ser activada por usuarios con el rol **Cloudability «Administrador de facturación** » o con el permiso **OrgCurrencyFeatureAccess** asignado a su rol (en adelante, «Administrador de facturación»).

En primer lugar, el administrador de facturación debe configurar la moneda preferida siguiendo los pasos que se indican a continuación:

1. Accede a la página de inicio de Cloudability.
2. Selecciona el icono **de Perfil** situado en la esquina superior derecha de la página y selecciona **Gestionar perfil**.
3. En la página de tu perfil, selecciona la pestaña «**DIVISAS** ».
4. En el menú «MONEDA», selecciona la moneda que prefieras.
5. En el menú **LOCALE**, selecciona la configuración regional que prefieras. Se muestra de forma dinámica una vista previa de la moneda seleccionada.
6. Selecciona **la opción «Guardar** configuración de divisas».

Se trata de una configuración que solo hay que realizar una vez, y que solo es aplicable durante la configuración inicial.

A continuación, el administrador de facturación debe acceder a la pantalla de configuración multidivisa desde el menú «Configuración» (icono de engranaje) situado en la esquina superior derecha de Apex Shell y seleccionar «Configuración multidivisa». Esto abrirá la página «Gestionar cambio de divisas».

Al hacer clic en «Subir nueva tabla de cambio de divisas», aparecerá una opción en el panel de la derecha para descargar una tabla de cambio de divisas de ejemplo. Puedes crear tu tabla de cambio de divisas utilizando este archivo.

Puedes crear una tabla de cambio de divisas utilizando un editor de texto o una hoja de cálculo. Multi-Currency Service Admite los formatos de archivo .xls, .xlsx,.csv y.tsv.

Tu tabla de cambio de divisas debe incluir las tres columnas siguientes:

- currrencyCode: Especifica el código de moneda ISO 4217 de tres caracteres; por ejemplo, USD, CAD, JPY y GBP. currencyCode No puede estar en blanco.
- currencyRate: Especifica el tipo de cambio entre esta moneda y tu moneda base. La moneda base siempre tendrá un valor de « currencyRate: » igual a 1. « currencyRate: » debe ser un valor numérico y no puede dejarse en blanco.
- rateType: Especifica si el tipo de cambio es de tipo «Plan» o «Real». Las tarifas del plan se pueden utilizar con los costes presupuestados o previstos, mientras que las tarifas reales se aplican a los costes reales o históricos en los que se ha incurrido efectivamente. Aunque esta columna es obligatoria, las celdas pueden quedar en blanco. Deja esta celda en blanco para la moneda base.

El siguiente ejemplo muestra una tabla de tipos de cambio a modo de muestra.

| currencyCode | currencyRate | rateType |
| --- | --- | --- |
| EUR | 0.96 | Real |
| EUR | 0.91 | Plan |
| CAD | 1.33 | Real |
| CAD | 1.2 | Plan |
| Libras esterlinas (GBP) | 0.85 | Real |
| Libras esterlinas (GBP) | 0.75 | Plan |
| USD | 1 |  |

Una vez creada la tabla, arrastra el archivo y suéltalo en el área de destino. También puedes seleccionar «Buscar un archivo » y, en el explorador de archivos, seleccionar el archivo.

En «Válido a partir del », selecciona el mes y el año a partir de los cuales deben ser válidos tus tipos de cambio

Selecciona «Guardar ».

Nota: Al hacer clic en «Guardar», se comprobará que los códigos de moneda del archivo subido sean válidos y se mostrarán los errores si alguno de los códigos de moneda que has subido no es válido. Además, si ya habías subido una tabla de cambio de divisas anteriormente y en el último archivo subido faltan algunas de las divisas que habías seleccionado como «Divisas mostradas» (en la subida anterior), aparecerá un aviso al hacer clic en «Guardar».

Una vez finalizada la carga, la nueva tabla de cambio de divisas se añade a la tabla de la página «Gestionar cambio de divisas ». Puedes seleccionar el título de la tabla para ver los datos que contiene. El campo «Moneda base (global) » se actualiza para reflejar la moneda base definida en la tabla de cambio de divisas. Ten en cuenta que la divisa cuyo tipo de cambio se haya fijado en 1 se considera la divisa base.

La lista de «Monedas mostradas» se actualiza para incluir todas las demás monedas especificadas en la tabla de cambio de divisas. Puedes abrir la lista «Monedas mostradas » y desmarcar las casillas correspondientes a las monedas que no quieras que vean los usuarios finales.

Una vez completados estos pasos, los cambios pueden tardar hasta 24 horas en surtir efecto.

Nota: Si recibes pagos en diferentes monedas procedentes de distintos proveedores de servicios en la nube, deberás definir los tipos de cambio de todas esas monedas en tu tabla de cambio de divisas, de modo que cada moneda se convierta a la moneda de la organización utilizando los tipos de cambio cargados en MCS.

Lista de códigos de divisas compatibles con Cloudability

| Nombre de la moneda | Código de moneda |
| --- | --- |
| Peso argentino | ARS |
| Dólar autraliano | AUD |
| Real brasileño | BRL |
| Dólar canadiense | CAD |
| Franco suizo | CHF |
| Yuan chino | CNY |
| Peso chileno | CLP |
| Corona checa | CZK |
| Corona danesa | DKK |
| Euro | EUR |
| Libra esterlina británica | Libras esterlinas (GBP) |
| Dólar de Hong Kong | HKD |
| Rupia indonesia | IDR |
| Shekel israelí | ILS |
| Rupia india | INR |
| Yen japonés | JPY |
| Won surcoreano | KRW |
| Peso mexicano | MXN |
| Ringgit malasio | MYR |
| Corona noruega | NOK |
| Dólar neozelandés | NZD |
| Zloty polaco | PLN |
| Rublo ruso | RUB |
| Riyal saudí | SAR |
| Corona sueca | SEK |
| Dólar de Singapur | SGD |
| Baht tailandés | THB |
| Lira turca | TRY |
| Dólar taiwanés | TWD |
| Dólar de EE.UU. | USD |
| Dong vietnamita | VND |
| Rand sudafricano | ZAR |
