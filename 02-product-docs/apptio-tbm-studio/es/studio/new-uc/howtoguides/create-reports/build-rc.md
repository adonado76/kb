---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear colecciones de informes de compilación"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Personalización de informes"
source_path: "studio/new-uc/howtoguides/create-reports/build-rc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear colecciones de informes de compilación

**Objetivo:** Crear y gestionar colecciones de informes que agrupen informes relacionados para facilitar la navegación y el control de acceso.

**Cuándo utilizarlas:** Utiliza las colecciones de informes cuando quieras:

- Informes relacionados con el grupo (por ejemplo, todos los informes financieros mensuales)
- Ofrecer una navegación intuitiva entre informes sobre temas similares
- Controlar el acceso por roles a nivel de colección
- Organizar los informes por departamento, función o periodo de tiempo

**Requisitos previos:**

- Rol de administrador (solo los administradores pueden crear o eliminar colecciones)
- Informes ya creados que deseas agrupar
- Determinar qué roles de usuario deben tener acceso a cada colección

**Tiempo estimado:** entre 10 y 15 minutos para crear una colección; entre 2 y 5 minutos por informe para añadirlo

## Comprender las colecciones de informes

Agrupa los informes relacionados para que los usuarios puedan navegar fácilmente entre ellos. Cuando los usuarios acceden a un informe de una colección, ven un navegador de la colección de informes en la parte superior del informe: una barra horizontal que muestra todos los informes de esa colección y permite navegar fácilmente con un solo clic.

**Puntos clave:**

- Solo los administradores pueden crear y eliminar colecciones de informes
- Una vez creadas, las colecciones abarcan todo el proyecto
- Cualquier usuario con los permisos adecuados puede añadir o eliminar informes de las colecciones existentes
- Un informe solo puede pertenecer a una colección a la vez
- Los administradores pueden establecer permisos basados en roles a nivel de colección
- Puedes ocultar informes en una colección sin eliminarlos, lo cual resulta útil para los informes que aún no están listos

**Paso a paso: Crear una colección de informes**

1. En la pestaña **Proyecto**, en el grupo **Datos del proyecto**, haz clic en **Colecciones de informes**.
2. En el cuadro de diálogo «**Administrar colecciones de informes** », haz clic en «**Añadir colección** ».
3. Aparece una nueva entrada denominada «Nueva colección de informes» y queda seleccionada en el campo «**Colección seleccionada** ».
4. Para cambiar el nombre de la colección, haz clic en la entrada de la lista, luego haz clic en el nombre que aparece en el campo «Colección seleccionada» y escribe un nuevo nombre (por ejemplo, «Paquete financiero mensual» o «Cuadros de mando ejecutivos»).
5. Haz clic fuera del campo del nombre para guardar.

## Paso a paso: añadir un informe a una colección

1. En el **Explorador de proyectos**, busca y selecciona el informe que quieras añadir.
2. En la pestaña **Informe**, en el grupo **Agrupación**, haz clic en **Asignar a colección**.
3. En la lista desplegable, selecciona la colección a la que deseas añadir el informe.

El informe ya forma parte de la colección. Cuando los usuarios vean el informe, aparecerá el navegador de colecciones.

**Nota:** *Un informe solo puede pertenecer a una colección. Si lo asignas a una nueva colección, se eliminará de la anterior.*

## Paso a paso: cómo eliminar un informe de una colección

**Método 1: Desde el informe**

1. Ve al informe y échale un vistazo.
2. En la pestaña **Informe**, en el grupo **Agrupación**, haz clic en **Asignar a colección**.
3. En el menú, haz clic en la X roja situada junto al nombre de la colección.

**Método 2: Desde «Gestionar colecciones de informes»**

1. En la pestaña **«Proyecto»**, haz clic en «**Colecciones de informes** ».
2. Selecciona la colección de la lista «**Colecciones disponibles** ».
3. Busca el informe en la lista de la derecha.
4. Haz clic en la X roja situada a la derecha de la fila del informe.

## Paso a paso: ocultar o mostrar informes en una colección

Es posible que desee ocultar temporalmente un informe; por ejemplo, un informe predeterminado que aún no haya configurado o un informe en fase de desarrollo.

**Para ocultar un informe:**

1. En la pestaña **Proyecto**, en el grupo **Datos del proyecto**, haz clic en **Colecciones de informes**.
2. Seleccione la colección que contiene el informe.
3. Busca el informe en la lista de la derecha.
4. Desmarca la casilla **«Mostrar en el navegador»** situada junto al nombre del informe.
5. Haz clic en «**Cerrar** ».

**Para mostrar un informe oculto:** sigue los mismos pasos, pero marca la casilla «Mostrar en el navegador».

**Importante:** *Nunca elimines los informes predeterminados de una colección. En su lugar, ocúltalas hasta que estés listo para activarlas.*

## Ejemplo: Creación de un paquete de informes mensuales

Un caso de uso habitual es agrupar todos los informes que los equipos de finanzas revisan cada mes:

1. Crea una colección llamada «Paquete financiero mensual».
2. Añade estos informes a la colección: Resumen de costes por unidad de negocio, Análisis del gasto en proveedores, Variación entre presupuesto y datos reales, Desglose de costes de la torre de TI, Informe detallado de repercuticiones.
3. Ordena los informes de forma lógica (los usuarios los verán en el orden en que aparecen en la colección).
4. Si el informe detallado de devoluciones aún no está listo, ocúltalo desmarcando la casilla «**Mostrar en el navegador** ».

Ahora, cuando los usuarios del departamento financiero abren cualquiera de estos informes, ven el navegador de colecciones y pueden desplazarse fácilmente entre todos los informes mensuales.

## Errores habituales

- **Si se olvida de una colección, se limita la visibilidad:** si un informe pertenece a una colección, los usuarios que no puedan acceder a dicha colección no verán el informe, aunque tengan permiso para acceder al propio informe.
- **Eliminación de informes predeterminados:** nunca elimines los informes predeterminados; en su lugar, ocúltalos. La eliminación puede provocar problemas con la actualización.
- **Colecciones desorganizadas:** un número excesivo de informes en una misma colección dificulta la navegación. Considera la posibilidad de dividir las colecciones extensas por subtemas.

**Tema principal:** [Personalización de informes](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
