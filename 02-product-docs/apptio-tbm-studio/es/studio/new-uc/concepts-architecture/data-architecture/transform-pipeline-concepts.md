---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Conceptos de la cadena de transformación"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura de datos"
source_path: "studio/new-uc/concepts-architecture/data-architecture/transform-pipeline-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conceptos de la cadena de transformación

El canal de transformación es el motor de procesamiento que constituye el núcleo de Data Studio. Cada tabla cuenta con un proceso de transformación: una secuencia de pasos que procesa los datos desde su formato bruto, tal y como se importan, hasta convertirlos en un resultado limpio y estructurado, listo para la modelización de costes.

## Pasos de la transformación

Un paso de transformación es una operación única de procesamiento de datos dentro del flujo de trabajo. Los pasos se ejecutan en orden, de arriba abajo, y el resultado de cada paso se convierte en la entrada del siguiente. Puedes añadir, eliminar y reordenar pasos para crear exactamente la lógica de procesamiento que necesitas.

Cada proceso de procesamiento de tablas comienza con dos pasos automáticos:

- **Fuente:** Define de dónde proceden los datos (carga de un archivo, tabla existente, conector de DataLink o tabla editable).
- **Tabla:** Muestra el resultado final de todo el proceso. Este paso siempre aparece al final.

En el caso de las fuentes de carga de archivos, se añaden automáticamente dos pasos adicionales:

- **Subir:** te permite seleccionar y gestionar el archivo subido.
- **Importación:** controla cómo se analiza el archivo: detección de la fila de encabezado, fila de inicio de datos, detección del tipo de columna y configuración de los delimitadores.

## Tipos de pasos de transformación disponibles

Puedes añadir los siguientes pasos al flujo de trabajo de cualquier tabla para transformar los datos:

|  |  |  |
| --- | --- | --- |
| **Tipo de escalón** | **Para qué sirve** | **Caso de uso habitual** |
| Columnas del mapa | Adapta la salida de la tabla para que se ajuste a un esquema estándar (como la taxonomía de ATUM ) y asigna las columnas del origen al destino | Asignación de datos de GL a categorías de grupos de costes |
| Unir | Combina datos de dos o más tablas en filas únicas basándose en la coincidencia de valores en columnas comunes | Ampliar los datos de costes con información de proveedores procedente de una tabla independiente |
| Añadir | Apila las filas de una tabla debajo de las filas de otra tabla | Combinar los archivos del libro mayor mensuales en un único conjunto de datos |
| Filtro | Elimina filas en función de condiciones aplicadas a una o varias columnas | Excluir del análisis los centros de coste no relacionados con las tecnologías de la información |
| Fórmula | Crea nuevas columnas calculadas, cambia los tipos de columna o sobrescribe los valores existentes | Calcular una clasificación derivada o convertir una divisa |
| Grupo | Agrupa las filas según los valores de una o varias columnas de texto, y agrega los valores numéricos | Resumen de transacciones por centro de coste |
| Partición de fecha | Utiliza los valores de fecha del archivo (en filas o columnas) para distribuir los datos a lo largo de distintos periodos de tiempo | Dividir una exportación del libro mayor que abarca varios meses en períodos mensuales individuales |
| Ocultar y renombrar | Oculta las columnas innecesarias o cambia el nombre de las columnas para mayor claridad | Eliminar los identificadores internos antes de que los datos entren en el modelo |
| Asignar filas | Utiliza el aprendizaje automático y reglas creadas por los usuarios para asignar datos a conceptos de taxonomía | Automatización de la asignación de grupos de costes mediante clasificación basada en aprendizaje automático |
| Aplanar la jerarquía | Añade una columna por cada nivel de una jerarquía de datos | Habilitar el filtrado basado en segmentadores en estructuras organizativas jerárquicas |

## Orden de ejecución de los pasos

Los pasos de transformación se ejecutan estrictamente de arriba abajo. El resultado de un paso se convierte en la entrada del siguiente. Este modelo secuencial implica que el orden de los pasos es importante:

- Si se coloca un paso de filtrado antes de una unión, se reducirá el número de filas antes de la operación de unión, lo que podría mejorar el rendimiento.
- Un paso de fórmula situado después de una unión puede hacer referencia a columnas de ambas tablas unidas.
- El paso «Map Columns» suele aparecer al final del proceso, una vez finalizadas las tareas de limpieza y enriquecimiento.

Puedes arrastrar los pasos para reordenarlos en el flujo de trabajo, salvo algunos pasos fijos (Fuente, Carga, Importación y Tabla), que deben permanecer en sus posiciones asignadas.

Nota:

**Buenas prácticas**

Organiza tu proceso de forma que el filtrado y la reducción de datos se realicen al principio, las uniones y el enriquecimiento se lleven a cabo en la parte central, y la asignación y el formato final se realicen al final. Este patrón mejora tanto la claridad como el rendimiento.

## Linaje de datos

El linaje de datos se refiere a la capacidad de rastrear un dato desde su origen (el archivo fuente cargado) a través de todas las transformaciones que sufre, hasta llegar al resultado final del modelo y al informe.

Comprender el linaje de los datos es importante por varias razones:

- **Precisión:** cuando un informe muestra una cifra inesperada, el historial te ayuda a rastrear el origen del problema, ya sea en los datos de origen, en un paso de transformación o en una regla de asignación del modelo.
- **Auditabilidad:** Los equipos de finanzas y cumplimiento normativo deben verificar que la asignación de costes se pueda rastrear hasta las transacciones originales.
- **Análisis de impacto:** antes de modificar una transformación, puedes seguir el linaje hacia adelante para comprender qué objetos del modelo e informes se verán afectados.

TBM Studio realiza un seguimiento del historial a través del modelo de pasos secuenciales del proceso. Dado que el resultado de cada paso se utiliza como entrada del siguiente, la cadena de transformaciones es siempre explícita y se puede examinar. El diagrama del modelo en Model Studio amplía aún más este linaje al mostrar cómo fluyen los datos desde las tablas de transformación, pasando por los objetos de asignación, hasta las unidades de negocio finales.

## Mejores prácticas de diseño de Transform

- **Mantén las transformaciones maestras centralizadas:** crea un único conjunto de datos maestro (como un «Cost Source Master») que unifique varios archivos de origen. Las transformaciones posteriores y los objetos de modelo deben hacer referencia a este archivo maestro en lugar de a los archivos fuente individuales.
- **Evita duplicar la lógica:** si varias tablas necesitan la misma transformación, crea una transformación intermedia compartida en lugar de repetir la lógica en cada canalización.
- **Comprueba los tipos de columna desde el principio:** una tipificación incorrecta de las columnas (por ejemplo, un campo numérico detectado como «Etiqueta») provoca errores que se propagan a las etapas posteriores. Confirma los tipos durante el proceso de importación.
- **Utiliza nombres descriptivos:** asigna nombres claros a las tablas y los pasos para que los demás miembros del equipo puedan comprender el proceso sin tener que revisar la configuración de cada paso.
- **Supervisión de tablas no utilizadas:** TBM Studio puede identificar las tablas a las que no hace referencia ningún informe ni objeto de modelo. Revisa y limpia periódicamente las tablas que no se utilicen para reducir la complejidad.
