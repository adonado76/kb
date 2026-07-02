---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Añadir datos de la unidad de negocio"
breadcrumb: []
source_path: "boit/business-unit-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Añadir datos de la unidad de negocio

Si el componente **CT - Unidades de Negocio** ha sido instalado y configurado en Transparencia de Costes, omita este paso. Si no se ha instalado el componente, deberá añadir datos a la tabla Datos maestros de asignación de unidades de negocio.

1. Cargue un archivo que contenga los datos de la empresa en una tabla del proyecto Billing Standard . Coloque la tabla en la categoría **General** y nómbrela `Business Unit
   Data` . Consulte [Cargar un archivo de datos](../studio/data_studio/upload-data-file.html "Se aplica a: TBM Studio 12.0 y posteriores. TBM Studio acepta datos de archivos planos en formatos separados por comas, tabulaciones, tuberías, tildes, dos puntos y punto y coma. Antes de poder cargar datos, debe crear una tabla en la que se cargarán los datos, si no existe ya.") para obtener más información.
2. Añada la tabla Datos de unidad de negocio a la tabla Datos maestros de asignación de unidad de negocio. Para más información, véase [Añadir datos](../studio/data_studio/append-data.html "Se aplica a: TBM Studio 12.0 y posteriores").

Datos necesarios de los datos maestros de asignación de unidades de negocio

- **Unidad de negocio** - Elemento o segmento lógico de una empresa que representa una función empresarial específica y un lugar en el organigrama. La unidad de negocio está bajo el dominio de un directivo. En Billing Standard, la Unidad de Negocio es el nivel 1 en la jerarquía de la organización y el Departamento es el nivel 2.
- **Ident** - Un identificador único para cada unidad de negocio.

Datos recomendados de los datos maestros de asignación de unidades de negocio

- **Plantilla de contratistas** - Número de contratistas externos que trabajan en la unidad de negocio.
- **Plantilla** - Número de empleados a tiempo completo o mano de obra no contratada que trabajan en la unidad de negocio.
- **Ubicación** - La ubicación física/geográfica de la unidad de negocio. En los informes de unidades de negocio, la ubicación se utiliza para agrupar datos y proporcionar un nivel adicional de granularidad.

Datos opcionales de los datos maestros de asignación de unidades de negocio

- **Órgano** de gobierno - El órgano de gobierno es una entidad de mayor nivel en la estructura organizativa que la unidad de negocio.   
   **Ejemplos** : entidades operativas, entidades internacionales.
