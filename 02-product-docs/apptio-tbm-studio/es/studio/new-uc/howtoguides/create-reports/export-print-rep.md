---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Exportar e imprimir informes"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Informes avanzados"
source_path: "studio/new-uc/howtoguides/create-reports/export-print-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Exportar e imprimir informes

**Objetivo:** Generar informes para su distribución mediante exportación a PDF, envío por correo electrónico, impresión y suscripciones automáticas.

**Cuándo utilizarlo:** al compartir informes con partes interesadas ajenas a TBM Studio, al crear distribuciones programadas de informes o al elaborar material impreso para reuniones y presentaciones.

**Tiempo estimado:** entre 10 y 20 minutos por informe

## Configurar el diseño de impresión

Antes de exportar o imprimir, configura el diseño de impresión para controlar cómo se muestra el informe en papel o en formato PDF:

1. Echa un vistazo al informe.
2. En la pestaña «Inicio», haz clic en «Ver» y, a continuación, selecciona «Diseño de impresión». El informe pasa al modo de diseño de impresión.
3. Haz clic en la pestaña «Diseño de impresión» para acceder a las opciones de diseño.
4. Configurar la configuración de página:
   - **Tamaño de página:** Selecciona entre los tamaños de papel estándar
   - **Orientación:** vertical u horizontal
   - **Márgenes:** Configurar los márgenes de la página
   - **Escala:** Nivel de zoom para la impresión
5. Configurar el flujo de componentes:
   - **Manual:** Los componentes permanecen donde los coloques
   - **Vertical:** los componentes se disponen en una sola columna
   - **Horizontal:** los componentes se disponen en filas
6. Configurar encabezados y pies de página:
   - **Encabezado:** Añade texto, formato HTML o texto dinámico. Puede aparecer en todas las páginas o solo en la primera página.
   - **Pie de página:** Añade texto personalizado al pie de página (nota: los pies de página no admiten texto dinámico)
7. Para los componentes individuales:
   - **Fijar/Desfijar:** Mueve los componentes (como los segmentadores) al final del informe
   - **Mostrar/Ocultar:** controla qué componentes aparecen en la impresión
8. Haz clic en «Guardar» en la pestaña «Diseño de impresión» para guardar la configuración.
9. Haz clic en «Salir del modo de diseño de impresión» para volver al modo de edición normal.
10. Consulta el informe.

Consejo: Utiliza texto dinámico en los encabezados para incluir el periodo actual. Por ejemplo: <%=CurrentDate( )%> muestra automáticamente el periodo del informe.

## Configurar la impresión de tablas de varias páginas

En el caso de tablas extensas que ocupan varias páginas:

1. Accede al modo de diseño de impresión.
2. Mueve la tabla a una página independiente (las tablas se imprimen mejor cuando ocupan una página completa).
3. Selecciona la tabla y, en la pestaña «Diseño de impresión», haz clic en «Ajustar el componente a página completa».
4. Con la tabla seleccionada, ve a la subpestaña «Tabla» y marca la casilla «Imprimir todas las páginas».
5. Guarda y sal del modo de diseño de impresión.

## Exportar a PDF

1. Abre el informe que deseas exportar.
2. En la pestaña Inicio, haz clic en Exportar y, a continuación, en PDF. Aparece el cuadro de diálogo «Exportar a PDF».
3. Selecciona una opción de exportación:
   - **Descargar el PDF directamente:** abre o descarga el PDF en tu ordenador
   - **Incluir un enlace al PDF en un correo electrónico:** envía un correo electrónico con un enlace al PDF almacenado en TBM Studio
   - **Adjuntar el PDF a un correo electrónico:** envía el PDF como archivo adjunto en un correo electrónico
4. En el apartado de opciones de correo electrónico, introduce la dirección de correo electrónico del destinatario.
5. Haz clic en «Aceptar» para generar y exportar o enviar por correo electrónico el PDF.

Nota: Cuando compartes un enlace a un informe por correo electrónico, el destinatario ve el informe en el mismo contexto en el que lo compartiste. Se conservan todos los filtros, segmentadores y selecciones de intervalos de fechas.

## Crear suscripciones por correo electrónico

Configura el envío automático y periódico de informes por correo electrónico:

1. Ve al informe al que quieras suscribirte.
2. Haz clic en el icono «Exportar» y selecciona «Suscripción por correo electrónico». Esta opción está disponible para los administradores de TBM.
3. En el cuadro de diálogo «Suscripción por correo electrónico», configura la suscripción:
   - **Nombre de la suscripción:** un nombre descriptivo para la suscripción
   - **Destinatarios:** direcciones de correo electrónico (deben pertenecer a dominios autorizados en tu entorno)
   - **Frecuencia:** entrega diaria, semanal o mensual
   - **Incluir vista de diseño de impresión:** adjuntar el PDF con el diseño de impresión configurado
   - **Incluir enlace con las selecciones del segmentador:** Incluir un hipervínculo al informe con los filtros ya aplicados
4. Haz clic en «Guardar» para crear la suscripción.

Advertencia: La seguridad a nivel de fila (RLS) no se aplica a las suscripciones por correo electrónico. Todos los destinatarios pueden ver los datos completos del informe. Tenga esto en cuenta al distribuir informes que contengan información confidencial.

## Gestionar suscripciones por correo electrónico

Para ver y gestionar las suscripciones existentes:

1. En el informe, haz clic en Exportar > Suscripción por correo electrónico.
2. Haz clic en «Gestionar suscripciones».
3. Desde aquí puedes:
   - Ver todas las suscripciones al informe
   - Editar la configuración de la suscripción
   - Activar o desactivar las suscripciones
   - Eliminar suscripciones

## Exportar a Excel

Para exportar los datos del informe a Excel con el fin de analizarlos más a fondo:

1. Mostrar el informe.
2. En la pestaña Inicio, haz clic en Exportar y, a continuación, en Excel.
3. Los datos del informe se exportan a un libro de Excel. El orden de las columnas coincide con la configuración del informe.

Nota: Excel limita la longitud de los nombres de las hojas a 31 caracteres. Los nombres de los informes que superen este límite se truncan y se les añade « "-0" ».

## Exportar tablas con vista de árbol

Al exportar tablas con estructura de árbol (jerárquicas) a Excel:

- Se exportan todas las filas principales y secundarias
- La primera columna muestra indicadores de sangría (símbolos >>) para representar el nivel jerárquico
- La exportación a Excel es una tabla plana (no una estructura de árbol que se pueda contraer)

## Requisitos del navegador

Para que las funciones de exportación a PDF funcionen correctamente:

- Permite las ventanas emergentes de Apptio y URL en la configuración de tu navegador
- Los archivos PDF pueden abrirse en una nueva pestaña o aparecer en la barra de descargas de tu navegador, dependiendo de la configuración de este

**Resultados previstos**

- Las exportaciones a PDF utilizan la configuración de diseño de impresión establecida
- Las suscripciones por correo electrónico envían informes según la programación configurada
- Los enlaces a informes compartidos conservan el contexto (filtros, intervalo de fechas) de cuando se creó el enlace
- Las exportaciones a Excel incluyen todos los datos visibles de la tabla con las columnas en el orden configurado

**Errores habituales**

- **El PDF no se muestra correctamente:** comprueba que la configuración de impresión esté bien configurada. Para obtener una vista previa, haz clic en «Exportar a PDF» en la pestaña «Diseño de impresión» antes de archivar el documento.
- **Error en la suscripción por correo electrónico:** comprueba que las direcciones de correo electrónico de los destinatarios pertenezcan a dominios autorizados en tu entorno.
- **Los encabezados y pies de página no se ven:** Los encabezados y pies de página no son visibles en el modo de diseño de impresión. Exporta a PDF para verlos.

## Tareas relacionadas

- Configurar los permisos de los informes (Sección 3.4 )
- Crear colecciones de informes (Sección « 3.3.1 »)
- Configurar compilaciones periódicas (Sección 6.1 )

**Tema principal:** [Informes avanzados](../../../../studio/new-uc/howtoguides/create-reports/adv-rep.html)
