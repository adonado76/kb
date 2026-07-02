---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Versiones y periodos"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura de datos"
source_path: "studio/new-uc/concepts-architecture/data-architecture/versioning-time-periods.html"
images:
  - "resources/images/studio_images/project-time-settings.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Versiones y periodos

TBM Studio es, en esencia, una plataforma centrada en el mes. Casi todo —datos, modelos e informes— se enmarca en un periodo mensual concreto. Comprender cómo funcionan los periodos de tiempo y el control de versiones es fundamental para trabajar de forma eficaz con la plataforma.

## Conceptos relacionados con los periodos de tiempo

En TBM Studio, un periodo de tiempo corresponde a un mes de datos. Al consultar una tabla de transformación, se muestran los datos de un mes cada vez. Cuando se ejecuta un cálculo del modelo, este se realiza para un periodo concreto. Al consultar un informe, este muestra los datos correspondientes al periodo seleccionado actualmente (aunque los informes pueden agregar datos de varios periodos para el análisis de tendencias).

Este diseño, centrado en el mes, refleja la realidad de la gestión financiera de las tecnologías de la información: por lo general, los costes se registran, se asignan y se consignan en un ciclo mensual.

Nota:

**Concepto clave**

Data Studio establece un único periodo de actividad para las vistas previas de las transformaciones. En el espacio de trabajo de transformación no es posible previsualizar varios meses a la vez. La agregación de varios periodos se realiza en la capa de informes, no en « Data Studio ».

## Ciclos de actualización de datos y control de versiones

Al crear una tabla y cargar datos, se elige un ciclo de actualización que indica con qué frecuencia se prevé que se actualicen los datos. Esta configuración determina cómo funciona el control de versiones de la tabla:

|  |  |  |
| --- | --- | --- |
| **Ciclo de actualización** | **Comportamiento del control de versiones** | **Ideal para** |
| Actualizaciones puntuales | Los datos se pueden añadir o sustituir según sea necesario. No se comprueba la fecha de caducidad. | Datos de referencia puntuales que rara vez cambian |
| Versión 1; No hay actualizaciones previstas | Los datos cargados sustituyen a los datos existentes. No se comprueba la fecha de caducidad. | Tablas de configuración estáticas |
| Versión 1; Actualización mensual | Versión única actualizada mensualmente. Los datos se marcarán como caducados si no se actualizan en el plazo de un mes. | Tablas de consulta que cambian periódicamente |
| 1 versión; Actualización anual | Versión única que se actualiza anualmente. Los datos se marcarán como caducados si no se actualizan en el plazo de un año. | Tarifarios anuales o listas de precios |
| Versiones mensuales; Actualización cada mes | Cada mes tiene su propia versión. Los datos nuevos no sobrescriben los de los meses anteriores. | Datos contables, presupuestos y previsiones (lo más habitual en el caso de los datos financieros) |
| Versiones anuales; Actualización mensual | Doce meses de datos cargados mensualmente, cada uno en su correspondiente periodo. | Análisis de los últimos doce meses |
| Versiones anuales con elementos heredados | Los datos anuales se cargan al inicio del ejercicio fiscal. Los valores del año anterior se mantendrán si no se cargan nuevos datos. | Tablas en las que los valores se mantienen prácticamente iguales de un año a otro |

El formato más habitual para los datos financieros es el mensual. Con este enfoque, la exportación del libro mayor, el archivo de presupuesto o la previsión de cada mes se convierte en una versión independiente. El modelo utiliza la versión correcta en función del periodo de tiempo activo, lo que garantiza que las asignaciones de enero utilicen los datos de enero y las de febrero, los de febrero.

## Calendario fiscal

TBM Studio admite tanto los años naturales estándar (enero-diciembre) como los calendarios fiscales personalizados. El calendario fiscal determina cómo se denominan los periodos, cómo se establecen los límites del ejercicio fiscal y cómo funcionan operaciones como los cálculos acumulados del año.

La configuración del calendario fiscal incluye:

- **Tipo de calendario:** estándar (12 meses) o patrones personalizados, como agrupaciones de 4-4-5 semanas.
- **Definición del ejercicio fiscal:** si el ejercicio fiscal se identifica por su periodo de inicio o por su periodo de finalización. Por ejemplo, un año fiscal comprendido entre junio 2024–May de 2025 podría denominarse FY2024 (periodo inicial) o FY2025 (periodo final).
- **Formato de visualización:** si las fechas se muestran con los nombres de los meses (Ene 2024, Feb 2024) o con los números de los meses ( P1 2024, P2 2024).

Los ajustes del calendario fiscal se configuran a nivel de proyecto y afectan a todos los componentes de la plataforma: las transformaciones, los modelos y los informes heredan todos el mismo calendario.

## Herencia de periodos

Los ajustes de tiempo se aplican desde el nivel del proyecto hacia abajo en todo el sistema:

![Configuración del tiempo del proyecto](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/project-time-settings.png)

Nota:

**Importante**

Los periodos cerrados bloquean la carga de datos e impiden que se vuelvan a calcular los modelos para esos meses. Esto protege los datos financieros cerrados frente a modificaciones accidentales. Las publicaciones de tablas editables también pueden bloquearse cuando se dirigen a períodos cerrados.
