---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Patrones de integración de datos"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura de datos"
source_path: "studio/new-uc/concepts-architecture/data-architecture/data-integrations-patterns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Patrones de integración de datos

Los datos pueden introducirse en TBM Studio mediante varios métodos de integración. La elección adecuada depende del volumen de datos, la frecuencia de actualización, las capacidades técnicas y los requisitos de gobernanza.

## Integración basada en archivos

La carga de archivos es la forma más habitual y sencilla de importar datos a TBM Studio.

**Carga manual de archivos**

Los usuarios crean una tabla en Data Studio y suben un archivo de CSV o Excel a través de la interfaz basada en navegador. La plataforma analiza el archivo, detecta el esquema y carga los datos en el proceso de transformación.

- **Ideal para:** cargas iniciales de datos, datos de referencia puntuales o actualizaciones puntuales.
- **Formatos compatibles:**CSV, TSV, XLS, XLSX. Los delimitadores admitidos son la coma, la tabulación, la barra vertical, la tilde, los dos puntos y el punto y coma.

Consejo: Los nombres de los archivos solo deben contener un punto (antes de la extensión). Por ejemplo, example\_data.xlsx es válido, pero example.data.xlsx provocará un error de carga.

**Procesamiento programado de archivos**

Para las cargas de datos periódicas, se configura el ciclo de actualización de la tabla (versiones mensuales, anuales, etc.) y subir archivos con regularidad. TBM Studio comprueba si se han realizado las subidas previstas y puede enviar notificaciones por correo electrónico cuando los datos se retrasan.

- Ideal para: archivos de contabilidad general mensuales, actualizaciones presupuestarias o cualquier dato que cambie siguiendo un ciclo predecible.

**Consideraciones sobre los formatos de archivo**

TBM Studio utiliza un analizador sintáctico de Excel mejorado (que se activa automáticamente para los nuevos clientes a partir de la versión 12.11.16 ) que lee directamente los valores numéricos sin procesar, sin tener en cuenta el formato de Excel. Esto garantiza una mayor precisión numérica y un tratamiento coherente de la fecha y la hora mediante la conversión al formato de época. Ten en cuenta que es posible que los archivos de Excel que contengan formato especial o macros no se carguen correctamente; el formato debe aplicarse mediante pasos de transformación tras la carga.

## Integración basada en API

La API de la plataforma « Apptio » ofrece una alternativa programática a la carga manual de archivos. Puedes automatizar la carga y descarga de datos mediante sencillos comandos de HTTP integrados en cualquier programador de tareas o aplicación.

La API utiliza una interfaz basada en el modelo « URL »:

- **Carga:** envía datos mediante el método POST a URL especificando el dominio, el proyecto, la tabla, el periodo de tiempo y la acción (añadir o sobrescribir).
- **Descargar:** Obtener datos de tablas o componentes de informes en formato Excel o TSV.

Entre las ventajas de la integración de API se incluyen la facilidad de implementación (no es necesario instalar ningún software), la compatibilidad con todos los sistemas de datos de la empresa y la automatización mediante programadores de tareas.

Nota:

**Cuándo utilizar la API y cuándo utilizar archivos**

Utiliza la API cuando necesites cargas de datos automatizadas y repetibles que se integren con los procesos ETL o los programadores de tareas existentes. Utilice la carga manual de archivos para cargas de datos puntuales o cuando la fuente de datos no admita la extracción automática.

## DataLink Conexiones

DataLink (Classic) ofrece un marco de conectores gestionados para importar datos desde bases de datos y aplicaciones externas sin necesidad de crear scripts personalizados. Incluye un agente independiente que se puede instalar en las propias instalaciones para acceder a fuentes de datos internas.

DataLink es compatible con:

- Conexiones directas a bases de datos para extraer datos de sistemas empresariales
- Ejecución programada por hora o por evento
- Integración con ServiceNow y otras plataformas de gestión de servicios de TI (ITSM) para enviar datos sobre el coste total de propiedad (TCO)

DataLink resulta especialmente útil para aquellas organizaciones que buscan un enfoque sin código para la integración de datos o que necesitan extraer datos de sistemas protegidos por cortafuegos.

## Las tablas editables como patrón de integración

Para pequeños volúmenes de datos de referencia o asignaciones de clasificación, las tablas editables constituyen un método de integración sencillo. Los usuarios introducen los datos directamente a través de la interfaz del informe, y estos se incorporan al proceso de transformación y al modelo de costes mediante el mecanismo de publicación.

- Ideal para: atributos de centros de coste, asignaciones de mano de obra, anotaciones presupuestarias y otros datos en los que el criterio humano es la fuente principal.

## Guía para la toma de decisiones sobre integración

Utiliza esta guía para elegir el método de integración adecuado:

|  |  |  |
| --- | --- | --- |
| **Situación** | **Enfoque recomendado** | **Aspectos clave a tener en cuenta** |
| Carga de datos puntual o ad hoc | Carga manual de archivos | Es sencillo, no requiere configuración |
| Datos programados periódicamente (contabilidad general mensual) | Carga automática de archivos o API | Configurar el ciclo de actualización y la supervisión de la vigencia |
| Integración de un proceso ETL automatizado | API de la plataforma | HTTP basado en; se integra con programadores de tareas |
| Acceso a bases de datos locales | DataLink (Clásico) | Requiere la instalación de un agente local |
| Integración de ITSM (por ejemplo, ServiceNow ) | DataLink conector | Conector preconfigurado para la salida de datos de TCO |
| Datos de referencia breves o clasificaciones | Tablas editables | Introducido manualmente; canal de publicación de feeds |
| Exportar datos del modelo a herramientas de BI externas | Tablas publicadas | Punto final de API estable; controlado por esquema |
