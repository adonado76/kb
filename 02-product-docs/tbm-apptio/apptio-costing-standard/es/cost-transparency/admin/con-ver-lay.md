---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Actualización de la versión del contenido"
breadcrumb:
  - "Costing Standard"
  - "Administración"
  - "Actualización de la norma de cálculo de costes"
source_path: "cost-transparency/admin/con-ver-lay.html"
images:
  - "resources/images/studio_images/s1-3a.png"
  - "resources/images/studio_images/s1-4.png"
  - "resources/images/studio_images/s10-10.png"
  - "resources/images/studio_images/s10-16.png"
  - "resources/images/studio_images/s10-16a.png"
  - "resources/images/studio_images/s10-17.png"
  - "resources/images/studio_images/s10-6.png"
  - "resources/images/studio_images/s10-8.png"
  - "resources/images/studio_images/s10-8a.png"
  - "resources/images/studio_images/s11-5.png"
  - "resources/images/studio_images/s12-3.png"
  - "resources/images/studio_images/s12-4.png"
  - "resources/images/studio_images/s12-6.png"
  - "resources/images/studio_images/s133.png"
  - "resources/images/studio_images/s134.png"
  - "resources/images/studio_images/s2-2.png"
  - "resources/images/studio_images/s2-2a.png"
  - "resources/images/studio_images/s3-2.png"
  - "resources/images/studio_images/s4-2.png"
  - "resources/images/studio_images/s5-1.png"
  - "resources/images/studio_images/s5-2.png"
  - "resources/images/studio_images/s5-4.png"
  - "resources/images/studio_images/s5-5.png"
  - "resources/images/studio_images/s5-7.png"
  - "resources/images/studio_images/s5-8.png"
  - "resources/images/studio_images/s7-3.png"
  - "resources/images/studio_images/s8-2.png"
  - "resources/images/studio_images/s8-3.png"
  - "resources/images/studio_images/s8-4.png"
  - "resources/images/studio_images/s9-5.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Actualización de la versión del contenido

## Actualizar los componentes de la aplicación a la última versión

Este artículo proporciona instrucciones generales para actualizar Costing Standard a la última versión de la plantilla. Complete los pasos descritos en este artículo solo después de haber actualizado la aplicación a la última versión de TBM Studio. Las imágenes de este artículo corresponden a la versión 12.5 con una actualización de la plantilla v104 a v105, pero las instrucciones sirven para cualquier actualización de plantilla.

Puede actualizar de forma selectiva solo los componentes cuyas nuevas funciones sean relevantes para sus necesidades. Antes de hacerlo, revise cuidadosamente las dependencias de los componentes que se muestran en la pantalla de instalación de componentes o que se documentan en la guía de configuración para garantizar la compatibilidad y evitar impactos no deseados.

## Mejores prácticas para el desarrollo paralelo durante el proceso de actualización

Si tiene previsto continuar con las actividades de desarrollo mientras actualiza los componentes, se recomiendan las siguientes prácticas recomendadas:

- Comprueba todos los cambios antes de crear una rama de actualización. Lo ideal es completar la actualización y fusionar la rama lo antes posible.
- Si es necesario continuar con el trabajo de desarrollo, las siguientes actividades también pueden continuar mientras la rama de actualización está abierta:
  - Cargar datos y publicar en los entornos de desarrollo, prueba y producción.
  - Crear nuevos informes personalizados.
  - Modificar los informes personalizados existentes.
- Evite las siguientes actividades hasta que se haya fusionado la rama:
  - Instalar nuevos componentes.
  - Añadir y asignar conjuntos de datos a conjuntos de datos maestros.
  - Cambiar las configuraciones o asignaciones del modelo.
  - Modificar informes listos para usar (OOTB).

El tiempo estimado para completar el proceso de actualización depende del número de componentes que se instalen, el grado de personalización de los informes OOTB y el nivel de validación necesario antes de poder fusionar la rama.

## Paso 1: Crear una rama

Antes de realizar este paso, actualice a la última versión de TBM Studio.

Realice el proceso de actualización en una rama separada, en lugar de hacerlo en un entorno de desarrollo personal.

1. Antes de crear la rama, completa y registra cualquier cambio en tu proyecto principal.
2. En la pestaña Proyecto, haga clic en Crear rama.

   Se abre el cuadro de diálogo Crear rama.
3. Introduce un nuevo nombre para la rama, por ejemplo, «Rama de actualización de versión».

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s1-3a.png)
4. Pulse Aceptar.

   Se abre el cuadro de diálogo Cola de cálculo. Espere a que se completen los cálculos.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s1-4.png)

## Paso 2: Abra la nueva rama

Actualiza el proyecto en una rama separada. Para obtener más información, consulte [Prácticas recomendadas: Ramificación de proyectos](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-best-practices-branching-projects "(se abre en una pestaña o una ventana nueva)").

1. En la pestaña Proyecto, haga clic en Trunk.
2. Seleccione la rama que desee, por ejemplo, «Rama de actualización de versión».

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s2-2.png)

   Después de seleccionar una rama, verás la rama activa en la barra de menú.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s2-2a.png)
3. Cada vez que vuelva a TBM Studio, compruebe que se encuentra en la rama de actualización correcta antes de continuar. Si no es así, y se muestra Trunk, deberá volver a seleccionar la rama de actualización de versión.

PRECAUCIÓN:

No realice cambios en el proyecto principal (por ejemplo, Trunk) durante las actividades de actualización en la rama de actualización independiente. Consulte [las prácticas recomendadas para el desarrollo paralelo durante el proceso de actualización](#converup__Best_practice_for) para obtener más detalles

## Paso 3: Cambiar la versión del componente

1. En la pestaña Proyecto, haga clic en Configuración del proyecto.

   Se abre el cuadro de diálogo Editar configuración del proyecto.
2. Para la versión del componente, seleccione la última versión, por ejemplo, la versión 105.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s3-2.png)
3. Haga clic en la opción para guardar.
4. Comprueba el cambio e introduce una descripción, como Configuración del proyecto: cambio a [actualizar versión de la plantilla].

## Paso 4: Revisar los componentes para actualizar

Confirme que las nuevas versiones de los componentes están disponibles y, a continuación, actualícelas.

1. En la pestaña Proyecto, haga clic en Componentes.

   Se abre el cuadro de diálogo Configuración de componentes.
2. Ver la lista de componentes instalados.

   Una flecha en la esquina inferior derecha de cada componente instalado indica que hay disponible una versión actualizada para ese componente.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s4-2.png)
3. Instalar y actualizar todos los componentes para la nueva versión de la plantilla. Realice el siguiente paso para cada componente que necesite actualizarse.

## Paso 5: Actualiza los componentes individuales y comprueba los cambios

1. En el cuadro de diálogo Configuración de componentes, haga doble clic en un componente específico, por ejemplo, CTF - Fuente de costes.

   Se abre una página de componentes.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s5-1.png)
2. Desplácese hacia abajo por debajo de la lista de informes incluidos hasta la sección Actualización disponible.
   - Un cuadro azul indica que no se han realizado personalizaciones en ningún elemento del componente.
   - Un cuadro amarillo indica que se han encontrado personalizaciones en los datos, las métricas calculadas o los informes.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s5-2.png)

   Nota: En ocasiones, el cuadro amarillo permanece después de revertir todas las personalizaciones. Para continuar, haga clic en el botón Actualizar del recuadro amarillo.
3. Si hay personalizaciones, haz clic en Ver conflictos o desplázate hasta la parte inferior de la página.
4. Revertir cualquier informe personalizado y métricas calculadas.

   Nota: No revierta los conjuntos de datos. Si se ha personalizado alguna de las columnas o fórmulas del conjunto de datos maestros estándar, es posible que deba revisar la configuración después de la actualización para asegurarse de que sus conjuntos de datos tengan las columnas y la configuración adecuadas.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s5-4.png)
5. Haga clic en Actualizar y, a continuación, confirme que la flecha de actualización ya no se muestra.

   La aplicación tarda unos minutos en procesar la actualización. Una vez que la página del componente se actualice y vuelva a la página Configuración del componente, podrá continuar.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s5-5.png)
6. Una vez completada la actualización, deberá cambiar manualmente cualquier otro conjunto de datos personalizado que no se haya revertido.

   Nota: Esta actividad podría requerir tiempo para comprender e implementar correctamente los cambios en el conjunto de datos maestro.
7. Realice los siguientes procedimientos según sea necesario para revertir sus conjuntos de datos personalizados:
   - Para añadir nuevas columnas a un conjunto de datos maestros existente:
     1. Vaya a «Tablas» y consulte «Datos maestros de fuentes de costes».
     2. Añade un paso de fórmula antes del paso de añadir.
     3. En el nuevo paso Fórmula, añada las nuevas columnas.

     ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s5-7.png)
8. Cuando haya terminado de actualizar sus conjuntos de datos personalizados, registre los cambios relacionados con la actualización de un solo componente, uno por uno, de la siguiente manera:
   1. Seleccione Proyectos y, a continuación, haga clic en Registrar.
   2. Seleccionar todos los elementos del panel izquierdo (predeterminado).
   3. Introduzca una descripción de los elementos en el panel Mensaje.
   4. Haga clic en «Check In» (Registrarse)

PRECAUCIÓN:

Si no se comprueban los componentes uno por uno, podría producirse un error que provoque la pérdida del trabajo y la necesidad de reiniciar la actualización desde beginning.\\

Nota: Introduzca una descripción útil, como «Fuente de costes: revertir cambios en el conjunto de datos, componente actualizado». Esto es fundamental para las actividades de fusión de ramas que se llevarán a cabo más adelante en este proceso de actualización. Revisa [el paso 10: Combinar los cambios en el proyecto principal (Trunk)](#converup__ten) para comprender por qué es importante.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s5-8.png)

## Paso 6: Pasos de actualización específicos para cada componente

Siga los pasos de actualización específicos de cada componente que se indican en la pantalla de instalación del componente o en la guía de configuración.

## Paso 7: Actualiza los componentes restantes en la rama de actualización

Repita los pasos 4 y 5 para actualizar tantos componentes como sea necesario.

Aunque no existe un orden prescriptivo para la actualización de los componentes, se recomienda actualizarlos en el mismo orden en que el objeto relacionado con el componente está asignado en los modelos. Por ejemplo, para Costing Standard, actualice Cost Source antes de IT Resource Towers, y IT Resource Towers antes de Applications.

Se recomienda actualizar todos los componentes instalados a la última versión para garantizar que dispone de las últimas funciones y del contenido de mayor calidad. También puede optar por actualizar solo un conjunto seleccionado de componentes con las características que desee.

PRECAUCIÓN:

Cuando termine de actualizar los componentes, siga estos pasos para evitar posibles pérdidas de datos.

1. Abra el componente CT Apps-Application.
2. En la sección Elementos personalizados, busca las siguientes métricas:
   - Desarrollo de aplicaciones (eliminado)
   - Ejecución de la aplicación (eliminada)
   - Presupuesto de ejecución de la aplicación (eliminado)
   - Presupuesto para desarrollo de aplicaciones (eliminado)
3. Haga clic en cada métrica que falte para volver a la versión original o estándar.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s7-3.png)
4. Comprueba el cambio.
5. Abra el componente CT-Unidades de negocio.
6. En la sección Elementos personalizados, busca las siguientes métricas:
   - CapEx Corregido (eliminado)
   - CapEx Variable (eliminada)
   - Inversiones en proyectos (eliminado)
7. Haga clic en cada métrica que falte para revertirla a la versión original o estándar.
8. Comprueba el cambio.

## Paso 8: Revisar la aplicación actualizada en la rama de actualización

1. En la pestaña Proyecto, haga clic en Cola de cálculo.

   Se abre el cuadro de diálogo Builds.
2. Verifique que las compilaciones hayan finalizado.

   Verás una lista de los registros individuales.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s8-2.png)
3. En la barra de navegación, seleccione «Costing Standard» en el menú «Application».

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s8-3.png)
4. Seleccione la rama de actualización, por ejemplo, la rama de actualización de versión.

   Se abre la página de inicio.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s8-4.png)

## Paso 9: Compare los informes de la versión anterior con los de la versión más reciente

1. Abre el proyecto Costing Standard en un navegador.
2. Seleccione Trunk para ver los informes de la plantilla anterior.
3. Abre el proyecto Costing Standard en otro navegador.
4. Seleccione la rama de actualización de versión para ver los nuevos informes de la plantilla actualizada.
5. Revisar los informes uno al lado del otro.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s9-5.png)
6. Si lo desea, vuelva a aplicar los cambios específicos del cliente a los informes directamente en la rama de actualización de versión.

   Nota:
   - Evite realizar cambios en los informes predefinidos para minimizar el esfuerzo que requieren las futuras actualizaciones.
   - Si es necesario personalizar los informes, aplique los cambios a los informes predeterminados después de completar el paso 7 para fusionar los cambios de actualización. Esto minimiza la cantidad de tiempo que tienes que trabajar en la rama de actualización de versión.
   - **Recuerda** : no realices cambios, salvo cargas de datos, en el proyecto principal (Trunk) después de crear tu rama de actualización.
7. Después de verificar la última versión de los informes, continúe con el siguiente paso para fusionar los cambios en su proyecto principal.

## Paso 10: Combinar los cambios en el proyecto principal (Trunk)

Consulte [las prácticas recomendadas: Ramificación de proyectos](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-best-practices-branching-projects "(se abre en una pestaña o una ventana nueva)") para obtener más información.

Nota: No combine todos los cambios en un solo paso. Si lo hace, el proceso de fusión fallará. La recomendación es fusionar pequeños lotes de registros de check-in, hasta un máximo de 5 registros a la vez. Esto requiere tomar notas para garantizar que todos los registros de check-in se fusionen en el tronco en el orden correcto.

1. Volver a TBM Studio.
2. Seleccione la rama de actualización, por ejemplo, Rama de actualización de versión.
3. En la pestaña Proyecto, haga clic en Comprobar historial.
4. Desplácese hasta la parte inferior de la lista, haga clic y comience con el primer elemento situado encima de las entradas *de arranque*. Esta debería ser la configuración del proyecto: cambiar a [nueva versión de la plantilla] check-in.

   Nota: Puede seleccionar elementos adicionales para registrar como una sola fusión, pero no seleccione más de 5 elementos a la vez.

   PRECAUCIÓN:

   La fusión de más de 5 elementos en un solo registro podría provocar un fallo en la aplicación.
5. Haga clic con el botón derecho en la línea y seleccione Combinar cambios en la rama.

   Este ejemplo utiliza el elemento de combinación CT-F Cost Source.
6. Seleccione Trunk como destinatario de la fusión.

   Se abre el cuadro de diálogo Combinar conjuntos de cambios.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s10-6.png)
7. Seleccionar todos los elementos para fusionar (predeterminado).

   Nota: No desmarque ningún elemento individual.
8. Pulse Aceptar.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s10-8.png)

   Recuerde: realice un seguimiento manual de los pasos fusionados a medida que actualiza los componentes, ya que el cuadro de diálogo Historial de registros no indica qué elementos se han fusionado. Si intenta registrar un artículo dos veces y aparece el siguiente mensaje, haga clic en Cancelar y continúe con otro componente.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s10-8a.png)
9. Una vez completado, la ventana debería cambiar a «Trunk». Si no es así, cambia a Trunk para registrar el elemento fusionado en tu proyecto.
10. Para verificar que el cambio se ha propagado al entorno de desarrollo:
    1. En la barra de navegación, seleccione el entorno En desarrollo.
    2. Haga clic en la pestaña Proyecto.
    3. Haga clic en Componentes.
    4. Compruebe que el componente ya no muestra la flecha de actualización, como en este ejemplo, para el componente CTF- Cost Source.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s10-10.png)
11. En el menú Entorno de la barra de navegación, seleccione Preparación.
12. En la cinta Proyecto, asegúrese de que el icono Bloqueado esté atenuado (no bloqueado).

    Solo tienes que hacerlo una vez.
13. En el menú Entorno de la barra de navegación, seleccione En desarrollo y, a continuación, haga clic en Registrar.

    Se abre el cuadro de diálogo Check In.
14. Seleccionar todos los elementos del panel izquierdo (predeterminado).

    Esto debería limitarse a los elementos fusionados.
15. Introduzca una descripción de los elementos en el panel Mensaje.

    Recuerde: utilice una descripción útil, como «Fusionar – CTF-Cost Source: revertir personalizaciones del informe de costes del servicio, actualizar componente».
16. Haga clic en «Check In».

    ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s10-16.png)

    Espera a que se complete la compilación.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s10-16a.png)
17. Verifica que el cambio esperado del paso de fusión de ramas se aplique al entorno de ensayo.

    En este ejemplo, en la pestaña Proyecto, haga clic en Componentes para verificar que la nueva versión de la plantilla ahora está activa.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s10-17.png)
18. Vuelve a la rama de actualización, por ejemplo, la rama de actualización de versión, para continuar con el siguiente elemento que se va a fusionar.
19. Repita los pasos anteriores para continuar fusionando hasta 5 ramas de actualización individuales (a la vez) y los registros posteriores en el tronco (en desarrollo) hasta que se hayan fusionado todas.

## Paso 11: Validar los informes de la última versión en el proyecto principal (Trunk)

1. Abre el proyecto Costing Standard en un navegador.
2. Seleccione Trunk para ver los informes actualizados.
3. Abre el proyecto Costing Standard en un segundo navegador.
4. Seleccione la rama de actualización de versión para comparar.
5. Compare y revise los informes uno al lado del otro.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s11-5.png)
6. Si lo desea, vuelva a aplicar los cambios específicos del cliente a los informes directamente en la rama principal, por ejemplo, Trunk.

Recuerde: Evite realizar cambios en los informes predeterminados para minimizar el esfuerzo que implican las actualizaciones futuras.

## Paso 12: Actualizar el entorno de producción

Una vez que haya terminado de verificar los informes, envíe la aplicación actualizada a Producción.

1. Ve al estudio « toTBM ».
2. Seleccione el entorno de ensayo.
3. En la cinta Proyecto, haga clic en Bloquear.

   Un breve mensaje emergente indicará que el entorno está bloqueado. El entorno ya está listo para pasar a producción.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s12-3.png)
4. En la cinta Proyectos, haga clic en Opciones de promoción y, a continuación, realice una de las siguientes acciones:
   - Haga clic en Promocionar ahora. La actualización se envía inmediatamente a producción.
   - Haga clic en Promocionar más tarde para programar cuándo se publicará la actualización en Producción.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s12-4.png)
5. En la cinta Proyecto, haga clic en Cola de cálculo para verificar la compilación de producción.
6. Compare los números de compilación de los entornos de desarrollo, prueba y producción.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s12-6.png)

## Paso 13: Cierre la rama de actualización

1. Seleccione la rama de actualización de versión.
2. En la cinta Proyecto, haga clic en Cerrar rama.

   Se abre el cuadro de diálogo Confirmar cierre.
3. Haga clic en Aceptar para cerrar la sucursal.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s133.png)
4. Confirma que Trunk ya no aparece en la barra de navegación.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/s134.png)

Recuerda: Cierra la rama de actualización lo antes posible. La rama consume la misma cantidad de recursos que el proyecto principal. Cerrar la rama de actualización libera recursos y mejora el rendimiento general.
