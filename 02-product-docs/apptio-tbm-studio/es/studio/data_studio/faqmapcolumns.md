---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Preguntas frecuentes sobre las columnas del mapa"
breadcrumb: []
source_path: "studio/data_studio/faqmapcolumns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Preguntas frecuentes sobre las columnas del mapa

**Se aplica a** : TBM Studio 12.7 y posteriores

Consejo: Si no encuentra aquí lo que busca, consulte los mensajes del [Foro de preguntas y respuestas de TBM Studio 12](https://community.apptio.com/community/apptio/product-central/apptio-qa-forum "(se abre en una pestaña o una ventana nueva)") o [envíe una pregunta al Foro](https://community.apptio.com/community/apptio/product-central/apptio-qa-forum "(se abre en una pestaña o una ventana nueva)").

## Transformar tuberías y mapear columnas

**¿Por qué no veo todas mis columnas al hacer un mapa?**

Sólo se pueden asignar columnas del mismo tipo. Por lo tanto, cuando seleccione una columna para una columna de destino con un tipo de etiqueta, sólo aparecerán sus columnas con un tipo de etiqueta. Si su carga inicial no contenía datos (sólo cabeceras), no se seleccionará ningún tipo por defecto. Los códigos suelen importar como numéricos. En ambos casos, vaya al paso **Importar** para anular el tipo de columna por defecto.

Cuando seleccione el tipo Fecha en Importar, rellene el formato de la fecha a la derecha de los selectores de tipo.

**Ejemplo:** Formato de fecha

```
yyyy-mm-dd:
      2018-09-26
```

.

**Quiero unir otra tabla a esta, pero necesito hacer algo de lógica en los resultados. ¿Qué debo hacer?**

Utilice el paso de canalización Unir justo antes de Asignar columnas para devolver columnas vinculadas a la tabla primaria por una columna de información coincidente. Cuando sea posible, complete cualquier lógica en la otra mesa. Puede seleccionar "Añadir columna personalizada" para añadir la columna a la salida, o asignarla a una columna de destino existente disponible.

Para "Is Labor" y "Is Depr": Los Datos Maestros del Plan General de Contabilidad calcularán estos campos en v107. Alternativamente, deje las columnas en blanco y cambie la asignación para utilizar el pool o subpool de costes para filtrar la fuente de las asignaciones.

Sin embargo, si necesita completar la lógica basándose en columnas tanto de la tabla primaria como de la tabla unida, utilice una fórmula Lookup() en el paso de canalización Fórmulas. Todavía puede utilizar el paso Join para devolver el resto de las columnas, si es necesario.

**¿Puedo cambiar el orden de los pasos Unir y Asignar columnas?**

En este momento, el paso Unir aparecerá junto al paso Modelo o al paso Mapear columnas (seleccione uno u otro).

Asignar Columnas siempre será el paso anterior a Tabla, a menos que haya un paso Asignar Pools de Costes. Esencialmente, todo lo que hay después de Columnas del mapa forma parte de la oferta de contenidos. Sin embargo, puede tener tantos pasos o transformaciones antes del paso Mapear columnas.

## Tablas mapeadas y el conjunto de datos maestros

**Veo una columna Tabla de origen en el conjunto de datos maestros, pero no he asignado nada a ella. ¿De dónde procede?**

Apptio añade automáticamente una columna con el nombre de la tabla que envió datos a un conjunto de datos maestros a través de Map Columns. Esto le permite rastrear más rápidamente sus datos desde el modelo hasta los datos de origen. Sólo los datos añadidos a través de Columnas de Mapa tienen esta información. Debe añadir manualmente cualquier dato añadido a la información o ésta quedará en blanco.

**VER TAMBIÉN** :

- [Columnas del mapa](mapcolumns.htm "(se abre en una pestaña o una ventana nueva)")
- [Asignar grupos de costes con aprendizaje automático](assigncostpools.htm "(se abre en una pestaña o una ventana nueva)")
- [Configurar el aprendizaje automático para los grupos de costes](configuremachinelearning.htm "(se abre en una pestaña o una ventana nueva)")
