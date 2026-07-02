---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Preferencias de dimensionamiento correcto"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto avanzado"
source_path: "product/premium-rightsizing-preferences.html"
images:
  - "images/advanced-rightsizing-preferences-hide.png"
  - "images/basic_rightsizing_preferences_S3.png"
  - "images/basic_rightsizing_preferences_VM.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Preferencias de dimensionamiento correcto

## Acerca de las preferencias

Esta página le permite configurar las preferencias globales para las recomendaciones de ajuste de tamaño de Cloudability en la pestaña «Básico». Como parte de Cloudability Premium, las acciones de optimización generadas por el motor Turbonomic se transfieren a Cloudability y se muestran en la pestaña «Avanzado» de la página «Optimizar > Redimensionamiento». Un administrador de Cloudability ahora puede controlar si desea que sus usuarios vean las recomendaciones de ajuste de tamaño generadas por Cloudability o si prefiere ocultarlas.

## Preferencias avanzadas

Para configurar la visibilidad de las recomendaciones de ajuste de tamaño de Cloudability, vaya a Configuración > Preferencias de ajuste de tamaño > pestaña Avanzado

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-preferences-hide.png)

La configuración predeterminada es «Mostrar todo», lo que significa que la página Optimizar > Redimensionamiento mostrará tanto las recomendaciones de redimensionamiento generadas por Cloudability en la pestaña «Básico» como las acciones de optimización generadas por el motor de Turbonomic en la pestaña «Avanzado». Sin embargo, un administrador de Cloudability puede optar por ocultar las recomendaciones de ajuste de tamaño generadas por Cloudability, lo que desactivará la pestaña «Básico» para todos los usuarios en la página Optimizar > Ajuste de tamaño. Cloudability El administrador puede cambiar esta configuración en cualquier momento. Aunque las recomendaciones de redimensionamiento seguirán generándose por Cloudability, esta bandera solo afecta a la visibilidad de las recomendaciones de redimensionamiento en la interfaz de usuario Cloudability para todos los usuarios.

## Ajustes de configuración avanzados

Esta sección te permite configurar políticas que influyen en las acciones de optimización generadas por el motor de Turbonomic y automatizan dichas acciones, así como las configuraciones relacionadas, entre las que se incluyen grupos, programaciones, flujos de trabajo y políticas. Se presentan en forma de mosaicos. Al hacer clic en cualquiera de estos mosaicos, se abre la página de configuración correspondiente en una nueva pestaña del navegador.

- Grupos : Los grupos reúnen conjuntos de recursos para que Turbonomic pueda supervisarlos y gestionarlos. Al definir el alcance de tu sesión al conectarte al motor de Turbonomic, puedes seleccionar grupos para centrarte en esos recursos específicos. Por ejemplo, si tienes máquinas virtuales dedicadas a un solo cliente, puedes crear un grupo que incluya esas máquinas virtuales. A continuación, puede establecer ese grupo como ámbito de aplicación al crear una política o ejecutar un plan. Turbonomic El motor admite grupos dinámicos y estáticos.
- Horarios : Los horarios especifican un periodo de tiempo durante el cual pueden tener lugar determinados eventos. Un calendario es una configuración que establece un intervalo de tiempo durante el cual se aplica una política de automatización. Esta política puede ejecutar acciones que no impliquen el estacionamiento en entidades de la nube pública o locales, o modificar ajustes que afecten al análisis y a la generación de acciones.
- Flujos de trabajo : El flujo de trabajo de automatización determina si un motor de « Turbonomic » ejecutará una acción o si un motor de « Turbonomic » automatizará flujos de trabajo externos para aplicar el cambio en su entorno. De este modo, puedes integrar los orquestadores compatibles para ejecutar acciones en ámbitos específicos de entidades de tu entorno. Puedes crear un flujo de trabajo de automatización que active un webhook cada vez que un motor de Turbonomic recomiende trasladar un VM, o bien puedes crear un flujo de trabajo de automatización que se ejecute en sustitución de la acción que ejecutaría un motor de Turbonomic.
- Políticas : Las políticas establecen las reglas de negocio para el análisis de la asignación de recursos, la visualización del estado de los recursos y la ejecución de acciones. Una política de automatización es un conjunto de reglas que Turbonomic debe cumplir al ejecutar acciones que no sean de estacionamiento en entidades de la nube pública o locales, o al modificar ajustes que afecten al análisis y a la generación de acciones.

Nota: Solo podrás gestionar políticas si se te han asignado los roles pertinentes de « Turbonomic » en Frontdoor

## Preferencias básicas

Para configurar las preferencias globales de las recomendaciones de redimensionamiento de Cloudability, vaya a Configuración > Preferencias de redimensionamiento > pestaña Básico

Preferencias de «Compute» ( VM )

Esta pestaña de preferencias le permite configurar las preferencias globales para las recomendaciones de ajuste de tamaño de Cloudability.

![Captura de pantalla de las preferencias de «Compute VM »](../../../../03-media/cloudability-premium/images/basic_rightsizing_preferences_VM.png)

| Nombre de campo | Descripción |
| --- | --- |
| Generaciones e instancias | Opciones para excluir tipos de instancias no actuales o recomendar solo dentro de la familia de instancias existente (por ejemplo, para garantizar la cobertura continua con los compromisos/reservas existentes) al generar recomendaciones de ajuste de tamaño. |
| Arquitectura del procesador | Elija excluir tipos específicos de procesadores de las recomendaciones de redimensionamiento y permita recomendaciones entre arquitecturas. Asegúrese de la compatibilidad de la carga de trabajo antes de cambiar el tipo de procesador. |
| Reducción de la capacidad | Opciones para incluir recomendaciones que darían lugar a una reducción de la capacidad de recursos (por ejemplo, reducir la memoria total disponible) si no se proporcionan métricas de utilización para la dimensión. |
| Umbral de ahorro de costes | La configuración opcional para determinar las recomendaciones de ahorro mínimo debe predecirse para poder incluirse en las que se muestran.  Importe mínimo de ahorro de 30 días : un valor de cero indica que se ignorará la configuración. |
| Vida útil de los recursos | Configuración opcional para eliminar las recomendaciones de los recursos que han estado inactivos durante un período de tiempo determinado. Un valor de cero indica que la configuración se ignorará. |

Introduzca los datos en los campos correspondientes y seleccione el botón Guardar. Aparece el mensaje «*Preferencias guardadas correctamente* ».

Múltiples formas de filtrar las recomendaciones de redimensionamiento

En Cloudability, hay muchas formas de filtrar las recomendaciones de redimensionamiento. En primer lugar, puede filtrar las recomendaciones utilizando las preferencias globales disponibles en la página Configuración > Preferencias de redimensionamiento. Otra forma de filtrar utilizando las opciones disponibles en las propias páginas de ajuste de tamaño, en Optimizar > Ajuste de tamaño. Hay opciones de filtrado adicionales disponibles en el panel «Detalles» para las propias recomendaciones.

Object Storage ( S3 ) Preferencias

Esta pestaña de preferencias le permite excluir clases específicas de las recomendaciones de redimensionamiento de Object Storage.

Para excluir una clase de almacenamiento:

1. Seleccione el botón «Añadir valor».
2. Añadir un valor (clase de almacenamiento) al campo de entrada
3. Continúe añadiendo tantos valores como sea necesario para excluir

S3 clases de almacenamiento:

- Standard
- Estratificación inteligente
- Acceso poco frecuente estándar
- Una vez Zona de acceso poco frecuente
- Recuperación instantánea de glaciares
- Recuperación flexible de glaciares
- Archivo profundo del glaciar

![Captura de pantalla de las preferencias de almacenamiento de objetos](../../../../03-media/cloudability-premium/images/basic_rightsizing_preferences_S3.png)

## Preguntas más frecuentes

1. ¿Tengo que volver a configurar las políticas en la interfaz de usuario de Cloudability, en la pestaña «Avanzado»?

   Independientemente de las configuraciones de políticas que haya establecido en la configuración del motor de Turbonomic con su implementación de Cloudability Premium, ahora también podrá gestionar esas mismas configuraciones a través de la interfaz de usuario de Cloudability. No perderás ninguna de tus configuraciones actuales al pasar de un motor de Cloudability Premium a uno de Turbonomic.
2. ¿Puedo ver y gestionar las mismas políticas también en la interfaz de usuario de Turbonomic, además de lo que se muestra en la pestaña «Avanzado»?

   Sí, las mismas configuraciones de políticas también se pueden gestionar a través de la interfaz de usuario de Turbonomic (a la que se accede mediante el mosaico « Cloudability Premium » en Frontdoor). Solo ofrecemos la posibilidad de ver y gestionar las configuraciones de la política « Turbonomic » a través de la interfaz de usuario de Cloudability, en la página «Rightsizing Preference > Advanced», como opción.
3. ¿Las preferencias configuradas en las pestañas «Básico» y «Avanzado» son diferentes?

   Sí, estas preferencias de ajuste de tamaño son muy diferentes. Mientras que la configuración de la pestaña «Básico» la utiliza el motor de recomendaciones de Cloudability, la de la pestaña «Avanzado» la utiliza el motor de Turbonomic. No son ni intercambiables ni interoperables.

**Tema principal:** [Redimensionamiento avanzado](../product/advanced-rightsizing-powered-by-turbonomic.html)
