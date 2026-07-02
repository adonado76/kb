---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Exportación de datos"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
source_path: "studio/new-uc/howtoguides/work-with-data/data-export.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Exportación de datos

**Tipo de contenido:** Guía práctica

**Destinatarios:** equipos de TI y finanzas, administradores y desarrolladores

**Tiempo de preparación:** 30-45 minutos (varía según el método)

**Requisitos previos:** Acceso a TBM Studio con los permisos adecuados; conocimientos básicos de « Data Studio » (véase la sección 3.1.1 )

## Visión general

TBM Studio ofrece potentes funciones para extraer los datos de costes del sistema e importarlos a herramientas externas, como almacenes de datos, plataformas de inteligencia empresarial y aplicaciones personalizadas. En esta sección se describen dos métodos principales para exportar datos:

- [Tablas publicadas](htg-config-pt.html) : conjuntos de datos preconfigurados y con esquema estable, diseñados para su extracción programada por parte de sistemas externos
- [Acceso a la API](htg-api.html) : recuperación de datos mediante programación para integraciones personalizadas y automatización

Saber cuándo utilizar cada método te garantiza que implementes la estrategia de exportación de datos más eficiente y fácil de mantener para tu organización.

## Elegir el método de exportación

Antes de entrar en detalles sobre la configuración, decide qué método de exportación se adapta mejor a tu caso de uso. La decisión depende de los usuarios de los datos, los requisitos de actualización y las capacidades técnicas.

## Guía de decisión: Tablas publicadas frente a API

Utiliza esta guía para determinar cuál es el enfoque más adecuado para tu caso:

**Selecciona «Tablas publicadas» cuando:**

- Debes introducir datos en herramientas de BI externas como Power BI o Tableau
- Los usuarios de datos necesitan un esquema estable y predecible que no cambie con frecuencia
- Quieres que los datos se actualicen automáticamente después de cada ciclo de cálculo
- Varios sistemas posteriores necesitan el mismo conjunto de datos seleccionado
- Estás sustituyendo las exportaciones manuales de informes puntuales por una automatización controlada
- Tu equipo de BI prefiere conectarse a un punto final conocido en lugar de crear consultas personalizadas

**Elige el acceso a la API cuando:**

- Necesitas flexibilidad para consultar diferentes tablas o informes cuando lo necesites
- Tu integración requiere una lógica personalizada o una recuperación de datos condicional
- Estás desarrollando una aplicación personalizada que utiliza datos de TBM Studio
- Necesitas extracciones de datos puntuales o esporádicas
- Tu canalización ETL ya se encarga de la transformación y la programación de los datos
- Necesitas datos de varias tablas combinados de forma personalizada

**Elige ambas opciones cuando:**

- Las tablas publicadas alimentan tus paneles de BI principales (estables, programados)
- Complementos de la API con consultas ad hoc o extracciones de tablas que no merece la pena publicar

## Referencia rápida: Comparación de métodos

|  |  |  |
| --- | --- | --- |
| **característica** | **Tablas publicadas** | **API** |
| **Uso principal** | Alimentaciones programadas a herramientas de BI y almacenes de datos | Recuperación de datos programada y bajo demanda |
| **Estabilidad del esquema** | Válido hasta que se modifique expresamente | Depende de la tabla o el informe de origen |
| **Actualidad de los datos** | Actualizaciones tras cada cálculo | En tiempo real (consulta de datos actuales) |
| **Configuración** | Configuración basada en la interfaz de usuario | Código de script o de aplicación |
| **Mantenimiento** | Bajo (configurar y olvidarse) | Medio (requiere mantenimiento del código) |
| **Ideal para** | Power BI, Tableau, Snowflake feeds | Aplicaciones personalizadas, herramientas ETL, automatización |

## Tareas relacionadas

- [Importar datos](data-import-mgmt.html) : Importar datos desde archivos
- [Transformar datos](transform-enrich-data.html) : transformar y limpiar datos
- [Informes de compilación](../create-reports/report-basic.html) : Véase la sección 3.3 (Crear informes)
- Referencia detallada de la API: consulte la sección 5.5 (Referencia de la API)

- **[Guía práctica: Configurar tablas publicadas](../../../../studio/new-uc/howtoguides/work-with-data/htg-config-pt.html)**
- **[Guía práctica: Exportar datos a través de la API](../../../../studio/new-uc/howtoguides/work-with-data/htg-api.html)**
