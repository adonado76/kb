---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Facturación Componentes estándar"
breadcrumb: []
source_path: "boit/boit-components.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Facturación Componentes estándar

A continuación se describen los componentes de Billing Standard . Billing Standard - Foundation es el único componente necesario e instala la mayoría de los conjuntos de datos, modelos y dimensiones.

- **Billing Standard - Fundación** (obligatorio) - El componente Fundación es necesario para Billing Standard . Proporciona informes basados en los cargos, incluida una factura que puede enviarse a los usuarios. Todos los modelos y tablas necesarios se instalan también con el componente Foundation.
- **Billing Standard - Aplicaciones** (opcional) - El componente Aplicación agrega nuevos informes centrados en los informes de aplicaciones. El componente añade dos nuevos informes:
  - El informe de **Cargos de Aplicación** proporciona a la Unidad de Negocio y al Gestor de Relaciones de Negocio vistas de los cargos de aplicación y las licencias (unidades) utilizadas.
  - El informe de **recuperación de aplicaciones** proporciona a TI una vista de los datos de recuperación por exceso/defecto por aplicación, donde los cargos por la aplicación se comparan con el coste de TI de la aplicación.
- **Billing Standard - Nube** (opcional) - El componente Nube agrega nuevos informes enfocados en informes IaaS en la nube. El componente añade dos nuevos informes y simulacros:
  - El informe **Cloud Charges** puede ser utilizado por la Unidad de Negocio y el Business Relationship Manager para entender los cargos por servicios en la nube. Incluye una lista detallada de los servicios en la nube utilizados por la unidad de negocio.
  - El informe **Recuperación en la nube** proporciona datos de recuperación por exceso/defecto por servicio. Las tarifas del servicio se comparan con el coste de prestación del servicio.
- **Billing Standard - Variación de costos** (opcional): el componente Variación de costos admite la comparación de los cargos con el costo real de brindar los servicios. El componente Desviación de costes incluye muchos informes que sólo puede ver el personal con funciones de Propietario de servicio o Gestor de relaciones comerciales.
- **Billing Standard - Variación del plan** (opcional): el componente Variación del plan agrega la capacidad de comparar cargos con el presupuesto y comparar costos con un presupuesto. El componente habilita nuevos informes para el análisis de desviaciones presupuestarias y de previsiones y expone comparaciones con el presupuesto y las previsiones en los informes existentes.
- **Billing Standard - Precio** (opcional) - El componente Precio permite exponer un precio a los usuarios finales. Los precios se fijan en la Biblioteca de Servicios. Cualquier ajuste o combinación de precios aplicados a un servicio puede hacer que el precio efectivo difiera del precio indicado en la Biblioteca de servicios.
- **Billing Standard - Proyectos** (opcional) - El componente Proyectos agrega nuevos informes centrados en los informes de proyectos. El componente añade dos nuevos informes con ejercicios de apoyo:
  - El informe de **gastos del proyecto** puede ser utilizado por la unidad de negocio y el gestor de relaciones comerciales para ver los gastos del proyecto y los servicios de apoyo que ha utilizado la unidad de negocio.
  - El informe de **recuperación de proyectos** proporciona datos de recuperación por exceso/defecto de TI por proyecto, desviación presupuestaria y estado.
- **Billing Standard - Servidores** (opcional) - El componente **Servidores** proporciona al proveedor de servicios de TI y al consumidor empresarial información sobre la composición de los servicios ofrecidos y consumidos. Billing Standard - Los servidores se pueden configurar para acomodar una vista de los costos y el consumo del servidor basada tanto en aplicaciones como en servicios.
- **Billing Standard - Unidades** (opcional) - El componente **Unidades** agrega unidades a todos los informes existentes y calcula un precio efectivo dividiendo el cargo por las unidades facturables. Se puede definir un tipo de unidad por Oferta de Servicio. Cuando también se instala la Desviación de costes, se pueden comparar las tarifas unitarias.

**Instale los componentes de Billing Standard**

Billing Standard no se instalan automáticamente al crear un proyecto Billing Standard . Debe instalar cada componente por separado. Sólo se requiere el componente Billing Standard - Foundation.

Para instalar los componentes:

1. En TBM Studio, haga clic en la pestaña **Proyecto**.
2. Haga clic en **Componentes**.
3. Haga clic en el componente **Billing Standard Foundation**.
4. Haga clic en **Instalar**.
5. Repita los pasos anteriores para cada uno de los componentes opcionales de Billing Standard que desee instalar.
