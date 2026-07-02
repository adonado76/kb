---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar permisos de informes"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Personalización de informes"
source_path: "studio/new-uc/howtoguides/create-reports/config-rep-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar permisos de informes

**Objetivo:** Controlar qué roles de usuario pueden ver informes y componentes de informes específicos, garantizando un acceso adecuado a los datos confidenciales.

**Cuándo utilizarlo:** Utilice los permisos de informe cuando desee:

- Limitar los informes a departamentos o funciones específicos
- Mostrar distintos componentes del informe según los distintos roles de usuario
- Crear vistas de datos confidenciales exclusivas para directivos
- Garantizar el cumplimiento de las políticas de acceso a los datos

**Requisitos previos:**

- Rol de administrador (para permisos a nivel de informe y permisos de recopilación)
- Rol de usuario avanzado (para visibilidad a nivel de componentes)
- Conocimiento de las funciones y los requisitos de acceso de su organización
- Conocimientos sobre la gestión de roles de usuario (véase la sección 3.4.2 )

**Tiempo estimado:** entre 5 y 10 minutos por informe; varía en función de la complejidad de las configuraciones de visibilidad de los componentes

## Comprender los permisos de los informes

TBM Studio ofrece varios niveles de control de acceso para los informes:

1. **Permisos a nivel de informe:** controla qué roles pueden acceder a un informe completo
2. **Permisos a nivel de colección:** controla qué roles pueden acceder a todos los informes de una colección
3. **Visibilidad a nivel de componente:** mostrar u ocultar componentes específicos en función del rol del usuario
4. **Seguridad a nivel de fila (RLS):** controla qué filas de datos ven los usuarios (se trata en la sección 3.4.2 )

Estas capas funcionan conjuntamente: el usuario debe tener permisos en cada una de las capas correspondientes para poder ver el contenido.

## Opciones de permisos a nivel de informe

Al crear o editar un informe, se configura quién puede verlo:

|  |  |
| --- | --- |
| **Opción** | **Descripción** |
| Todo el mundo | Todos los usuarios con acceso al proyecto pueden ver el informe |
| Roles seleccionados | Solo los usuarios con los roles especificados pueden ver el informe |
| Personal (solo visible para el autor) | Solo tú puedes ver el informe, lo cual resulta útil para borradores y análisis personales |

Nota: El permiso «Editar informes personales» (asignado por defecto al rol de Analista) permite a los usuarios crear informes que solo ellos pueden ver.

## Paso a paso: cómo configurar los permisos de un informe al crearlo

1. En la pestaña **Inicio**, haz clic en **Nuevo > Informe**.
2. Introduce el nombre y la descripción del informe.
3. En la sección **«Visible para»**, selecciona la opción de permisos: **«Todos»** (mantén la configuración predeterminada) o «**Roles seleccionados** » (marca los roles que deben tener acceso a este informe).
4. Rellena el resto de opciones y genera el informe.

**Paso a paso: cómo cambiar los permisos de un informe existente**

1. Busca el informe que quieras modificar.
2. En la pestaña **Informe** (o en la pestaña **Proyecto** ), en el grupo **Avanzadas**, haz clic en **Permisos**.
3. En el cuadro de diálogo de permisos, selecciona **«Todos»** para que el informe esté disponible para todos los usuarios, o selecciona **«Roles seleccionados»** y marca los roles específicos para restringir el acceso.
4. Haz clic en **Aceptar** para guardar.
5. Guarda el informe para que los cambios surtan efecto.

## Paso a paso: Configurar la visibilidad de los componentes según el rol

Puedes mostrar u ocultar componentes concretos del informe en función del rol del usuario, lo cual resulta útil para crear un único informe con diferentes vistas para distintos públicos:

1. Echa un vistazo al informe.
2. Selecciona el componente (tabla, gráfico, cuadro de grupo, etc.) que quieres controlar.
3. En la pestaña **Informe**, en el grupo **Avanzadas**, haz clic en **Visibilidad**.
4. En el cuadro de diálogo «**Visibilidad de los componentes del informe** », configura las opciones de visibilidad:
   - **El componente contiene datos:** ocultar si el componente no tiene datos
   - **El rol actual del usuario es:** Selecciona los roles específicos que deben poder ver este componente
   - **El texto dinámico se evalúa como «oculto»:** utiliza el texto dinámico para controlar la visibilidad mediante programación
5. Pulse **Aceptar**.
6. Repite el proceso con los demás componentes según sea necesario y comprueba los resultados en el informe.

## Estrategias de permisos de informes

**Estrategia 1: Permisos basados en colecciones**

- Crea colecciones por público (ejecutivos, finanzas, operaciones de TI)
- Establecer permisos a nivel de colección
- Añadir informes a las colecciones correspondientes

**Estrategia 2: Permisos basados en informes**

- Organizar los informes por función en colecciones
- Establecer permisos específicos para cada informe
- Resulta útil cuando la composición de la colección no se ajusta a las necesidades de acceso

**Estrategia 3: Visibilidad basada en componentes**

- Crea informes completos con toda la información relevante
- Utiliza los ajustes de visibilidad para mostrar los componentes adecuados para cada rol
- Reduce el número de informes que hay que mantener

## Errores habituales

- **Olvidar los permisos de la colección:** un usuario puede tener permiso para consultar informes, pero seguir viéndose bloqueado por las restricciones de la colección.
- **Reglas de visibilidad excesivamente complejas:** cuando hay demasiadas reglas de visibilidad basadas en roles, resulta difícil mantenerlas. Considera la posibilidad de elaborar informes distintos para públicos muy diferentes.
- **No realizar pruebas con usuarios reales:** comprueba siempre los permisos consultando los informes desde el punto de vista de usuarios con diferentes roles.
- **Sin tener en cuenta la seguridad a nivel de fila:** los permisos de los informes controlan el acceso a los mismos; la RLS controla el acceso a los datos dentro de los informes. Es posible que se necesiten ambas cosas.

**Tema principal:** [Personalización de informes](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
