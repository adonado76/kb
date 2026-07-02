---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Cloud Daily/Hourly Reports - Ampliación o modificación ( 12.5 y anteriores)"
breadcrumb: []
source_path: "cost-transparency/configuration/clouddailyhourlyreports.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cloud Daily/Hourly Reports - Ampliación o modificación ( 12.5 y anteriores)

Los informes diarios/hora se basan en un formato de datos que permite un almacenamiento y consulta rápidos y eficientes de conjuntos de datos de gran volumen (como las facturas de nube muy granulares, como el informe de costes y uso de AWS ). En consecuencia, la ampliación del esquema de los conjuntos de datos implicados y la modificación de los informes creados a partir de dichos conjuntos de datos requieren cierta configuración

Se aplica a: Cloud en Costing Standard en TBM Studio 12.3.3 y posteriores; Cloud Business Management en TBM Studio 12.5.x y anteriores

Los datos Diarios/Horarios se almacenan en un formato diferente, separado del resto de datos de Apptio. El objeto sobre el que se construyen los informes se llama dbr\_daily, que se puede encontrar en la sección de tablas de TBM Studio, pero, debido al altísimo volumen de datos y al nuevo formato de los mismos, no se pueden realizar ciertas acciones:

- No podrá ver los datos en TBM Studio.
- No puede añadir elementos a la cadena de transformación (con la excepción explicada en la sección "Añadir nuevos atributos personalizados", más abajo).
- No se pueden añadir transformaciones al conjunto de datos.

## Ampliación del esquema diario/horario

Para utilizar los atributos out-of-the-box (la forma más rápida de ver los datos específicos de su organización):

### Procedimiento

1. Mapear desde las columnas de las facturas de los proveedores, como Cuentas o Etiquetas, a los atributos CBM listos para usar.

   Por ejemplo, si tiene una etiqueta de usuario llamada Propietario, asigne esa etiqueta al atributo existente Propietario del sistema.
2. Para obtener más información, consulte Asignar etiquetas de AWS al esquema de Apptio o Etiquetar valores en Azure al esquema de Apptio.
