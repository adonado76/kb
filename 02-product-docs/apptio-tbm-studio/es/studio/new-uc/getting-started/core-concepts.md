---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Conceptos fundamentales"
breadcrumb:
  - "TBM Studio"
  - "Cómo empezar"
source_path: "studio/new-uc/getting-started/core-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conceptos fundamentales

|  |  |
| --- | --- |
| **Tipo de contenido** | Conceptual |
| **Destinatarios** | Nuevos usuarios |
| **Tiempo de lectura** | 5 minutos |
| **Requisitos previos** | Ninguna |

Antes de empezar a utilizar TBM Studio, conocer estos seis conceptos básicos te ayudará a trabajar de forma más eficaz. Estos componentes se combinan para convertir los datos brutos sobre costes de TI en información útil para tu organización.

## Proyectos

Un **proyecto** es tu espacio de trabajo exclusivo en TBM Studio, donde organizas todo tu trabajo en TBM. Piensa en ello como un espacio de cálculo autónomo dentro del dominio de tu organización que contiene todo lo necesario para la modelización de costes y la elaboración de informes.

Dentro de un proyecto, encontrarás:

- Tablas de datos con la información que has importado y transformado
- Modelos de costes que muestran cómo circula el dinero por tu organización
- Métricas que calculan valores como el coste, el presupuesto y las previsiones
- Informes que ofrecen información útil a las partes interesadas

Es posible que su organización cuente con varios proyectos: quizá uno dedicado a la transparencia de los costes de TI, otro al cálculo de costes de las aplicaciones o proyectos independientes para las distintas unidades de negocio. En cada proyecto, los datos, los modelos y los informes están interrelacionados y son interdependientes.

## Tablas y datos

**Las tablas** son donde se almacenan tus datos en TBM Studio. Contienen la información bruta sobre tus operaciones informáticas y tus finanzas, que se incorporará a tus modelos de costes.

Las tablas proceden de dos fuentes:

**Las tablas de origen** se crean cargando archivos (como de CSV o o Excel) que contienen datos de sus sistemas: asientos del libro mayor, facturas de servicios en la nube, inventarios de activos o plantillas de personal.

**Las tablas de transformación** se crean a partir de tablas existentes mediante la aplicación de operaciones como el filtrado, la unión, la asignación o los cálculos. Estas transformaciones te permiten limpiar, enriquecer y remodelar tus datos para que se ajusten a la estructura que necesitan tus modelos.

Las tablas están organizadas por periodos de tiempo, lo que te permite seguir la evolución mes a mes. Cada tabla se compone de columnas (dimensiones como «Departamento» o «Aplicación») y puede incluir valores numéricos que se utilizarán en los cálculos.

## Modelos de

Un **modelo** muestra cómo se distribuyen los costes y otros indicadores por toda la organización. Es el motor que calcula el coste real de los servicios de TI distribuyendo los gastos desde su origen hasta los elementos que los consumen.

El núcleo de un modelo lo constituyen **los objetos del modelo**, cada uno de los cuales representa una capa distinta de la estructura de costes, como por ejemplo:

- Fuente de costes (de dónde procede el dinero, como tu libro mayor)
- Proveedores (externos)
- Servicios tecnológicos (componentes de infraestructura)
- Aplicaciones (los sistemas que utiliza tu empresa)
- Unidades de negocio (que son, en última instancia, las que consumen los servicios de TI)

Los modelos funcionan creando **asignaciones** que definen cómo se transfieren los costes de un objeto a otro. Por ejemplo, se pueden asignar los costes del centro de datos a los servidores en función del espacio de rack, luego asignar los costes de los servidores a las aplicaciones en función del consumo de CPU y, por último, asignar los costes de las aplicaciones a las unidades de negocio en función del número de usuarios.

**Los controladores** determinan la lógica de estas asignaciones. Un factor determinante puede ser un simple valor de columna (como el número de empleados), otra métrica (como el coste del mes anterior) o una fórmula. El modelo calcula automáticamente cómo se distribuyen los costes por cada nivel según estas reglas.

## Métricas

**Las métricas** son los indicadores que importan a tu organización. Definen qué se calcula y se supervisa a través de tus modelos.

Hay dos tipos de métricas:

1. **Las métricas del modelo** representan los valores que se tienen en cuenta en las asignaciones. Los más comunes son:
   - **Coste** : gastos reales incurridos
   - **Presupuesto** : Gastos previstos
   - **Previsión** : costes futuros estimados

   Puedes crear varias métricas de modelo para hacer un seguimiento de diferentes aspectos al mismo tiempo. Por ejemplo, se pueden imputar tanto los costes reales como los importes presupuestados a través de la misma estructura de modelo, lo que permite realizar un análisis de desviaciones.
2. **Las métricas calculadas** son fórmulas que obtienen nuevos valores a partir de métricas del modelo o tablas de datos. Algunos ejemplos habituales son la desviación (presupuesto menos coste), los totales acumulados del año, los costes unitarios (coste total dividido por el número de transacciones) y las tasas de crecimiento.

Las métricas respetan las reglas de formato (símbolos monetarios, decimales) y tienen en cuenta si se pueden sumar a lo largo de distintos periodos de tiempo o dimensiones organizativas.

## Informes

**Los informes** presentan los datos modelizados y las métricas calculadas a las partes interesadas de forma clara y concisa. Son la principal vía de acceso a la información de TBM.

Los informes pueden mostrar los datos de la siguiente manera:

- Tablas con filas, columnas y valores calculados
- Gráficos y visualizaciones
- Diagramas de flujo modelo (diagramas de Sankey) que muestran las vías de asignación de costes
- Paneles personalizados que combinan varias vistas

Los informes son interactivos: los usuarios pueden filtrar los datos, profundizar en los detalles, modificar los periodos de tiempo y exportar los resultados. Tú decides quién ve qué mediante permisos a nivel de informe y filtros de seguridad a nivel de fila.

Los informes pueden extraer información tanto de las tablas de transformación (datos sin procesar o procesados) como de los objetos de modelo (costes asignados), lo que te permite mostrar tanto los datos de origen como los resultados totalmente asignados en una misma vista.

## Entornos

TBM Studio utiliza tres **entornos** para gestionar el ciclo de vida del desarrollo y garantizar la calidad antes de que los cambios lleguen a los usuarios finales:

**«Desarrollo»** es tu espacio de trabajo personal. Cuando extraes un documento para editarlo —ya sea una tabla de datos, un modelo o un informe—, estás trabajando en tu entorno de desarrollo. Los cambios que realices se aplicarán únicamente a tu espacio de trabajo y no afectarán a los demás hasta que decidas compartirlos.

**La fase de integración** es donde se combinan todos los cambios realizados por los miembros del equipo. Cuando registras un documento, este pasa a la fase de preparación y se activa un cálculo. Aquí es donde se prueban y validan los cambios antes de publicarlos para los usuarios de los informes. Todos los miembros del equipo pueden ver el entorno de prueba para revisar el trabajo en curso.

**La producción** es el entorno en vivo que ven los usuarios finales. Solo los administradores pueden pasar los proyectos del entorno de pruebas al de producción. Este entorno solo debe contener cambios validados y probados. Por lo general, la producción se actualiza según un calendario controlado: diariamente, semanalmente o mensualmente, en función de las necesidades de su organización.

Este enfoque de tres niveles evita que los errores lleguen a los usuarios y ofrece un entorno seguro para la experimentación y el desarrollo.

## Cómo se complementan estos conceptos

Este es el flujo de trabajo típico que muestra cómo se relacionan estos conceptos:

1. **Cargar datos** → Crear tablas de origen en tu proyecto
2. **Transformar datos** → Crear tablas de transformación para limpiar y estructurar los datos
3. **Crear el modelo** → Crear objetos del modelo y definir asignaciones mediante controladores
4. **Definir métricas** → Configurar el coste, el presupuesto y las métricas calculadas
5. **Generar informes** → Presentar los costes asignados y las métricas a las partes interesadas
6. **Gestionar cambios** → Trabajar en el entorno de desarrollo, validar en el entorno de prueba, implementar en el entorno de producción

Cada paso se basa en el anterior, creando así un sistema de transparencia total en los costes.

## ¿Qué viene ahora?

Ahora que ya entiendes los conceptos básicos, estás listo para:

- Echa un vistazo a [la Guía de inicio rápido](qsg.html) para practicar de forma práctica cómo crear tu primer modelo de costes
- Echa un vistazo a [la descripción general de la interfaz de usuario](tbm-navigation.html) para familiarizarte con la ubicación de cada elemento
- Profundiza en conceptos específicos en la sección 4 (Conceptos y arquitectura):
  - **4.2 Arquitectura de datos:** para obtener más información sobre tablas y transformaciones
  - **4.3 Arquitectura de modelos** para una orientación integral en materia de modelización
  - **4.5 Ciclo de vida** de la compilación y la implementación: mejores prácticas para la gestión del entorno
