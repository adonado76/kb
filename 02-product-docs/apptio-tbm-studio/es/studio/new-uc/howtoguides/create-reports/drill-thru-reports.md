---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear informes de desglose"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Informes avanzados"
source_path: "studio/new-uc/howtoguides/create-reports/drill-thru-reports.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear informes de desglose

**Objetivo:** Permitir a los usuarios hacer clic en los datos resumidos y acceder a informes detallados, lo que facilita una exploración progresiva de los datos, desde vistas generales hasta detalles específicos.

**Cuándo utilizarlo:** cuando los usuarios necesitan explorar jerarquías de datos de forma interactiva, por ejemplo, haciendo clic en una unidad de negocio para ver sus aplicaciones, o haciendo clic en una categoría de costes para ver las partidas individuales.

**Tiempo estimado:** entre 20 y 30 minutos por configuración de desglose

## Comprender la navegación por desglose

Los informes de desglose permiten a los usuarios hacer clic en valores de las tablas o en elementos de los gráficos para acceder a informes más detallados. Una vez configurados, los valores vinculados aparecen en azul en las tablas. Los gráficos también pueden enlazar con informes cuando los usuarios hacen clic en los sectores de un gráfico circular o en los segmentos de una gráfica de barras.

TBM Studio ofrece varios patrones de desglose:

- **Exploración de datos agrupados:** cuando se utiliza la función GROUPBY en una tabla, las entradas agrupadas se convierten automáticamente en enlaces en los que se puede hacer clic y que muestran los detalles subyacentes.
- **Enlaces de navegación configurados:** puedes configurar explícitamente columnas de tablas o elementos de gráficos para acceder a informes específicos con filtros opcionales.
- **Navegación mediante botones:** utiliza componentes de botones para facilitar la navegación entre informes.
- **Enlaces codificados:** utiliza la sintaxis de estilo wiki en los cuadros de texto HTML para crear una navegación personalizada con texto dinámico.

**Requisitos previos**

- Informe de origen con datos resumidos (el informe desde el que partirán los usuarios)
- Informe de objetivos con datos detallados (al que accederán los usuarios del informe)
- Relaciones entre datos establecidas a través del motor de inferencia de Apptio
- Tablas o gráficos ad hoc (la navegación solo funciona con componentes ad hoc, no con componentes heredados)

## Método 1: Configurar enlaces de navegación en las columnas de una tabla

Este método crea enlaces en las columnas de una tabla que permiten acceder a un informe de destino y, si se desea, pasar el contexto de filtrado.

1. Abre el informe original y échale un vistazo.
2. Selecciona la columna de la tabla que quieras que sea clicable (por ejemplo, «Unidad de negocio»).
3. En la pestaña «Ad Hoc», haz clic en «Drill» en la sección «Navegación». Aparece el panel de propiedades de navegación.
4. Marca la casilla «Habilitar navegación» para activar los enlaces de esta columna.
5. En el campo «Ir a», selecciona el informe de destino en el menú desplegable. También puede hacer clic en «Nuevo informe» para crear el informe deseado.
6. Configura las opciones de contexto para controlar qué información se transmite al informe de destino:
   - **Filtrar por la fila seleccionada:** filtra el informe de destino según el valor en el que haya hecho clic el usuario
   - **Filtrar según las selecciones del segmentador aplicado:** aplica cualquier filtro activo del segmentador al informe de destino
   - **Incluir los filtros del informe actual:** Aplica los filtros definidos en el cuadro de diálogo «Configuración del componente»
   - **Añadir la columna seleccionada actualmente:** añade la columna en la que se ha hecho clic al informe de destino, si aún no está presente
7. (Opcional) Marca la casilla «Abrir como modal» para mostrar el informe de destino en una ventana emergente en lugar de abrir una nueva página en el navegador.
8. Guarda y revisa el informe.

Consejo: En el caso de los informes de desglose modales (ventanas emergentes), procura que el informe de destino sea sencillo. Evita los filtros complejos o los selectores de columnas que puedan no mostrarse correctamente en la ventana emergente.

## Método 2: Configurar la navegación por el gráfico

Permitir a los usuarios hacer clic en los elementos de los gráficos (porciones de gráficos circulares, segmentos de gráficos de barras) para acceder a informes detallados.

1. Selecciona tu gráfico y ve a la pestaña de configuración del gráfico.
2. En la sección «Navegar» (Explorar), marca la casilla «Habilitar navegación». Esto hace que los elementos del gráfico sean interactivos.
3. (Opcional) Marca la casilla «Usar desgloses por métrica» para permitir hacer clic en los valores numéricos que aparecen en las barras o en los sectores del gráfico circular, y no solo en los propios segmentos.
4. En el campo «Navegar», introduzca el nombre del informe de destino. El informe debe ser un subinforme del informe actual.
5. Guarda y revisa el informe.

Nota: Los enlaces de los informes solo se aplican a las tablas basadas en objetos y a los gráficos ad hoc. No es posible configurar el desglose a partir de tablas de transformación ni de gráficos heredados.

## Método 3: Navegación mediante botones

Añade botones de navegación explícitos que dirijan a los usuarios a informes específicos.

1. En la pestaña «Informe», haz clic en el botón. Se añade un componente de botón al informe.
2. Haz clic en el pequeño triángulo situado en la esquina superior izquierda del botón y selecciona «Propiedades».
3. En la pestaña Botón, introduce un texto descriptivo en el campo Texto del botón (por ejemplo, «Ver detalles de la solicitud»).
4. En la pestaña «Acciones», configura la navegación:
   - **Navegación:** Introduce un enlace de tipo wiki al informe de destino
   - **Cambiar fecha:** si lo deseas, puedes modificar el periodo de tiempo al navegar
   - **Botón Atrás:** marca esta casilla para crear un botón «Atrás» que permita volver al informe anterior
5. Haz clic en Aceptar para guardar la configuración del botón.

## Sintaxis de enlaces al estilo wiki

Utiliza esta sintaxis en los cuadros de texto HTML o en los campos de navegación de botones:

`[[report|display-text|tooltip]]`

|  |  |
| --- | --- |
| **Sintaxis** | **Descripción** |
| [[ReportName]] | Enlace a un informe secundario con el nombre del informe como texto del enlace |
| [[ ReportName|Click Aquí]] | Enlace con texto de visualización personalizado |
| [[..]] | Subir un nivel en la jerarquía del informe |
| [[/]] | Accede al informe predeterminado del proyecto |
| [[//ProjectName/Report]] | Enlace a un informe de otro proyecto |
| [[dialog:report:ReportName]] | Abrir el informe en una ventana emergente modal |
| [[tab:TabName/ReportName]] | Enlace a un informe en una pestaña concreta |

## Patrones habituales de desglose

**Patrón 1: De la unidad de negocio a las aplicaciones**

Un informe resumido de costes muestra los costes por unidad de negocio. Los usuarios hacen clic en una unidad de negocio para ver todas las aplicaciones que pertenecen a dicha unidad. Configure la columna «Unidad de negocio» marcando la casilla «Habilitar navegación» y seleccionando la opción «Filtrar por fila seleccionada». Esto aplica la unidad de negocio seleccionada como filtro al informe de aplicaciones.

**Patrón 2: De categoría a partidas**

Un gráfico muestra los costes por categoría (gráfico circular). Los usuarios hacen clic en una porción del gráfico circular para ver las partidas individuales que componen esa categoría. Active la navegación en el gráfico y seleccione el informe «Partidas» como destino.

**Patrón 3: Jerarquía multinivel**

El informe A muestra las unidades de negocio. Al hacer clic en una unidad, se accede al Informe B, donde se muestran los centros de coste de dicha unidad. Al hacer clic en un centro de costes, se accede al Informe C, que muestra las aplicaciones de dicho centro de costes. Configura la navegación de cada nivel para que se filtre según la fila seleccionada e incluya las selecciones de los segmentadores aplicados, con el fin de mantener el contexto a lo largo de la ruta de desglose.

## Resultados previstos

- Los valores vinculados en las tablas aparecen como texto subrayado en azul
- Al hacer clic en un enlace, se accede al informe correspondiente
- El contexto del filtro se transmite según tu configuración
- Aparecen las migas de pan, que muestran la ruta de navegación

## Errores habituales

- **La navegación no funciona:** comprueba que estás utilizando tablas y gráficos ad hoc, y no componentes heredados. La navegación solo funciona con los componentes de configuración de componentes ad hoc.
- **El informe de destino no muestra datos:** asegúrese de que las relaciones entre los datos estén establecidas a través del motor de inferencia de Apptio. Los datos de origen y de destino deben estar vinculados.
- **Problemas de rendimiento:** ten cuidado al vincular informes que requieran mucho tiempo de cálculo. Esto puede afectar al rendimiento del sistema.

## Tareas relacionadas

- [Crear colecciones de informes](build-rc.html)
- [Añadir segmentadores y filtros](use-slicers.html)
- [Configurar la visibilidad de los componentes](add-et-rep.html)

**Tema principal:** [Informes avanzados](../../../../studio/new-uc/howtoguides/create-reports/adv-rep.html)
