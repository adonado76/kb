---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Asignación de etiquetas y marcas"
breadcrumb:
  - "Cloudability Premium"
  - "Configuración"
  - "Organiza tus gastos en la nube"
source_path: "admin/map-tags.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Asignación de etiquetas y marcas

Cloudability permite una asignación exhaustiva de costes mediante la importación y normalización de etiquetas y marcadores procedentes de proveedores de servicios en la nube compatibles, plataformas de « SaaS » y entornos de contenedores. Este documento describe los tipos de etiquetas y marcas que admite cada proveedor, cómo se recopilan (datos de facturación frente a API), los permisos necesarios y aspectos clave que hay que tener en cuenta, como las diferencias de formato, las reglas de prioridad y las limitaciones conocidas

## Compatibilidad con etiquetas y marcadores según el fabricante

AWS Etiquetas

Cloudability admite los siguientes tipos de etiquetas para AWS

- **Etiquetas de nivel de recurso**

  Estos forman parte de los archivos CUR de AWS y no se necesitan permisos adicionales en Cloudability para activarlos
- **Etiquetas a nivel de cuenta** (a través de la API)

  Para obtener las etiquetas a nivel de cuenta de las organizaciones de « AWS », « Cloudability » necesita un permiso adicional denominado « **organizations:ListTagsForResource** ». Nota: Las etiquetas a nivel de cuenta no están disponibles actualmente en Cloudability Gov.

  En Cloudability se muestran con el siguiente formato:

  `cldy:aws:accountLevelTag:<tag
  key>`

Nota: Si un cliente cambia del CUR antiguo al CUR 2.0, deberá volver a configurar sus etiquetas y rótulos en Cloudability.

Diferencia entre las etiquetas « AWS » y «CUR» heredadas de CUR y las etiquetas «CUR» de 2.0 :

Formato antiguo de las etiquetas CUR:

- AWS etiquetas = `aws:<tag key>` p. ej., `aws:autoscaling:groupname`
- etiquetas de usuario = `<tag key>`

Formato de las etiquetas «CUR 2.0 »:

- AWS Las etiquetas = `aws_<tag key>` se separarán con un guión bajo = p. ej.: `aws_autoscaling_group_name`
- etiquetas de usuario = `user_<tag key>` p. ej., `user_application`

Azure Etiquetas

Cloudability admite los siguientes tipos de etiquetas para Azure :

- **Etiquetas de nivel de recurso**
  - Estos forman parte de los archivos de exportación de « Azure » y no se necesitan permisos adicionales en Cloudability para activarlos
  - Formato de etiquetas - `cldy:Azure:ResourceTag:<resource tag key>`
- **Etiquetas de grupos de recursos** (a través de la API)
  - Para obtener las etiquetas de los grupos de recursos de Azure, Cloudability necesita permisos adicionales para credenciales avanzadas, concretamente **«management:Reader»** o « **Microsoft.Resources/subscriptions/resourceGroups/read** » en la suscripción.
  - Formato de etiquetas - `cldy:Azure:ResourceGroupTag:<resource group tag key>`

  Importante:

  Si una clave de etiqueta existe en un recurso tanto a nivel de recurso como a nivel de grupo de recursos, y se asigna la **clave de etiqueta sin formato** del menú desplegable (por ejemplo, `project`), Cloudability resolverá el valor de la siguiente manera:

  - La etiqueta de nivel de recurso se utiliza cuando está presente.
  - Si la etiqueta de nivel de recurso no existe o es nula, se utiliza la etiqueta de grupo de recursos como alternativa.

  Si no quieres que se utilice la etiqueta del grupo de recursos como alternativa, asigna en su lugar la **etiqueta explícita a nivel de recurso** (por ejemplo, `cldy:Azure:ResourceTag:project`).
- **Etiquetas de nivel de suscripción** (a través de la API)
  - Para obtener las etiquetas de nivel de suscripción de Azure, Cloudability necesita un permiso adicional: **subscription:ReadSubscription**
  - Formato de etiquetas - `cldy:Azure:SubscriptionLevelTag:<subscription tag key>`

GCP Etiquetas y rótulos

Cloudability admite los siguientes tipos de etiquetas y rótulos para « GCP »:

- **GCP Etiquetas**

  Estos datos forman parte del extracto de datos de facturación de « GCP » y no se requieren permisos adicionales en Cloudability para habilitarlos. Cloudability es compatible con las siguientes etiquetas:

  - Etiquetas de recursos
  - Etiquetas de proyectos
  - Etiquetas del sistema

  Si se configura la misma clave para las etiquetas de proyecto, sistema y recurso, el orden de prioridad para mostrar la etiqueta en la interfaz de usuario de Cloudability es el siguiente: **Recurso** > **Proyecto** > **Sistema**

  Nota: Cloudability no admite la asignación de etiquetas resultantes de la función «Asignación de costes de GKE » de GCP. Las etiquetas como `goog-k8s-*` o `k8s-*` darán lugar a valores (no definidos). Para poder beneficiarse de la asignación de costes de contenedores, los clústeres deben aprovisionarse para su uso en la función *« Cloudability » de contenedores,* que permite la asignación de costes a nivel de espacio de nombres y de etiquetas.
- **GCP Etiquetas**

  Estos datos forman parte del extracto de datos de facturación de « GCP » y no se requieren permisos adicionales en Cloudability para habilitarlos

  Formato de las etiquetas « GCP » compatibles con Cloudability :

  `cldy:gcp:tag:<tagKey>` para asignaciones directas de etiquetas

  `cldy:gcp:tag:<tagKey>:inherited` para las etiquetas heredadas

  `cldy:gcp:tag:<tagKey>:namespace` para el nivel de fijación de la etiqueta

Etiquetas OCI

- **Etiquetas a nivel de recurso y de compartimento**
  - Nivel de recurso o nivel de compartimento asignado por espacio de nombres. Estos datos forman parte de los datos de facturación de OCI y no se necesitan permisos adicionales en Cloudability para activarlos
  - Las etiquetas a nivel de compartimento deben asignarse primero a través de un espacio de nombres de etiquetas y, a continuación, configurarse como valor predeterminado de etiqueta en OCI

Nota: Asignamos los campos de facturación de OCI «*nombre del* compartimento» e *«id del compartimento»* a claves de etiqueta denominadas `cldy:oci:compartmentname` y `cldy:oci:compartmentid`

IBM Etiquetas

- **Etiquetas de nivel de recurso**
  - Estos datos forman parte de los datos de facturación de « IBM » y no se requieren permisos adicionales en Cloudability para activarlos

Etiquetas de Databricks

- **Etiquetas personalizadas a nivel de recurso**

  Estos datos forman parte de la información de facturación de Databricks y no se necesitan permisos adicionales en Cloudability para habilitarlos

Nota: Transmitimos los metadatos de uso de Databricks, los metadatos de identidad y las características del producto en forma de etiquetas. *WorkspaceId* aparecerá como clave de etiqueta en `cldy:databricks:workspaceid`

MongoDB Etiquetas

- **Etiquetas de nivel de recurso**
  - Estos datos forman parte de los datos de facturación de « MongoDB » y no se requieren permisos adicionales en « Cloudability » para activarlos

Nota: Asignamos los campos de facturación « MongoDB » ( *ID* de grupo y *Nombre de grupo*) a claves de etiqueta denominadas `cldy:mongodb:groupid` y `cldy:mongodb:groupname`

Snowflake Etiquetas

Admitimos las etiquetas de « Snowflake » a nivel de almacén y de cuenta en el formato que se indica a continuación. Ten en cuenta que existen requisitos específicos para que se rellenen las etiquetas de almacén, entre los que se incluye habilitar la vista TAG\_REFERENCES en Snowflake. Para obtener más información, consulta la documentación sobre acreditación.

`cldy:snowflake:account:<tagkey>`

`cldy:snowflake:warehouse:<tagkey>`

Kubernetes ( K8s ) Etiquetas para envases

A diferencia de las etiquetas de asignación de costes típicas de los proveedores, las etiquetas de « Kubernetes » también son compatibles con la función «Asignación de etiquetas y marcas». Estas etiquetas son fundamentalmente diferentes de las etiquetas de coste, ya que no figuran en los datos de facturación, sino que son el resultado de la función « Cloudability » de Container Insights, que ofrece una asignación granular de los costes para el gasto en contenedores compatibles (EKS, GKE, AKS, OpenShift ).

Estas etiquetas estarán disponibles para su asignación una vez que hayas configurado un clúster compatible con el agente de IBM FinOps. Para obtener más información, consulte «Definir dimensiones adicionales basadas en las etiquetas de K8s » en la sección «[Asignación de costes de contenedor](../product/k8s-cost-allocation.html) ».

## Preguntas más frecuentes

¿Por qué faltan las etiquetas de nivel de recurso de « AWS » en la página «Asignación de etiquetas y rótulos»?

Antes de realizar la asignación, debes indicar a AWS qué etiquetas deben incluirse en las exportaciones de datos de costes. Puedes hacerlo en las «Preferencias de facturación» de AWS. Solo aparecerán en el CUR las claves de etiqueta seleccionadas.

¿Por qué aparece el valor «(no establecido)» en los informes?

Si has creado un informe en Cloudability con una columna de etiquetas, es probable que hayas visto un valor denominado **«(no establecido)** ».

Esto podría significar una de estas cosas:

- No has indicado al proveedor (como AWS ) que incluya todas tus etiquetas en tus datos de facturación
- Tienes recursos que se pueden etiquetar, pero que aún no están etiquetados
- Tienes un gasto que no se puede etiquetar
- No has solicitado que se vuelvan a procesar los datos históricos

¿Cómo puedo saber qué recursos se pueden etiquetar?

Cada proveedor tiene sus propias definiciones y restricciones sobre lo que entiende por «recurso etiquetable». Cloudability ofrece la función *«Tag Explorer»* para ayudarte a obtener una visión clara de tus principales gastos etiquetables y no etiquetables, lo que puede ayudarte a comprender en qué aspectos debes centrar tus esfuerzos de etiquetado.

En caso de duda, lo mejor es consultar la documentación específica del proveedor para saber si un tipo concreto de uso puede etiquetarse. Algunos ejemplos habituales de gastos que no se pueden clasificar son los costes de asistencia técnica, las comisiones de compromiso, los impuestos, las capturas de pantalla de « EBS » y algunos cargos de los mercados online.

¿Por qué no aparecen las etiquetas de mi grupo de recursos « Azure »?

Para rellenar las etiquetas a nivel de grupo de recursos y de suscripción para Azure, necesitamos permisos adicionales para obtenerlas de la API de Azure (lo que se conoce como «credenciales avanzadas» en Cloudability ). Consulte la parte anterior de este documento para comprobar los permisos necesarios.

¿Puedo asignar varias claves de etiqueta a una única dimensión de etiqueta en Cloudability utilizando una herramienta como expresiones regulares o comodines?

Actualmente, Cloudability no permite asignar varias claves de etiqueta a una sola dimensión mediante expresiones regulares o comodines.

¿Cómo gestiona « Cloudability » las claves de etiquetas múltiples?

Si un mismo recurso tiene varias claves de etiqueta, Cloudability seleccionará la primera clave de etiqueta válida (es decir, aquella que tenga un valor) que se haya añadido a la lista de claves de etiqueta de la dimensión en cuestión.

¿Cómo puedo extraer un valor de una etiqueta?

En Cloudability, hay varias formas de averiguar el valor de una etiqueta:

1. Cómo utilizar el Explorador de etiquetas: Ve a «Insights» > «Explorador de etiquetas» y, en la pestaña «*Gasto etiquetable* », aplica el filtro para la dimensión «Etiquetas y etiquetas». En el gráfico, puedes pasar el cursor por encima de las distintas etiquetas para ver sus valores.
2. Uso de informes: puedes generar un informe incluyendo una dimensión específica de *«Etiqueta (Valor)»* en el mismo. El resultado mostrará todos los diferentes valores de las etiquetas correspondientes a las distintas claves de las etiquetas.

¿Cuál es el límite de etiquetas que se pueden asignar en «Etiquetas y etiquetas»?

En Cloudability, el límite actual de dimensiones para las etiquetas y los rótulos es de 50.

¿Se pueden añadir más de 30 asignaciones de etiquetas y rótulos?

Cloudability ha aumentado en 20 el número de asignaciones disponibles de «Etiquetas y etiquetas» en Cloudability. Esto significa que los clientes ahora pueden disponer de hasta 50 dimensiones de informe en la plataforma específicas para las etiquetas y los rótulos asignados. Esto resultará especialmente útil para los clientes que utilizan un entorno multinube y cuentan con numerosas claves de etiquetas en su entorno. Cloudability Los administradores pueden añadir estas asignaciones adicionales en la función de asignación «Etiquetas y marcas».

Si cambia el valor de una etiqueta en los datos sin procesar de la CSP, ¿cómo aparecerá en Cloudability?

Supongamos que has cambiado la etiqueta en el lado de CSP de «playground» a «game». El valor anterior de la etiqueta ya se ha registrado en los datos de facturación anteriores, por lo que cualquier cambio en dicho valor no tendría carácter retroactivo. Por lo tanto, cualquier dato de facturación nuevo relacionado reflejará el nuevo valor de la etiqueta. Deberías aprovechar las correspondencias empresariales, que se pueden aplicar a los datos históricos.

No puedes actualizar las etiquetas históricas a menos que subas nuevos archivos de facturación correspondientes a meses anteriores con el nuevo valor de la etiqueta. Si quieres seguir adelante con esto, abre un caso de asistencia y Apptio El servicio de asistencia puede iniciar una nueva recuperación de datos para obtener los datos actualizados. **Ten en cuenta que**, cuando se vuelvan a recuperar los datos, todos los datos anteriores se sobrescribirán con los valores actuales. Así pues, en el caso de las etiquetas jerárquicas (a nivel de cuenta o suscripción), Cloudability tomará el valor **actual** de dichas etiquetas y lo aplicará a todos los datos recuperados.

¿Cómo procesará Cloudability las etiquetas si a un mismo recurso se le han asignado varias categorías de etiquetas, es decir, etiquetas de recurso, etiquetas de grupo de recursos y etiquetas a nivel de cuenta?

Si un cliente tiene tres recursos, a saber: el recurso A, el recurso B y el recurso C.

- El recurso A tiene una etiqueta de recurso llamada **«Owner»** cuyo valor es « **R1** »
- El recurso B tiene una etiqueta de recurso llamada **«Owner»** cuyo valor es « **R2** »
- El recurso C no tiene ninguna etiqueta asignada

Estos tres recursos pertenecen a un grupo de recursos denominado **«Resource X»,** que tiene una etiqueta de grupo de recursos llamada **«Owner»** con el valor « **RG1** »

**El recurso X** pertenece a una suscripción de Azure denominada **«Suscripción Z»,** que tiene una etiqueta de nivel de suscripción llamada **«Owner»** con el valor « **S1** »

En « Cloudability », el cliente crea una nueva dimensión de etiquetas denominada **«CLDY Owner»** y asigna las claves de etiqueta anteriores en el orden que se indica a continuación:

cldy:azure:resourcetag:owner | cldy:azure:subscriptionleveltag:owner | cldy:azure:resourcegrouptag:owner

El recurso A tiene las tres etiquetas (etiqueta de recurso, etiqueta de grupo de recursos y etiqueta de suscripción), pero, dado que la etiqueta de recurso es la primera de la secuencia según la dimensión creada anteriormente (CLDY Owner), se seleccionará en primer lugar la etiqueta de recurso para el recurso A, con la clave «Owner» y el valor « R1 », y se ignorarán la etiqueta de grupo de recursos y la etiqueta de suscripción. Lo mismo ocurrirá con el recurso B, en el que se recuperará la etiqueta del recurso con la clave «Owner» y el valor « R2 ». En cuanto al recurso C, no tiene ninguna etiqueta de recurso asociada, por lo que se comprobará cuál es el siguiente en la secuencia de la dimensión creada. Dado que la siguiente es una etiqueta de grupo de recursos, la etiqueta de grupo de recursos con la clave «Owner» y el valor « RG1 » se asignará al recurso C.

Ahora supongamos que el cliente ha creado la dimensión de etiquetas en un orden diferente, como se muestra a continuación, en el que las etiquetas de los grupos de recursos aparecen en primer lugar:

cldy:azure:resourcegrouptag:owner | cldy:azure:resourcetag:owner | cldy:azure:subscriptionleveltag:owner

En este caso, la etiqueta del grupo de recursos se asignará a los tres recursos, ya que todos ellos tienen etiquetas de grupo de recursos (clave de la etiqueta = «Owner» y valor = « RG1 »). Las etiquetas de recursos y las de suscripción se ignorarán en este caso, ya que las etiquetas de los grupos de recursos tienen prioridad en la secuencia y los tres recursos tienen asociadas etiquetas de grupos de recursos.

Del mismo modo, si la etiqueta de nivel de suscripción fuera la primera añadida en la secuencia, se asignaría a la dimensión de etiquetas la etiqueta de suscripción con la clave «Owner» y el valor « S1 », y se ignorarían las etiquetas de grupo de recursos y de recursos.

**Tema principal:** [Organiza tu gasto en la nube](../admin/tag-data.html)
