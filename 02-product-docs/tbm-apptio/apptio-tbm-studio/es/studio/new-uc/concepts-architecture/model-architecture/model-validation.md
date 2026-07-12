---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Validación y seguimiento de modelos"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura del modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/model-validation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Validación y seguimiento de modelos

Una vez que el modelo esté configurado y se haya calculado, el siguiente paso fundamental es verificar que los costes se distribuyan correctamente y que los resultados de la asignación sean razonables y auditables.

## Validación de modelo

La validación es el proceso de comprobar que tu modelo produce resultados precisos, completos y equilibrados. Hay tres tipos de comprobaciones de validación que hay que realizar.

**Comprobaciones de saldo**

La comprobación más básica: ¿coinciden los totales de origen con los totales de destino? Si has empezado con 5 millones de dólares en «Cost Source», la suma de todos los objetos de destino finales también debería ser de 5 millones de dólares (menos cualquier importe no asignado intencionadamente).

- **Qué hay que comprobar:** la suma de los valores del objeto de origen debe ser igual a la suma de los valores finales del objeto de destino más cualquier importe no asignado
- **Si no cuadran:** comprueba si hay sobreasignaciones (el tipo «Valor estándar» puede sobreasignar), fórmulas mal configuradas o problemas de calidad de los datos

**Comprobaciones de integridad**

Comprueba que todos los datos previstos hayan pasado por el modelo. Esto implica comprobar que se hayan procesado todas las filas de origen, que todos los objetos del modelo hayan recibido datos de entrada y que no se haya omitido ninguna asignación de memoria de forma silenciosa debido a problemas de configuración.

- Revisa los importes de los costes no asignados en cada nivel (no solo en el primero)
- Comprueba que los objetos intermedios tengan valores distintos de cero
- Comprueba que todos los periodos previstos aparezcan en los resultados

**Comprobaciones de plausibilidad**

Incluso cuando un modelo está equilibrado y completo, es posible que los resultados no sean razonables. Compara los resultados actuales con los de periodos anteriores, los presupuestos o los puntos de referencia externos para detectar anomalías.

- ¿Ha variado el gasto de alguna unidad de negocio en más de un 20 % respecto al mes anterior sin que se conozca la causa?
- ¿Se encuentran los costes unitarios (coste por servidor, coste por aplicación) dentro de los rangos previstos?
- ¿Se ajustan las proporciones relativas entre las unidades de negocio a las expectativas?

## Seguimiento de costes

El seguimiento de costes es la capacidad de rastrear un coste específico desde su origen hasta su destino final (seguimiento hacia adelante) o desde una cifra final hasta sus orígenes (seguimiento hacia atrás). Esto es fundamental para las auditorías, las consultas de las partes interesadas y la resolución de problemas.

**Seguimiento hacia atrás: ¿adónde se ha ido este gasto?**

Partiendo de una fuente conocida (por ejemplo, una factura concreta de un proveedor), siga su recorrido a través del modelo para ver qué unidades de negocio recibieron finalmente parte de ese coste. Tanto la vista de diagrama de TBM Studio como el Modelador de objetos individuales permiten navegar hacia adelante a lo largo de la cadena de asignación.

**Análisis retrospectivo: ¿De dónde proviene este coste?**

Partiendo de una cifra final de un informe (por ejemplo, la asignación de « $1.8M » del departamento de Ingeniería), hay que remontarse a lo largo del modelo para comprender qué costes de origen han contribuido a ella. Esta es la pregunta que más suelen hacer las partes interesadas: «¿Por qué los gastos de TI de mi departamento se presentan así?»

Nota:

**Identificación de las mejores prácticas**

Documenta la lógica de asignación de tu modelo en un lenguaje sencillo, junto con la configuración técnica. Cuando un director financiero pregunta: «¿Por qué han subido mis costes?», Tener preparada una explicación narrativa («Tu departamento añadió 15 servidores en marzo, lo que ha aumentado tu participación en los costes del centro de datos») es mucho más eficaz que explicarles el modelo técnico paso a paso.

## Informes de modelos (diagramas de Sankey)

TBM Studio ofrece informes de modelos que utilizan visualizaciones de tipo Sankey para mostrar los flujos de costes de una forma intuitiva y visual. Estos informes se diferencian de los informes estándar de Report Studio y están diseñados específicamente para la validación de modelos y la comunicación con las partes interesadas.

**Características del diagrama de Sankey:**

- Muestra los costes que se distribuyen a través de los niveles definidos (por ejemplo, Finanzas → Centros de coste → Infraestructura → Servicios)
- El grosor de la línea es proporcional al valor del coste, lo que permite visualizar de inmediato los grandes flujos
- Haz clic en cualquier línea del flujo para acceder a los detalles a nivel de transacción subyacentes
- Alternar entre la visualización de Sankey y la vista de datos en forma de tabla
- Admite varias columnas por capa para un análisis detallado

**Cuándo utilizar los informes modelo:**

- **Validación:** Comprueba que los costes se distribuyen según lo previsto en cada nivel
- **Comunicación:** Mostrar a las partes interesadas cómo se calculan sus costes mediante un formato visual intuitivo
- **Auditoría:** Analizar en profundidad líneas de flujo específicas para rastrear partidas de costes individuales
- **Incorporación:** Ayudar a los nuevos miembros del equipo a comprender rápidamente la estructura del modelo
