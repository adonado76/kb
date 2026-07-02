---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Prácticas recomendadas para la elaboración de informes maestros"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Informes principales"
source_path: "studio/new-uc/reference/report-studio-reference/master-report-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Prácticas recomendadas para la elaboración de informes maestros

Siga estas recomendaciones a la hora de crear y utilizar informes maestros para garantizar unos resultados óptimos:

**Directrices de diseño**

1. **Utiliza los informes principales como ayuda para el diseño** : por lo general, crea contenedores, como cuadros de grupo, en los que colocarás componentes como gráficos y tablas en los informes secundarios. Las plantillas son más eficaces cuando definen la estructura, no el contenido.
2. **Planifica cuidadosamente el uso de los componentes con pestañas** : si añades un componente con pestañas a un informe maestro, asegúrate de incluir todo el contenido necesario en cada pestaña dentro del propio informe maestro. No se pueden añadir componentes a pestañas concretas del informe secundario. Los componentes situados encima de un componente con pestañas en el informe secundario se mostrarán por encima de todas las pestañas.
3. **Utilice los cuadros de grupo únicamente con fines de estructura visual** : los cuadros de grupo añadidos a un informe principal pierden su funcionalidad de agrupación de componentes cuando se aplican a informes secundarios. Úsalos como bordes visuales y contenedores de diseño, no como mecanismos de agrupación funcional.
4. **Configure correctamente el contexto del botón** : si añade un botón a un informe maestro que utiliza texto Wiki sin especificar un «Data URL », la aplicación utilizará el informe actual (secundario) como contexto. Planifica tu ruta en consecuencia.

**Pautas de mantenimiento**

- **Documenta los informes maestros** : mantén una lista de los informes maestros existentes y de los informes secundarios que utilizan cada uno de ellos
- **Comprueba minuciosamente los cambios** : al actualizar un informe principal, comprueba cómo afectan los cambios a todos los informes secundarios antes de implementarlos
- **Utiliza convenciones de nomenclatura** : antepone a los nombres de los informes maestros el prefijo «Master -» o un identificador similar para distinguirlos fácilmente de los informes normales
- **Limitar el anidamiento de informes maestros** : aunque es posible aplicar informes maestros a otros informes maestros, no se recomienda debido a la complejidad que ello conlleva y a la posible confusión que puede generar

Consejo: Intenta que los informes principales sean lo más sencillos posible. Los masters complejos con muchos componentes pueden dificultar la creación de informes secundarios y afectar al rendimiento.

**Tema principal:** [Informes maestros](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
