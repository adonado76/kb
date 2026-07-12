---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Guía de configuración del impacto del coste total de propiedad (TCO) de la TI híbrida"
breadcrumb:
  - "Costing Standard"
  - "Otras soluciones"
  - "Impacto del TCO de la TI híbrida"
source_path: "cost-transparency/reports/hybrid-it-tco-config.html"
images:
  - "resources/images/ct_images/cg-200.jpg"
  - "resources/images/ct_images/cg-300.jpg"
  - "resources/images/ct_images/cg-sum.jpg"
  - "resources/images/ct_images/cg0200a.jpg"
  - "resources/images/ct_images/config-hyb-3.jpg"
  - "resources/images/ct_images/fw-2-hyb.jpg"
  - "resources/images/ct_images/hyb-3.jpg"
  - "resources/images/ct_images/hyb-comp.jpg"
  - "resources/images/ct_images/hyb-frame.jpg"
  - "resources/images/ct_images/hyb-s-1.jpg"
  - "resources/images/ct_images/hyb-s-2.jpg"
  - "resources/images/ct_images/hyb-s1.jpg"
  - "resources/images/ct_images/hyb-s3.jpg"
  - "resources/images/ct_images/hyb-s4.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Guía de configuración del impacto del coste total de propiedad (TCO) de la TI híbrida

La siguiente pantalla ofrece una descripción general de alto nivel de los pasos de configuración. Los requisitos de configuración detallados para cada paso se describen más adelante en el documento.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/config-hyb-3.jpg)

## Instalación de componentes

El primer paso es instalar los tres nuevos componentes que se han creado para la solución Hybrid IT TCO Impact.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/hyb-comp.jpg)

Nota: Asegúrese de que la versión de los componentes en la configuración del proyecto se ha establecido en la versión 120. Una vez instalada, puede volver a cambiar la versión del componente a la plantilla deseada/(anterior).

**Componente Workbench de aplicaciones**

El primer componente que se debe instalar es *el* componente Applications Workbench.

Este componente no incluye la referencia «Impacto del TCO de la TI híbrida» en su nombre, pero es esencial para la generación de informes sobre el impacto del TCO de la TI híbrida, ya que permite a los usuarios añadir metadatos esenciales de las aplicaciones. El campo (nuevo) más importante de este Workbench es la columna «**Alojado en** ». Esto debe completarse para todas las aplicaciones con el valor de: *On Prem, Private Cloud o Public Cloud* . Además de este nuevo campo, permite a los usuarios enriquecer los metadatos de sus aplicaciones existentes. Otro campo importante para esta solución es **el «objetivo de inversión de la aplicación** ». Asegúrese de que el valor esté establecido en «Migrar» para las aplicaciones sujetas a migración.

**Componente del impacto del TCO de la TI híbrida**

El segundo componente es *el* componente de impacto del TCO de la TI híbrida.

Esto crea el marco y, por lo tanto, instala todas las tablas necesarias (tanto editables como normales), métricas y modelos asociados con la solución Hybrid IT TCO Impact. Presenta el entorno de trabajo para la migración de aplicaciones.

Nota: También implementa tres informes. No están destinados a los usuarios finales, sino a facilitar el paso en el que se recopilan y «congelan» el TCO medio, el coste unitario y los volúmenes de uso del conjunto actual de aplicaciones como una instantánea en el tiempo (según el paso 3 del proceso anterior). Para obtener más detalles sobre el contenido de este componente, consulte la descripción al navegar hasta el componente.

**Componente de informes sobre el impacto del coste total de propiedad (TCO) de la TI híbrida**

El tercer y último componente es *el* componente de informes sobre el impacto del coste total de propiedad de la TI híbrida.

Esto instala tres informes para el usuario final. Va desde un informe de alto nivel, tipo «nivel 100», dirigido a ejecutivos de alto nivel, hasta el «nivel 300», en el que se pueden analizar las ventajas y desventajas financieras de cada aplicación individual.

Para obtener más detalles sobre el contenido de este componente, consulte la descripción al navegar hasta el componente.

## Arquitectura

**IBM Apptio Marco**

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/hyb-frame.jpg)

El diagrama anterior ofrece una visión general del marco « IBM » ( Apptio ) en lo que respecta a la arquitectura que sustenta la solución Hybrid IT TCO Impact. Se pueden ver los distintos flujos desde la fuente original hasta los informes del usuario final. Los puntos principales a destacar son los siguientes:

1. Introducción de Application Workbench y Application Migration Workbench: conjunto de tablas editables que permiten realizar modificaciones muy necesarias tanto en los datos existentes como en algunas columnas nuevas. El mapeo de aplicaciones requiere la eliminación (manual) de los datos maestros de la aplicación para permitir que la transformación editable (ET Transform) se convierta en la nueva fuente (editada) de los datos maestros de la aplicación.
2. Cambios mínimos en los datos maestros de las aplicaciones: aparte de la sustitución de la fuente, esta arquitectura tiene por objeto minimizar cualquier impacto directo en los datos maestros de las aplicaciones. Algunas columnas nuevas ( g.: Hosted On, Migration Strategy, etc.) Se introducen, indirectamente, a través del paso Columnas mapeadas de Aplicaciones ET Transformar en datos maestros de aplicaciones.
3. Informes de usuarios no finales críticos para «congelar» los datos migrados: como se muestra en la arquitectura, hay tres informes en el lado izquierdo (posición inicial), en contraposición al lado derecho (posición final). Esto es intencionado, ya que capturan los datos de migración y se crean de tal manera que esos datos deben volver a introducirse en Apptio, en tablas, para facilitar en última instancia la comparación entre el antes y el después.
4. Tras la migración de las aplicaciones, la nueva tabla clave actúa como fuente principal para la mayor parte de la configuración, los modelos y los informes.

**IBM Apptio Asignaciones de modelos**

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/fw-2-hyb.jpg)

El marco « IBM » ( Apptio ) ofrece una visión general de las nuevas tablas, conjuntos de datos maestros, etc. que se introducen, mientras que el diagrama anterior se centra en las nuevas métricas y asignaciones del modelo.

- **Coste tras la migración** : métrica modelada que se crea como una métrica modelada «paralela» al modelo de costes principal, con el fin de:
  - No «alterar» el modelo de costes existente
  - Permitir que se establezca un vínculo entre el objeto Aplicaciones (que contiene los datos nuevos de la aplicación de destino) y el objeto Aplicaciones migradas (que contiene los datos antiguos de la aplicación migrada)
  - Permite que el cliente (que desea ampliar aún más esta métrica modelada) establezca cualquier conductor adicional (relacionado específicamente con los costes de migración) según sea necesario

    Nota: Si ya es cliente, deberá asegurarse (manualmente) de que esta métrica modelada tenga todas las líneas de asignación necesarias etiquetadas, según su modelo de costes actual:
  - De fuente de costes a torres de recursos informáticos
  - De las torres de recursos informáticos a las aplicaciones
  - De aplicaciones a aplicaciones migradas
    - Peso por: Ponderación objetivo
    - Relación de datos: ID de aplicación = ID de aplicación de destino
- **Recuento de aplicaciones tras la migración** : métrica modelada necesaria para capturar el recuento de aplicaciones de las nuevas aplicaciones de destino. Esto es necesario para garantizar que el cálculo del promedio móvil de 12months es tenga en cuenta los meses en los que la aplicación «existe». I.e. En determinados casos, la aplicación solo puede estar disponible durante, por ejemplo, 8 meses. Si ese es el caso, debemos asegurarnos de que los costes se dividan entre 8 y no entre un número «fijo» de 12.

El recuento de las aplicaciones antiguas/migradas ya se recoge cuando se crean los informes «intermedios». Esta métrica modelada se aprovecha aún más en algunas de las otras métricas y reportes calculados para garantizar que el nuevo recuento de aplicaciones objetivo se represente correctamente.

Nota: Si ya es cliente, deberá asegurarse (manualmente) de que esta métrica modelada tenga todas las líneas de asignación necesarias, tal y como se muestra en el diagrama anterior, lo que significa:

- Crear un controlador «falso» establecido en 1 en Cost Source
- Crear una asignación desde la fuente de costes a las torres de TI.
  - No se necesita relación de peso ni datos
- Crear una asignación desde IT Towers a Aplicaciones migradas
  - Utilizando el método del «valor estándar»
  - Valor establecido en la columna «Número de aplicaciones objetivo»
- **Coste previo a la migración** : métrica modelada que expone el valor principal del « 12months” medio mensual acumulado» tomado de los datos «congelados» de las aplicaciones migradas.

Este modelo está preconfigurado, es decir, no requiere configuración manual.

## Configuraciones

En esta sección se describen todas las actividades de configuración relacionadas con la generación de informes sobre el impacto del coste total de propiedad (TCO) de la TI híbrida.

Los pasos 1 a 4 requieren cierta configuración (resaltados en amarillo ), mientras que los pasos 5 y 6 son el resultado final, centrados en los beneficios y la información que proporcionan los informes.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/hyb-s1.jpg)

1. **Paso 1: Aplicaciones actuales de TCO**
   - Para poder elaborar los tres informes sobre el impacto del TCO de la TI híbrida (dirigidos al usuario final), el primer paso es asegurarse de que el coste total de propiedad (TCO), los volúmenes de uso y los costes unitarios estén disponibles y se calculen para el conjunto actual de aplicaciones. Utilizando las asignaciones y el modelo normales y recomendados de ATUM.
   - Incluso antes de que se seleccione ninguna aplicación para la migración, utilice el nuevo Applications Workbench para asegurarse de que se introducen valores al menos para:

   Alojado en: Local, nube privada o Public
   Cloud

   Objetivo de inversión de la aplicación: mantener, retirar, migrar, invertir

   Ambos deben configurarse directamente en el nivel de la aplicación.

   Nota: Para empezar a utilizar la funcionalidad del banco de trabajo de aplicaciones, será necesario eliminar manualmente los datos de la aplicación sin procesar/fuente de los datos maestros de aplicaciones y volver a añadirlos a la tabla de fuentes de aplicaciones. Como se destaca en la vista de arquitectura anterior, este paso desbloquea los datos de la aplicación para que estén disponibles para su edición.

   Ejemplo:

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/hyb-s-1.jpg)

   *El ejemplo anterior muestra la aplicación ABC actual, que sigue su «vida normal» con el TCO, los volúmenes y el coste unitario establecidos como punto de partida fundamental*.
2. **Paso 2: Capturar los datos de las aplicaciones objetivo**

   Una vez que la aplicación actual se configura en Migrar, es esencial comenzar a capturar los metadatos relacionados con la migración de la aplicación, a medida que estén disponibles. Aquí es donde entra en juego el nuevo Application Migration Workbench, con tres áreas de configuración de la información. Nota: Las tablas siguientes solo muestran las aplicaciones cuyo objetivo de inversión de aplicaciones está establecido en «Migrar»

   **Migración de aplicaciones** : esta tabla editable contiene los siguientes campos:
   - *Estrategia de migración* (reubicación, replataforma, recompra, refactorización)

     Campo de texto libre, pero idealmente se debe establecer con uno de los valores anteriores

     Se utiliza en los informes como opción de pivote y/o filtro.
   - *Estado de la migración* (Planificación, En curso, Revisión, Finalizado)

     Indica principalmente el estado operativo de la migración.

     Campo de texto libre, pero idealmente se debe establecer con uno de los valores anteriores

     El valor «Hecho» se utiliza para indicar que los datos de la aplicación están listos para ser «congelados» y, por lo tanto, se utiliza como filtro crítico en los informes «intermedios». Nota: se utiliza junto con el campo «Estado de la migración» ( Apptio ) establecido en «Hecho».
   - *Apptio Estado de la migración* (Planificación, En curso, Revisión, Finalizada)

     Indica principalmente el estado de asignación de la migración en Apptio.

     Campo de texto libre, pero idealmente se debe establecer con uno de los valores anteriores

     El valor «Hecho» se utiliza para indicar que los datos de la aplicación están listos para ser «congelados» y, por lo tanto, se utiliza como filtro crítico en los informes «intermedios». Nota: se utiliza junto con el campo «Estado de la migración» establecido en «Hecho».
   - *Mes Año Migrado*

     Indica cuándo se migró oficialmente la aplicación.

     Campo de texto libre, pero idealmente se debe configurar como e. g.: Oct 2025.

   **Relación de migración de aplicaciones** : esta tabla editable contiene los siguientes campos:
   - *ID* de la aplicación de destino: ID de la nueva aplicación de destino. Se espera que se incorpore y exista en los datos maestros de aplicaciones (como es habitual). Nota: Puede ser más de 1, es decir, admite escenarios en los que una aplicación actual se migra a 1, 2, 3 o n aplicaciones nuevas.
   - *Ponderación objetivo* : en el caso de un escenario de 1 m, esto permite establecer una ponderación y asociarla a las nuevas aplicaciones m(any). Si no es aplicable, déjelo en blanco, se establecerá en 1.
   - **ID del grupo de migración de aplicaciones** : Se creará y configurará manualmente. En el caso de un escenario de 1 m, esto permitiría al usuario examinar los datos financieros comparativos antes y después a través del prisma de un grupo agregado, en lugar de aplicaciones individuales (en las que algunos de los datos financieros podrían no tener sentido)

   E.g:

   Aplicación actual/antigua | Aplicación nueva/destino | ID del grupo de migración de aplicaciones

   ABC 123 Aplicación Grupo A

   ABC 456 Grupo de aplicaciones A

   **Configuración de migración de aplicaciones** :

   Tabla editable que permite al usuario establecer determinados ajustes con respecto al seguimiento de objetivos y personalizar el texto HTML de los informes. La columna Descripción proporciona los detalles necesarios sobre cada uno de los ajustes.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/hyb-s-2.jpg)

   *En el paso 2, la aplicación ABC ha sido marcada para migrar, el proceso de migración ha comenzado y está en curso. La aplicación XYZ ha sido identificada como el ID de aplicación de destino.*
3. **Paso 3: «Congelar» las métricas actuales de la aplicación.**

   En algún momento, la aplicación actual se considerará migrada. Apptio Lo confirmaremos cuando se hayan actualizado y establecido como «Hecho» las columnas «Estado de la migración» y «Estado de la migración de Apptio ».

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/hyb-3.jpg)

   *En el paso 3, la aplicación ABC se ha migrado por completo. Por lo tanto, es hora de «congelar» y capturar los datos medios 12months (en azul) con respecto al TCO, los volúmenes y el coste* unitario.

   Se considera que ese es el punto de activación para que se produzca la «congelación» de los datos de la aplicación actual. Esta congelación se llevará a cabo de la siguiente manera: el conjunto de los tres informes que se indican a continuación recogerá todas las aplicaciones de los datos maestros de aplicaciones en las que las columnas «Estado de migración» y «Estado de migración de Apptio » sean iguales a «Hecho». Estos informes calcularán el promedio de los últimos doce meses para las métricas clave de coste total de propiedad (TCO), volúmenes y coste unitario. Las dos últimas métricas solo se calcularán en el nivel Resumen y, por lo tanto, no se aplican a los informes del grupo de costes y de la torre de TI.

   Nota: La fórmula que calcula el promedio garantiza que se comprueba cuánto tiempo lleva existiendo la aplicación mediante la comprobación del recuento de aplicaciones (ya que es posible que no todas las aplicaciones hayan existido durante un 12months e).

   Mientras que la parte a se realiza automáticamente, la parte b requiere que el usuario configure un conector de enlace de datos Apptio -to- Apptio. Este conector es necesario para tomar la salida del informe, «congelarla» en ese momento y volver a colocarla en la tabla asociada.

   Apptio Datalink Conector: Muestra a continuación. Para obtener más información, consulte el Centro de ayuda.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/hyb-s3.jpg)

   Tablas «Receptor» asociadas

   Aplicaciones migradas sin procesar

   Aplicaciones migradas CP Raw

   Aplicaciones migradas TI sin procesar

   Nota: Este conector está diseñado para incluir TODAS las aplicaciones migradas correspondientes a un mes determinado. En ese sentido, será una visión acumulativa a lo largo del tiempo. El mes 1 puede tener 10 solicitudes. El mes 2 podría tener 15 solicitudes.
4. **Paso 4: Modelo antiguo y nuevo**

   Una vez completado el paso 3, todos los datos necesarios «antes de la migración» están ahora disponibles en las tres tablas, tal y como se ha indicado anteriormente.

   El conjunto de datos principal de «Aplicaciones migradas» se utiliza y se expone automáticamente a la (nueva) métrica modelada de «Coste previo a la migración». No es necesario realizar ninguna acción aquí, ya que el controlador para esta métrica modelada se crea automáticamente para utilizar la columna «Costo total de propiedad mensual promedio». Los otros dos conjuntos de datos no se exponen a ninguna métrica modelada, ya que solo se utilizan en el informe Análisis del impacto del TCO de la TI híbrida (nivel 300). Se les ha añadido un paso modelado para que se pueda informar sobre ellos según sea necesario.

   La actividad clave de configuración en este paso está relacionada con la (nueva) métrica modelada de «Coste tras la migración». El componente introduce una asignación de «Aplicaciones» a «Aplicaciones migradas», aprovechando el modelo de costes existente como impulsor. Esto basta para iluminar el informe Hybrid IT TCO Impact Insights (nivel 200). Sin embargo, para poder generar el informe «Análisis del impacto del TCO de la TI híbrida (nivel 300)», el modelo de «Costes tras la migración» debe replicar todas las líneas de asignación desde «Fuente de costes» hasta «Aplicaciones» y «Aplicaciones migradas». Por lo tanto, es necesario etiquetar (manualmente) todas estas líneas de asignación de costes existentes con la nueva métrica modelada de «Cost Post Migration» (coste tras la migración), para que los desgloses del análisis del grupo de costes y de la torre de TI funcionen en el informe de análisis del impacto del TCO de la TI híbrida (nivel 300).

   La tercera y última métrica modelada nueva, «Recuento de aplicaciones tras la migración», es necesaria para capturar el recuento de aplicaciones nuevas y de destino. Esto es necesario para garantizar que el cálculo del promedio móvil de 12months es tenga en cuenta los meses en los que la aplicación «existe».

   Nota: Si ya es cliente, deberá asegurarse de que esta métrica modelada cuente con todas las líneas de asignación necesarias, tal y como se muestra en el diagrama anterior, lo que significa:
   - Crear un controlador «falso» establecido en 1 en Cost Source
   - Crear una asignación desde la fuente de costes a las torres de TI.
   - No se necesita relación de peso ni datos
   - Crear una asignación desde IT Towers a Aplicaciones migradas
   - Utilizando el método del «valor estándar»
   - Valor establecido en la columna «Número de aplicaciones objetivo»

A través de las tres métricas modeladas anteriormente, ahora se dispone de un marco que permite calcular y mostrar en los informes los resultados antes y después de la migración.

Para facilitar esto, se han establecido diversas métricas calculadas, entre las que destacan aquellas cuyo nombre comienza por «TTM...». Estas medidas se han implementado para garantizar que los datos sobre el coste total de propiedad, el coste unitario y el volumen de la aplicación tras la migración se calculen utilizando los mismos métodos de promedio de los últimos doce meses (TTM), con el fin de garantizar una comparación equitativa entre los resultados anteriores y posteriores.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/hyb-s4.jpg)

*En el paso 4, la nueva aplicación XYZ ya está lista y, por lo tanto, se compara de forma continua con los datos «congelados» de la aplicación ABC migrada.*

## Informes

El componente Hybrid IT TCO Impact Reporting instala tres informes, como parte de la colección de informes denominada «Hybrid IT». Se verá una referencia al nivel 100, 200, 300, lo que implica que el conjunto de informes expone cada vez más datos y va un paso más allá y más en profundidad.

**Nivel 100: Impacto del TCO de la TI híbrida - Resumen**

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cg-sum.jpg)

Nota: Este informe utiliza principalmente el conjunto de datos maestro de aplicaciones (como es habitual), así como la nueva columna «Alojado en», introducida a través del nuevo componente Applications Workbench. Esta columna debe configurarse en todas las aplicaciones, a nivel de aplicaciones. El establecimiento de objetivos se realizará utilizando el nuevo Applications Migrations Workbench.

**Nivel 200: Impacto del TCO de la TI híbrida: perspectivas**

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cg-200.jpg)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cg0200a.jpg)

Nota: Este informe utiliza principalmente el (nuevo) conjunto de datos de aplicaciones migradas. Requiere que los datos previos a la migración se introduzcan mediante el «método de congelación», tal y como se ha descrito anteriormente.

**Nivel 300: Impacto del coste total de propiedad (TCO) de la TI híbrida: análisis**

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cg-300.jpg)

Nota: Este informe utiliza principalmente el (nuevo) conjunto de datos de aplicaciones migradas. Requiere que los datos previos a la migración se introduzcan mediante el «método de congelación», tal y como se ha descrito anteriormente. También requiere que los datos del grupo de costes y los detalles de la torre de TI fluyan, tal y como se ha descrito anteriormente.

## Llamadas

Esta última sección tiene como objetivo resumir una serie de «avisos» que hay que tener en cuenta al configurar y utilizar esta solución como parte de sus procesos mensuales de gestión empresarial IBM Apptio.

**Horizonte temporal de comparación**

El método utilizado para la comparación «antes y después» es el método de los últimos 12 meses. Al revisar las aplicaciones migradas a lo largo del tiempo y compararlas con las nuevas aplicaciones de destino, tenga en cuenta que, transcurridos 12 meses, las aplicaciones antiguas/migradas ya no se recogerán o, al menos, ya no aparecerán los costes correspondientes a dichas aplicaciones.

En otras palabras, en este momento, el horizonte temporal de comparación (el periodo de tiempo durante el cual se puede realizar una comparación significativa entre el TCO, los volúmenes y el coste unitario antes y después) se establece en un máximo de 12 meses.

**Añadir otros controladores a Cost Post Migration**

Aprovecha el hecho de que esta nueva métrica modelada, «Coste tras la migración», es un modelo de costes «paralelo».

Añada cualquier otro factor financiero que considere que debe tenerse en cuenta en la vista «Cost Post Migration» (Coste tras la migración) si alguno de ellos no se recoge «de forma natural» en el modelo de costes.
