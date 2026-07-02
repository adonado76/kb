---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "IBM Apptio Guía del Asistente de migración de informes"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Configuración y personalización"
source_path: "studio/report-studio/migration-assistant.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# IBM Apptio Guía del Asistente de migración de informes

## Visión general

En esta guía se explica cómo funciona el Asistente de migración de informes de IBM Apptio, qué datos se conservan, qué elementos requieren actualizaciones manuales y cómo planificar una transición satisfactoria. La migración del informe crea una nueva versión del informe con el formato actualizado, sin modificar el informe original.

- El informe que ya tienes no se modifica
- Un nuevo informe migrado se abre en una pestaña independiente
- Puedes comparar la versión antigua con la nueva en paralelo para verificar los resultados y realizar actualizaciones
- Los informes se crean con el mismo nombre que el original, al que se le añade la indicación «(Migrado)».

Este documento se aplica a los informes creados en la versión clásica de Report Studio que se están migrando a IBM Apptio Report Studio. Migración de Report Studio clásico a IBM Apptio Report Studio es una actividad gestionada por el cliente. Los clientes son responsables de llevar a cabo la migración y deben asegurarse de que la persona encargada de realizarla disponga de permisos de administrador en TBM Studio. Como parte de este proceso de modernización de IBM Apptio, la versión clásica de Report Studio dejará de estar disponible el 31 de diciembre de 2027. A partir de esa fecha, ya no se podrá acceder a los informes clásicos de Report Studio existentes.

Para facilitar la transición, el Asistente de migración de informes de IBM Apptio ayuda a los clientes a trasladar los informes existentes del Report Studio clásico a la nueva interfaz. El proceso de migración está en gran medida automatizado y permite transferir más del 90 % de los componentes de los informes, las configuraciones de datos y los diseños, lo que permite a los equipos realizar la transición de forma eficiente sin perder continuidad. Aunque se conservan la mayoría de los elementos estructurales, el formato (incluidos los colores, las fuentes, el estilo y los temas) no se transferirá por completo y será necesario ajustarlo en el nuevo Report Studio.

Aunque la migración está pensada para que la realicen los propios clientes, aquellos que deseen recibir ayuda o no puedan llevarla a cabo pueden ponerse en contacto con su gestor de éxito del cliente (CSM) para definir un proyecto concreto en el marco de un pliego de condiciones (SOW). IBM Apptio Los clientes de Essentials pueden hacer uso del servicio TAS que tienen a su disposición.

Los clientes también pueden optar por utilizar los informes nuevos o actualizados listos para usar (OOTB) en lugar de migrar sus colecciones de informes actuales.

## Guía de migración

En esta sección se describe el manual de procedimientos que se debe aplicar

1. **Descubrimiento** :
   - El cliente revisa la lista de informes utilizados recientemente en CT Report Studio para seleccionar cuáles deben migrarse.
2. **Migración** :
   - Para cada informe:
     - El usuario debe «cerrar» el informe
     - El usuario hace clic en el botón «Migrar informe» en TBM Studio. Esto genera un nuevo informe con el mismo nombre que el anterior, al que se le añade la indicación «(Migrado)», por ejemplo, «Revisión financiera (Migrado)». Este nuevo informe se abre en una nueva pestaña.
     - El usuario accede al nuevo informe en IBM Apptio Report Studio, comprueba que la configuración de los datos sea la misma y aplica las opciones de formato deseadas para que el informe tenga el mismo aspecto que el anterior.
   - Qué esperar tras la migración
     - [Aquí](#migasst__What_will_be) se incluye una lista de los componentes y widgets que se migrarán. La tabla también incluye una lista de widgets y funciones que no se migrarán a la nueva interfaz.
     - Los widgets no compatibles se mostrarán como marcadores de posición. Los marcadores de posición solo se pueden eliminar.
     - La navegación de Drill no se migrará.
     - Los colores pueden variar.
     - La migración de un solo informe no debería llevar más de un par de minutos.
     - Si desea añadir logotipos personalizados, puede utilizar un componente HTML con una etiqueta de imagen, por ejemplo: <img src="https://logos.apptio.com/myLogo.jpg" >.
3. **Flujo de trabajo recomendado tras la migración**
   - Abre ambos informes uno al lado del otro
     - Original (desbloqueado para permitir la visualización de la configuración)
     - Versión migrada (editable)
   - Validar datos
     - Comprueba que las métricas y los resultados coincidan
   - Validar componentes
     - Abre el panel «Capas» para ver todos los componentes y detectar aquellos que puedan estar ocultos.
   - Revisar los marcadores de posición
     - Identifica los componentes no compatibles a través del panel de capas
     - Elimina o vuelve a crear según sea necesario
   - Corregir el formato
     - Ajustar los colores, las fuentes y el diseño
     - Alinea los componentes con las herramientas de diseño
   - Reconstruir interacciones
     - Recrear manualmente la navegación por el ejercicio
4. **Pruebas de aceptación del usuario** :
   1. Una vez que se han migrado todos los informes de un cliente, este revisa las actualizaciones.
      - El usuario adapta los informes en función de los comentarios recibidos
5. **Entrega del balón** :
   - El usuario cambia el nombre de todos los informes aceptados para eliminar la etiqueta «(Migrado)» y registra los nuevos informes.
   - Los informes existentes creados con CT Report Studio pueden seguir coexistiendo hasta que el usuario se sienta cómodo con IBM Apptio Report Studio

## Qué se migrará y qué no

|  |  |  |  |
| --- | --- | --- | --- |
| Se migrará | No se migrará | Se trasladará más adelante (fecha por determinar) | En estudio |
| - Configuraciones de datos (métricas, dimensiones, filtros) - Tipos de componentes (compatibles) - Estructura de diseño - Ubicación (aproximada) - Dimensionamiento de componentes (exacto) - Resultados de los datos (los números se mantienen constantes) - Nombre del informe (con la indicación «(Migrado)» añadida) - Botón - Gráficos   - Barra   - Columna   - Línea   - Superposición: columna + línea   - Superposición: Columna apilada + Línea   - Superposición: Línea + Línea   - Gráfico circular   - Barra apilada   - Columna apilada - Selector de columnas - Cortadora compacta - Tabla editable - Grupo - HTML - ICR - Giro rápido - Subida simplificada - Creador de secciones - Tabla - Tabuladores | - Tabla   - Demanda   - Lista de tareas   - o Anotaciones de celdas - Símbolo   - Indicador   - Símbolo - Formato (colores, fuentes, estilo, temas) - Configuraciones de perforación (las rutas de perforación no se migran debido a diferencias en la identificación de los informes (rutas heredadas frente a nuevos identificadores únicos)) - Componentes no compatibles o obsoletos - Alineación exacta (pueden producirse ligeras variaciones en la disposición) - Mapeador GL - Cuadrícula de mapeo - Diagrama del modelo - Nota - Carga de tablas - Recopilaciones de informes - Estructura de carpetas | - Gráfico   - Mapa de árbol - Icono - Texto - Cascada | - Gráfico   - Burbuja   - Radial |

## Informes sobre perfiles de complejidad

Utiliza estos perfiles para establecer las expectativas respecto al esfuerzo que supone la migración:

**Informes sencillos**

- Gráficos y tablas básicos
- Formato mínimo
- Pocos componentes personalizados o ninguno
- Resultado esperado:
- Limpieza rápida
- Principalmente ajustes de formato

**Informes de complejidad media**

- Combinación de gráficos, indicadores clave de rendimiento y filtros
- Algunos formatos personalizados
- Complejidad moderada del diseño
- Resultado esperado:
- Requiere correcciones de formato y una pequeña recompilación
- Algunos marcadores de posición que hay que tratar

**Informes complejos**

- Diseños avanzados y gran capacidad de personalización
- Componentes HTML, botones o widgets heredados
- Rutas de perforación e interactividad
- Resultado esperado:
  - Se requiere un importante trabajo de pulido manual
  - Es posible que haya que volver a compilar varios componentes
  - Hay que volver a crear la lógica de interacción

Nota:

- Migrar primero los informes de destino y después los de origen. Dado que la navegación por los desgloses debe volver a añadirse tras la migración, puede resultar más eficaz migrar los informes clásicos de abajo hacia arriba. De esta forma, cuando corrijas los desgloses del informe de origen, podrás elegir entre los distintos destinos disponibles.
- La posición de los componentes puede variar dependiendo de si el encabezado clásico de los componentes está visible. En los informes clásicos, los títulos o encabezados de los componentes se encuentran fuera de los bordes de los componentes, mientras que en los nuevos informes se encuentran dentro. Cuando los componentes clásicos de los informes tienen encabezados ocultos, los autores de los informes suelen desplazarlos hacia arriba para reducir los espacios en blanco. Por lo tanto, al migrar los informes, los trasladamos a una carpeta inferior.

## Problemas conocidos

A continuación se enumeran los problemas conocidos del Asistente de migración de informes en la versión 12.11.21 (abril de 2026). La mayoría o todas estas cuestiones se tratarán en « 12.11.22 » (mayo de 2026)

- Las cortadoras compactas que integran varias funciones en un solo componente se han reestructurado en un grupo de cortadoras independientes. Esta agrupación hace que los segmentadores dejen de funcionar, ya que modifica su ámbito de aplicación. Para solucionarlo, basta con desagrupar los segmentadores.
- Es posible que las tablas de árbol con configuraciones entre objetos (filas, columnas, valores o filtros con dos o más objetos del modelo) no funcionen. Esto se tratará en 12.11.22.

**Tema principal:** [Configuración y personalización](../../studio/report-studio/config-custom.html)
