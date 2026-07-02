---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Grupo de pares y métodos estadísticos"
breadcrumb:
  - "Benchmarking"
  - "Informes comparativos"
  - "Datos y metodología Referencia"
source_path: "it-benchmarking/data-and-methodology/peer-group-statistical-method.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Grupo de pares y métodos estadísticos

Los índices de referencia no muestran organizaciones individuales. Muestran cómo es la distribución de los pares.

## Construcción de grupos de pares

Un grupo de pares se define normalmente por:

- Sector
- Rango de tamaño (normalmente ingresos)
- Región o geografía

Reglas aplicadas en segundo plano:

- Tamaños mínimos de muestra antes de informar una métrica
- Exclusión o recorte de valores atípicos extremos en algunos conjuntos de datos
- Anonimización que impide identificar a los colaboradores individuales

## Percentiles y cuartiles

Estadísticas comunes:

- Mediana: el percentil 50
- Cuartil inferior: el percentil 25
- Cuartil superior: el percentil 75
- Mínimo y máximo, a veces con valores atípicos recortados

Los gráficos suelen representar:

- Mediana como línea o punto
- Rango intercuartílico como banda o caja
- Tu organización como marcador independiente

Interpretación:

- Si estás cerca de la mediana, eres típico
- Dentro de la banda, estás dentro de un rango normal
- Fuera de la banda, eres estructuralmente diferente y debes saber por qué

  ![Diagrama de caja interactivo de benchmarking](../../resources/images/it%20benchmarking_images/indistry-specific-distribution.png)

## Arquetipos

Los arquetipos son patrones derivados de la agrupación de organizaciones en función de su estructura de gastos.

Tipos compatibles con datos de evaluación comparativa interactiva:

- **Centrado en la tecnología de hardware:** un modelo operativo tecnológico en el que la prestación de servicios depende en gran medida de una infraestructura propia o gestionada directamente. Las características típicas incluyen:
  - Mayor presencia física en las instalaciones o en la coubicación, más infraestructura física que gestionar.
  - Mayor inversión en plataformas de infraestructura y pilas tecnológicas subyacentes.
  - A menudo, operaciones gestionadas más internamente (o al menos la propiedad del hardware), incluso si parte de la mano de obra se subcontrata.
- **Centrado en la tecnología de software:** un modelo operativo tecnológico en el que la entrega depende en gran medida de plataformas de software, herramientas y licencias, en lugar de hardware propio. Las características típicas incluyen:
  - Mayor uso de suscripciones a plataformas de « SaaS, », herramientas de automatización y paquetes de software empresarial.
  - La infraestructura puede ser abstracta (en la nube o gestionada), lo que desplaza el énfasis de la propiedad del hardware.
  - Mayor inversión en seguridad, observabilidad, ITSM, colaboración, plataformas de desarrollo y aplicaciones empresariales.
- **Centrado en el proveedor:** modelo operativo tecnológico en el que una gran parte del trabajo lo realizan terceros. Las características típicas incluyen:
  - Servicios gestionados pesados, integradores de sistemas, socios de externalización y contratistas.
  - Los equipos internos se centran más en la gobernanza, la arquitectura, la gestión de proveedores y la propiedad de los productos.
  - La capacidad de entrega se mide más por los proveedores que por la contratación.
- **Centrado en las personas:** un modelo operativo tecnológico en el que la capacidad la aportan principalmente los empleados internos. Las características típicas incluyen:
  - Equipos internos de ingeniería y operaciones más amplios.
  - Fuerte implicación interna en las actividades de entrega y ejecución.
  - Puede que haya proveedores, pero los equipos internos realizan la mayor parte del trabajo.

Casos de uso:

- Comprender a qué patrón general se asemeja su organización.
- Explicar que te ves diferente de la media porque sigues intencionalmente un arquetipo diferente.

![Gráficos de radar arquetípicos que aparecen en el informe «Industry & OpEx Benchmarks» (Referencias del sector y del mercado) en Costing.](../../resources/images/it%20benchmarking_images/archetype-radar-chart.png)
