---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía práctica 1: Aplicar la seguridad a nivel de fila a las tablas"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Seguridad de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-arls.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía práctica 1: Aplicar la seguridad a nivel de fila a las tablas

## Objetivo

Configura la seguridad a nivel de fila en una tabla de transformación para que los usuarios solo vean las filas para las que tienen autorización.

## Cuándo se utiliza

Cuando sea necesario restringir la visibilidad de los datos en función de los límites organizativos (por ejemplo, unidad de negocio, centro de coste, región o departamento) o al implementar restricciones de datos multitenant.

## Tiempo estimado

Entre 30 y 45 minutos para la configuración inicial; entre 10 y 15 minutos por cada mesa adicional

## Requisitos previos

- Una tabla de transformación que ha sido modelada (tiene un paso de modelado)
- Tablas de asignación cargadas en el proyecto de seguridad a nivel de fila (véase la Guía práctica 2)
- Permisos adecuados para editar tablas y el proyecto de seguridad a nivel de fila

## Paso 1: Accede al proyecto de seguridad a nivel de fila

1. Abre el menú **de ajustes** (icono de engranaje en la barra de navegación superior).
2. Haga clic en «**Configurar seguridad a nivel de fila** ».
3. Se abre el proyecto «Row-Level Security». Este es un proyecto específico que almacena todas las tablas de correspondencias de tu dominio.

Consejo: El proyecto «Row-Level Security» se instala automáticamente al crear tu instancia de « Apptio ». Sirve para todos los proyectos de tu dominio, por lo que las tablas de correspondencias que crees aquí se pueden utilizar en varios proyectos.

## Paso 2: Comprueba que las tablas de correspondencias existen

Antes de configurar RLS en tus tablas de datos, asegúrate de que las tablas de asignación estén configuradas:

1. En el proyecto «Row-Level Security», ve al **Explorador de proyectos**.
2. Busca tus tablas de correspondencias. Deberías ver tablas que contienen los ID de usuario y los elementos a los que cada usuario tiene acceso.
3. Si no existen tablas de asignación, consulta **la Guía práctica 2: Controlar el acceso mediante la asignación de usuarios** para crearlas antes de continuar.

Una tabla de asignación típica para el acceso de las unidades de negocio podría tener este aspecto:

|  |  |
| --- | --- |
| **ID de usuario** | **Unidad de negocio** |
| bob@acme.com | BU 2 |
| rachel@acme.com | BU 1 |
| rachel@acme.com | BU 3 |
| tom@acme.com | BU 1 |

Nota: Rachel tiene acceso a dos unidades de negocio, por lo que aparece dos veces en la tabla de correspondencias.

## Paso 3: Abre la mesa para asegurarla

1. Ve al proyecto en el que estés trabajando (no al proyecto de seguridad a nivel de fila).
2. En el **Explorador de proyectos**, busca la tabla que deseas proteger.
3. Saca la mesa si aún no está fuera.
4. Haz doble clic para abrir la tabla en el editor de transformaciones.

## Paso 4: Insertar un paso de seguridad a nivel de fila

1. En el panel del flujo de transformación (a la izquierda), haz clic con el botón derecho del ratón en el lugar donde quieras añadir el paso RLS.
2. Selecciona **Insertar paso** > **Seguridad a nivel de fila**.
3. Aparece el panel de configuración de «Seguridad a nivel de fila».

Consejo: Al añadir un paso de seguridad a nivel de fila, se añadirá automáticamente un paso de modelo si aún no existe. Solo se puede aplicar la seguridad a nivel de fila a las tablas modeladas y a las tablas editables.

## Paso 5: Configurar el filtro de seguridad

El filtro RLS cuenta con cuatro campos que definen la regla de seguridad. Configura cada campo de la siguiente manera:

1. **Primer campo (columna para filtrar):** Selecciona la columna de la tabla de datos que contenga los valores que deseas filtrar. Por ejemplo, si estás filtrando por unidad de negocio, selecciona la columna «BU» o «Unidad de negocio».
2. **Segundo campo (intersecciones):** Seleccione la tabla de asignación del proyecto de seguridad a nivel de fila que define los permisos de acceso de los usuarios.
3. **Tercer campo (columna «Elemento»):** Seleccione la columna de la tabla de correspondencias que contenga los valores que los usuarios pueden ver (por ejemplo, la columna «Unidad de negocio» de la tabla de correspondencias).
4. **Cuarto campo (donde se encuentra el usuario):** Selecciona la columna de la tabla de correspondencias que contiene los ID de usuario (por ejemplo, «ID de usuario» o «Correo electrónico»).

Esta configuración crea una regla: *«Mostrar las filas en las que el valor de la [columna] de la tabla de datos coincida con la [columna de elemento] de la tabla de asignación correspondiente al ID del usuario actual en la [columna de ID de usuario]».*

## Paso 6: Añadir reglas adicionales (opcional)

Es posible que necesites varias reglas para gestionar diferentes situaciones de acceso. Por ejemplo, es posible que desees que determinados usuarios (como los directores financieros) puedan ver todos los datos, independientemente de la unidad de negocio.

1. Haz clic en **«Añadir entrada»** para crear una regla adicional.
2. Configura la nueva entrada siguiendo el mismo patrón de cuatro campos.
3. Las entradas múltiples utilizan la lógica «**O** »: si alguna de las entradas es cierta para un usuario, este verá la fila.

**Ejemplo:** Para que los usuarios con «acceso completo» puedan ver todas las filas, crea una segunda tabla de asignación (por ejemplo, «BU Acceso completo») en la que el indicador «Es administrador» esté marcado como «Sí» para esos usuarios. Añade una columna de fórmula a tu tabla de datos con el valor «Sí» y, a continuación, crea una entrada RLS que vincule esta columna con la columna «Es administrador» de la tabla de acceso completo en la que aparece el usuario.

## Paso 7: Comprueba la configuración de seguridad

Antes de guardar, comprueba que la configuración de RLS funciona correctamente:

1. En el paso RLS, busca el campo «**Filtro de vista previa** ».
2. Introduce la dirección de correo electrónico de un usuario (por ejemplo, « bob@acme.com ») para ver qué datos vería.
3. Revisa el panel de vista previa para comprobar que solo aparecen las filas esperadas.
4. Prueba con varios usuarios, incluidos aquellos con acceso restringido, los que tienen varios permisos de acceso y (si está configurado) los que tienen acceso total.

Consejo: La función de suplantación de identidad resulta útil para realizar pruebas en los informes. Puedes consultar el informe como un usuario concreto para comprobar que el RLS funciona correctamente.

## Paso 8: Guardar y registrar

1. Haz clic en **«Guardar»** para guardar los cambios en la tabla.
2. Comprueba la tabla para que la configuración de RLS esté disponible en el entorno de prueba y en el de producción.

## Resultados previstos

- Ahora la tabla tiene un paso RLS visible en el proceso de transformación.
- Los usuarios que consultan informes que incluyen esta tabla solo ven las filas que se ajustan a sus permisos de acceso.
- Las agregaciones de los informes (sumas, recuentos, medias) reflejan únicamente los datos filtrados por el usuario.
- El filtro de vista previa muestra el subconjunto de datos previsto para cada usuario de prueba.

## Errores habituales y solución de problemas

**El usuario no ve ningún dato:**

- Comprueba que el ID de usuario de la tabla de correspondencias coincida exactamente con la dirección de correo electrónico de inicio de sesión del usuario (se distingue entre mayúsculas y minúsculas).
- Comprueba que los valores de la columna «item» de la tabla de correspondencias coincidan exactamente con los valores de tu tabla de datos.

**El usuario ve todos los datos (sin filtrar):**

- Comprueba que la tabla tenga un paso «Modelo». RLS solo funciona con tablas modeladas.
- Comprueba que el paso RLS esté correctamente configurado y que los cuatro campos estén rellenados.

**RLS no aplicado a las tablas relacionadas:**

- Recuerda que RLS no se hereda. Cada tabla que requiera seguridad debe tener configurado su propio nivel de RLS.

**Tema principal:** [Seguridad de los datos](../../../../studio/new-uc/howtoguides/work-with-data/data-security.html)
