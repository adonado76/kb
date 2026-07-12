---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración de desglose"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Navegación"
source_path: "studio/new-uc/reference/report-studio-reference/drill-through-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración de desglose

La navegación por niveles es una función fundamental de los informes de TBM Studio, que permite a los usuarios explorar los datos con un nivel de detalle cada vez mayor. Las rutas de desglose correctamente configuradas ayudan a los usuarios a comprender los flujos de costes, investigar las desviaciones y rastrear las transacciones hasta su origen.

**Desglose a partir de las filas de una tabla**

Configura las columnas de la tabla para que actúen como enlaces de desglose. Cuando un usuario hace clic en un valor de la columna configurada, se le redirige al informe de destino con los filtros correspondientes ya aplicados.

**Pasos de configuración**

1. Selecciona la columna que deseas habilitar como enlace de desglose
2. Abre la pestaña «Ad Hoc» y haz clic en «Drill» en la sección «Navegación»
3. Marca la casilla «Habilitar navegación» para activar los enlaces
4. Seleccione el informe de destino en el campo «Ir a»
5. Configura las opciones de paso de contexto para controlar qué filtros se aplican

**Desglose a partir de elementos del gráfico**

Los gráficos también pueden ofrecer navegación con función de desglose. Cuando esta opción está activada, al hacer clic en una barra, una porción u otro elemento del gráfico, se accede al informe de destino filtrado según el dato seleccionado.

**Importante:** En los gráficos, la navegación debe basarse en la columna de valores, no en la columna de etiquetas. Configura el desglose en la medida numérica, no en las etiquetas de las dimensiones.

**Opciones para pasar el contexto**

Controla qué contexto de datos se pasa al informe de destino:

- **Filtrar en todas las columnas de filas:** aplica todas las dimensiones de fila como filtros
- **Filtrar solo por columnas agrupadas:** solo se tienen en cuenta las dimensiones agrupadas
- **Filtrar solo por la columna seleccionada actualmente:** solo se muestra el valor de la columna en la que se ha hecho clic
- **Filtrar según las selecciones del segmentador aplicado:** incluye los valores actuales del filtro del segmentador
- **Incluir los filtros del informe actual:** Aplica los filtros predefinidos del informe

Consejo: Para que la función de «drill-through» funcione correctamente, los datos de los informes de origen y destino deben estar vinculados a través del motor de inferencia. Asegúrate de que ambos informes utilicen tablas con las relaciones adecuadas definidas en el modelo.

**Desglose multinivel**

Crea rutas de desglose en cascada que permitan a los usuarios explorar los datos de forma progresiva a través de varios niveles. Por ejemplo, un usuario podría profundizar desde un informe resumido hasta los detalles de la unidad de negocio, luego a los detalles del centro de coste y, finalmente, a los datos a nivel de transacción.

**Ejemplo: Trayectoria de perforación de tres niveles**

**Nivel 1 - Informe resumido:**

- Tabla de costes por unidad de negocio con desglose en la columna «Unidad de negocio»
- Configurar el filtro en la fila seleccionada con las columnas «Filtrar en todas las filas»

**Nivel 2 - Informe detallado de la unidad de negocio:**

- Recibe el filtro del Nivel 1, mostrando únicamente la unidad de negocio seleccionada
- Tabla de centros de coste con desglose hasta el nivel 3

**Nivel 3 - Informe detallado de centros de coste:**

- Muestra los detalles a nivel de transacción del centro de coste seleccionado

**Tema principal:** [Componentes del informe: Navegación](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
