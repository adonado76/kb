---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Herramientas de diagnóstico"
breadcrumb:
  - "TBM Studio"
  - "Solución de problemas y asistencia técnica"
source_path: "studio/new-uc/ts-support/diagnostic-tools.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Herramientas de diagnóstico

TBM Studio ofrece varias herramientas para diagnosticar problemas de rendimiento, supervisar compilaciones y analizar el comportamiento del sistema.

## Calc Explorer

Calc Explorer permite a los administradores analizar el rendimiento de la compilación e identificar los componentes que requieren un mayor esfuerzo de cálculo. Accede a través de la pestaña «Build» > «Calc Explorer».

**Definiciones clave:**

|  |  |
| --- | --- |
| **Plazo** | **Descripción** |
| Crear | Un punto concreto del proceso de facturación que se puede calcular |
| Tipo de cálculo | Todo (cálculo completo), Parcial (solo entidades dependientes) o Ninguno (no se necesita cálculo) |
| Esfuerzo de cálculo | Una estimación de los recursos necesarios, expresada en millones (p. ej., 3.2M ) |
| Consulta | La unidad de cálculo más pequeña, normalmente una entidad correspondiente a un período de tiempo concreto |

**Cómo utilizar el diagrama de Sankey:**

En todas las compilaciones, Calc Explorer muestra un diagrama de Sankey en el que las entidades aparecen clasificadas y ordenadas según el esfuerzo de cálculo. Haz clic en la entidad «Informes» para ver los 10 informes principales. Pasa el cursor por encima de los nombres de los informes para ver los porcentajes de esfuerzo de cálculo. Haz clic con el botón derecho del ratón para abrir los documentos o ver las rutas completas de los archivos. Sigue investigando para identificar los componentes concretos que plantean problemas.

## Cola de cálculos

La cola de cálculo muestra el estado de las compilaciones en todos los entornos. Accede a través de la pestaña «Compilación» > «Cola de cálculos».

|  |  |
| --- | --- |
| **Estado** | **Descripción** |
| Pendiente | La compilación está en cola y a la espera de ser procesada |
| Calculando | En construcción (muestra los cálculos completados frente al total) |
| Finalizado | Compilación completada (muestra el tiempo transcurrido desde la finalización y la duración) |

## Panel de errores

El panel de errores ofrece una vista general de todos los errores del proyecto. Accede a través de la pestaña «Proyecto» > «Errores». Revisa la lista de errores, haz clic en cada uno para ver los detalles y ve al documento afectado. Los errores impiden que se realice el cálculo del modelo hasta que se resuelvan.

## Historial de registros

Realiza un seguimiento de los cambios introducidos en los documentos a lo largo del tiempo. Selecciona un documento en el Explorador de proyectos, haz clic con el botón derecho del ratón en la pestaña de la parte inferior y selecciona «Historial de registros». Ver la fecha, el usuario, el estado y los mensajes de cada registro. Desde aquí, también puedes volver a una configuración anterior si es necesario.
