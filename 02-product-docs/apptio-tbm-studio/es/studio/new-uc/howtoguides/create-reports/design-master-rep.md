---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Diseñar informes maestros (plantillas)"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Personalización de informes"
source_path: "studio/new-uc/howtoguides/create-reports/design-master-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Diseñar informes maestros (plantillas)

**Objetivo:** Crear y aplicar plantillas de informes que garanticen un diseño y una imagen de marca uniformes en todos los informes.

**Cuándo utilizarlos:** Utilice los informes maestros cuando desee:

- Asegúrate de que los encabezados, los pies de página y la navegación sean uniformes en todos los informes
- Aplicar los elementos de marca habituales (colores, logotipos, cuadros de grupo) a varios informes
- Crea diseños reutilizables que puedan adoptar otros creadores de informes
- Mantenga la coherencia visual en todos los informes de su organización

**Requisitos previos:**

- Rol de usuario avanzado o administrador
- Una idea clara del diseño que quieres para tu informe
- Conocimiento de los cuadros de grupo y los componentes con pestañas

**Tiempo estimado:** entre 30 y 60 minutos para diseñar un informe maestro; 5 minutos para aplicarlo

## Comprender los informes principales

Los informes maestros funcionan como las diapositivas maestras en los programas de presentaciones: proporcionan una plantilla que se sitúa detrás del contenido del informe. Cuando se aplica un informe maestro a un informe personalizado, los componentes del informe maestro aparecen como un «fondo» de pantalla

**Características principales:**

- Los componentes del informe maestro no se pueden editar desde los informes que utilizan dicho informe maestro
- Los componentes que añadas a los informes personalizados se superponen a los elementos del informe maestro
- Los cambios realizados en el maestro se aplican automáticamente a todos los informes que lo utilizan
- Los informes maestros son siempre informes de nivel superior por defecto
- Puedes aplicar másteres a otros másteres (no recomendado)

## Paso a paso: Crear un informe maestro

1. Crea un nuevo informe o elige uno ya existente que quieras utilizar como plantilla.
2. Diseña la maquetación con los elementos que quieras que aparezcan en todos los informes que utilicen esta plantilla: cuadros de grupo para definir las áreas de contenido, botones de navegación para destinos habituales, encabezados con la imagen de marca de la empresa y ubicaciones estándar para los filtros.
3. En la pestaña **Informe**, en el grupo **Avanzadas**, haz clic en **Informe maestro** para designar este informe como informe maestro.
4. Guarda y revisa el informe.

Tu informe maestro aparece ahora en el menú desplegable **«Masters»** de la pestaña «**Informe** ».

## Paso a paso: aplicar un informe maestro

1. Selecciona el informe al que deseas aplicar la plantilla.
2. En la pestaña **«Informe»**, abre la lista desplegable «**Plantillas** ».
3. Haz clic en el informe maestro que quieras aplicar.

Los elementos de la plantilla aparecen ahora detrás del contenido de tu informe. Coloca los componentes de manera que se ajusten al diseño maestro.

**Paso a paso: Eliminar un informe maestro**

1. Echa un vistazo al informe.
2. En la pestaña **«Informe»**, abre la lista desplegable «**Plantillas** ».
3. Selecciona **«Ninguno»** al final de la lista.

## Buenas prácticas para los informes maestros

1. **Utilice las plantillas como ayuda para el diseño:** cree contenedores (cuadros de grupo) en los que los creadores de informes puedan colocar tablas y gráficos. No añadas componentes basados en datos a las plantillas.
2. **Ten cuidado con los componentes con pestañas:** si añades un componente con pestañas a una plantilla, incluye contenido de relleno en cada pestaña. Los usuarios no pueden añadir componentes a pestañas individuales desde el informe personalizado.
3. **Comprender las limitaciones de los cuadros de grupo:** los cuadros de grupo de un modelo pierden su funcionalidad de agrupación al aplicarlos. Úsalas únicamente como bordes visuales.
4. **Ten en cuenta la disposición del fondo:** coloca los elementos del modelo principal sabiendo que los componentes del informe personalizado se superpondrán sobre ellos. Deja el espacio adecuado para las áreas de contenido.

## Errores habituales

- **Incorporación de componentes de datos a los informes maestros:** las tablas y los gráficos de los informes maestros no se actualizan dinámicamente en los informes secundarios. Utiliza las plantillas solo para los elementos de diseño.
- **Componentes superpuestos con pestañas:** los componentes situados sobre las áreas con pestañas de una plantilla aparecen en TODAS las pestañas al visualizarlas.
- **Olvidar las actualizaciones del maestro afecta a todos los informes:** los cambios realizados en un maestro se reflejan inmediatamente en todos los informes que lo utilizan. Prueba los cambios con cuidado.

**Tema principal:** [Personalización de informes](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
