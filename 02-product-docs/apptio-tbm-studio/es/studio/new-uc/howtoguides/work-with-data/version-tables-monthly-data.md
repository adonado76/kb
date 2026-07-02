---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tablas de versiones para datos mensuales"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Importación y gestión de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/version-tables-monthly-data.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tablas de versiones para datos mensuales

**Objetivo:** Configurar las tablas para mantener conjuntos de datos independientes para cada periodo, lo que permite realizar un seguimiento histórico y análisis comparativos entre periodos.

**Cuándo utilizar este procedimiento:** Utilice el control de versiones mensual cuando:

- Los valores de los datos cambian cada mes (por ejemplo, el libro mayor, los costes reales, la utilización del servidor)
- Es necesario conservar los valores históricos para el análisis de tendencias
- Sus procesos empresariales requieren el cierre de fin de mes y el bloqueo de período
- Se aplican diferentes estructuras de datos o valores a distintos periodos de tiempo

**No utilices el control de versiones mensual cuando:**

- Los datos son estáticos o cambian con poca frecuencia
- Solo necesitas los datos más recientes
- Los datos son información de referencia o de consulta (por ejemplo, asignaciones de grupos de costes)

**Requisitos previos:**

- Se ha habilitado el tiempo para el proyecto
- Conocer el calendario fiscal de su organización
- Conocimientos sobre la creación y la carga de tablas
- Permisos para editar tablas (rol « AccessDev »)

**Tiempo estimado:** 15 minutos para la configuración inicial; 5 minutos por periodo para las subidas continuas

## Pasos

**Parte 1: Configurar el control de versiones mensual para una nueva tabla**

1. **Crear una nueva tabla:** En el **Explorador de proyectos**, haz clic en **Nuevo** → **Tabla**, introduce un nombre (por ejemplo, «Datos reales mensuales del libro mayor»), selecciona una categoría y haz clic **en Aceptar**.
2. **Selecciona el control de versiones mensual:** en la parte superior de la pantalla, busca el menú desplegable **«Ciclo de actualización de datos»** y selecciona «**Versiones mensuales; Actualizar cada mes** ».

**Comprender las opciones de versiones mensuales:**

- **Versiones mensuales; Actualización mensual:** se añaden nuevos datos cada mes; se conservan los datos de los meses anteriores
- **Versiones anuales; Actualización mensual:** 12 meses cargados mensualmente (año móvil)
- **Versiones anuales; actualización a principios de año:** publicación anual; sin cambios hasta el año siguiente
- **Versiones anuales con traspaso:** carga anual con traspaso automático de los valores del año anterior
  1. **Sube los** **datos del primer mes:** asegúrate de que el selector de fechas muestre el periodo deseado, haz clic en «**Subir archivo** », sube tu archivo de datos, configura los ajustes de importación y haz clic en «**Guardar** y **registrar** ».
  2. **Configurar notificaciones de caducidad de datos** (opcional): **haz clic aquí para configurar notificaciones** y recibir alertas por correo electrónico cuando los datos no se hayan actualizado según lo programado.

**Parte 2: Carga de datos para períodos posteriores**

1. **Extraer la tabla:** ve a la tabla, haz clic con el botón derecho del ratón y selecciona «**Extraer** ».
2. **Cambia al periodo deseado:** utiliza el **selector de fechas** para seleccionar el periodo para los nuevos datos. En el paso «Subir» aparece un marcador de posición.
3. **Carga los** **datos del periodo:** haz clic en el marcador de posición, busca el archivo o arrástralo hasta allí. El sistema crea una nueva versión para este periodo.
4. **Comprueba y guarda:** haz clic en el paso **«Tabla»** para obtener una vista previa y comprobar los valores; a continuación, haz clic en **«Guardar»** y «**Registrar** ».

## Resultados previstos

- La tabla contiene conjuntos de datos independientes para cada periodo
- Al cambiar de periodo en el selector de fechas, se muestra el conjunto de datos correspondiente
- Los datos históricos se conservan y están disponibles
- En los informes se pueden realizar comparaciones entre periodos
- Las alertas de actualidad de los datos te avisan cuando faltan las subidas mensuales

## Errores habituales y solución de problemas

**Problema:** Errores de «datos faltantes» en el modelo o los informes

- **Causa:** No se han cargado los datos correspondientes a todos los periodos comprendidos entre el inicio del proyecto y la fecha actual
- **Solución:** Carga los archivos de datos correspondientes a todos los periodos requeridos. Considera la posibilidad de ajustar la fecha de inicio del proyecto, utilizar el control de versiones de traspaso o crear conjuntos de datos provisionales.

**Problema:** Se ha subido a un periodo incorrecto

**Solución:** Comprueba siempre el selector de fechas antes de subir el archivo. Elimina la subida incorrecta seleccionando ese periodo, finalizando el proceso y eliminando el archivo del paso «Subir».

**Problema:** Los cambios en el esquema no se aplicaron a los periodos anteriores

- **Motivo:** los cambios en el esquema solo se aplican a partir del periodo seleccionado
- **Solución:** Se trata de un comportamiento esperado. Para actualizar períodos anteriores, selecciona cada uno de ellos con el selector de fechas, realiza los cambios y guarda los cambios.

## ¿Qué viene ahora?

- [Configurar la partición por fecha](transform-enrich-data.html) : para los archivos del libro mayor que contengan columnas mensuales, añade pasos de transformación de partición por fecha
- Configurar períodos cerrados: bloquear los períodos finalizados para evitar modificaciones accidentales (Sección 6.1 )
- Programar compilaciones automáticas: sincronizar los cálculos de los modelos con los procesos de cierre de fin de mes (Sección 6.1 )
- [Crear informes de tendencias](../create-reports/report-basic.html) : Aprovecha los datos mensuales para realizar análisis interanuales

**Tema principal:** [Importación y gestión de datos](../../../../studio/new-uc/howtoguides/work-with-data/data-import-mgmt.html)
