---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Buenas prácticas de navegación"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Navegación"
source_path: "studio/new-uc/reference/report-studio-reference/navigation-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Buenas prácticas de navegación

**Patrones de navegación coherentes**

- Coloca los controles de navegación en los mismos lugares en todos los informes (por ejemplo, siempre en la esquina superior izquierda)
- Utiliza los mismos estilos y colores de botones para acciones de navegación similares
- Incluir opciones de navegación hacia atrás (botón «Atrás» o ruta de navegación) en los informes de desglose
- Incluye etiquetas claras e información emergente que describan el destino de la navegación

**Diseño de la jerarquía de navegación**

- Diseña rutas de desglose que sigan jerarquías lógicas de datos (de lo general a lo particular)
- Limita la profundidad de la navegación a 3 o 4 niveles para evitar que el usuario se desoriente
- Crea todos los informes como informes de primer nivel para simplificar la gestión de los enlaces
- Rutas de navegación por los documentos para los responsables del mantenimiento de informes

**Consideraciones sobre el rendimiento**

- Evita acceder a informes con cálculos complejos que puedan provocar retrasos
- Mantén los informes de los cuadros de diálogo modales sencillos, sin filtros ni selectores complejos
- Considera la posibilidad de utilizar la actualización diferida para los informes que contengan muchos destinos de navegación
- Prueba las rutas de navegación con volúmenes de datos realistas

**Solución de problemas de navegación**

**Cómo encontrar la ruta correcta del informe:**

1. Accede al informe de destino
2. Haz clic con el botón derecho del ratón en una tabla y selecciona «Mostrar API» URL
3. La ruta mostrada se puede adaptar a la sintaxis de enlaces al estilo wiki
4. Elimina el prefijo «.View:» y utiliza la ruta restante

**Tema principal:** [Componentes del informe: Navegación](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
