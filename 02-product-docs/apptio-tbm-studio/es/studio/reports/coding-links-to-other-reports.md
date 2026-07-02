---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Enlaces de código a otros informes"
breadcrumb: []
source_path: "studio/reports/coding-links-to-other-reports.html"
images:
  - "resources/images/studio_images/studioimages/reports/studio_code_links_to_other_reports_700x534.png"
  - "resources/images/studio_images/studioimages/reports/studio_report_show_api_url_600x155.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Enlaces de código a otros informes

**Se aplica a** : TBM Studio 12.0 y posteriores

Si está creando muchos informes, puede proporcionar al usuario enlaces para pasar rápidamente de un informe a otro utilizando la sintaxis de estilo Wiki. Los enlaces deben introducirse en un cuadro de texto HTML o en un botón.

- Para obtener información sobre la creación de cuadros de texto HTML, consulte [Cuadro de texto HTML](html.html "Se aplica a: TBM Studio 12.0 y posteriores").
- Para obtener información sobre la creación de botones, consulte [Botón](button.html "Se aplica a: TBM Studio R.12.0 y posteriores.").

Los enlaces de estilo wiki también pueden utilizarse en la pestaña **Acciones** de los botones.

## Sintaxis

A continuación se muestra la sintaxis de un enlace tipo Wiki:

> `[[report|display-text|ToolTip-text]]`

Los parámetros de los enlaces se describen en la tabla siguiente:

*informe*

El nombre de un informe infantil. Las opciones son las siguientes:

| **Apptio versión** | **Opción** | **Descripción** |
| --- | --- | --- |
| Todos | *%métrico* | Crea un enlace al informe de métrica especificado y muestra el valor de la métrica como texto del enlace. |
| Todos | .. | Sube un nivel en la jerarquía de informes. |
| Todos | @ | Inserta literalmente esa parte del enlace. Por ejemplo, para informes sobre objetos. |
| Todos | / | Pasa al informe por defecto del proyecto. |
| Todos | *//nombredelproyecto/* | Indica un proyecto diferente del proyecto actual. |
| Todos | diálogo:informe: | Abre el informe como un diálogo modal (es decir, emergente). |
| Todos | tab *:nombre de la ficha/nombre del informe* | Indica un informe en una pestaña. |
| v.11 | ¡ */@Objeto/*!FILTRO[ *Table.Column ="valor"* ] | Puede utilizarse para calificar un informe de objetos. |
| v.11 | ¡/@*.TableTransform:Table/*!FILTRO[ *Table.Column ="valor"* ] | Puede utilizarse para calificar un informe TableTransform. |
| v.12.1, v.12.2+ | dataTable *:nombre de la tabla* | Crea un enlace a una tabla especificada. |
| v.12.1, v.12.2+ | costModel *:nombre del modelo* | Crea un enlace a un informe de resumen del modelo especificado. |

*mostrar-texto*

El texto que aparece en el enlace. Si no se especifica, se utiliza el nombre del informe como texto del enlace.

*texto-herramienta*

El texto que aparece cuando el usuario detiene el puntero del ratón sobre el enlace.

## Caracteres especiales

Si URL incluye caracteres especiales, debe *codificarlos* utilizando la codificación de caracteres estándar URL.

## Ejemplo

- Introduzca %2FA para una barra oblicua ( / )
- Introduzca %22 para las comillas (")

Para más información sobre la codificación de caracteres URL, busque *URL encoding* en Internet.

**VEA TAMBIÉN** : Consulte lo siguiente en *w3schools.com* : [Referencia de codificación HTML URL](https://www.w3schools.com/tags/ref_urlencode.asp "(se abre en una pestaña o una ventana nueva)").

## Codificar URL

Las URL sólo pueden enviarse por Internet utilizando el juego de caracteres ASCII.

- Como las URL suelen contener caracteres fuera del conjunto ASCII, hay que convertir la dirección URL. URL convierte la dirección URL a un formato ASCII válido.
- URL sustituye los caracteres ASCII no seguros por "%" seguido de dos dígitos hexadecimales correspondientes a los valores de los caracteres del juego de caracteres [HTML ISO-8859-1](https://www.w3schools.com/charsets/ref_html_8859.asp "(se abre en una pestaña o una ventana nueva)").
- Las URL no pueden contener espacios. URL sustituye un espacio por un signo **+**.

## Ejemplos

El siguiente ejemplo crea un enlace al informe secundario Aplicaciones, con el texto de enlace **Haga clic aquí** y una sugerencia de herramienta que indica **Este informe Aplicaciones es preliminar** :

> ```
> [[Applications|Click here|This Applications report is
>       preliminary.]]
> ```

El siguiente ejemplo crea un enlace a un informe de nivel superior denominado Análisis de grupos de servidores (observe la barra oblicua inicial).

> ```
> [[dialog:report:/Server Group Analysis/Server Detail|Server Detail|Examine server
>           details.]]
> ```

El siguiente ejemplo crea un diálogo modal (diálogo emergente) a un informe llamado Detalle del Servidor:

> ```
> [[dialog:report:/Server Group Analysis/Server Detail|Server Detail|Examine server
>           details.]]
> ```

El siguiente ejemplo crea un informe filtrado basado en el objeto Fuente de costes, que filtra al grupo de costes Software:

> ```
> [[/Software
>           Report/@Cost Source/!FILTER[Cost Source Master Data.Cost Pool="Software"]|Software
>           Report|Examine the Software Cost Pool.]]
> ```

El siguiente ejemplo crea un informe filtrado basado en la transformación de Datos Maestros de la Fuente de Coste ( v.11 solamente):

> ```
> [[/Software
>           Report/@.TableTransform:Cost Source Master Data/!FILTER[Cost Source Master Data.Cost
>           Pool="Software"]|Software Report|Examine the Software Cost
>       Pool.]]
> ```

El siguiente ejemplo crea un enlace a un informe de métricas denominado Coste. Si el valor de Coste para este objeto es 1.500 $, el texto del enlace será **1.500 $** :

> `[[%Cost]]`

El siguiente ejemplo enlaza con el mismo informe de costes que el ejemplo anterior, pero el texto del enlace es Informe de costes abierto:

> ```
> [[%Cost|Open cost
>           report]]
> ```

El siguiente ejemplo enlaza con el informe Presupuesto 2013 en la pestaña Presupuestos del proyecto Budget1 :

> `[[//Budget1/tab:Budgeting/2013 Budget]]`

Suponiendo la siguiente jerarquía de informes: Inicio > Unidades de Negocio > Informe de Servicios

- [[/|Ir a Inicio]] - Produce un enlace Ir a Inicio que enlaza con el informe por defecto.
- [[..|Volver a BU]] introducido en el Informe de Servicios - Produce un enlace Volver a BU que enlaza con el informe padre. En este caso, Inicio > Unidades de Negocio.

Supongamos que tiene un informe principal llamado Prueba. Tiene dos informes hijo: Hijo 1 e Hijo 2. Para crear un botón que vaya del Hijo 1 al Hijo 2, introduzca lo siguiente en el campo **Navegar** :

> ```
> ../Child
>         2
> ```

El siguiente ejemplo crea un enlace a la tabla Fuente de costes ( v.12.1, v.12.2+ ):

> ```
> dataTable:Cost
>           Source
> ```

El siguiente ejemplo crea un enlace a un informe de resumen del modelo denominado Resumen ( v.12.1, v.12.2+ ):

> `costModel:Summary`

## Resolución de problemas

A veces la ruta a un informe no es obvia por el nombre o por dónde aparece en el Explorador de proyectos. Además, cambiar el nombre de los informes puede complicar las cosas porque el sistema utiliza el nombre original del informe para la ruta. En estos casos, consulte la dirección URL del informe. Esta sección presenta un escenario de ejemplo para mostrar cómo hacerlo.

Supongamos que desea crear un botón o un enlace HTML que dirija al informe de revisión financiera.

El siguiente gráfico muestra el informe de revisión financiera en TBM Studio.

1. Haga clic con el botón derecho del ratón en un elemento del informe, como una tabla, para generar un menú contextual que incluya la selección Mostrar API URL.

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_code_links_to_other_reports_700x534.png)
2. Seleccione **Mostrar API URL**. Aparece un cuadro de diálogo que muestra la ruta del informe:

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_report_show_api_url_600x155.png)

## Formato de la cadena de ruta

A continuación figura la información pertinente de la ruta anterior:

> /.View:tab:Service Costing/.View:Financial Consulte

En el contexto del campo de navegación de un botón o de un enlace HTML, se utilizaría esto:

> [[/tab:Cálculo de costes del servicio/revisión financiera]]

Nota: Indica una situación importante que, si no se evita, puede perjudicar gravemente las operaciones.

Si intenta utilizar [[/IT Finanzas - Resumen]], falla porque no es la ruta completa, incluida la especificación de la pestaña.
