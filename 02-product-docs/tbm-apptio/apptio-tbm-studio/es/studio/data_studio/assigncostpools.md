---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Asignar grupos de costes con aprendizaje automático"
breadcrumb: []
source_path: "studio/data_studio/assigncostpools.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Asignar grupos de costes con aprendizaje automático

**Se aplica a** : TBM Studio 12.7 y posteriores. TBM Studio 12.7 y más tarde puede utilizar el aprendizaje automático para acelerar la configuración de Costing Standard . Anteriormente, la asignación de cuentas a conjuntos de costes requería la creación manual de archivos de asignación con asignaciones individuales para llegar a los conjuntos de costes estándar de la taxonomía. Ahora, el aprendizaje automático mapea la mayoría de las cuentas por usted en milisegundos.

Vea este vídeo de demostración de Apptio Education Services: [Machine Learning en 12.7](https://community.apptio.com/videos/2375 "(se abre en una pestaña o una ventana nueva)"). O consulte [todos los vídeos de Apptio](https://community.apptio.com/docs/DOC-7714 "(se abre en una pestaña o una ventana nueva)").

Apptio recopila información y desarrolla modelos de predicción. A medida que se clasifican más datos, estos modelos aprenden con el tiempo.

He aquí una visión general de cómo funciona el aprendizaje automático en Apptio.

1. La información existente en Apptio se clasifica en función del resultado deseado, como el pool de costes, y se introduce en el servicio de formación (alojado en AWS ).
2. Apptio identifica los algoritmos adecuados, determina los mejores parámetros y establece un modelo de predicción. El modelo se publica en el catálogo.
3. A continuación, puede acceder a ese modelo, aplicarlo a sus datos y revisar los resultados directamente en Apptio. Cuando se hayan revisado las predicciones como parte de su proceso de configuración, los datos ahora clasificados se enviarán a nuestro servicio de formación.
4. Los nuevos datos hacen que el servicio de formación anonimice y genere un nuevo modelo. Apptio sigue y ajusta los modelos a lo largo del tiempo para mejorar la calidad y cantidad de nuestras predicciones.
5. Cuando un modelo cumple nuestra revisión de calidad, se publica en el catálogo.
6. Puede actualizarse al último modelo si lo desea.

He aquí un diagrama del proceso:

![](../../resources/images/studio_images/studioimages/studio_diagram_download%20model.png)

**VER TAMBIÉN** :

- [Columnas del mapa](mapcolumns.htm "(se abre en una pestaña o una ventana nueva)")
- [Configurar el aprendizaje automático para los grupos de costes](configuremachinelearning.htm "(se abre en una pestaña o una ventana nueva)")
- [Preguntas frecuentes sobre las columnas del mapa](faqmapcolumns.htm "(se abre en una pestaña o una ventana nueva)")
