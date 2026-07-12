---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Deshacer una configuración"
breadcrumb: []
source_path: "studio/admin/roll-back-configuration.html"
images:
  - "resources/images/studio_images/changehist-rollback.png"
  - "resources/images/studio_images/rollback-dialog.png"
  - "resources/images/studio_images/rollback-result.png"
  - "resources/images/studio_images/rollback.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Deshacer una configuración

En Apptio TBM Studio versión 12.2.2 y posteriores, es posible utilizar la función de **retroceso** en el Historial de comprobaciones para retroceder una configuración a un punto anterior en el tiempo. Esta función es útil para revertir cambios cuando algo ha ido mal, y es similar a la función Deshacer todo después del registro de auditoría de v.11.

Nota: Hay consideraciones importantes antes de ejecutar un rollback. Le recomendamos que lea y comprenda completamente este artículo antes de intentar una reversión. Si sigue teniendo preguntas o dudas, póngase en contacto con el servicio de asistencia Apptio para obtener ayuda.

Estas son algunas de las razones por las que podría considerar el uso de la función de reversión:

- Se ha registrado algo que está causando problemas de rendimiento.
- Algo fue desplegado a producción prematuramente. Consulte [las prácticas recomendadas de check out y check in](bp-check-out.html "◆ Se aplica a: Apptio TBM Studio 12.x y versiones posteriores. En Apptio TBM Studio R12, todos los elementos son documentos, incluidas las tablas de datos, métricas, perspectivas y modelos. Para editar un documento, primero debe verificarlo. Cuando sacas un documento, se bloquea para que otros no puedan editarlo. Puede guardar sus cambios en el documento sin activar un recálculo. Cuando termines de editar un documento, puedes registrarlo. El registro de un documento provoca un nuevo cálculo. Ahora, los demás verán los cambios que hayas realizado en el documento cuando finalice el cálculo en modo de desarrollo y se actualice su espacio de trabajo. Además, ahora otros podrán consultar este documento.") para obtener información sobre cómo aplicar hotfix a un proyecto si este es el motivo por el que se plantea una reversión, ya que puede resultar más rápido.

## Consideraciones importantes

El retroceso no debe utilizarse a la ligera. Cuando se ejecuta una operación de retroceso, se detienen todos los cálculos en curso del proyecto y se inicia un nuevo cálculo, utilizando la configuración asociada a la comprobación a la que se está retrocediendo. Cuando se ejecuta el rollback, se aplican las siguientes consideraciones:

- Se descartarán todas las comprobaciones posteriores a la comprobación a la que está retrocediendo. Si hay cambios en esos controles que usted desea, tendrá que volver a aplicar esos cambios. Consulte la última sección de este documento sobre cómo facilitar esta tarea.
- Deberá ejecutarse un cálculo completo, que puede tardar un poco en función de la configuración del proyecto en el check in al que se está retrocediendo.
- Si se están realizando cálculos para otros proyectos, es posible que el cálculo resultante de un retroceso se coloque detrás de éstos.

## Deshacer una configuración

[Compruebe las mejores prácticas](bp-check-out.html "◆ Se aplica a: Apptio TBM Studio 12.x y versiones posteriores. En Apptio TBM Studio R12, todos los elementos son documentos, incluidas las tablas de datos, métricas, perspectivas y modelos. Para editar un documento, primero debe verificarlo. Cuando sacas un documento, se bloquea para que otros no puedan editarlo. Puede guardar sus cambios en el documento sin activar un recálculo. Cuando termines de editar un documento, puedes registrarlo. El registro de un documento provoca un nuevo cálculo. Ahora, los demás verán los cambios que hayas realizado en el documento cuando finalice el cálculo en modo de desarrollo y se actualice su espacio de trabajo. Además, ahora otros podrán consultar este documento.").

1. Seleccione el documento en **el Explorador de proyectos**.
2. En la pestaña **Construir**, seleccione **Historial de entradas**.
3. Haga clic con el botón derecho del ratón en la casilla de verificación a la que desea retroceder y seleccione **Retroceder a**.

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rollback.png)
4. Introduzca el motivo de la reversión (se recomienda ser lo más descriptivo posible) y, a continuación, haga clic en **Registro de reversión**.

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rollback-dialog.png)

   Tras la reversión, el resultado se muestra de forma similar al ejemplo siguiente:

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rollback-result.png)

   Puede ver el estado del cálculo en la pestaña Builds:

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/changehist-rollback.png)

   Nota: Todas las comprobaciones posteriores a la comprobación seleccionada para la reversión se deshacen, excepto el cierre de la rama (las operaciones de rama están exentas de reversión).
5. Una vez finalizada la compilación, actualice los espacios de trabajo con documentos retirados. En la pestaña Inicio, seleccione **Actualizar espacio de trabajo**.
6. Para actualizar forzosamente el área de trabajo, puede que tenga que desactivar temporalmente el Cálculo automático. En la pestaña Inicio, seleccione Cálculo automático, luego seleccione Actualizar espacio de trabajo y, a continuación, vuelva a seleccionar Cálculo automático.

   Nota: Actualizar los espacios de trabajo es especialmente importante si la reversión se debe a problemas de rendimiento. Si los documentos fueron retirados mientras la configuración sospechosa estaba en juego, el espacio de trabajo del usuario puede sufrir los mismos efectos nocivos que provocaron la reversión.

## Examinar algo que se ha anulado

Después de un rollback, es posible que desee examinar lo que estaba en los check ins que se deshicieron, ya sea para depurar lo que estaba causando problemas de rendimiento, o para ver una configuración que desea volver a implementar. Para ello, utilice una rama. Consulte [las prácticas recomendadas de check out y check in](bp-check-out.html "◆ Se aplica a: Apptio TBM Studio 12.x y versiones posteriores. En Apptio TBM Studio R12, todos los elementos son documentos, incluidas las tablas de datos, métricas, perspectivas y modelos. Para editar un documento, primero debe verificarlo. Cuando sacas un documento, se bloquea para que otros no puedan editarlo. Puede guardar sus cambios en el documento sin activar un recálculo. Cuando termines de editar un documento, puedes registrarlo. El registro de un documento provoca un nuevo cálculo. Ahora, los demás verán los cambios que hayas realizado en el documento cuando finalice el cálculo en modo de desarrollo y se actualice su espacio de trabajo. Además, ahora otros podrán consultar este documento.") para saber cómo crear una sucursal. Puede bifurcarse a partir de registros no realizados. También es posible copiar el contenido de un informe de una rama y pegarlo en los documentos comprobados de su espacio de trabajo. En algunos casos, esto puede ser conveniente para minimizar la repetición del trabajo.
