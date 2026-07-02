---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración de impresión y exportación"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Propiedades de informe"
source_path: "studio/new-uc/reference/report-studio-reference/print-export-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración de impresión y exportación

Los ajustes de diseño de impresión determinan el aspecto que tendrán los informes al exportarlos a formato PDF o al imprimirlos. Estos ajustes se pueden personalizar para cada informe con el fin de optimizar el resultado impreso.

**Acceder al modo de diseño de impresión**

1. Echa un vistazo al informe
2. En la pestaña Inicio, haz clic en Ver > Diseño de impresión
3. La pestaña «Diseño de impresión» queda disponible para su configuración

**Opciones de configuración de página**

|  |  |
| --- | --- |
| **Opción** | **Descripción** |
| Tamaño de página | Selecciona el tamaño de papel en el menú desplegable (Carta, A4, Legal, etc.) |
| Orientación | Orientación de la página: vertical o horizontal |
| Márgenes | Configurar los márgenes superior, inferior, izquierdo y derecho |
| Flujo | Manual: Los componentes permanecen en el lugar donde se colocan. Vertical: los componentes se disponen en una sola columna. Horizontal: los componentes se disponen en filas con el número máximo de componentes por fila. |

**Encabezados y pies de página**

**Opciones de encabezado:**

- Mostrar en todas las páginas o solo en la primera página
- Cambia el tamaño arrastrando los bordes del encabezado
- Dar formato al texto utilizando etiquetas HTML
- Utiliza texto dinámico (por ejemplo, <%=CurrentDate( )%> para el periodo actual)

**Opciones de pie de página:**

- Personalizar las secciones del pie de página de la izquierda, el centro y la derecha
- Escriba el texto del pie de página o déjelo en blanco si no desea incluirlo
- El texto dinámico no es compatible con los pies de página

**Opciones de impresión de componentes**

|  |  |
| --- | --- |
| **Opción** | **Descripción** |
| Fijar/Desfijar | Fija un componente (como los segmentadores) al final del informe para conservar los filtros aplicados |
| Mostrar/ocultar | Ocultar componentes específicos en la impresión. Utiliza el campo «Filtro» para buscar componentes en listas largas. |

**Opciones de exportación**

Los informes se pueden exportar mediante los siguientes métodos:

|  |  |
| --- | --- |
| **Método de exportación** | **Descripción** |
| Descargar directamente en formato PDF | Genera un archivo PDF y lo abre en el navegador o lo descarga, según la configuración del navegador |
| Incluir un enlace al PDF en el correo electrónico | Envía un correo electrónico con un enlace para acceder al PDF generado |
| Adjuntar un PDF al correo electrónico | Envía un correo electrónico con el PDF como archivo adjunto |

Nota: *Cuando se comparten informes mediante un enlace por correo electrónico, los destinatarios ven el informe con los mismos filtros, segmentadores, selectores y intervalo de fechas que se aplicaron en el momento de compartirlo.*

**Tema principal:** [Propiedades del informe](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
