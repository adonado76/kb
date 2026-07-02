---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Configurar un proyecto en un idioma distinto del inglés"
breadcrumb: []
source_path: "cost-transparency/configuration/configproject.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configurar un proyecto en un idioma distinto del inglés

Para las versiones traducidas de Costing Standard y Planning, la configuración de las versiones traducidas es prácticamente la misma que para las versiones en inglés, con la salvedad de que los datos aparecen en el idioma que se haya suministrado a partir de los datos de origen. Sin embargo, algunas columnas requieren el inglés para mostrar adecuadamente el contenido.

Se aplica a: Costing Standard y IT Financial Management en TBM Studio 12.8.2 y posteriores, utilizando la plantilla v107 y posteriores

## Configuración de nombres de columna no ingleses

La siguiente información enumera los nombres de columna que deben permanecer en inglés durante la configuración. Consulte esta lista con regularidad a medida que Apptio vaya traduciendo nuevos productos.

### Procedimiento

1. Puede crear sus propios controladores o modificar los existentes para que admitan el idioma que desee.
2. Configure sus asignaciones utilizando columnas precisas en las relaciones de datos en lugar de utilizar columnas clave (esto también es válido para los proyectos en lengua inglesa).
3. Asegúrese de que los ajustes del proyecto para el tamaño del papel y la configuración regional están configurados adecuadamente para el idioma que desea.
4. La configuración regional de clasificación se mantiene separada de la configuración regional de moneda. Elija la configuración regional que mejor se adapte al idioma del usuario o deje la configuración regional en inglés si el idioma de destino no necesita una clasificación especial.
5. Conserve las siguientes columnas en inglés, independientemente del idioma del usuario:

   Para la PTI:

   - Datos maestros de fuentes de costes
   - Tipo de gasto
   - Tipo de plan
   - Datos maestros de trabajo
   - Es interno

   Para CT:

   - Ninguna.
