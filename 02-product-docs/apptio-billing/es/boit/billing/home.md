---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Facturación"
breadcrumb:
  - "Billing"
source_path: "boit/billing/home.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Facturación

## Notas del release

- [Últimos lanzamientos](release-notes/whats-new.html "Esta sección describe únicamente los cambios en el contenido de facturación listo para usar, no en la plataforma subyacente. Para las actualizaciones a nivel de plataforma, como el comportamiento de TBM Studio y el servidor cliente, los lectores deben revisar las notas de la versión de TBM Studio y tener en cuenta los cambios aplicables junto con lo que se documenta aquí.")

## Cómo empezar

- Introducción a la facturación
  - [Resumen de facturación](getting-started/intro-billing-what-how.html)
  - [Ediciones de facturación y ediciones de costes](getting-started/bill-cost-editions.html "La facturación está disponible en dos ediciones. Cada edición está asociada a un conjunto diferente de componentes y está diseñada para distintos niveles de complejidad y madurez.")
  - [Conceptos básicos: servicios, unidades, tarifas, recuperación, diarios](getting-started/core-concepts.html "El resto de esta guía se basa en un pequeño conjunto de conceptos recurrentes. Entenderlos aquí reduce la confusión más adelante.")
  - [Principales ventajas](getting-started/key-benefits.html "A alto nivel, Billing te ayuda a:")
- [Glosario y acrónimos](getting-started/key-concepts-terms.html "Este apéndice define los términos y acrónimos comunes utilizados en toda la Ayuda sobre facturación. Úsalo como referencia rápida cuando leas otras secciones o trabajes con el producto.")
- Roles y permisos de usuario
  - [Descripción general y funciones](getting-started/std-custom-role.html "Los roles y permisos de los usuarios controlan quién puede ver y trabajar con Benchmarking. Un rol es un conjunto de permisos que se asigna a un usuario, y nadie puede acceder a un producto IBM Apptio sin tener al menos un rol en su cuenta, que se gestiona en Administración de accesos. En la administración de Access, los administradores autorizados crean y gestionan los registros de usuarios, asignan o eliminan roles y controlan qué roles pueden acceder a cada punto final del producto, qué puntos finales están abiertos a cualquier rol elegible y qué puntos finales están ocultos por completo.")
  - [Permisos y tipos de acceso para Billing Standard](getting-started/perm-access-bs.html)
  - [Patrones de acceso para Billing Essentials](getting-started/access-patters-be.html)
  - [Patrones de acceso para la norma de facturación](getting-started/access-patterns-bs.html "Billing Standard introduce un punto final de facturación independiente, además del proyecto de cálculo de costes. El acceso debe tener en cuenta ambos aspectos.")
  - [Segregación de funciones y prácticas recomendadas](getting-started/duty-segregation.html "Al configurar roles y permisos, tenga en cuenta estas prácticas:")
  - [Gestión del acceso a lo largo del tiempo](getting-started/manage-access.html "El acceso rara vez permanece estático. Las personas cambian de funciones, se añaden nuevos servicios y se implementan nuevas capacidades de facturación.")
- [Recursos de soporte](getting-started/support-resources.html)

## Cómo utilizar esta guía

- [A quién va dirigida esta guía](getting-started/audience.html "En esta sección se explica a quién va dirigida la guía, cómo funcionan los avisos de edición, qué abarca cada sección principal y por dónde deben empezar los diferentes perfiles.")
- [Notificaciones sobre ediciones y costes](getting-started/edition-costing-notice-conventions.html "La facturación siempre se basa en un proyecto de cálculo de costes, pero esta guía simplifica la nomenclatura centrándose en las ediciones de facturación:")
- [Qué abarca cada sección](getting-started/section-coverage.html "Utiliza esto como un mapa rápido de la guía:")
- [Por dónde empezar con la persona](getting-started/persona.html "No es necesario leer la guía en orden. Utilice las sugerencias siguientes para ir a las secciones más relevantes.")
- [Lista de verificación de implementación](getting-started/checklist.html "Para cualquiera que esté planificando o modificando una implementación de facturación, esta lista de verificación de alto nivel resume la guía. Las secciones posteriores proporcionan los pasos detallados.")

## Requisitos e integración de datos

- [Bases de datos compartidas](datareq-integrate/shared-data.html "La facturación se sitúa por encima del cálculo de costes. Si los datos que alimentan el cálculo de costes y la facturación son deficientes, las facturas serán deficientes. En esta sección se detalla qué datos necesita el departamento de facturación, cómo se estructuran normalmente y dónde suele producirse la integración.")
- [Requisitos de datos para Billing Essentials](datareq-integrate/data-be.html)
- [Requisitos de datos para el estándar de facturación](datareq-integrate/data-bs.html "Billing Standard utiliza un conjunto más amplio de componentes y, por lo tanto, un modelo de datos más amplio. Sigue necesitando los mismos fundamentos básicos que Essentials, pero los extiende a múltiples dominios.")
- [Expectativas en materia de calidad de los datos](datareq-integrate/data-quality.html "Los datos erróneos aparecerán inmediatamente en los resultados de facturación: líneas que faltan, cargos inexplicables o tarifas que parecen incorrectas.")
- [Calendarios y periodos](datareq-integrate/calendar.html "La facturación necesita una noción coherente de los periodos:")
- [Divisas y mercado de divisas](datareq-integrate/currency.html "La facturación puede operar en entornos multidivisa, pero suele ser más sencillo si los resultados de la facturación se presentan en una única moneda de presentación para las partes interesadas del negocio.")
- [Mecanismos de integración y opciones ajenas a Studio](datareq-integrate/integration.html "Los datos pueden llegar a Facturación a través de varios mecanismos. Las que se utilicen dependerán de quién gestione la implementación y de las herramientas disponibles.")

## Configuración de los elementos esenciales de facturación (implementación)

- [Ámbito de aplicación y requisitos previos](config-be/be-overvie.html "En esta sección se describe cómo se configura Billing Essentials en un proyecto de Costing Essentials, desde la instalación de los componentes hasta las primeras facturas utilizables. Se da por hecho que Costing Essentials ya está implementado y es estable.")
- [Instalación de los componentes de Billing Essentials](config-be/install-be.html "Billing Essentials se entrega como componentes que se instalan en el proyecto Costing Essentials existente.")
- [Conjuntos de datos y tablas clave](config-be/key-datasets.html)
- [Creación del catálogo de productos](config-be/populate.html "El catálogo de ofertas determina lo que aparece en las facturas. Debe completarse y validarse antes de la primera facturación.")
- [Preparación de los datos de los consumidores](config-be/prepare.html "El modelo Billing Essentials necesita una visión coherente de a quién se le factura.")
- [Integración de datos de consumo](config-be/integrate.html "Los datos de consumo son los que impulsan las unidades en el cálculo de la tasa de consumo ( PxQ ).")
- [Configuración y tarifas de recarga](config-be/configure.html "Las tarifas convierten las unidades en cargos monetarios.")
- [Ejecutar el cálculo de «Fundamentos de facturación»](config-be/running.html "Una vez establecidas las ofertas, los consumidores, el consumo y las tarifas, el cálculo de Billing Essentials se puede ejecutar en Desarrollo y Pruebas.")
- [Traslado al entorno de producción y primera puesta en marcha](config-be/prmoting.html "Una vez que Billing Essentials funcione como se espera en Staging:")
- [Entrega y puesta en marcha](config-be/handover.html "Tras la primera tirada de producción satisfactoria:")

## Configuración del estándar de facturación (implementación)

- [Ámbito de aplicación y requisitos previos](config-bs/bs-overview.html "En esta sección se describe cómo se configura Billing Standard sobre un proyecto de Costing Standard, desde la instalación de los componentes hasta las primeras facturas con dominios enriquecidos utilizables. Se da por hecho que Costing Standard ya está implementado y es estable.")
- [Instalación de los componentes de Billing Standard](config-bs/bs-install.html "El estándar de facturación se envía como un conjunto de componentes instalados en el proyecto estándar de costes existente. El punto final Billing Standard en el front-end muestra el contenido creado por estos componentes.")
- [Tablas y relaciones del dominio principal](config-bs/bs-core.html "La fortaleza de Billing Standard proviene de su modelo rico en dominios. Como mínimo, espere trabajar con las siguientes familias de tablas:")
- [Configuración de servicios y ofertas](config-bs/bs-setup.html "El catálogo de lo que se factura es fundamental independientemente de la edición, pero Billing Standard a menudo necesita una vinculación más rica con los dominios.")
- [Introducción de datos maestros de dominio](config-bs/bs-pop-domain.html "Los administradores de dominio habilitan los informes estándar de facturación que desglosan los cargos por aplicación, infraestructura, nube, proyecto y entidad legal.")
- [Armonización de las definiciones de costes, consumo y unidades](config-bs/bs-align-cost.html "La norma de facturación requiere una historia coherente en cuanto a costes, unidades y precios.")
- [Configuración de la lógica de precios y variaciones](config-bs/bs-config-price.html "Billing Standard puede analizar costes, planes y precios. La configuración decide cómo funciona eso.")
- [Ejecución del cálculo de la norma de facturación en el entorno de desarrollo/pruebas](config-bs/run-bill.html "Una vez que se hayan establecido los dominios maestros, las unidades, los precios y las asignaciones, se podrá comprobar el cálculo del estándar de facturación.")
- [Habilitar el punto final de Billing Standard y el acceso a los informes](config-bs/enable-bill.html "Una vez validado el contenido en Staging, se pueden preparar el punto final y los informes para los usuarios.")
- [Traslado a producción y primera ejecución completa de Billing Standard](config-bs/promote-bill.html "Después de facturar, se validan el contenido estándar y el comportamiento del punto final en Staging:")
- [Aplicación práctica de la norma de facturación](config-bs/operate-bill.html "Tras su puesta en marcha, la norma de facturación pasa a formar parte del ciclo de facturación recurrente descrito en la sección 9, con responsabilidades de dominio añadidas.")

## Ejecutar el ciclo de facturación

- [Planificación anual y fijación de tarifas](run-bill-cycle/anual-plan.html "La mayoría de las implementaciones de facturación siguen un ritmo anual para la planificación y las tarifas, incluso si se producen ajustes durante el año.")
- [Proceso de facturación mensual](run-bill-cycle/monthly-bill.html "Cada período de facturación suele seguir una serie de pasos repetibles.")
- [Validación de las facturas del período actual](run-bill-cycle/validating.html "La validación es donde se detectan la mayoría de los problemas de facturación antes de que lleguen a los consumidores.")
- [Generación y distribución de facturas](run-bill-cycle/generating.html "Una vez que los resultados de facturación pasan la validación, el siguiente paso es generar vistas de facturas y distribuirlas.")
- [Exportación y contabilización de asientos](run-bill-cycle/exporting.html "En el caso de las devoluciones, los resultados de facturación suelen alimentar los sistemas financieros como diarios.")
- [Lista de comprobación para la gestión de la facturación](run-bill-cycle/admin-checklist.html "Esta lista de verificación resume las tareas recurrentes para cada período de facturación. Se puede adaptar para convertirlo en un manual operativo más detallado.")

## Trabajar con informes de facturación

- [Dónde encontrar los informes de facturación](work-bill-reports/where-to-find.html "Los informes de facturación son donde la mayoría de las personas experimentan el resultado del modelo de facturación. Esta sección se centra en cómo encontrar esos informes, cómo son los principales grupos de informes en cada edición y cómo se utilizan normalmente.")
- [Informes de facturación en Billing Essentials](work-bill-reports/billrep-be.html "Billing Essentials incluye un pequeño conjunto de informes específicos que se instalan a través del componente «Bill-Charge Reporting» (Informes de facturación y cargos):")
- [Informes de facturación en Billing Standard](work-bill-reports/billrep-bs.html "Billing Standard incluye vistas específicas del dominio, facturas e informes resumidos. Los informes se agrupan en secciones que se muestran en la página de inicio del informe. A menos que se indique lo contrario, los informes se instalan a través del componente « “BoIT- Foundation».")
- [Tareas habituales relacionadas con los informes y patrones de uso](work-bill-reports/common-rep-ratasks.html "Independientemente de la edición, los usuarios suelen realizar las mismas acciones básicas en los informes de facturación. Esta subsección se centra en los patrones más que en controles específicos de la interfaz de usuario.")

## Administración y operaciones

- [Visión general](admin-ops/ao-admin.html "Esta sección te ofrece patrones concretos para estructurar la facturación, de modo que no tengas que inventarlo todo desde cero cada vez.")
- [Showback de servicio simple](admin-ops/ao-simple-service.html)
- [Contracargo con diarios](admin-ops/ao-chargeback-journal.html)
- [Diseño centrado en el catálogo de servicios](admin-ops/ao-service-catalog.html)
- [Diseño centrado en la nube](admin-ops/ao-cloud-centric.html)
- [Diseño centrado en proyectos](admin-ops/ao-project-centric.html)
- [Perspectiva de la entidad jurídica y los precios de transferencia](admin-ops/ao-legal-entity.html)
- [Combinar patrones sin crear caos](admin-ops/ao-comb-patter.html)
- Ediciones y prestaciones
  - [Resumen y sinopsis de las ediciones](edition-capabilities/es-intro.html "La facturación está disponible en dos ediciones: Billing Essentials y Billing Standard.")
  - [Diseñar pensando en la edición](edition-capabilities/es-design.html "Al trabajar con Billing Essentials:")
- Arquitectura de la solución y dependencias
  - [Relación entre facturación y cálculo de costes](sol-arch-depend/sol-arch-intro.html "En esta sección se explica cómo se empaqueta la facturación, cómo se relaciona con el cálculo de costes y qué debe existir antes de que se pueda utilizar el contenido de facturación.")
  - [Arquitectura de Billing Essentials](sol-arch-depend/be-arch.html "Billing Essentials se implementa dentro del mismo proyecto que ejecuta Costing Essentials. No hay un punto final independiente para Billing Essentials. Todo el contenido se entrega como componentes adicionales y colecciones de informes dentro de ese proyecto.")
  - [Arquitectura estándar de facturación](sol-arch-depend/bs-arch.html "Billing Standard amplía la misma arquitectura con un punto final adicional y un conjunto más amplio de componentes.")
  - [Relaciones entre el front-end y los puntos finales](sol-arch-depend/fe-endpoint-relation.html "Aunque esta guía no profundiza en Frontdoor, es importante comprender cómo los usuarios llegan a Facturación.")
  - [Resumen de dependencias](sol-arch-depend/depend-summary.html "La siguiente tabla resume las dependencias clave para cada edición.")
- Entornos y gestión de versiones
  - [Entornos de cálculo de costes: desarrollo, staging, producción](environ-relnmgmt/environments.html "La facturación utiliza los mismos entornos que el proyecto de cálculo de costes en el que está instalada. Los cambios de configuración en Facturación se gestionan a través de los entornos del proyecto Costing: En desarrollo, En fase de pruebas y En producción.")
  - [Check-out, check-in y creación de compilaciones](environ-relnmgmt/checkin-checkout.html "Los cambios de configuración para la facturación siguen el mismo patrón que los de costes:")
  - [Cierre de la fase de pruebas y paso a producción](environ-relnmgmt/lock-stage-promote.html "Antes de promover cambios a Producción, el entorno de ensayo debe bloquearse para evitar que los nuevos registros generen compilaciones adicionales.")
  - [Flujo de entorno para Billing Essentials](environ-relnmgmt/env-be.html)
  - [Flujo de entorno para el estándar de facturación](environ-relnmgmt/env-bs.html "La norma de facturación sigue el mismo ciclo de vida medioambiental que el proyecto de la norma de costes subyacente, pero introduce un punto final de facturación independiente para los usuarios finales.")

## Temas avanzados

- [Análisis y optimización de tarifas unitarias](advance-topic/unit-rate-analysis.html "Las tarifas unitarias suelen ser el tema central de las conversaciones sobre facturación. Esta subsección se centra en cómo analizarlos y ajustarlos a lo largo del tiempo.")
- [Patrones de facturación en la nube](advance-topic/cloud-billing-patterns.html "La facturación en la nube depende en gran medida del etiquetado, la estructura de la cuenta y la asignación de servicios. Los componentes de facturación estándar en la nube están diseñados para que esto sea fácil de manejar.")
- [Facturación y vistas centradas en los proyectos](advance-topic/project-centric-billin.html "Los proyectos suelen representar inversiones en productos, servicios o iniciativas de cambio. Los componentes del proyecto Billing Standard permiten la facturación y la retroalimentación centradas en el proyecto.")
- [Precios de transferencia y perspectivas de las entidades jurídicas](advance-topic/transfer-price.html "Los precios de transferencia y las opiniones a nivel de entidad jurídica cobran importancia cuando los costes tecnológicos traspasan las fronteras legales o fiscales.")
- [Previsión frente a real frente a precio](advance-topic/plan-vs-actual.html "Se aplica principalmente a Billing Standard, pero los conceptos se pueden utilizar de forma simplificada con Billing Essentials si se dispone de datos del plan.")

## Patrones de diseño y casos de uso

- [Servicio sencillo de «showback» de « PxQ »](design-uc/uc-simple.html)
- [Contracargo con exportación de diario](design-uc/uc-chargeback.html)
- [Investigar un aumento repentino de la tasa unitaria.](design-uc/uc-investgate.html)
- [Vista de costes y tarifas unitarias en la nube](design-uc/uc-cloud.html)
- [Vista del proyecto de gasto en tecnología](design-uc/uc-project.html)
- [Persona jurídica y visión interempresarial](design-uc/uc-legal.html)
- [Compare el plan, los datos reales y el precio de un servicio clave.](design-uc/uc-compare.html)

## Manual de puesta en marcha

- [¿Qué significa «poner en marcha» para la facturación?](go-live/gl-overview.html)
- [Lista de verificación de preparación previa a la puesta en marcha](go-live/gl-checklist.html "Esto es lo mínimo que debe tener preparado antes incluso de fijar una fecha de puesta en marcha.")
- [Ensayo general](go-live/gl-dress-rehersal.html "Un ensayo general es una ejecución completa de principio a fin en Desarrollo y verificada en Preproducción que imita lo que se publicará en Producción.")
- [Enfoque de transición](go-live/gl-cutover.html "El cambio es el paso controlado de «estamos probando» a «estamos utilizando la facturación como fuente de verdad»")
- [Hipercuidado: primeros 1-3 ciclos](go-live/gl-hypercare.html "La puesta en marcha no finaliza cuando se cierra el primer periodo. Los primeros ciclos son donde se manifiestan las debilidades.")
- [Estrategias de retroceso y corrección](go-live/gl-falback.html "A veces las cosas salen mal. Decida de antemano cómo los corregirá.")
- [Responsabilidades de puesta en marcha](go-live/gl-resp-runbook.html "Es útil dejar claro quién es el propietario de cada cosa durante la puesta en marcha.")
- [Captura del libro de procedimientos de «estado estable»](go-live/runbook.html)

## Guía de formación basada en funciones

- [Objetivos de la formación](role-based-tg/train-objectives.html "En esta sección se describe cómo formar a diferentes públicos para que el sistema de facturación se utilice y se confíe en él, y no solo se implemente técnicamente. Úsalo para diseñar la incorporación, la formación periódica y los traspasos cuando las personas cambian de funciones.")
- [Ámbito de formación por función](role-based-tg/train-scope.html "Esta subsección resume lo que cada función debe aprender. La matriz de formación detallada se puede documentar por separado.")
- [Ruta de incorporación para administradores y analistas](role-based-tg/op-admin.html "Esta es la ruta de formación más intensiva y debe estar estructurada, no ser improvisada.")
- [Ruta de incorporación para propietarios de servicios y productos](role-based-tg/op-so-po.html "Esta ruta es más corta y se centra en la interpretación, no en la configuración.")
- [Proceso de incorporación para Finanzas](role-based-tg/op-finance.html "La formación financiera debe ser práctica: cómo conciliar y contabilizar, no cómo escribir ETL.")
- [Formación para altos directivos y partes interesadas](role-based-tg/op-sl.html "Se trata de apoyo a la toma de decisiones, no de mecánica.")
- [Entrenamiento, cadencia y formatos](role-based-tg/cadence-format-measure.html "Una vez completada la incorporación inicial, la formación no debe detenerse. Como mínimo:")

## Resolución de problemas

- [Resolución de problemas](troubleshooting/troubleshoot.html "Este apéndice es una guía práctica sobre «qué ha fallado y qué hay que comprobar primero». Úselo cuando los números no cuadren, los informes estén vacíos o los diarios no concuerden.")
