---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Actualizar Costing Standard de la plantilla v104+ a la última versión"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgradect-v104.html"
images:
  - "resources/images/ct_images/prereqs-uprading-to-v104-1.png"
  - "resources/images/ct_images/prereqs-uprading-to-v104-2.png"
  - "resources/images/ct_images/step-1-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-1-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-3.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-4.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-5.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-6.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-7.png"
  - "resources/images/ct_images/step-11-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-12-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-12-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-12-upgrading-to-v104-3.png"
  - "resources/images/ct_images/step-13-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-13-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-2-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-2-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-3-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-4-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-3.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-4.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-5.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-6.png"
  - "resources/images/ct_images/step-7-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-8-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-8-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-8-upgrading-to-v104-3.png"
  - "resources/images/ct_images/step-9-upgrading-to-v104-1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Actualizar Costing Standard de la plantilla v104+ a la última versión

Se aplica a: Costing Standard en TBM Studio 12 y posteriores, con Plantilla v104 y posteriores

## Actualizar los componentes de la aplicación a la última versión

Este artículo ofrece instrucciones generales para actualizar Costing Standard a la última versión de la plantilla. Complete los pasos de este artículo sólo después de haber actualizado la aplicación a la última versión de TBM Studio . Las imágenes de este artículo corresponden a la versión 12.5 con una actualización de la plantilla v104 a v105, pero las instrucciones sirven para cualquier actualización de plantilla. Estas instrucciones le indican en el [Paso 6: Pasos de actualización específicos del](#UpgradeCostingStandardfromtemplatev104tothelatestversion__Step6Componentspecificupgradesteps) componente que vaya a otro artículo para obtener instrucciones específicas del componente y, a continuación, vuelva a este artículo para completar la actualización.

Para ver una lista de los conjuntos de datos que deben actualizarse, consulte:

- Cambios en el conjunto de datos maestros para aplicaciones en TBM Studio 12.5
- Cambios en el conjunto de datos maestros para aplicaciones en TBM Studio 12.6
- Cambios en el conjunto de datos maestros para aplicaciones en TBM Studio 12.7

Nota: La actualización a la plantilla v104 introdujo una nueva experiencia de usuario con colecciones de informes recién organizadas e informes nuevos y simplificados. Si necesita actualizar de v103 a una versión de plantilla más reciente ( v104 o posterior), utilice las instrucciones de [Actualización de Costing Standard de la plantilla v103 a la última versión](upgrade-guide-v103-to-latest/upgradect.html) en lugar de este artículo.

## Buenas prácticas para el desarrollo paralelo durante el proceso de actualización

Si tiene previsto continuar con las actividades de desarrollo mientras actualiza los componentes, se recomiendan las siguientes prácticas recomendadas:

- Compruebe todos los cambios antes de crear una rama de actualización. Lo ideal es completar la actualización y fusionar la rama lo antes posible.
- Si es necesario continuar con el trabajo de desarrollo, las siguientes actividades también pueden continuar mientras esté abierta una rama de actualización:
  - Cargue datos y publíquelos en los entornos de desarrollo, ensayo y producción.
  - Crear nuevos informes personalizados.
  - Modificar los informes personalizados existentes.
- Evite las siguientes actividades hasta que se haya fusionado la rama:
  - Instalar nuevos componentes.
  - Añada y asigne conjuntos de datos a conjuntos de datos maestros.
  - Modificar configuraciones o asignaciones de modelos.
  - Modificar los informes out-of-the-box (OOTB).

El tiempo estimado para completar el proceso de actualización depende del número de componentes que se instalen, la cantidad de personalización realizada en sus informes OOTB y el nivel de validación necesario antes de poder fusionar la rama. Por ejemplo, una actualización reciente de 25 componentes para Costing Standard (pila completa) y Vendor Insights llevó aproximadamente 1-1/2 semanas.

## Configuración previa

Si necesita actualizar el componente Proveedor de servicios en la nube, la métrica Ponderación de facturas en la nube debe estar configurada antes de iniciar el proceso de actualización.

Para actualizar la métrica de ponderación de facturas en nube antes de iniciar el proceso de actualización.

1. Navegue a TBM Studio, luego en el Explorador de Proyectos, haga clic en Métricas

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/prereqs-uprading-to-v104-1.png)
2. Busque la métrica Ponderación de la factura en nube y actualícela como se indica a continuación:
   - Actualice el campo Tipo de métrica a Cálculo de costes
   - Asegúrese de que el valor del campo Cálculo de valor es =TimePeriod(Cloud Invoice,-1 )

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/prereqs-uprading-to-v104-2.png)
3. Compruebe las actualizaciones

## Paso 1: Crear una sucursal

Antes de realizar este paso, actualice a la última versión de TBM Studio .

Realice el proceso de actualización en una sucursal independiente, en lugar de en un entorno de Desarrollo personal.

1. Antes de crear la rama, completa y comprueba cualquier cambio en tu proyecto principal.
2. En la pestaña Proyecto, haga clic en Crear rama.

   Se abre el cuadro de diálogo Crear sucursal.
3. Introduzca un nuevo nombre de rama, por ejemplo, Rama de actualización de versión.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-1-upgrading-to-v104-1.png)
4. Pulse Aceptar.

   Se abre el cuadro de diálogo Cola de Cálculo. Espere a que finalicen los cálculos.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-1-upgrading-to-v104-2.png)

## Paso 2: Abrir la nueva rama

Actualiza el proyecto en una rama separada. Para más información, consulte [Buenas prácticas: Bifurcación de proyectos](../../studio/admin/bp-branching-projects.html "Se aplica a: TBM Studio 12.1 y posteriores").

1. En la pestaña Proyecto, haga clic en Tronco.
2. Seleccione la rama que desee, por ejemplo, Rama de actualización de versiones.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-2-upgrading-to-v104-1.png)

   Tras seleccionar una rama, verá la rama activa en la barra de menús.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-2-upgrading-to-v104-2.png)
3. Cada vez que vuelva a TBM Studio, compruebe que se encuentra en la rama de actualización correcta antes de continuar. Si no es así, y aparece Troncal, deberá volver a seleccionar la Rama de Actualización de Versión.

PRECAUCIÓN:

No realice cambios en el proyecto principal (por ejemplo, Trunk) durante el transcurso de las actividades de actualización en la rama de actualización independiente. Si lo hace, todos los cambios realizados en el tronco principal se perderán después de fusionar la rama de actualización.

## Paso 3: Cambiar la versión del componente

1. En la pestaña Proyecto, haga clic en Configuración del proyecto.

   Se abre el cuadro de diálogo Editar configuración del proyecto.
2. En Versión del componente, seleccione la última versión, por ejemplo, la versión 105.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-3-upgrading-to-v104-1.png)
3. Haga clic en la opción para guardar.
4. Marque el cambio e introduzca una descripción, como Configuración del proyecto: cambiar a [actualizar versión de plantilla].

## Paso 4: Revisar los componentes a actualizar

Confirme que las nuevas versiones de los componentes están disponibles y, a continuación, actualícelas.

1. En la pestaña Proyecto, haga clic en Componentes.

   Se abre el cuadro de diálogo Configuración de componentes.
2. Ver la lista de componentes instalados.

   Una flecha en la esquina inferior derecha de cada componente instalado indica que hay disponible una versión mejorada para ese componente.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-4-upgrading-to-v104-1.png)
3. Instale y actualice todos los componentes para la nueva versión de la plantilla. Realice el siguiente paso para cada componente que deba actualizarse.

## Paso 5: Actualizar componentes individuales y comprobar los cambios

1. En el cuadro de diálogo Configuración de componentes, haga doble clic en un componente específico, por ejemplo, CTF - Fuente de costes.

   Se abre una página de componentes.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-1.png)
2. Desplácese por debajo de la lista de informes incluidos hasta la sección Actualización disponible.
   - Un recuadro azul indica que no se han realizado personalizaciones en ningún elemento del componente.
   - Un recuadro amarillo indica que se han encontrado personalizaciones con los datos, las métricas calculadas o los informes.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-2.png)

   Nota: En ocasiones, el cuadro amarillo permanece después de revertir todas las personalizaciones. Para continuar, haga clic en el botón Actualizar del recuadro amarillo.
3. Si existen personalizaciones, haga clic en Ver conflictos o desplácese hasta el final de la página.
4. Revertir los informes personalizados y las métricas calculadas.

   Nota: No revierta los conjuntos de datos. Si alguna de las columnas o fórmulas del conjunto de datos maestros estándar se ha personalizado, es posible que tenga que revisar la configuración después de la actualización para asegurarse de que sus conjuntos de datos tienen las columnas y la configuración adecuadas. Consulte el paso 6 para obtener más información.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-3.png)
5. Haga clic en Actualizar y confirme que ya no aparece la flecha de actualización.

   La aplicación tarda unos minutos en procesar la actualización. Después de que la página del componente se actualice y vuelva a la página de Configuración del componente, puede continuar.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-4.png)
6. Una vez finalizada la actualización, deberá modificar manualmente cualquier otro conjunto de datos personalizado que no se haya revertido. Consulte una de las siguientes listas acumulativas para identificar qué cambios son necesarios:
   - Cambios en el conjunto de datos maestros para aplicaciones en TBM Studio 12.5
   - Cambios en el conjunto de datos maestros para aplicaciones en TBM Studio 12.6
   - Cambios en el conjunto de datos maestros para aplicaciones en TBM Studio 12.7

   Nota: Esta actividad podría requerir tiempo para comprender y aplicar correctamente los cambios en el conjunto de datos maestro.
7. Realice los siguientes procedimientos según sea necesario para revertir sus conjuntos de datos personalizados:
   - Para añadir nuevas columnas a un conjunto de datos maestros existente:
     1. Vaya a Tablas y compruebe los Datos maestros de la fuente de costes.
     2. Añada un paso Fórmula antes del paso Añadir.
     3. En el nuevo paso Fórmula, añada las nuevas columnas.

     ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-5.png)
   - Para actualizar los siguientes componentes de Cloud Cost Management (CCM), siga los pasos que se indican a continuación y vuelva a este artículo:
     - CT Apps - AWS Recomendaciones
     - CTF - Amazon Web Services
     - CTF - Azure
     - CTF - Proveedor de servicios en nube
     - CTF - Public Cloud MTD
     - CTF - Integración de CCM en CT
   - Para actualizar los siguientes componentes de Vendor Insights , haga clic en el enlace correspondiente para obtener instrucciones detalladas:
     - Fundación Vendor Insight
     - Vendor Insight PO
8. Cuando haya terminado de actualizar sus conjuntos de datos personalizados, compruebe los cambios relacionados con la actualización de un único componente, de uno en uno, del siguiente modo:

   PRECAUCIÓN:

   Si no comprueba los componentes de uno en uno, podría producirse un error que le obligaría a perder su trabajo y a reiniciar la actualización desde el principio.

   1. Seleccione Proyectos y, a continuación, haga clic en Registrar.
   2. Seleccione Todos los elementos en el panel izquierdo (por defecto).
   3. Introduzca una descripción de los elementos en el panel Mensaje.

      Se abre el cuadro de diálogo Check In.

      Nota: Introduzca una descripción útil, como Fuente de costes: revertir cambios en el conjunto de datos, componente actualizado. Esto es crítico para las actividades de fusión de ramas más adelante en este proceso de actualización. Revise [el Paso 10: Fusionar cambios en el proyecto principal (Trunk](upgradect-v104.html) ) para entender por qué esto es importante.

      ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-6.png)
   4. Haga clic en Check In.

## Paso 6: Pasos de actualización específicos del componente

Los siguientes componentes requieren instrucciones especiales:

- v106 Componentes - Actualice todos los componentes de Nube con las instrucciones de Actualización de Nube para la Transparencia de Costes R12.6 ( v106 ), después vuelva al siguiente paso de esta guía.
- v107 Componentes - Actualizar el Apptio Value Explorer (AVE) con instrucciones para [Actualizar a Apptio Value Explorer 12.7 ( v107](../configuration-additional/upgradetoave1.7v107.html) ).

## Paso 7: Actualizar los componentes restantes en la rama de actualización

Repita los pasos 4 y 5 para actualizar tantos componentes como sea necesario.

Aunque no existe un orden preceptivo para la actualización de componentes, se recomienda actualizar los componentes en el mismo orden en que se asigna el objeto relacionado con el componente en sus modelos. Por ejemplo, para Costing Standard, actualice Fuente de costes antes de Torres de recursos de TI, y Torres de recursos de TI antes de Aplicaciones.

La recomendación es actualizar todos los componentes instalados a la última versión para asegurarse de que dispone de las últimas funciones y los contenidos de mayor calidad. También puede elegir actualizar sólo un conjunto selecto de componentes con las funciones que desee. Póngase en contacto con Apptio si tiene alguna pregunta.

**Precaución**

Cuando termine de actualizar los componentes, realice los siguientes pasos para evitar posibles pérdidas de datos.

1. Abra el componente CT Apps-Application.
2. En la sección Elementos personalizados, busque las siguientes métricas:
   - Desarrollo de aplicaciones (eliminado)
   - App Run (eliminada)
   - Presupuesto de ejecución de la aplicación (eliminado)
   - Presupuesto para desarrollo de aplicaciones (suprimido)
3. Haga clic en cada métrica que falte para volver a la versión original o de stock.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-7-upgrading-to-v104-1.png)
4. Comprueba el cambio.
5. Abra el componente CT-Unidades de Negocio.
6. En la sección Elementos personalizados, busque las siguientes métricas:
   - CapEx Fijo (suprimido)
   - CapEx Variable (suprimida)
   - Inversiones en proyectos (suprimido)
7. Haga clic en cada métrica que falte para volver a la versión original.
8. Comprueba el cambio.

## Paso 8: Revisar la aplicación actualizada en la rama de actualización

1. En la pestaña Proyecto, haga clic en Cola de cálculo.

   Se abre el cuadro de diálogo Builds.
2. Compruebe que las construcciones han finalizado.

   Verá una lista de los registros individuales.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-8-upgrading-to-v104-1.png)
3. En la barra de navegación, seleccione Costing Standard en el menú Aplicación.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-8-upgrading-to-v104-2.png)
4. Seleccione la rama de actualización, por ejemplo Rama de actualización de versión.

   Se abre la página de inicio.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-8-upgrading-to-v104-3.png)

## Paso 9: Comparar los informes de la versión anterior con los de la versión más reciente

1. Abra el proyecto Costing Standard en un navegador.
2. Seleccione Tronco para ver los informes de la plantilla más antigua.
3. Abra el proyecto Costing Standard en otro navegador.
4. Seleccione la rama de actualización de versión para ver los nuevos informes de la plantilla actualizada.
5. Revise los informes uno al lado del otro.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-9-upgrading-to-v104-1.png)
6. Si lo desea, vuelva a aplicar los cambios específicos del cliente a los informes directamente en la rama de actualización de versiones.

   Nota:
   - Evite realizar cambios en los informes preconfigurados para minimizar el esfuerzo que suponen las futuras actualizaciones.
   - Si es necesario personalizar los informes, aplíquelos a los informes listos para usar después de completar el paso 7 para fusionar los cambios de actualización. Esto minimiza el tiempo de trabajo en la rama de actualización de versiones. **Recuerde** - no realice cambios, salvo cargas de datos, en el proyecto principal (Trunk) después de crear su rama de actualización.
7. Después de verificar la última versión de los informes, continúe con el siguiente paso para fusionar los cambios en su proyecto principal.

## Paso 10: Fusionar los cambios en el proyecto principal (Trunk)

Consulte [Prácticas recomendadas: Bifurcar proyectos](../../studio/admin/bp-branching-projects.htm "(se abre en una pestaña o una ventana nueva)") para más información.

Nota: No fusione todos los cambios en un solo paso. Si lo hace, el proceso de fusión falla. La recomendación es fusionar pequeños lotes de registros de facturación: hasta 5 registros a la vez. Esto requiere tomar notas para garantizar que todos los registros de entrada se fusionan en el tronco en el orden correcto.

1. Volver a TBM Studio.
2. Seleccione la rama de actualización, por ejemplo, Rama de actualización de versión.
3. En la pestaña Proyecto, haga clic en Historial de entradas.
4. Desplácese hasta el final de la lista, haga clic y comience por el primer elemento situado encima de las entradas de *arranque*. Este debería ser el check-in Ajustes del proyecto: cambiar a [nueva versión de plantilla].

   NOTA: Puede seleccionar elementos adicionales para facturar como una fusión única, pero no seleccione más de 5 elementos a la vez.

   PRECAUCIÓN Fusionar más de 5 elementos en un mismo registro podría provocar el fallo de la aplicación.
5. Haga clic con el botón derecho del ratón en la partida y seleccione Combinar cambios en la rama.

   Este ejemplo utiliza el elemento de fusión Fuente de coste CT-F.
6. Seleccione Troncal como destinatario de la fusión.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-1.png)

   Se abre el cuadro de diálogo Combinar conjuntos de cambios.
7. Seleccionar todos los elementos para la fusión (por defecto).

   NOTA: No deseleccione ningún elemento individual.
8. Pulse Aceptar.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-2.png)

   RECOMENDACIÓN: Realice un seguimiento manual de los pasos fusionados a medida que actualiza los componentes, ya que el cuadro de diálogo Historial de registros no indica qué elementos se han fusionado. Si intenta registrar un elemento dos veces y aparece el siguiente mensaje, haga clic en Cancelar y, a continuación, proceda con otro componente.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-3.png)
9. Una vez completado, la ventana debería cambiar a Tronco. Si no es así, cambie a Trunk para comprobar el elemento fusionado en su proyecto.
10. Para verificar que el cambio se ha propagado al entorno de Desarrollo:
    1. En la barra de navegación, seleccione el entorno En desarrollo.
    2. Haga clic en la pestaña Proyecto.
    3. Haga clic en Componentes.
    4. Compruebe que el componente ya no muestra la flecha de actualización, como en este ejemplo, para el componente CTF- Fuente de costes.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-4.png)
11. En el menú Entorno de la barra de navegación, seleccione Puesta en escena.
12. En la cinta Proyecto, asegúrese de que el icono Bloqueado está en gris (no bloqueado).

    Sólo tiene que hacerlo una vez.
13. En el menú Entorno de la barra de navegación, seleccione En desarrollo y, a continuación, haga clic en Registrar.

    Se abre el cuadro de diálogo Check In.
14. Seleccionar todos los elementos del panel izquierdo (por defecto).

    Esto debería limitarse a los elementos fusionados.
15. Introduzca una descripción de los elementos en el panel Mensaje.

    RECOMENDACIÓN: Utilice una descripción útil como Fusión - CTF-Coste Fuente: revertir las personalizaciones del informe de cálculo de costes del servicio, actualizar el componente.
16. Haga clic en Check In.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-5.png)

    Espere a que finalice la compilación.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-6.png)
17. Verificar que el cambio esperado del paso de fusión de rama se aplica al entorno de puesta en escena.

    En este ejemplo, en la pestaña Proyecto, haga clic en Componentes para comprobar que la nueva versión de la plantilla ya está activa.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-7.png)
18. Vuelva a la rama de actualización, por ejemplo, Rama de actualización de versión, para proceder con el siguiente elemento a fusionar.
19. Repita los pasos anteriores para continuar fusionando hasta 5 ramas de actualización individuales (a la vez) y las subsiguientes revisiones del tronco (En desarrollo) hasta que todas se hayan fusionado.

## Paso 11: Validar los informes de la última versión en el proyecto principal (Trunk)

1. Abra el proyecto Costing Standard en un navegador.
2. Seleccione Tronco para ver los informes actualizados.
3. Abra el proyecto Costing Standard en un segundo navegador.
4. Seleccione Rama de actualización de versión para comparar.
5. Compare y revise los informes uno al lado del otro.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-11-upgrading-to-v104-1.png)
6. Si lo desea, vuelva a aplicar los cambios específicos del cliente a los informes directamente en la rama principal, por ejemplo, Troncal.

   RECOMENDACIÓN Evite realizar cambios en los informes preconfigurados para minimizar el esfuerzo de futuras actualizaciones.

## Paso 12: Actualizar el entorno de producción

Cuando termine de verificar los informes, envíe la aplicación actualizada a Producción.

1. VisiteTBM Studio.
2. Seleccione el entorno Staging.
3. En la cinta Proyecto, haga clic en Bloquear.

   Un breve mensaje emergente indicará que el entorno está bloqueado. El entorno ya está listo para pasar a Producción.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-12-upgrading-to-v104-1.png)
4. En la cinta Proyectos, haga clic en Opciones de promoción y, a continuación, realice una de las siguientes acciones:
   - Haga clic en Promover ahora. La actualización se envía a Producción inmediatamente.
   - Haga clic en Promover más tarde para programar cuándo se publicará la actualización en Producción.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-12-upgrading-to-v104-2.png)
5. En la cinta Proyecto, haga clic en Cola de cálculo para verificar la compilación de producción.
6. Compare los números de compilación de los entornos de desarrollo, ensayo y producción.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-12-upgrading-to-v104-3.png)

## Paso 13: Cerrar la rama de actualización

1. Seleccione la rama de actualización de versión.
2. En la cinta Proyecto, haga clic en Cerrar rama.

   Se abre el cuadro de diálogo Confirmar cierre.
3. Haga clic en Aceptar para cerrar la rama.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-13-upgrading-to-v104-1.png)
4. Confirme que Tronco ya no aparece en la barra de navegación.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-13-upgrading-to-v104-2.png)

   RECOMENDACIÓN: Cierre la rama de actualización lo antes posible. La rama consume la misma cantidad de recursos que el proyecto troncal principal. El cierre de la rama de actualización libera recursos y mejora el rendimiento general.

## Paso 13: Hacer visibles los informes de infraestructura

A partir de TBM Studio 12.6 (y Plantilla v106 ), los informes Infra Server y Storage se trasladaron a la colección de informes Infrastructure Insights. Debido a este cambio, por defecto en Enhanced Access Administration se muestra que los informes pueden ser vistos por Nadie, lo que puede crear confusión cuando intente acceder a sus antiguos informes. Para corregir la navegación, consulte [Actualizar la visibilidad de los informes de infraestructura tras la actualización de v106](ct-upgrade-inf-visibility-after-v106.html "A partir de TBM Studio 12.6 (con la plantilla v106 ), los informes Infra Server y Storage se trasladaron a la colección de informes Infrastructure Insights desde la colección de informes Infrastructure & Cloud en Costing Standard. Debido a este cambio en la navegación, el valor predeterminado en Enhanced Access Administration muestra que los informes pueden ser vistos por Nadie, lo que puede crear confusión cuando intente acceder a sus antiguos informes.").

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
