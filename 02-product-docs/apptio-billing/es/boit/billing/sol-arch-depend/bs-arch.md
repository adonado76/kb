---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Arquitectura estándar de facturación"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Arquitectura de soluciones y dependencias"
source_path: "boit/billing/sol-arch-depend/bs-arch.html"
images:
  - "resources/images/boit_images/fdlp.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Arquitectura estándar de facturación

Billing Standard amplía la misma arquitectura con un punto final adicional y un conjunto más amplio de componentes.

Nota: Se aplica únicamente a la norma de facturación.

Elementos fundamentales:

- **Componentes**
  - BoIT- Fundación

    Requerido para la norma de facturación. Instala los modelos de facturación, las tablas y las estructuras de informes básicos, incluidos los informes tipo factura que resumen los cargos por servicio y consumidor.
  - BoIT- Unidades

    Añade vistas basadas en unidades en los informes de facturación. Introduce unidades facturables para cada oferta de servicio, calcula las tarifas unitarias efectivas dividiendo los cargos por unidades y, cuando también se instala Cost Variance, permite comparar las tarifas unitarias basadas en los costes con las basadas en los precios.
  - BoIT- Aplicaciones

    Añade vistas de facturación centradas en las aplicaciones. Incluye informes que muestran los cargos y las unidades de licencia o uso por aplicación para el público empresarial, además de vistas de recuperación que comparan los cargos con el coste tecnológico subyacente de cada aplicación para resaltar el exceso y el déficit de recuperación.
  - BoIT- Servidores

    Añade informes centrados en el servidor a la facturación. Introduce informes y pestañas que desglosan los costes y cargos relacionados con los servidores, mostrando cómo la infraestructura de servidores contribuye a los servicios y aplicaciones que se facturan.
  - BoIT- Almacenamiento

    Añade informes centrados en el almacenamiento a la facturación. Introduce informes y pestañas que detallan los costes y cargos relacionados con el almacenamiento, mostrando cómo los niveles y grupos de almacenamiento se incorporan a los servicios y aplicaciones que aparecen en las facturas.
  - BoIT- Dispositivos de usuario final

    Añade vistas de facturación a nivel de dispositivo. Integra los datos de los dispositivos del modelo de costes y proporciona informes tanto para los proveedores de servicios como para los consumidores empresariales, centrados en la asignación de dispositivos, los patrones de consumo y los cargos asociados a los dispositivos de los usuarios finales.
  - BoIT- Nube

    Añade informes centrados en la infraestructura en la nube ( IaaS ). Incluye informes que muestran los cargos por servicios en la nube por proveedor, cuenta y servicio para el público empresarial, así como vistas de recuperación que comparan los cargos por servicios en la nube con el costo de prestar dichos servicios para resaltar los casos de recuperación excesiva e insuficiente.
  - BoIT- Proyectos

    Añade vistas de facturación centradas en proyectos. Incluye informes que muestran los gastos del proyecto y los servicios subyacentes consumidos, junto con vistas de recuperación y variación que combinan la recuperación excesiva o insuficiente, la variación presupuestaria y el estado del proyecto en un solo lugar.
  - BoIT- Precio

    Permite mostrar precios explícitos a los usuarios finales. Los precios se definen en la biblioteca de servicios y se aplican en los modelos de facturación; cuando se aplican múltiples ajustes o combinaciones de precios a un servicio, el precio unitario efectivo que se muestra en los informes puede diferir del precio base de la biblioteca de servicios.
  - BoIT- Variación de costes

    Compara los cargos de facturación con el coste real de la prestación de los servicios. Añade informes, normalmente dirigidos a propietarios de servicios y funciones similares, que muestran los costes, los cargos y las variaciones a nivel de servicio y dominio para respaldar las decisiones de recuperación y fijación de precios.
  - BoIT- Variación del plan

    Presenta comparaciones entre el presupuesto y las previsiones. Permite generar informes que comparan los cargos con el presupuesto y los costes con el presupuesto, y añade dimensiones de variación del presupuesto/previsión a las vistas de facturación existentes para obtener un análisis más claro del rendimiento con respecto al plan.
  - BoIT- Precios de transferencia entre empresas

    Admite el modelado y la generación de informes sobre cargos en todas las entidades jurídicas. Permite una lógica de asignación y facturación que rastrea el impacto financiero del consumo de servicios entre entidades legales o centros de coste, lo que facilita los escenarios de facturación cruzada en organizaciones tecnológicas descentralizadas o con múltiples entidades.
- **Dónde se instalan**
  - Instalado en el **proyecto Costing Standard** utilizando TBM Studio.
  - Añadir modelos, tablas, métricas y definiciones de informes que abarquen múltiples ámbitos tecnológicos y perspectivas financieras.

- **Cómo lo ven los usuarios**
  - Expuesto a los usuarios a través de un **punto final estándar de facturación independiente**, además del punto final estándar de cálculo de costes.
  - Las colecciones de informes dentro del punto final Billing Standard se alinean con dominios tales como:
    - Servicios y consumidores
    - Unidades y tasas unitarias
    - Nube
    - Aplicaciones
    - Infraestructura (servidores, almacenamiento, dispositivos de usuario final)
    - Proyectos
    - Variación y precios
    - Precios de transferencia y entidades jurídicas

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/fdlp.png)

Fig. n.º: Página de inicio de Frontdoor con el punto final «Billing Standard» resaltado

Dependencias y supuestos:

- Un proyecto de norma de cálculo de costes se implementa con un modelo de costes estable.
- IBM Ha aprovisionado un **punto final de la norma de facturación** y lo ha vinculado al proyecto de la norma de cálculo de costes correspondiente.
- Los componentes de Billing Standard se instalan y configuran de manera que:
  - Se rellenan las tablas de datos maestros del dominio (aplicaciones, servidores, almacenamiento, nube, proyectos, dispositivos de usuarios finales, entidades jurídicas).
  - Se definen las relaciones con los consumidores, los servicios y las tablas de precios.
- Los usuarios que necesitan informes de facturación estándar tienen acceso al punto final de facturación estándar y a las colecciones de informes pertinentes.
