---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tipos de componentes de navegación"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Navegación"
source_path: "studio/new-uc/reference/report-studio-reference/navigation-component-types.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tipos de componentes de navegación

**Componente de botón**

El componente «Botón» ofrece controles de navegación explícitos dentro de los informes. Utiliza los botones para acceder a informes concretos, cambiar el periodo de tiempo mostrado, ejecutar scripts o volver atrás. Los botones son la opción de navegación más visible y fácil de usar.

**Añadir un botón**

1. En la pestaña «Informe», haz clic en el icono del botón
2. El componente de botón se añade al informe dentro de un panel de componentes estándar
3. Coloca y ajusta el tamaño del botón según sea necesario
4. Configura el aspecto y las acciones a través del cuadro de diálogo «Propiedades»

**Propiedades de apariencia de los botones**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Texto del botón | Texto que aparece en el botón. Admite etiquetas estáticas y texto dinámico mediante la sintaxis <%=...%>. Se puede incluir código HTML para hacer referencia a imágenes de la biblioteca de imágenes de Apptio. |
|  |  |
| Información sobre el botón | Texto que aparece cuando los usuarios pasan el cursor por encima del botón. Utiliza las descripciones emergentes para proporcionar información adicional sobre la función del botón. |
| Habilitada | Estado del botón de control: déjalo en blanco para que esté activo, escribe «desactivado» para que aparezca atenuado o «oculto» para ocultarlo. Utiliza fórmulas para los estados condicionales, por ejemplo: <%=IF( Cost>5000,"habilitado","deshabilitado")%> |
| Color del botón | Establece el color de fondo del botón |
| Color del texto del botón | Establece el color del texto del botón |
| Tamaño del texto | Permite controlar el tamaño del botón y de su texto. También se puede cambiar el tamaño arrastrando el borde del panel. |
| Crecimiento de Button | Automático: tamaño predeterminado. Horizontal: alarga el botón para que se ajuste al panel circundante. |
| Color de fondo del panel | Establece el color del panel que rodea el botón |

**Propiedades de la acción del botón**

Configura las acciones de los botones en la pestaña «Acciones» del cuadro de diálogo «Propiedades»:

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Acción del servidor | ApptioScript código que se ejecuta al hacer clic en el botón. Se ejecuta antes de las acciones «Fecha de cambio» y «Navegar». Esta es una función avanzada. |
| Cambiar fecha | Cambia el intervalo de tiempo que se muestra. Seleccione una opción del menú desplegable o introduzca una fecha personalizada en el formato «mes:año» (por ejemplo, January:FY2012, P3:FY2012 ). |
| Navegar | Introduce un enlace utilizando la sintaxis de estilo wiki para ir a otro informe. Consulte la sección «Enlaces codificados» para obtener más detalles sobre la sintaxis. |
| Botón Atrás | Si está seleccionado, al hacer clic en el botón, el usuario volverá al informe anterior. Esto ofrece una alternativa a la navegación por ruta de navegación. Anula los ajustes de «Acción del servidor», «Cambiar fecha» y «Navegar». |
| Enviar formulario | Si el botón se coloca en un componente de formulario, al hacer clic en él se envía el formulario. |

**Nota sobre el rendimiento:** Ten cuidado al crear botones que dirijan a informes que requieran cálculos complejos. La navegación por informes complejos puede afectar al rendimiento del sistema.

**Enlaces a informes (desglose)**

Los enlaces a informes permiten a los usuarios pasar de un valor seleccionado en una tabla o de un elemento de un gráfico a un informe relacionado. Esta función de desglose es fundamental para crear informes interactivos y explorables. Los enlaces de las tablas aparecen en azul.

**Importante:** Los enlaces de informe solo se aplican a las tablas basadas en objetos creadas mediante el cuadro de diálogo «Configuración de componentes ad hoc». No se pueden añadir enlaces a informes en tablas de transformación, tablas heredadas ni gráficos.

**Configuración de enlaces a informes**

1. Selecciona una columna de una tabla o selecciona todo un gráfico
2. Selecciona la pestaña «Ad Hoc» y haz clic en «Drill» en la sección «Navegación»
3. Configura las propiedades de navegación en el cuadro de diálogo

**Referencia de propiedades de navegación**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Activar navegación | Activa los enlaces de la columna o el gráfico seleccionados. En los gráficos, la navegación debe basarse en la columna de valores, no en la columna de etiquetas. |
| Abrir en ventana emergente | Muestra el informe de destino en un cuadro de diálogo emergente. Los usuarios pueden ver el informe y hacer clic en «Cerrar» para volver. Ideal para informes sencillos sin filtros complejos ni selectores de columnas. |
| Ir a | Selecciona el informe de destino de cualquier informe del proyecto. Haga clic en «Nuevo informe» para crear un nuevo informe de destino directamente desde este cuadro de diálogo. |
| Filtrar por la fila seleccionada | Filtra el informe de destino según el valor en el que haya hecho clic el usuario. Opciones: Filtrar en todas las columnas de las filas, filtrar solo en las columnas agrupadas, filtrar solo en la columna seleccionada actualmente. |
| Filtrar según las selecciones del segmentador aplicado | Pasa las selecciones actuales del segmentador al informe de destino, conservando el contexto del filtro. |
| Incluir los filtros del informe actual | Incluye los filtros definidos en la sección «Filtros» del cuadro de diálogo «Configuración de consulta ad hoc». |
| Añadir la columna seleccionada actualmente | Si la columna seleccionada no existe en el informe de destino, se añade automáticamente. |
| Incluir las columnas añadidas en el informe actual | Conserva y aplica cualquier columna añadida del informe actual al informe de destino. |

**Enlaces codificados (sintaxis tipo wiki)**

Para disfrutar de la máxima flexibilidad en la navegación por los informes, utiliza enlaces codificados al estilo wiki. Estos enlaces se pueden colocar en cuadros de texto HTML o en el campo «Navegar» de las propiedades del botón. Los enlaces codificados permiten navegar a cualquier informe, incluidas las vistas filtradas y los informes de otros proyectos.

**Sintaxis básica**

`[[report|display-text|tooltip-text]]`

Donde «report» es el destino, «display-text» es el texto visible del enlace (opcional) y «tooltip-text» es el texto que aparece al pasar el cursor por encima (opcional).

**Opciones de sintaxis de enlaces**

|  |  |
| --- | --- |
| **Sintaxis** | **Descripción** |
| /ReportName | Accede a un informe de primer nivel (la barra inclinada indica la raíz) |
| ChildReport | Ir a un informe secundario (en relación con el actual) |
| .. | Subir un nivel en la jerarquía del informe |
| ../SiblingReport | Accede a un informe de nivel superior (sube un nivel y, a continuación, ve al informe) |
| / | Accede al informe predeterminado (de inicio) del proyecto |
| //nombre-del-proyecto/informe | Acceder a un informe de otro proyecto |
| tab:TabName/ReportName | Acceder a un informe en una pestaña concreta |
| dialog:report:/ReportName | Abrir el informe en un cuadro de diálogo modal (ventana emergente) |
| %MetricName | Enlace a un informe de métricas; muestra el valor de la métrica como texto del enlace |
| dataTable:TableName | Acceder a una tabla de datos específica ( v12.1+ ) |
| costModel:ModelName | Accede al informe general del modelo ( v12.1+ ) |
| /@Object/!FILTRO[...] | Acceder a un informe de objetos filtrado |

**Ejemplos de enlaces codificados**

**Accede a un informe secundario con texto personalizado y una descripción emergente:**

`[[Applications|Click here|This report is preliminary.]]`

**Acceder a un informe de primer nivel en un cuadro de diálogo modal:**

`[[dialog:report:/Server Group Analysis/Server Detail|Server Detail|Examine details.]]`

**Acceder a un informe filtrado:**

`[[/Software Report/@Cost Source/!FILTER[Cost Source Master Data.Cost
Pool=Software]|Software Report]]`

**Acceder a un informe en una pestaña de otro proyecto:**

`[[//Budget1/tab:Budgeting/2013 Budget]]`

**URL Codificación de caracteres especiales**

Si los nombres de tu informe o los valores de los filtros contienen caracteres especiales, codifícalos utilizando la codificación estándar URL :

|  |  |  |
| --- | --- | --- |
| **Carácter** | **Valor codificado** | **Ejemplo de uso** |
| / (barra) | %2F | Informe de nombres que contienen barras |
| « (comillas) | %22 | Filtrar valores entre comillas |
| (espacio) | + o %20 | Nombres de informes compuestos por varias palabras |

**Recopilación de informes Navigator**

Las colecciones de informes agrupan los informes relacionados entre sí, y el componente «Navegador de colecciones de informes» ofrece a los usuarios una forma visual de cambiar de un informe a otro dentro de la misma colección. Cuando añades un informe a una colección, el componente de navegación se añade automáticamente al informe y aparece como una barra de pestañas o un menú en la parte superior del informe.

Los navegadores de colecciones de informes se gestionan a través de la pestaña «Proyecto» > cuadro de diálogo «Colecciones de informes». Los administradores pueden crear colecciones personalizadas, asignar informes a las colecciones, establecer el orden de visualización y configurar qué roles tienen acceso a cada colección.

**Cuadros de texto HTML con enlaces**

Los cuadros de texto HTML pueden contener enlaces de navegación que utilicen sintaxis de estilo wiki, lo que ofrece flexibilidad a la hora de crear interfaces de navegación personalizadas. Añade imágenes, texto con formato y varios enlaces dentro de un mismo componente.

**Añadir un cuadro de texto HTML**

1. En la pestaña «Informe», haz clic en el icono de HTML
2. Se abre el cuadro de diálogo «Editar contenido», donde puedes introducir código HTML y enlaces de estilo wiki
3. Haz clic en «Aplicar» para obtener una vista previa o en «Aceptar» para guardar y cerrar

Nota: Los cuadros de texto HTML no admiten el atributo « JavaScript ». Los enlaces HTML no pueden incluir controladores de eventos de tipo « JavaScript ».

**Tema principal:** [Componentes del informe: Navegación](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
