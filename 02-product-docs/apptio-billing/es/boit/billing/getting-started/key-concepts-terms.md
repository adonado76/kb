---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Glosario y acrónimos"
breadcrumb:
  - "Billing"
  - "cómo empezar"
source_path: "boit/billing/getting-started/key-concepts-terms.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Glosario y acrónimos

Este apéndice define los términos y acrónimos comunes utilizados en toda la Ayuda de facturación. Úselo como referencia rápida cuando lea otras secciones o trabaje con el producto.

## Cómo utilizar este apéndice

- Los términos se agrupan por tema:
  - Conceptos fundamentales
  - Datos y modelización
  - Informes y procesos
  - Acrónimos
- Los términos específicos de la edición están etiquetados:
  - «Solo lo esencial de facturación»
  - «Solo norma de facturación»

## Conceptos básicos de facturación

**Facturación**

El conjunto de modelos, tablas e informes que calculan, presentan y, opcionalmente, registran los cargos tecnológicos a los consumidores. Construido sobre la base de un proyecto de cálculo de costes.

**Fundamentos de facturación**

Edición básica de facturación, centrada en la retroalimentación e PxQ e y el reembolso sencillo. Entregado como componentes dentro de un proyecto de Costing Essentials y presentado como una colección de informes de «Facturación».

**Norma de facturación**

Edición completa de Facturación, con componentes adicionales específicos del dominio (nube, aplicaciones, infraestructura, proyectos, variación, precios de transferencia) y un punto final dedicado a Facturación. Construido sobre un proyecto de estándar de costes.

**Cálculo de costes**

La capa de modelización de costes que asigna el gasto en tecnología a servicios, aplicaciones y consumidores. La facturación depende del cálculo de costes para las estructuras de costes y, a menudo, para la información sobre los costes unitarios.

**PxQ (Precio por Cantidad)**

El patrón básico de cálculo de facturación:

Cargo = Unidades × Tarifa

Las unidades representan el consumo, la tarifa representa el precio o la recuperación por unidad.

**Consumidor**

Cualquier entidad que reciba cargos por tecnología. Ejemplos: unidad de negocio, departamento, centro de costes, producto, proyecto, programa, región o entidad jurídica.

**Servicio / Oferta / Producto**

El «qué» que se está facturando. Puede tratarse de un servicio tecnológico, una plataforma, un producto o un paquete que aparece en las facturas y en los informes de facturación.

**Showback**

Informar de los cargos o precios «simulados» a los consumidores sin contabilizar los asientos en el libro mayor. Se utiliza para lograr transparencia y cambios de comportamiento sin ingresos internos formales.

**Retorno de cargos**

Utilizar la facturación para generar cargos listos para el diario que se contabilizan en el libro mayor como ingresos y gastos internos.

**Edición**

El nivel de capacidad de facturación suscrito. Para facturación, las ediciones son Essentials y Standard. Un proyecto de cálculo de costes solo ejecuta una edición de facturación a la vez.

## Términos relacionados con los datos y la modelización

**Cálculo de costes del proyecto**

El proyecto TBM Studio, donde se encuentran los modelos de costes, las tablas y muchos componentes de facturación compartidos. Contiene entornos de desarrollo, ensayo y producción.

**En el entorno de desarrollo**

El entorno en el que se realizan y prueban primero los cambios de configuración. Aquí se revisan, editan y registran los artículos. Las compilaciones creadas aquí se reflejan en Staging.

**Entorno de ensayo**

El entorno utilizado para el control de calidad y los ensayos generales. Las compilaciones en Staging son candidatas para pasar a Producción tras su validación y aprobación.

**Entorno de producción**

El entorno en vivo donde se ejecutan los informes de los usuarios finales, los modelos de facturación y las exportaciones de diarios para los períodos oficiales.

**Componente**

Un conjunto empaquetado de modelos, tablas, métricas e informes que se pueden instalar en un proyecto de cálculo de costes. Ejemplos: Facturación: cargos, Facturación: informes de cargos, BoIT : servidores, BoIT : nube.

**Punto final**

El punto de entrada frontal que muestra los informes de un proyecto y un ámbito determinados.

- En el caso de Billing Essentials, los informes aparecen en el punto final de Costing Essentials como una colección denominada «Billing».
- Para Billing Standard, existe un punto final de facturación independiente.

**Datos maestros**

Datos de referencia relativamente estables, como consumidores, servicios, aplicaciones, entidades jurídicas y unidades. Se utilizan como claves y dimensiones en modelos e informes.

**Datos de consumo**

Registros que representan «cuánto» se utilizó un servicio, por qué consumidor y en qué período. Normalmente contiene: consumidor, servicio, unidades, período y atributos opcionales.

**Tarifa / precio**

El valor por unidad utilizado en los cálculos de un PxQ. Las tablas de tarifas definen qué precio se aplica a cada servicio y período y, en ocasiones, por tipo de consumidor, región u otras dimensiones.

**Unidad**

La medición del consumo y los precios. Ejemplos: usuario por mes, GB por mes, máquina virtual por mes, ticket por mes, dispositivo por mes.

**Coste unitario**

Coste por unidad de un servicio, normalmente derivado del cálculo de costes dividiendo el coste total entre el total de unidades. Se utiliza para comparar el coste con el precio.

**Tabla de correlación**

Una tabla que vincula valores de un dominio o sistema a otro. Ejemplos: centro de costes externo a consumidor interno, etiquetas en la nube a servicios y consumidores, ID de proyectos a aplicaciones.

**Entidad legal**

Una empresa o entidad que existe a efectos legales y fiscales. Se utiliza para los precios de transferencia y las vistas entre empresas en el estándar de facturación.

**Precio de transferencia**

El precio utilizado para los cargos internos entre entidades o entre países. Normalmente se derivan de los precios de facturación estándar o están relacionados con ellos, pero están sujetos a restricciones fiscales y normativas.

## Términos relacionados con la presentación de informes y los procesos

**Informe tipo factura**

Un informe que muestra los cargos correspondientes a un consumidor y un periodo determinados en un formato similar al de una factura, normalmente con columnas de servicio, unidades, tarifa y cargo, además de los totales.

**Informe detallado**

Un informe más detallado que muestra los factores determinantes a nivel de línea que hay detrás de una factura. A menudo incluye campos adicionales como el entorno, la región, el proyecto o segmentos basados en etiquetas.

**Informe del diario / Exportación del diario**

Un informe de facturación diseñado para cumplir con los requisitos de contabilización financiera. Incluye segmentos de cuentas GL, segmentos de consumidores, importes y referencias, y se utiliza para contabilizar devoluciones.

**Informe de control de calidad / Informe de excepciones**

Informes diseñados para destacar posibles problemas. Ejemplos: asignaciones faltantes, volúmenes cero o negativos, picos inusuales, registros huérfanos.

**Varianza**

La diferencia entre dos valores, comúnmente:

- Real vs plan
- Coste frente a precio
- Período actual frente al período anterior

**Análisis de la tasa unitaria**

Análisis centrado en el coste por unidad de un servicio a lo largo del tiempo, utilizado a menudo para explicar y optimizar la economía de la tecnología.

**Ensayo general**

Una ejecución completa de principio a fin del ciclo de facturación en Staging antes de la primera puesta en marcha en Producción. Utiliza datos reales o realistas y valida modelos, informes y exportaciones.

**Hipercuidado**

El período inmediatamente posterior a la puesta en marcha (normalmente de uno a tres ciclos de facturación) en el que la gestión de incidencias, el control de calidad y la asistencia técnica son deliberadamente más intensivos.

**Runbook**

Descripción detallada y documentada del ciclo operativo de facturación. Incluye plazos, responsabilidades y dependencias para cargas de datos, ejecuciones de modelos, control de calidad y exportaciones.

**Período de solo retroalimentación**

Un período en el que se utiliza la facturación para informar de los cargos, pero aún no se han contabilizado los asientos, a menudo durante la fase piloto o la adopción inicial.

## Acrónimos

**Unidad de negocio**

Unidad de negocio. Un segmento organizativo de alto nivel que a menudo actúa como consumidor de servicios tecnológicos.

**Director de informática / Director técnico / Director financiero / Director de operaciones**

Director de Información, Director de Tecnología, Director Financiero, Director de Operaciones. Patrocinadores ejecutivos o partes interesadas de Facturación y Costes.

**GL**

Libro mayor. El sistema financiero de registro de asientos contables, incluidos los diarios de devoluciones cuando se utilicen.

**ITFM / ITFM(A)**

Gestión financiera de TI. ITFMA se refiere a un analista responsable de los procesos, análisis y herramientas de ITFM.

**Oficina de Gestión de Proyectos**

Oficina de gestión de proyectos. A menudo se consume con vistas de proyecto de los resultados de facturación.

**PPM**

Gestión de proyectos y carteras. Las herramientas y procesos utilizados para gestionar proyectos y carteras que pueden asignarse a la facturación.

**PxQ**

Precio por Cantidad, el patrón básico de cálculo de facturación que genera los cargos.

**QA**

Garantía de calidad. Actividades y comprobaciones que garantizan que los datos y resultados de facturación son aptos para su uso antes de su publicación.

**RACI**

Responsable, responsable, consultado, informado. Un marco que a veces se utiliza para describir las funciones y responsabilidades de los procesos de facturación y cálculo de costes.

**TBM**

Gestión de negocios tecnológicos. La disciplina y taxonomía más amplias para gestionar el coste, el rendimiento y el valor de la tecnología. La facturación utiliza conceptos alineados con TBM, pero puede ser utilizada por organizaciones que no etiquetan su práctica como TBM.

**TBMA**

Analista de TBM. Analista responsable de trabajar con datos, modelos y herramientas alineados con TBM, como Costing y Billing.

**UOM**

Unidad de medida. La unidad utilizada para cuantificar el consumo del servicio y definir las tarifas, como usuario por mes o GB por mes.

## Dónde aparecen las definiciones en el producto

Algunas implementaciones muestran definiciones breves directamente en las descripciones de los informes o en las descripciones emergentes.

Ejemplos:

- Campos de descripción del informe que explican qué muestra el informe y a quién va dirigido.
- Descripciones de las columnas para campos críticos como Unidad, Tarifa, Consumidor y Servicio.
- Enlaces de ayuda desde los informes de facturación que remiten a este apéndice.

Mantener la coherencia terminológica en este apéndice, los modelos y los informes reduce la confusión y facilita que los nuevos usuarios confíen en Billing y lo adopten.
