---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Recomendaciones para planificar la carga de trabajo"
breadcrumb:
  - "Cloudability Premium"
  - "Plan"
  - "Planificación de la carga de trabajo"
source_path: "product/get-recommendations-for-workload-planning.html"
images:
  - "images/3-dots.jpg"
  - "images/drop-down.jpg"
  - "images/edit-icon.jpg"
  - "images/modify-delete.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Recomendaciones para planificar la carga de trabajo

Workload Planning le ayuda a optimizar su arquitectura de cargas de trabajo y a mejorar la precisión de su planificación financiera en todos los proveedores de nube.

Puede:

1. Modele sus cargas de trabajo.
2. Obtenga una recomendación de recursos y una estimación de costes para un conjunto de tipos de servicio (máquina virtual, base de datos gestionada, almacenamiento de objetos y bloques, equilibrador de carga) en función de sus requisitos.
3. Obtenga presupuestos para un proveedor de nube o compare recursos entre proveedores de nube para elegir el destino de nube óptimo.

## Casos de uso para la planificación de la carga de trabajo

Estos son los principales casos de uso de los clientes que utilizan la función de planificación de cargas de trabajo de « Cloudability »:

1. **Estimación y comparación de costes previos a la implementación**
   - Comparación de proveedores de servicios en la nube: los clientes pueden calcular el coste de una carga de trabajo prevista en distintos proveedores de servicios en la nube ( AWS, Azure, GCP, OCI, etc.) para determinar la opción más rentable para sus necesidades específicas. Esto es fundamental para las estrategias multicloud.
   - Evaluación de regiones y tipos de recursos: Antes de la puesta en marcha, los usuarios pueden comparar las implicaciones económicas que supone implementar una carga de trabajo en distintas regiones y utilizar diferentes tipos de recursos (por ejemplo, distintas familias de « VM » u opciones de almacenamiento) para encontrar la configuración óptima.
   - Planificación de escenarios para nuevos proyectos: Los ingenieros y los responsables de producto pueden calcular rápidamente los costes de la infraestructura en la nube para nuevas aplicaciones, servicios o funcionalidades, lo que permite a los equipos financieros comprender el impacto en el presupuesto y tomar decisiones de inversión basadas en datos.
2. **Optimización de las cargas de trabajo existentes (ajuste de recursos y cambio de plataforma)**
   - Análisis de optimización: Al introducir los requisitos de carga de trabajo actuales, los clientes pueden ver recomendaciones sobre instancias o servicios más rentables que satisfacen las necesidades de rendimiento sin un aprovisionamiento excesivo. Esto ayuda a eliminar el desperdicio derivado de los recursos inactivos o infrautilizados.
   - Análisis de opciones de contratación (instancias reservadas, planes de ahorro, instancias spot): La planificación de cargas de trabajo ayuda a los clientes a comprender el ahorro de costes asociado a los diferentes modelos de contratación (bajo demanda, instancias reservadas, planes de ahorro, instancias spot) y les orienta a la hora de elegir la opción más adecuada para cargas de trabajo predecibles o interrumpibles.
   - Planificación de la migración: A la hora de planificar la migración de una aplicación desde un entorno local a la nube, o entre distintos proveedores de servicios en la nube, la herramienta «Workload Planning» permite simular los costes en el nuevo entorno, lo que garantiza una estrategia de migración financieramente sólida.
3. **Presupuestación y previsión colaborativas**
   - Comprensión común de los costes de la nube: La capacidad de guardar, compartir y comentar los planes de cargas de trabajo fomenta la colaboración entre los equipos de ingeniería, FinOps, y finanzas, lo que permite alcanzar una comprensión común de los próximos gastos en la nube.
   - Previsiones precisas: al utilizar la planificación de la carga de trabajo para estimar futuras implementaciones, los clientes pueden elaborar previsiones sobre la nube más precisas y fundamentadas, lo que reduce la desviación entre el gasto previsto y el real.
   - Responsabilidad y implicación: Cuando los equipos participan en el proceso de planificación y pueden ver las repercusiones económicas de sus decisiones arquitectónicas, se fomenta un mayor sentido de la responsabilidad respecto al gasto en la nube.
4. **Adquisición estratégica de recursos en la nube**
   - Decisiones de compra fundamentadas: la planificación de la carga de trabajo proporciona los datos necesarios para tomar decisiones acertadas sobre compromisos de compra, como las instancias reservadas o los planes de ahorro, garantizando que se ajusten a las necesidades reales de la carga de trabajo y maximicen los descuentos.
   - Identificación de oportunidades para reducir costes: Mediante la simulación de diversos escenarios, los clientes pueden identificar de forma proactiva oportunidades para consolidar recursos, aprovechar diferentes modelos de precios o realizar cambios en la arquitectura con el fin de reducir el gasto total en la nube.
5. **Cumplimiento normativo y gobernanza**
   - Estandarización de la asignación de recursos: la planificación de la carga de trabajo puede ayudar a establecer las mejores prácticas para la asignación de recursos, al ofrecer una vía clara y optimizada en términos de costes para las nuevas implementaciones, lo que contribuye a una mejor gobernanza de la nube.
   - Seguimiento y generación de informes sobre los costes previstos frente a los reales: Aunque no se trata de una función directa de generación de informes, los planes creados en «Workload Planning» sirven como referencia con la que se puede comparar el gasto real en la nube, lo que facilita la supervisión del rendimiento y la identificación de desviaciones.

En esencia, la función de planificación de cargas de trabajo de « Cloudability » permite a los clientes pasar de una gestión reactiva de los costes a una planificación financiera proactiva, lo que les permite tomar decisiones estratégicas que optimizan el gasto en la nube desde el principio.

## Antes de empezar

Actualice sus preferencias de Planificación de la carga de trabajo

Los administradores definen las opciones que aparecen en Planificación de la carga de trabajo. Visite [Preferencias de planificación de la carga de trabajo](workload-planning-preferences.html) para obtener más información.

Comprender los precios personalizados:

- Para AWS, Azure, y OCI, todos los precios en Workload Planning incluyen por defecto precios personalizados. No es necesaria ninguna configuración para estos proveedores.
- Para utilizar « GCP », debes habilitar la exportación de datos de precios personalizados desde tu cuenta de facturación de GCP. Para obtener más información, consulta [la guía «Configuración de la compatibilidad con precios personalizados para GCP](gcp-rightsizing-custom-pricing-support.html) ».

Establezca su moneda por defecto (clientes no estadounidenses):

- Establezca una moneda por defecto en Cloudability para que los precios se muestren con la moneda correcta.
- Cargue una tabla de tipos de cambio en Cloudability para mostrar el tipo de conversión correcto.

Revisar las cargas de trabajo existentes

Puede visualizar todas sus cargas de trabajo en la pestaña Lista. Seleccione una carga de trabajo para ver los detalles.

- Selecciona ![desplegable](../../../../03-media/cloudability-premium/images/drop-down.jpg) para modificar el estado de cualquier carga de trabajo.
- Selecciona ![3 puntos](../../../../03-media/cloudability-premium/images/3-dots.jpg) para ver el resto de opciones. Puede eliminar, duplicar o exportar una carga de trabajo, o guardarla como plantilla.

## Crear una carga de trabajo

Para crear una carga de trabajo:

1. Inicie sesión en Cloudability.
2. En el menú principal, seleccione Planificar > Planificación de la carga de trabajo.
3. Seleccione el botón Nueva carga de trabajo o la pestaña Constructor.
4. Registre la información común para su carga de trabajo.
5. Añade tus recursos.

   Nota: Solo puedes añadir 30 recursos por plan.
6. Visualice sus recomendaciones.
7. Revise el resumen de su recomendación.

## Registre la información común para su carga de trabajo

1. Introduzca un Nombre y una Descripción para su carga de trabajo.
2. Revise los proveedores de servicios permitidos. (Si no ve el proveedor de servicios que busca, pida a su administrador que lo añada en Preferencias de planificación de la carga de trabajo)
3. Para cualquier proveedor de servicios para el que desee recomendaciones, marque la casilla Incluir en el presupuesto.
4. En el menú desplegable Región preferida, seleccione la región en la que desea desplegar su carga de trabajo. Puede seleccionar hasta cinco regiones para cada proveedor de nube. También puede cambiar la región más adelante cuando añada recursos.
5. Seleccione su tipo de alquiler preferido. Su selección ayuda a elegir el tipo de arrendamiento y el tipo de precio correctos cuando llegue al paso de recomendación.

   Nota: El precio a la carta corresponde al precio personalizado a la carta, incluidos los precios personalizados.
6. Si procede, seleccione su Tipo de compromiso, Plazo de compromiso y Opción de pago.

   Nota: Estos campos solo se aplican al precio comprometido para los recursos de computación de AWS, Azure y GCP. No solicitan la OCI. Si posteriormente selecciona Precio a la carta o Precio al contado, estos campos dejarán de tener efecto.
7. Seleccione el botón Siguiente para añadir recursos.

Nota: El Precio Comprometido corresponde al precio de los Planes de Ahorro o Instancias Reservadas para los recursos de AWS Compute. Para Azure, corresponde a Precio de Instancias Reservadas o Plan de Ahorro. En el caso de « GCP », se corresponde con el precio de descuento por uso comprometido basado en recursos. El precio comprometido no se utiliza para el ICO.

Por defecto, el estado de la carga de trabajo es "En curso" (puede cambiar este estado más adelante en la pestaña Lista, después de crear la carga de trabajo).

## Añada sus recursos

Indique sus necesidades de recursos para la carga de trabajo. La planificación de la carga de trabajo utiliza los datos introducidos para buscar recursos con necesidades iguales o superiores a la cantidad solicitada.

Puede introducir los datos de los recursos manualmente o importarlos.

Para importar los datos de tus recursos:

1. Para añadir varios recursos a la vez, seleccione el botón Importar.

   Nota: La importación de recursos sobrescribe los recursos existentes.
2. En el menú desplegable, elija si desea importar un archivo JSON o un archivo Excel.
3. Se abre el cajón de Importación. Utilice los enlaces del cajón para descargar una plantilla con ejemplos de necesidades de recursos o una lista de los recursos existentes.

   Nota: En los archivos JSON, los nombres de todos los servicios deben estar presentes en el archivo. Si no hay necesidad de recursos o requisitos para un tipo de servicio determinado, introdúzcalo entre paréntesis vacíos. Por ejemplo, para el equilibrador de carga, el formato es "loadbalancer": [].
4. Seleccione el botón Siguiente.
5. Arrastre su archivo a la zona de carga o utilice el enlace Buscar un archivo para buscarlo.
6. Seleccione el botón Siguiente.
7. Planificación de la carga de trabajo muestra un resumen de su expediente. Seleccione el botón Hecho cuando esté listo para continuar.

También puede añadir recursos manualmente. Para ello:

1. En el paso de flujo de trabajo Añadir recursos, seleccione el botón Añadir recurso.
2. Seleccione el Tipo de Servicio y proporcione un Nombre de Recurso.

   Nota: El tipo de servicio "Base de datos gestionada" no está disponible para OCI.
3. Si ha seleccionado Tipo de servicio Máquina virtual, Base de datos gestionada, Object Storage o Almacenamiento adicional :
   - Introduzca requisitos genéricos si no está buscando un tipo de recurso específico, O
   - Active el conmutador Buscar tipo de recurso para seleccionar el recurso deseado. Si Planificación de la carga de trabajo encuentra recursos más baratos con requisitos similares, los recomendará en primer lugar. Para la comparación entre varias nubes, Workload Planning utiliza los requisitos asociados al recurso seleccionado para generar recomendaciones para otros proveedores de nubes. Esta opción también le permite seleccionar hasta cinco regiones diferentes para su recurso.
4. Introduzca todos sus requisitos personalizados.
5. Una vez introducidos todos los requisitos, seleccione el botón Añadir. Se muestran las necesidades de recursos. Para modificarlos o eliminarlos, selecciona ![icono desplegable](../../../../03-media/cloudability-premium/images/drop-down.jpg)y, a continuación, elige ![Borrar símbolo](../../../../03-media/cloudability-premium/images/modify-delete.jpg).
6. Seleccione el botón Siguiente.

## Visualice sus recomendaciones

Una vez que se desplaza al paso del flujo de trabajo Recomendación, aparece una ventana emergente para mostrar que la herramienta está generando la recomendación. Mientras se genera, puede ir a la pestaña Lista para definir una nueva carga de trabajo. Cloudability seguirá generando la recomendación entre bastidores.

Una vez que Cloudability haya terminado de generar la recomendación, se cerrará la ventana emergente y pasará al paso de flujo de trabajo Recomendación.

Para realizar una comparación entre distintas plataformas en la nube, selecciona una opción en el menú desplegable «Servicio» para ver las recomendaciones correspondientes a cada tipo de servicio ( AWS, Azure, GCP y OCI).

Puede seleccionar cualquier tipo de precio. Los precios a la carta, comprometidos y al contado se calculan como precio mensual por unidad. El precio comprometido se calcula a partir de los datos que aparecen en el paso [Información común](#common).

Para visualizar el coste total de su carga de trabajo y comparar los costes entre los proveedores de nube uno al lado del otro, seleccione el botón Siguiente.

Para obtener una recomendación diferente:

- Selecciona el ![Editar icono](../../../../03-media/cloudability-premium/images/edit-icon.jpg) icono para actualizar tus requisitos; O BIEN
- Seleccione el botón Atrás para ir al paso anterior. Esta opción le permite modificar muchos requisitos a la vez.

## Revise el resumen de su recomendación

En el paso de flujo de trabajo Resumen, Cloudability muestra sus recomendaciones en dos pestañas: Resumen y Análisis.

Explorar la pestaña Resumen

La pestaña Resumen muestra un resumen de la información asociada a su carga de trabajo. Para las comparaciones entre nubes, seleccione el proveedor Elegido. Cloudability actualiza tu Coste Total (mensual) en consecuencia.

Mientras observa los recursos añadidos a su carga de trabajo, seleccione Detalles para ver información adicional.

Explorar la pestaña Análisis

La pestaña Análisis visualiza el desglose de costes por tipo de servicio y proveedor de servicios en caso de comparación entre nubes.

Comparta su resumen

Selecciona ![icono de tres puntos](../../../../03-media/cloudability-premium/images/3-dots.jpg) una de las pestañas «Resumen» o «Análisis» para exportar el resumen de la carga de trabajo como un archivo « CSV », duplicar la carga de trabajo o compartirla con otras personas.

Siempre puede volver a los pasos anteriores desde las pestañas Resumen o Análisis para realizar cualquier cambio. Una vez que haya terminado de definir su carga de trabajo, seleccione el botón Hecho. Cloudability vuelve a la pantalla Lista.

## **Preguntas más frecuentes**

1. ¿Por qué debería seleccionar el proveedor de **servicios** en la nube y las preferencias de compra en «Información general > Proveedores de servicios»?

   Elige el proveedor **de** servicios en la nube y los tipos de contrato de alquiler y de compromiso que prefieras en «Información general > Proveedores de servicios», de modo que recibas recomendaciones más precisas basadas en las preferencias que establezcas aquí.
2. ¿Cuántas regiones puedo seleccionar en **«Información general» > «Proveedores de servicios»**? ¿Por qué debería seleccionarlos aquí?

   Puedes seleccionar hasta 5 regiones por cada proveedor de servicios en la nube; en función de ello, recibirás recomendaciones sobre los precios en cada una de esas regiones
3. ¿Por qué no puedo ver el tipo de contrato de alquiler o el tipo de compromiso que busco en **«Información general» > «Proveedores de servicios»**?

   Esto podría deberse a que el administrador haya desactivado esos tipos de arrendamiento o tipos de compromiso en la sección «Preferencias» de Work.Planning.
4. ¿Por qué aparece este mensaje al editar una carga de trabajo existente? *Esta carga de trabajo no cumple con las preferencias de planificación de cargas de trabajo. Los tipos de contrato y/o las preferencias de compromiso establecidos por tu administrador no se ajustan a tu carga de trabajo. Puedes hacer clic en «Editar carga de trabajo» para actualizarlas.*

   Esto podría deberse a que algunos de los conceptos definidos en tu carga de trabajo (por ejemplo: proveedor de servicios en la nube, tipo de contrato de arrendamiento, tipo de compromiso, etc.) Han sido actualizados por tu administrador desde la sección «Preferencias» de Work.Planning
5. ¿Cómo recomienda la función recursos si no selecciono el tipo de recurso exacto (utilizando la opción de búsqueda por tipo de recurso) al añadir un nuevo recurso?

   Si no has seleccionado el tipo de recurso concreto (utiliza la opción de búsqueda por tipo de recurso) al añadir un nuevo recurso, la función te recomendará los 30 recursos más rentables de cada uno de los proveedores de nube seleccionados, en función de la configuración del recurso que hayas introducido.
6. ¿Cómo recomienda la función recursos si elijo el tipo de recurso exacto (utilizando la opción de búsqueda por tipo de recurso) al añadir un nuevo recurso?

   Si has seleccionado el tipo de recurso exacto (utiliza la opción de búsqueda por tipo de recurso) al añadir un nuevo recurso, la función fijará ese recurso específico en la parte superior como primera recomendación, seguido de 29 recursos rentables de cada uno de los proveedores de nube seleccionados, en función de la configuración del recurso que hayas introducido.
7. ¿Qué debo hacer para que las recomendaciones de recursos tengan en cuenta mis EDP u otros precios personalizados?

   No es necesario que hagas nada para que las recomendaciones de recursos tengan en cuenta tus EDP u otros precios personalizados. Cloudability Ya recupera tu información de precios personalizada, si existe, y los descuentos se incorporarían de forma predeterminada a las recomendaciones de «Planificación de la carga de trabajo».
8. ¿Tengo que configurar los precios personalizados de mi organización en el campo «Descuento adicional / % de recargo» de la sección «Preferencias» de Work.Planning?

   Núm. Cloudability Ya recupera tu información de precios personalizada, si existe, y tus descuentos se tendrían en cuenta de forma predeterminada en las recomendaciones de planificación de la carga de trabajo.

   El «% de descuento adicional/reajuste al alza» corresponde a cualquier otro descuento que se aplique a los costes de todos los recursos recomendados, excluidos los «Otros costes». Una vez configurado, este descuento o recargo se añadiría a cualquier precio personalizado ya mostrado en Cloudability
9. ¿Por qué observo una diferencia entre los precios que aparecen en las recomendaciones de planificación de la carga de trabajo y los de la calculadora de precios del proveedor de servicios en la nube?

   Si observas alguna diferencia entre los precios que aparecen en las recomendaciones de «Workload Planning» y los de la calculadora de precios del proveedor de servicios en la nube:

   - Comprueba si el tipo de recurso, la región y otras configuraciones coinciden exactamente entre la calculadora de precios y Workload Planning
   - Comprueba si tienes activada la función «Multidivisa» en Cloudability y, en caso afirmativo, verifica si el tipo de cambio que habías establecido para tu moneda preferida en el módulo «Multidivisa» coincide con el tipo de cambio que aplica el proveedor de servicios en la nube
   - Comprueba si has iniciado sesión en la calculadora de precios del proveedor de servicios en la nube utilizando la cuenta de tu organización que tiene habilitada la tarificación personalizada. Si estás consultando los precios sin iniciar sesión en la calculadora de precios del proveedor de servicios en la nube, es probable que veas los precios de venta al público en la calculadora y los precios personalizados en «Workload Planning»
   - Comprueba si tu administrador ha configurado algún descuento adicional que se aplique a los costes de todos los recursos recomendados en la sección **Preferencias de Work.Planning**
10. Para la importación masiva de recursos, ¿cuál es el número máximo de recursos que puedo añadir para un servicio concreto?

    Puedes añadir hasta 30 recursos en tu archivo « CSV » al realizar una importación masiva
11. ¿Cómo se define el tipo de recurso en el archivo « CSV » al realizar una importación masiva?

    Verás que la información sobre la CPU y la RAM también aparece en la interfaz de usuario de planificación de la carga de trabajo. Al realizar una importación masiva, omite la información sobre la CPU y la RAM y utiliza únicamente la primera parte del nombre del tipo de recurso. Por ejemplo, para el tipo de recurso que aparece como « D2s\_v6 - 2 CPU/s, 8 RAM» en la interfaz de usuario de planificación de cargas de trabajo, utiliza « D2s\_v6 » como nombre del tipo de recurso en el archivo de importación de CSV. Como alternativa, también puedes descargar todos los tipos de recursos compatibles desde la sección «Buscar tipo de recurso», dentro de «Añadir recurso», y utilizar directamente esos nombres de tipos de recursos en tu archivo de importación masiva CSV.
12. ¿Tengo que definir la información sobre la CPU y la RAM en la importación masiva CSV si estoy definiendo un tipo de recurso?

    Núm. Si estás definiendo un tipo de recurso específico, puedes dejar todos los demás campos de configuración del recurso tal y como están, ya que se rellenarán automáticamente según el tipo de recurso definido. Aunque introduzcas tus propios datos de configuración de recursos, estos quedarían sustituidos por los datos de configuración definidos por el proveedor de servicios en la nube
13. ¿Cómo puedo editar una carga de trabajo creada por otro usuario?

    El autor de la carga de trabajo debe compartirla con permisos de edición para que puedas editar la carga de trabajo de otro usuario. Esto se aplica incluso si eres un usuario administrador: si eres administrador, puedes ver todas las cargas de trabajo creadas en tu organización, pero solo puedes editar la carga de trabajo de otro usuario si este la ha compartido contigo con acceso de edición.
