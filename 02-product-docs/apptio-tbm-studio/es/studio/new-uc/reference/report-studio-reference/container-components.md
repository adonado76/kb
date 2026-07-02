---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Componentes del contenedor"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Opciones de diseño"
source_path: "studio/new-uc/reference/report-studio-reference/container-components.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componentes del contenedor

Los componentes de contenedor agruparán los elementos relacionados y aportarán una estructura organizativa a los informes.

**Cuadros de grupo**

Los cuadros de grupo agrupan de forma visual y lógica los componentes del informe. Los componentes de un cuadro de grupo se desplazan como una unidad cuando se cambia la posición del grupo.

**Comportamientos clave:**

- Los filtros dentro de un cuadro de grupo solo se aplican a las tablas y gráficos que se encuentran dentro de ese cuadro de grupo (y a cualquier grupo anidado).
- Los filtros situados fuera de los cuadros de grupo se aplican a todas las tablas y gráficos del informe.

**Para añadir un cuadro de grupo:**

1. En la pestaña «Informe», haz clic en el icono «Agrupar».
2. Mueve y cambia el tamaño del cuadro según sea necesario arrastrando el encabezado (para moverlo) o los bordes (para cambiar su tamaño).

**Opciones de diseño de grupo (disponibles en la pestaña «Grupo»):**

|  |  |
| --- | --- |
| **Diseño** | **Comportamiento** |
| **Manuales** | Coloca los componentes donde quieras; se mantendrán en su sitio |
| **Vertical** | Alinea automáticamente los componentes en una columna vertical |
| **Horizontal** | Alinea automáticamente los componentes en filas horizontales |
| **Espaciado** | Abre un cuadro de diálogo para configurar el espaciado vertical y horizontal entre los componentes |

Consejo: Utiliza diseños verticales u horizontales cuando los componentes puedan ocultarse de forma condicional en función de los roles de los usuarios. Los componentes restantes ocuparán automáticamente el espacio que dejen los componentes ocultos.

**Componentes con pestañas**

Los componentes con pestañas organizan varios elementos en pestañas seleccionables, lo que permite ahorrar espacio en el informe y, al mismo tiempo, acceder a contenido relacionado.

Para añadir un componente con pestañas: en la pestaña Informe, haz clic en el icono Pestañas.

**Cómo trabajar con pestañas:**

|  |  |
| --- | --- |
| **Acción** | **Cómo** |
| **Añadir una pestaña** | Haz clic en la pestaña con el signo +; escribe un nombre y pulsa Intro |
| **Añadir un componente a una pestaña** | Crea el componente en el área de trabajo del informe y arrástralo al grupo con pestañas |
| **Eliminar el componente de la pestaña** | Arrastra el componente fuera de la pantalla o haz clic en el icono de eliminar situado en la esquina superior derecha |
| **Cambiar el orden de tabulación** | Selecciona una pestaña y haz clic en los iconos de doble flecha hacia la izquierda o hacia la derecha (<< / >>) |
| **Eliminar una pestaña** | Selecciona la pestaña y haz clic en el icono de eliminar |
| **Cambiar el tamaño del grupo de pestañas** | Haz clic y arrastra los bordes |
| **Establecer el color de fondo de la pestaña** | Haz clic con el botón derecho del ratón en la pestaña → Propiedades → Color de fondo de la pestaña |

**Control de la visibilidad de las pestañas con texto dinámico:**

Puedes utilizar expresiones de texto dinámicas para controlar la visibilidad de las pestañas en función de los datos o de los roles de los usuarios:

|  |  |
| --- | --- |
| **Valor** | **Comportamiento** |
| **habilitado** | La pestaña está visible y se puede seleccionar |
| **oculto** | La pestaña no se ve |
| **inhabilitado** | La pestaña está visible, pero no se puede seleccionar |

Nota: Todos los componentes, excepto los cuadros de grupo, se pueden colocar en una pestaña.

**Tema principal:** [Opciones de diseño](../../../../studio/new-uc/reference/report-studio-reference/layout-options.html)
