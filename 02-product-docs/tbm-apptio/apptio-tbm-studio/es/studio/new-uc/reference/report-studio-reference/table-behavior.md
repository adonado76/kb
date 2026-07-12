---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Comportamiento de la tabla"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Tablas"
source_path: "studio/new-uc/reference/report-studio-reference/table-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Comportamiento de la tabla

**Columnas de congelación**

Fija las columnas para que sigan visibles al desplazarte horizontalmente. Las columnas congeladas se desplazan hacia el extremo izquierdo.

**Para congelar una columna:**

- Selecciona la columna y haz clic en el icono «Congelar» de la pestaña «Datos», O BIEN
- Haz clic con el botón derecho del ratón en el encabezado de la columna > Formato > Fijar columna.

Para desbloquear: haz clic con el botón derecho del ratón en el encabezado de la columna > Formato > Desbloquear columna.

**Paginación**

Las tablas con muchas filas muestran una barra de paginación para facilitar la navegación. Configura la paginación utilizando la opción «Máximo de filas» en el cuadro de diálogo «Propiedades».

|  |  |
| --- | --- |
| **Opción** | **Comportamiento** |
| Número máximo de filas = 20 | Muestra 20 filas por página con barra de navegación. |
| Ocultar barra de paginación = Sí | Muestra solo las primeras filas, sin navegación. |
| Caso de uso | Listas de los 10 mejores, tablas resumen en las que no conviene tener que desplazarse por la pantalla. |

**Configuración de desglose**

Permitir la navegación desde los valores de la tabla a los informes detallados. Los enlaces aparecen en azul.

**Para configurar el desglose:**

1. Selecciona una columna de la tabla.
2. Haz clic en la pestaña «Ad Hoc» y, a continuación, en «Drill» en la sección «Navegación».
3. Configurar las propiedades de navegación.

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Activar navegación | Convierte los valores de la columna en enlaces activos. |
| Abrir en ventana emergente | Abre el informe de destino en una ventana emergente. El usuario está a punto de volver. |
| Informe de objetivos | El informe al que se accede al hacer clic. |
| El contexto incluye | Qué contexto de datos se debe pasar: filtro de filas, valores de columna, selección. |

**Nota:** Los enlaces de los informes solo funcionan con tablas basadas en objetos. Las tablas de transformación no admiten la navegación de desglose.

**Opciones de exportación**

Las tablas se pueden exportar como parte de los informes en varios formatos.

|  |  |
| --- | --- |
| **Formato** | **Detalles** |
| PDF | Exporta desde la pestaña Inicio > Exportar > PDF. Utiliza el modo «Diseño de impresión» para crear diseños personalizados. Las tablas de varias páginas son compatibles con la opción «Imprimir todas las páginas». |
| Excel | Las columnas mantienen el orden de la configuración del informe. Se han añadido las columnas sin configurar. Las tablas de árbol se exportan como tablas planas con sangría. |
| Correo electrónico | Los informes se pueden enviar por correo electrónico como archivos PDF adjuntos o como enlaces. Configurar a través de la suscripción por correo electrónico. |

**Actualización diferida**

En el caso de informes complejos con muchos controles interactivos, configura el comportamiento de actualización para evitar actualizaciones excesivas de la pantalla.

|  |  |
| --- | --- |
| **Opción** | **Descripción** |
| Retardo de actualización: 3s | El sistema espera 3 segundos antes de actualizar tras la interacción del usuario. Configuración predeterminada. |
| Renovación manual | El usuario debe hacer clic en «Actualizar» para actualizar la página. Ideal para informes con numerosos filtros y selectores. |

Configuración global: pestaña «Proyecto» > «Configuración del proyecto» > «Actualización diferida». Modificación por informe: Informe de caja > pestaña Informe > Ajustes de actualización.

**Tema principal:** [Componentes del informe: Tablas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
