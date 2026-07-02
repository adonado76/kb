---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Contenido del informe principal"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Informes principales"
source_path: "studio/new-uc/reference/report-studio-reference/master-report-content.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Contenido del informe principal

**Componentes aptos para informes maestros**

Los informes maestros pueden incluir todos los componentes disponibles en los informes normales. Sin embargo, hay ciertos componentes que resultan más adecuados para los máster:

|  |  |  |
| --- | --- | --- |
| **Componente** | **Uso recomendado** | **Consideraciones** |
| **Cuadros de grupo** | Estructura de diseño, contenedores visuales | Se pierde la función de agrupación en los informes secundarios |
| **Botones** | Navegación entre informes | El texto de la wiki utiliza el contexto del informe secundario |
| **Componentes con pestañas** | Diseños de varias secciones | Añadir todo el contenido de las pestañas en la pestaña principal; el contenido de la pestaña secundaria se superpone a todas las demás pestañas |
| **Notas** | Instrucciones, avisos legales, texto fijo | Solo estático; no se puede editar en el elemento secundario |
| **Encabezados/Pies de página** | Logotipos, títulos, números de página | Los encabezados admiten texto dinámico; los pies de página no |

**Elementos comunes del informe maestro**

**Encabezados y pies de página**

Se pueden añadir encabezados a los informes maestros para que aparezcan en todas las páginas o solo en la primera. Puedes dar formato al texto del encabezado utilizando etiquetas de formato HTML e incluir texto dinámico. Por ejemplo, utiliza `<%=CurrentDate()%>` para mostrar el período actual. Los pies de página se pueden personalizar por completo, aunque, a diferencia de los encabezados, no admiten texto dinámico.

**Elementos de navegación**

Los botones y enlaces de los informes principales permiten navegar entre los distintos informes. Cuando añades un botón a un informe maestro que utiliza texto Wiki y no has especificado un « URL » de datos para dicho botón, la aplicación utilizará el informe actual (el informe secundario) como contexto cuando los usuarios interactúen con él.

**Identidad corporativa (logotipos y colores)**

Los administradores pueden definir paletas de colores personalizadas a nivel de entorno para que los informes se ajusten a las directrices de imagen corporativa de la organización. Estas paletas de colores se pueden aplicar a colecciones de informes y a informes individuales. Las paletas de colores se definen en «**Configuración > Paleta de colores personalizada** » y están disponibles para los roles de administrador de « Apptio », administrador y administrador asociado. Cada paleta de colores contiene 12 colores, y hay disponibles hasta 10 paletas personalizadas.

**Cuadros de grupo como contenedores de diseño**

Los cuadros de grupo resultan especialmente útiles en los informes maestros para crear secciones y delimitaciones visuales. Sin embargo, ten en cuenta que los cuadros de grupo añadidos a un informe maestro pierden su funcionalidad de agrupación de componentes cuando el informe maestro se aplica a un informe secundario. En los informes secundarios, los cuadros de grupo del informe principal solo sirven como bordes visuales alrededor de las áreas de contenido.

**Tema principal:** [Informes maestros](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
