---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Gestionar la configuración de la puntuación"
breadcrumb: []
source_path: "it-planning/planning/pfp/score-manage.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gestionar la configuración de la puntuación

◆ Se aplica a: Apptio Planning aplicaciones con [Project Financial Planning](gs-project-financial.html "◆ Se aplica a: Planificación con proyecto Planificación financiera."). Las tareas que se describen a continuación requieren una licencia de Project Financial Planning. Para activar las funciones de Project Financial Planning , consulte [Editar el perfil de la empresa](../edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.").

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles Admin o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

|  |  |
| --- | --- |
| icono de cámara | Vea este vídeo de Apptio Education Services: [Configuración de datos de referencia: Project Financial Planning Dimensiones](https://community.apptio.com/videos/1995 "(se abre en una pestaña o una ventana nueva)").  O vea todos los [vídeos y recursos de formación de Apptio Planning](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(se abre en una pestaña o una ventana nueva)") . |

## Gestionar puntuación

La tabla de datos de Puntuación define el valor de Puntuación aplicado a los proyectos cuando se ha activado la opción **Habilitar puntuación automática de proyectos**. Véase [Editar el perfil de la empresa](../edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning."). El valor de Puntuación se calcula utilizando las dimensiones de datos de Puntuación que usted especifique. Cada fila de la tabla de datos Puntuación constituye una cláusula de la fórmula. La fórmula utiliza los siguientes valores que se establecen por atributo:

- Factor de normalización - Número utilizado para ajustar los valores de los atributos grandes a un rango utilizable.
- Ponderación - Contribución relativa del atributo. Una ponderación inferior a 1 reduce la contribución del atributo. 1 no tiene ningún efecto sobre la ponderación, y mayor que 1 amplifica la contribución relativa.

Por ejemplo, los siguientes datos de Puntuación:

| Atributo | Factor de normalización | Ponderación |
| --- | --- | --- |
| Riesgo | 2 | 2 |
| Prioridad | 1 | 3 |

Resultados en esta fórmula de puntuación:

> ```
> Score = 4/5 + 3/5
>           = 7/5 = 1.4
> ```

Para gestionar la puntuación:

1. En el panel de navegación izquierdo, seleccione Configuración > Puntuación
2. Actualice los valores de las dimensiones según sea necesario. Puede especificar cada cláusula de su fórmula de Puntuación por fila:
   - Atributo - Seleccione la dimensión del Proyecto para la que desea definir la cláusula de Puntuación. Los tipos de dimensión soportados son: Booleana (un valor verdadero equivale a 1 y un valor falso a 0), Número, Entero, Enum (el ordinal equivale al valor donde el primer elemento equivale a 1, el segundo a 2 y así sucesivamente).

     Nota: Las dimensiones Memo, Cadena y Fecha no están permitidas para dimensiones de atributos en Puntuación.
   - Tipo - Es el tipo de datos del atributo seleccionado.
   - Factor de normalización - Introduzca un valor numérico.
   - Ponderación - Introduzca un valor numérico.
3. Haga clic en Publicar para que los datos estén disponibles en la planificación y la gestión de gastos.

Consejo: Cuando visualice la Puntuación en tablas de datos del proyecto, (en la vista Resumen, por ejemplo) puede hacer lo siguiente:

- Sustituir una Puntuación calculada por un valor numérico introducido manualmente.
- Sustituye un valor introducido manualmente por la puntuación calculada. Para ello, haga clic en el icono Revertir puntuación del proyecto situado junto al valor de la puntuación.
