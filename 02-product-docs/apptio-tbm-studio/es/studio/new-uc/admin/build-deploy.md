---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Compilación e implementación"
breadcrumb:
  - "TBM Studio"
  - "Administración"
source_path: "studio/new-uc/admin/build-deploy.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Compilación e implementación

**Tipo de contenido:** Conceptual / Guía práctica

**Destinatarios:** Administradores, usuarios avanzados

**Requisitos previos:** Conocimientos sobre entornos de desarrollo, staging y producción

El ciclo de vida de compilación e implementación en TBM Studio gestiona el flujo de los cambios desde el desarrollo, pasando por el entorno de prueba, hasta la producción. Comprender este ciclo de vida es fundamental para mantener un entorno de producción estable y, al mismo tiempo, permitir el desarrollo iterativo.

## Comprender los entornos

TBM Studio utiliza tres entornos para gestionar el proceso de implementación de los cambios, desde la fase de desarrollo hasta los usuarios finales.

|  |  |
| --- | --- |
| **Entorno** | **Descripción** |
| **Desarrollo** | Donde se realizan los cambios de configuración. Las registraciones activan cálculos de desarrollo que procesan transformaciones y métricas. Los cambios se validan aquí antes de pasar al entorno de prueba. |
| **Transfiriendo** | Entorno de validación previo a la producción. Calcula los desgloses y genera los informes una vez finalizado el cálculo de desarrollo. Se utiliza para verificar los cambios antes de implementarlos en el entorno de producción. |
| **Producción** | Entorno de producción al que acceden los usuarios de la empresa. Los cambios solo se aplican al entorno de producción mediante una promoción explícita desde el entorno de staging. El ascenso es casi inmediato. |

## Proceso de salida y llegada

En TBM Studio, todos los elementos (tablas, métricas, perspectivas, modelos) son documentos que deben extraerse para poder editarlos. Cuando se extrae un documento, este se bloquea para que otros usuarios no puedan editarlo al mismo tiempo.

**Para sacar un documento:**

- Selecciona el documento en el Explorador de proyectos
- En la pestaña Inicio, en el grupo Documento, haz clic **en Desproteger**
- Aparece un icono de desprotección junto al nombre del documento, y el nombre se muestra en naranja

## Buenas prácticas para el registro:

- Revisa los datos antes de subirlos para comprobar el contenido y el formato
- Haz clic en «Guardar» después de modificar cualquier documento
- Resuelve todos los errores antes de realizar el check-in
- Valida los informes que utilizan los datos modificados
- Coordina las comprobaciones con los miembros del equipo para evitar que se acumulen los cálculos

**Consejo:** *Establece una política de comunicación entre el equipo para coordinar los contactos una o dos veces al día (por ejemplo, a la hora del almuerzo y al final de la jornada). Esto reduce los conflictos en la cola de cálculos y garantiza que todos vean los mismos datos.*

## Supervisión de la cola de cálculo

La cola de cálculo muestra el estado de las compilaciones en todos los entornos. Úsalo para supervisar el progreso de los cálculos, identificar las compilaciones en cola y consultar el historial de cálculos.

**Para acceder a la cola de cálculos:**

- Ve a **«Compilación» > «Cola de cálculos»**

**Indicadores del estado de la compilación:**

- **Pendiente** : la compilación está en cola y a la espera de ser procesada
- **Calculando** : la compilación está en curso (muestra los cálculos completados frente al total)
- **Finalizado** : la compilación ha finalizado (muestra el tiempo transcurrido desde la finalización y la duración)

## Bloquear y pasar a producción

Para implementar los cambios en el entorno de producción, primero debes bloquear el entorno de staging para evitar que se realicen más cambios y, a continuación, pasar la compilación de staging al entorno de producción.

**Para pasar a producción:**

- Asegúrate de que se hayan completado todos los cálculos de preparación pendientes
- Ve a **«Build» > «Lock»** para bloquear el entorno de prueba
- Haz clic en **«Promocionar ahora»** para implementar en producción
- Verificar los informes en el entorno de producción tras la implementación

**Nota:** *La migración a la versión de producción en TBM Studio R12 es prácticamente instantánea. Los usuarios verán los datos actualizados inmediatamente después de que finalice la promoción.*

## Trabajar con ramas

La ramificación crea una copia completa de tu proyecto, lo que permite el desarrollo en paralelo sin afectar al proyecto principal (trunk). Las ramas son útiles para cambios de configuración de larga duración, correcciones de emergencia y el archivo de estados anteriores.

**Cuándo utilizar las ramas:**

- **Configuración de larga duración** : cambios importantes que tardan semanas en completarse, mientras que la carga de datos operativos continúa en el canal principal
- **Producción de parches** : soluciona los problemas de producción sin afectar al trabajo de desarrollo en curso
- **Archivar estados anteriores** : conservar y consultar los estados históricos de los proyectos (por ejemplo, ejercicios fiscales anteriores)

**Limitaciones de la sucursal:**

- Máximo de 5 ramas por entorno
- Cada rama utiliza los mismos recursos que el proyecto principal
- Los cálculos de las ramas se ponen en cola junto con los cálculos del tronco (excepto las ramas de correcciones urgentes)
- No se puede cerrar una rama si su compilación se utiliza en producción

**Consejo:** *Para mejorar el rendimiento de la rama, adapta el periodo de tiempo ajustando las fechas de inicio y finalización del proyecto para que solo incluyan los periodos necesarios. Esto reduce considerablemente el tiempo de cálculo.*

## Deshacer cambios

La función de reversión te permite restaurar un proyecto a una configuración anterior. Utiliza la función de reversión cuando un cambio registrado provoque problemas que deban solucionarse rápidamente.

**Advertencia:** *la reversión es una operación importante. Se descartarán todos los registros realizados después del punto seleccionado. Asegúrate de comprender las consecuencias antes de continuar y, si es necesario, considera la posibilidad de utilizar una rama para conservar el trabajo.*

**Para revertir una configuración:**

- Ve a **«Build» > «Historial de entregas»**
- Haz clic con el botón derecho del ratón en la versión que deseas restaurar y selecciona **«Revertir a»**
- Introduce un motivo descriptivo para la reversión
- Haz clic **en «Deshacer» y «Guardar»**
- Una vez completada la reversión, actualiza los espacios de trabajo haciendo clic en **Inicio > Actualizar espacio de trabajo**

## Promociones programadas y periódicas

TBM Studio admite promociones programadas para flujos de trabajo de implementación automatizados. Puedes configurar actualizaciones y promociones periódicas para automatizar la implementación de datos de tablas editables y otros cambios.

**Para configurar promociones programadas:**

- Ve a **«Compilación» > «Opciones de promoción»**
- Configurar **actualizaciones periódicas** para establecer el calendario de las compilaciones de prueba
- Configura **las promociones periódicas** para automatizar la implementación en producción
