---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Lista de solicitudes"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso del informe"
  - "Recopilación de solicitudes"
source_path: "cost-transparency/reports/application-list.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Lista de solicitudes

Este informe está destinado a los propietarios de aplicaciones. Se trata de un informe analítico que proporciona un acceso rápido a los detalles completos sobre cualquiera de las aplicaciones de la organización.

Este informe está destinado a:

- Liderazgo en TI
- Propietarios de aplicaciones
- Analistas comerciales
- Arquitectos de empresa
- Gestores de cartera

Este informe permite a los propietarios de aplicaciones profundizar en los detalles de las aplicaciones de las que son responsables. Puede establecer un slicer global para un propietario de aplicación específico o una familia de aplicaciones. Por ejemplo, es posible que desee establecer el slicer global Propietario de la aplicación para filtrar su propio nombre para que pueda ver sus aplicaciones cada vez que se conecte.

Puede añadir y eliminar columnas de forma dinámica mediante el panel Seleccionar columnas adicionales para obtener una mejor visión de los detalles de las aplicaciones de las que es responsable. Por ejemplo, después de establecer el filtro Propietario de la aplicación en su propio nombre, puede optar por eliminar la columna Propietario de la aplicación de la tabla, ya que no necesita ver su nombre como propietario en cada fila.

Otro caso de uso es analizar rápidamente los datos sobre las aplicaciones que se están eliminando. Por ejemplo, puede establecer el corte por objetivo en Eliminar y, a continuación, buscar cifras elevadas de App Dev. Esto podría llevarle a preguntarse por qué continúa el desarrollo de una aplicación que va a quedar obsoleta. Además, es de esperar que los costes asociados a las aplicaciones que se eliminan sean nulos. Puede utilizar estos datos para confirmar y limpiar el uso de su aplicación.

Otro caso de uso podría ser el filtrado de datos históricos en un esfuerzo por encontrar nuevas formas de almacenar aplicaciones no utilizadas fuera de línea sin consumir infraestructura. Para más información sobre las cortadoras, véase la explicación del elemento 2, más abajo.

El informe Lista de solicitudes contiene los siguientes elementos:

![imagen](../../resources/images/ct_images/ct%20report%20collections/application%20list.jpg)

| Elemento clave | Descripción |
| --- | --- |
| (1) Recogida de informes | Esta colección de informes proporciona los detalles que necesita para revisar el gasto, las tendencias y el uso de sus aplicaciones:  - [Informe de revisión de la solicitud](application_review.html) (abierto por defecto) - [Informe sobre la cartera de aplicaciones](application_portfolio.html) - Lista de solicitudes (descrita en esta página - [Informe de análisis de infraestructuras por aplicaciones](infrastructure_analysis_by.html) - [Informe sobre aplicaciones nuevas y retiradas](new_retired_apps.html) |
| (2) Cortadoras | Este informe dispone de los siguientes filtros globales:   - Tipo de aplicación: - COTS: Aplicaciones de consumo empaquetadas - Personalizadas: Aplicaciones propias, creadas internamente - SaaS: Aplicaciones web a la carta - Propietario de TI de la aplicación: al igual que el propietario de un grupo de costes, el propietario de una aplicación es la persona responsable de comprender y entregar una aplicación. - Familia de aplicaciones: Las familias son grupos de aplicaciones relacionadas, definidas por su organización.  Las siguientes funciones podrían utilizar los divisores de este informe para obtener una vista más personalizada:  - Application Portfolio Manager o CIO: Sin necesidad de configurar ningún rebanador, puede ver una visión general del gasto en aplicaciones en toda la organización. Utilice los divisores para acotar lo que ve en todos los informes de Aplicaciones. Puede seleccionar un nombre del rebanador Propietario de TI de aplicaciones para conocer las responsabilidades de esa persona en relación con las aplicaciones. Puede seleccionar un grupo de aplicaciones de la Familia de aplicaciones para comprender el rendimiento global de ese grupo. - Propietario de la aplicación: seleccione su nombre para limitar las aplicaciones a aquellas de las que es responsable y para ver el rendimiento de esas aplicaciones a alto nivel. - Analista financiero: Establezca los divisores para las áreas a las que presta asistencia a fin de permitir un análisis de gastos detallado e interorganizativo.   Nota: Recuerde que los filtros que establezca en otros informes de Solicitud pueden afectar a lo que vea en el informe de Revisión de solicitudes. Por ejemplo, es posible establecer un filtro en el informe Lista de solicitudes que impida o limite accidentalmente las solicitudes que puede ver en el informe Revisión de solicitudes. |
| (3) Datos de la solicitud | Utilice esta tabla para ver detalles específicos sobre todas sus aplicaciones. La tabla enumera los propietarios empresariales y de TI de cada aplicación, el gasto en ejecución y desarrollo de la aplicación, el recuento de servidores, el espacio de almacenamiento, el gasto por usuario y mucho más. Seleccione cualquier elemento de la columna Nombre de la aplicación para abrir el [informe detallado de Aplicaciones](https://tbmcouncil.jiveon.com/docs/DOC-9217 "(se abre en una pestaña o una ventana nueva)") a página completa, que proporciona todos los datos estándar del sistema para la aplicación específica en la que ha hecho clic.  La tabla Detalles de la aplicación incluye las siguientes rebanadoras adicionales, que son específicas de este informe. Estas rebanadoras no persisten en otros informes de la colección de informes Aplicación:   - Clasificación por objetivos: Este rebanador le permite filtrar según los objetivos de inversión que puede asignar a aplicaciones individuales. También puede ver estos objetivos para las aplicaciones con los gastos más altos en la pestaña Gastos de aplicaciones del informe Revisión de aplicaciones. - Tolerar: Son aplicaciones que quieres mantener en cartera durante mucho tiempo. Los necesitas, pero no necesariamente quieres invertir en ellos. En el mejor de los casos, estas aplicaciones no tendrán mucho desarrollo continuado, como demuestran las bajas cifras de la columna App Dev. - Invertir: Se trata de aplicaciones que la empresa desea mejorar o cambiar. Como resultado, se espera ver cifras más altas en la columna App Dev para estas aplicaciones.   Si ve cifras bajas de solicitudes marcadas como Invertir, debe cuestionarse si se ha iniciado el desarrollo.   - Migrar: Son aplicaciones que se están migrando. Es de esperar que el desarrollo continuado de estas aplicaciones sea escaso o nulo (como demuestra la columna App Dev). - Eliminar: Estas aplicaciones deben eliminarse. Es de esperar que en la columna App Dev aparezcan cifras bajas para estas aplicaciones. Si ve cifras elevadas en la columna App Dev para aplicaciones que se están migrando o eliminando, querrá cuestionarlo, porque el desarrollo continuado de esas aplicaciones iría en contra de su objetivo para su cartera de aplicaciones. - Clasificación por criticidad: Este rebanador permite filtrar según el nivel de necesidad empresarial. - Esenciales para la empresa: Sin estas aplicaciones, la empresa sufriría pérdidas o sanciones económicas, legales o de otro tipo. La pérdida de estas aplicaciones tendría graves consecuencias para la empresa. - Histórico: Estas aplicaciones ya no se utilizan. - Misión crítica: sin estas aplicaciones, la empresa sufriría graves pérdidas o sanciones, ya sea financieras, legales o de otro tipo. La pérdida de estas aplicaciones perturbaría por completo el negocio. - Productividad del usuario: Estas aplicaciones ayudan a la organización a lograr los resultados finales deseados, reducen los fallos, mejoran el rendimiento laboral y simplifican la gestión de datos. La pérdida de estas aplicaciones tendría un efecto de bajo a moderado en la empresa. - Clasificación por categorías: Este rebanador permite filtrar según el tipo de aplicación. |
| (4) Seleccionar columnas adicionales | Controle la visibilidad de las columnas de la tabla Detalles de las aplicaciones seleccionando y deseleccionando los nombres de las columnas que aparecen en el panel Seleccionar columnas adicionales. |

Preguntas contestadas

- Puede utilizar este informe para responder a las siguientes preguntas:
- ¿Quiénes son nuestros proveedores en SaaS y cuánto gastamos con cada uno?
- ¿Cuál es nuestro gasto total por usuario y aplicación?
- ¿Cuál es el total de aplicaciones ejecutadas y desarrolladas por aplicación?
