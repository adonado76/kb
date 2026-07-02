---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Revisar la calidad de los datos"
breadcrumb: []
source_path: "boit/review-data-quality.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Revisar la calidad de los datos

Los datos de calidad son importantes cuando se envía a las unidades de negocio un resumen de los servicios que han utilizado. Billing Standard incluye una serie de informes sobre la calidad de los datos que debes revisar periódicamente para asegurarte de que son correctos.

Para acceder a los informes de Calidad de Datos de Facturación:

1. En el menú **Aplicación**, haga clic en **Billing Standard** (véase el [menú Billing Standard](getting_started/boit-menu.html)  ).
2. En el menú **Recopilación de informes**, haga clic en **Calidad de los datos de facturación**.
3. En la barra de la parte superior de la página, seleccione un informe de la colección. Las opciones de informe incluyen:
   - Informe de resumen de configuración
   - Informe sobre la actualidad de los datos
   - Informes sobre la calidad de los datos
     - Informe sobre la calidad de los piensos
     - Informe sobre la calidad del servicio de biblioteca
     - Modelo de informe de calidad

**Informe de resumen de configuración**

El informe **Resumen de configuración** incluye métricas clave para la calidad de los datos.

**Informe sobre la actualidad de los datos**

El informe de actualización de datos muestra información sobre las tablas de datos que se han cargado en.

Las reglas de actualización de datos se definen al cargar por primera vez una tabla en la aplicación. Puede elegir entre varias opciones. Las reglas de actualización de datos se utilizan para determinar si los datos se han actualizado en el plazo especificado. No programan ni realizan cargas de datos. Para ver una descripción de las opciones, consulte "Ciclos de actualización de datos" en [Cargar un archivo de datos](../studio/data_studio/upload-data-file.html "Se aplica a: TBM Studio 12.0 y posteriores. TBM Studio acepta datos de archivos planos en formatos separados por comas, tabulaciones, tuberías, tildes, dos puntos y punto y coma. Antes de poder cargar datos, debe crear una tabla en la que se cargarán los datos, si no existe ya.").

**Informes sobre la calidad de los datos**

Los informes de calidad de los datos (Calidad de la alimentación de consumo, Calidad de la biblioteca de servicios y Calidad del modelo) muestran información sobre la calidad de los datos de la aplicación.

Aunque la calidad de los datos puede variar, el objetivo debe ser que se ajusten a las siguientes directrices.

- **Consumo Calidad de los piensos** :
  - El recuento de filas debería estar dentro del rango esperado. Cualquier cambio significativo debe ser explicable.
  - La unidad de medida debe coincidir con el servicio.
- **Actualidad de los datos** - Los datos deberían haberse actualizado en función de las cargas programadas.
- **Calidad del modelo** - El cambio en la factura más grande debe ser relativamente pequeño y los gastos no asignados deben estar dentro de límites aceptables basados en las asignaciones definidas en el modelo.
- **Distribución** - Deben definirse los destinatarios adecuados de las facturas.

**Consumo Informe sobre la calidad de los piensos**

El informe Calidad de la alimentación de consumo muestra información sobre el recuento de registros, las unidades de medida y los campos publicados para cada tabla de datos clave de la aplicación.

**Informe sobre la calidad del servicio de biblioteca**

El informe Calidad de la biblioteca de servicios muestra información detallada de relaciones y registros sobre las entradas de la biblioteca de servicios.

**Validar relaciones de ID de servicio**

Utilice la sección superior del informe para comprobar que las relaciones son válidas. Utilice la pestaña **ID de** servicio para comprobar que cada ID de servicio es único.

**Asegúrese de que los nombres de los servicios son únicos**

Utilice la pestaña **Nombre de** servicio para comprobar que cada combinación de Nombre de servicio/Oferta de servicio es única.

Si hay duplicados, el número de duplicados se mostrará en la columna **Recuento total de errores**.

**Comprobar los datos del registro**

Utilice la sección inferior del informe para comprobar si hay valores en blanco en las entradas de la biblioteca de servicios. Puede filtrar la tabla por campos obligatorios y campos opcionales.

**Modelo de informe de calidad**

El informe Calidad del modelo muestra información sobre las asignaciones del modelo en las secciones **Descripción general de la asignación/Detalles de la asignación** y **Asignaciones configuradas**, así como la desviación intermensual de las ofertas de servicio en la sección **Desviación**. Puede filtrar el informe para cada una de las métricas del modelo: Cargo, Unidades facturables, Coste, Presupuesto, Previsión, Presupuesto empresarial, Previsión empresarial y Unidades facturables previstas. El contenido del informe variará en función de la métrica que seleccione.

**Revisar los detalles de la asignación**

En qué fijarse:

- Las asignaciones deben ser relativamente constantes a lo largo del tiempo.
- Determine la causa de cualquier variación significativa en la asignación consultando la tabla Asignación por objeto y profundizando en los Detalles de asignación de un objeto.

**Revisión de la varianza**

En qué fijarse:

- Las variaciones deben ser coherentes y estar dentro de un margen aceptable.
- Investigue los valores atípicos.
