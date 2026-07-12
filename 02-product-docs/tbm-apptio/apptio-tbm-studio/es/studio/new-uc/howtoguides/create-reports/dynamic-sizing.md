---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar el tamaño y la posición dinámicos"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Informes avanzados"
source_path: "studio/new-uc/howtoguides/create-reports/dynamic-sizing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar el tamaño y la posición dinámicos

**Objetivo:** Crear diseños de informes adaptables que se ajusten a diferentes tamaños de pantalla y permitan controlar la visibilidad de los componentes en función del rol sin dejar espacios vacíos.

**Cuándo utilizarlo:** cuando los informes se visualizan en pantallas de distintos tamaños, cuando la visibilidad de los componentes depende del rol del usuario o cuando se necesita un control preciso sobre la disposición de los componentes.

**Tiempo estimado:** 15-20 minutos

## Comprender las opciones de diseño

TBM Studio ofrece herramientas de diseño flexibles en la pestaña «Formato» para organizar los componentes de los informes. Puedes colocar los componentes manualmente o utilizar cuadros de grupo con opciones de diseño automático que se ajustan cuando se ocultan o se muestran los componentes.

## Método 1: Colocación manual de componentes

**Mover componentes:**

1. Haz clic y mantén pulsado el encabezado del componente (la barra de título situada en la parte superior del componente).
2. Arrastra el componente hasta la ubicación deseada.
3. Suelta para colocar el componente en su sitio.

**Cambiar el tamaño de los componentes:**

1. Pasa el cursor por el borde o la esquina de un componente hasta que aparezca el cursor de cambio de tamaño.
2. Haz clic y arrastra para cambiar el tamaño del componente.

**Posicionamiento preciso:**

1. Haz clic con el botón derecho del ratón en el componente y selecciona «Posición y tamaño».
2. Introduce los valores exactos en píxeles para la posición X, la posición Y, el ancho y la altura.
3. Haz clic en «Aplicar» para obtener una vista previa y, a continuación, en «Aceptar» para guardar.

Consejo: Utiliza valores negativos para la posición X (hasta -24 píxeles) para ocultar el encabezado de un componente y alinearlo con el borde de un cuadro de grupo.

## Método 2: Herramientas de alineación y distribución

Utiliza las herramientas de la pestaña «Formato» para alinear y distribuir varios elementos:

1. Selecciona varios elementos (Ctrl + clic en Windows, Alt + clic en Mac).
2. En la pestaña «Formato», utiliza el grupo «Alinear»:
   - **Izquierda/Centro/Derecha:** Alinear los componentes horizontalmente
   - **Arriba/En medio/Abajo:** Alinear los componentes verticalmente
3. Utiliza el grupo «Distribuir»:
   - **Horizontal:** Distribuir los elementos de manera uniforme de izquierda a derecha
   - **Vertical:** Distribuye los elementos de forma uniforme de arriba abajo
4. Utiliza «Ajustar tamaño» para que los componentes tengan la misma anchura, altura o ambas (utiliza el primer componente seleccionado como referencia).

## Método 3: Cuadros de grupo con diseño automático

Los cuadros de grupo ofrecen un diseño automático que se ajusta cuando se ocultan los componentes:

1. En la pestaña Informe, haz clic en Agrupar. Se añade un cuadro de grupo al informe.
2. Arrastra los componentes al cuadro de grupo.
3. Selecciona el cuadro de grupo y haz clic en la pestaña «Grupo» para acceder a las opciones de diseño:
   - **Manual:** Los componentes permanecen donde los coloques
   - **Vertical:** los componentes se disponen en una sola columna y los espacios vacíos se rellenan automáticamente cuando se ocultan algunos componentes
   - **Horizontal:** los componentes se disponen en filas y los espacios vacíos se rellenan automáticamente cuando se ocultan algunos componentes
4. Haz clic en «Espaciado» para configurar la distancia entre los componentes en píxeles.

## Método 4: Ajuste automático del tamaño de los cuadros de grupo

Configura los cuadros de grupo para que cambien de tamaño dinámicamente en función de su contenido:

1. Selecciona el cuadro de grupo.
2. En la pestaña «Grupo», utiliza las opciones de «Ajuste automático»:
   - **Solucionado:** El cuadro de grupo mantiene su tamaño independientemente del contenido (puede mostrar barras de desplazamiento)
   - **Ancho automático:** el ancho del cuadro de grupo se ajusta para adaptarse al contenido
   - **Altura automática:** la altura del cuadro de grupo se ajusta para adaptarse al contenido
   - **Automático: ambas** dimensiones se ajustan dinámicamente

## Método 5: Configuración de la visibilidad de los componentes

Configura los componentes para que se muestren u oculten en función de determinadas condiciones:

1. Selecciona el componente.
2. En la pestaña Informe, en el grupo Avanzadas, haz clic en Visibilidad.
3. Configurar las condiciones de visibilidad:
   - **El componente contiene datos:** ocultar cuando el componente no tenga datos que mostrar
   - **El rol actual del usuario es:** Mostrar solo para roles de usuario específicos
   - **El texto dinámico no se interpreta como «oculto»:** utiliza una fórmula para controlar la visibilidad

**Ejemplo:** Para mostrar un componente de explicación de la varianza solo cuando la varianza sea negativa, utiliza texto dinámico:

`<%=IF(Variance<0,"visible","hidden")%>`

## Método 6: Grupos de componentes con pestañas

Utiliza grupos con pestañas para organizar muchos componentes en un espacio reducido:

1. En la pestaña Informe, haz clic en Grupo con pestañas.
2. Arrastra los componentes al grupo con pestañas. Cada componente aparece en su propia pestaña.
3. Utiliza los botones de flecha situados debajo de la zona de pestañas para cambiar el orden de las pestañas.
4. Para eliminar un componente, arrástralo fuera del grupo con pestañas.

## Método 7: Opciones de diseño dinámico

Para diseños adaptativos avanzados, utiliza las opciones del menú «Dinámico»:

- **Alinear horizontalmente:** centra el componente en su contenedor a medida que este cambia de tamaño
- **Mantener distancia respecto a la parte superior/inferior:** mantiene la posición del componente con respecto a los bordes del contenedor
- **Ajustarse al contenedor:** el componente cambia de tamaño proporcionalmente a medida que cambia el tamaño del contenedor
- **Anclaje a la derecha/parte inferior:** el componente mantiene su posición con respecto al borde derecho o inferior

## Consideraciones sobre el tamaño de la pantalla

Al crear un informe, se selecciona el tamaño de pantalla de destino:

- **Estándar:** 1024 píxeles de ancho
- **Pantalla panorámica:** 1440 píxeles de ancho

Elige en función de las resoluciones de pantalla habituales de tus usuarios. Utiliza las opciones de diseño dinámico para garantizar que los informes se visualicen correctamente en pantallas que difieran del diseño previsto.

## Ajustar a la cuadrícula

En la pestaña «Formato», marca la casilla «Ajustar a la cuadrícula» para que los componentes se alineen con una cuadrícula invisible al colocarlos. Esto permite crear diseños ordenados y alineados rápidamente.

## Orden Z (delante/detrás)

Cuando los componentes se superponen, controla cuál aparece delante:

1. Selecciona el componente.
2. En la pestaña «Formato», en el grupo «Posición y tamaño», haz clic en «Traer al frente» o «Enviar al fondo».

## Resultados previstos

- Los componentes se alinean con precisión mediante herramientas de alineación
- Los cuadros de grupo con disposición vertical u horizontal se reorganizan automáticamente cuando se ocultan los componentes
- Las condiciones de visibilidad muestran u ocultan componentes en función del rol del usuario o de determinadas condiciones de los datos
- Los grupos con pestañas permiten navegar de forma compacta entre varios componentes

## Tareas relacionadas

- Crear plantillas de informes (Sección « 3.3.1 »)
- Configurar diseños de impresión (esta sección)
- Configurar los permisos de los componentes por rol (Sección 3.4 )

**Tema principal:** [Informes avanzados](../../../../studio/new-uc/howtoguides/create-reports/adv-rep.html)
