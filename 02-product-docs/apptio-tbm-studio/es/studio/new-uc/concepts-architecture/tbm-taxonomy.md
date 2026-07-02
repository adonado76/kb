---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "La taxonomía TBM"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Fundamentos de la TBM"
source_path: "studio/new-uc/concepts-architecture/tbm-taxonomy.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# La taxonomía TBM

La taxonomía TBM es un marco estandarizado para clasificar los costes de TI en una jerarquía por niveles. Proporciona un lenguaje común para relacionar los datos financieros brutos con los servicios y los usuarios que impulsan el gasto en TI. Imagínatelo como un edificio de cuatro plantas: los costes entran por la planta baja y van subiendo hasta llegar a las unidades de negocio que, en última instancia, los consumen.

## Las cuatro capas

La taxonomía estándar de TBM define cuatro niveles principales. Cada capa responde a una pregunta diferente sobre el gasto en TI:

|  |  |  |  |
| --- | --- | --- | --- |
| **Capa** | **Pregunta** | **Ejemplos comunes** | **TBM Studio Mapping** |
| **Grupos de costes** | ¿De dónde proceden los costes? | Hardware, software, mano de obra, instalaciones, nube | Objeto del modelo de origen de costes y tablas del libro mayor |
| **Torres de TI** | ¿Cómo se organizan los costes? | Informática, almacenamiento, redes, usuario final, seguridad | Objetos del modelo intermedio (proveedores, servicios tecnológicos) |
| **Servicios de TI / Aplicaciones** | ¿Qué ofrece el departamento de TI? | Correo electrónico, ERP, CRM, análisis de datos, plataforma de « DevOps » | Objeto modelo de soluciones |
| **Unidades de negocio** | ¿Quién utiliza los servicios de TI? | Ventas, marketing, finanzas, operaciones, I+D | Objeto del modelo de unidades de negocio |

## Nivel 1: Grupos de costes — Origen de los costes

Los grupos de costes representan las categorías financieras básicas en las que se origina el gasto en TI. Por lo general, se corresponden con cuentas del libro mayor o facturas de proveedores. Los grupos de costes responden a la pregunta: «¿En qué tipo de cosas estamos gastando el dinero?»

Entre las categorías habituales de grupos de costes se incluyen:

- **Hardware** : servidores, dispositivos de almacenamiento, equipos de red, dispositivos de usuario final
- **Software** : software con licencia, suscripciones a SaaS, contratos de mantenimiento
- **Personal** : personal interno de TI, contratistas, servicios externalizados
- **Servicios** : Espacio para centros de datos, suministro eléctrico, refrigeración
- **Nube y alojamiento** : IaaS,, PaaS, y SaaS (tarifas por consumo)
- **Telecomunicaciones** : servicios de red, conexión a Internet, servicios de voz

Nota:

Por qué es importante en TBM Studio

En TBM Studio, los grupos de costes suelen representarse mediante el objeto de modelo «Fuente de costes», que se alimenta de los datos del libro mayor importados a través de Data Studio. La fuente de costes suele ser el punto de partida del modelo y se sitúa en la parte inferior de la cadena de asignación. TBM Studio también es compatible con el aprendizaje automático para asignar automáticamente las cuentas del plan general a las categorías estándar de grupos de costes.

## Nivel 2: Torres de TI — Cómo se organizan los costes

IT Towers agrupa los costes en categorías tecnológicas funcionales. Representan la infraestructura y los servicios que gestiona el departamento de TI, independientemente de las funciones empresariales que los utilicen. Piensa en las torres como los «bloques de construcción» de la prestación de servicios de TI.

Las categorías estándar de IT Tower incluyen: recursos informáticos, almacenamiento, redes, informática para el usuario final, desarrollo de aplicaciones, gestión de TI y seguridad. Las torres sirven de puente entre los costes de los insumos y los servicios orientados al negocio a los que dan soporte.

Nota:

Por qué es importante en TBM Studio

En TBM Studio, las torres de TI se representan como objetos de modelo intermedios entre la fuente de costes y las soluciones. Las implementaciones habituales utilizan los objetos «Vendor» y «Technology Services» como capa de torre. Las asignaciones de los grupos de costes a las torres suelen basarse en factores determinantes, como el número de servidores, el consumo de almacenamiento o la plantilla en equivalentes a tiempo completo.

## Capa 3: Servicios y aplicaciones de TI — Lo que ofrece el departamento de TI

Los servicios de TI representan las capacidades que la TI ofrece al negocio. Es aquí donde los costes cobran importancia para las partes interesadas sin conocimientos técnicos. Puede que a un directivo no le preocupen los costes de los servidores, pero sí le preocupa mucho cuánto cuesta su sistema CRM y si aporta el valor adecuado.

Esta capa asigna los costes de la torre a servicios específicos como el correo electrónico, la planificación de recursos empresariales (ERP), la gestión de las relaciones con los clientes (CRM), las plataformas de análisis de datos y las aplicaciones internas personalizadas.

Nota:

Por qué es importante en TBM Studio

En TBM Studio, el objeto «Solutions» suele representar esta capa. Los costes se transfieren de Servicios Tecnológicos a Soluciones mediante asignaciones basadas en datos de correspondencia entre aplicaciones e infraestructura. La vista del diagrama del modelo ofrece una representación visual de cómo los costes fluyen desde los grupos de costes, pasando por las torres, hasta los servicios individuales.

## Nivel 4: Unidades de negocio y usuarios — Quiénes utilizan los servicios de TI

La última capa asigna los costes de los servicios de TI a las unidades de negocio o departamentos que los utilizan. Esta es la capa que permite el showback y el chargeback, es decir, mostrar a cada unidad de negocio lo que está pagando por los servicios de TI en función de su consumo real.

La asignación de unidades de negocio suele basarse en indicadores de consumo, como el número de usuarios, el volumen de transacciones o los datos de uso de las aplicaciones. El objetivo es lograr una distribución justa y transparente de los costes de TI que refleje el uso real de los recursos.

Nota:

Por qué es importante en TBM Studio

En TBM Studio, «Unidades de negocio» es el objeto de modelo terminal situado en la parte superior de la cadena de asignación. El flujo completo de costes suele ser el siguiente: Fuente de costes → Proveedores → Servicios tecnológicos → Soluciones → Unidades de negocio. Los informes de modelos (vistas de Sankey) ofrecen una visualización intuitiva de este flujo de costes completo.

## Cómo fluyen los datos a través de las capas

La fuerza de la taxonomía TBM reside en el flujo progresivo de los costes a lo largo de cada nivel. He aquí un ejemplo sencillo:

1. **Asiento en el grupo de costes** : « $10M » en los costes de hardware del servidor, contabilizado desde el libro mayor
2. **Asignación de torres** : $10M se asigna a la torre de cómputo en función del uso del servidor (producción, desarrollo, pruebas)
3. **Asignación de servicios** : los costes de computación se asignan a los servicios (CRM: $3M; ERP: $4M; correo electrónico: $1.5M; otros: $1.5M ) en función de las métricas de uso del servidor
4. **Asignación de usuarios** : el servicio « $3M » de CRM se asigna a los departamentos de Ventas ( $1.8M ), Marketing ( $0.9M ) y Atención al cliente ( $0.3M ) en función del número de usuarios

En cada capa, el coste total sigue siendo el mismo; simplemente se distribuye con mayor detalle. Este principio de control de costes es fundamental para TBM y garantiza que se rinda cuentas de cada dólar.

## Flexibilidad y personalización

Aunque la taxonomía de cuatro niveles es el marco estándar, las organizaciones disponen de una gran flexibilidad a la hora de aplicarla:

- **Niveles adicionales** : algunas organizaciones añaden niveles (por ejemplo, subtorres o niveles de servicio) para obtener más detalles
- **Categorías personalizadas** : Las categorías específicas de cada nivel se pueden personalizar para que se ajusten a la terminología y la estructura de su organización
- **Modelos simplificados** : las organizaciones más pequeñas pueden combinar u omitir capas para obtener un modelo más sencillo
- **Múltiples vías de asignación** : los costes pueden distribuirse a través de diferentes vías en función de su naturaleza (por ejemplo, los costes de mano de obra pueden seguir una vía diferente a la de los costes de hardware)

Nota: TBM Studio no impone una estructura taxonómica rígida. Puedes crear objetos de modelo que se adapten a las necesidades específicas de tu organización. Sin embargo, la adaptación a la taxonomía estándar de TBM permite realizar comparativas con el sector y facilita la comprensión del modelo por parte de los nuevos miembros del equipo.
