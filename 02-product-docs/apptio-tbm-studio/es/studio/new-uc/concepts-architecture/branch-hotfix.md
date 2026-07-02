---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Ramas y correcciones"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Ciclo de vida de la compilación y la implementación"
source_path: "studio/new-uc/concepts-architecture/branch-hotfix.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ramas y correcciones

Las ramificaciones te permiten crear una copia completa de un proyecto, realizar cambios en paralelo y, a continuación, fusionar esos cambios. Esta función avanzada permite gestionar flujos de trabajo complejos en los que los procesos habituales de registro no son suficientes.

**Ramas frente a espacios de trabajo**

**Un espacio de trabajo** es un entorno específico para cada usuario en el que se almacenan los cambios realizados en los documentos extraídos hasta que se vuelven a guardar. Cuando extraes un documento, obtienes un bloqueo exclusivo sobre él.

**Una rama** es una copia completa del proyecto en el momento en que se creó. Los cambios realizados en una rama son independientes del tronco principal hasta que se fusionan. Tu espacio de trabajo en una rama es independiente de tu espacio de trabajo en el tronco.

**Cuándo utilizar las ramificaciones**

Las ramas admiten tres casos de uso principales:

**1. Cambios de configuración de larga duración**

Cuando los cambios de configuración tarden semanas o meses en completarse, crea una rama para trabajar en paralelo mientras se siguen cargando los datos operativos en el tronco. Ejemplo: una reestructuración importante del modelo que requiere pruebas exhaustivas.

**2. Corrección de emergencia en el entorno de producción**

Cuando el entorno de producción tenga un problema, pero el de desarrollo contenga cambios que aún no estén listos para su implementación, crea una rama de corrección. Soluciona el problema concreto en la rama, pásalo a Producción y, a continuación, integra la corrección en el tronco. Las ramas de correcciones se compilan en paralelo con otras compilaciones, sin pasar por la cola habitual.

**3. Auditar o archivar el estado anterior**

Cuando necesites consultar un estado anterior del proyecto —por ejemplo, un ejercicio fiscal cerrado—, crea una rama a partir de ese momento. Esto te permite ver las cifras exactas tal y como eran, aunque el modelo actual haya cambiado.

**Límites de las ramas y consideraciones sobre el rendimiento**

- **Límite de ramas:** máximo de 5 ramas por entorno (en todos los proyectos)
- **Uso de recursos:** Cada rama utiliza los mismos recursos que el proyecto de origen. Crear una rama duplica, en la práctica, el consumo de recursos.
- **Cola de cálculos:** los cálculos de las ramas (excepto los de las revisiones) se colocan en la cola junto con los cálculos del tronco. Si el tronco tarda 3 horas en calcularse, la rama también lo hará.
- **Optimiza el tiempo:** limita el intervalo de tiempo en tu rama (Configuración del proyecto > Configuración de tiempo) para reducir al mínimo el tiempo de cálculo. Utilice únicamente los periodos necesarios para la prueba.

Atención:

**Repercusión en el rendimiento:** antes de crear una rama, ten en cuenta el impacto que esto puede tener en los tiempos de cálculo. Si el cálculo de tu proyecto «trunk» tarda 3 horas, al crear una rama se iniciará inmediatamente un cálculo de más de 3 horas, que podría quedar en cola detrás o delante de los cálculos del «trunk».

**Creación de una rama de correcciones**

Cuando el equipo de producción necesita una solución urgente, pero el equipo de escenario aún no está listo para la promoción:

1. Accede al documento en el entorno de producción.
2. Echa un vistazo al documento. Cuando se te solicite, selecciona «Hotfix» (no «Development»).
3. Realiza los cambios y guarda el trabajo. La rama de correcciones se compila en paralelo con otras compilaciones.
4. Bloquea la rama de la revisión en Stage y selecciona «Promover ahora».
5. Incorpora los cambios al tronco principal para que no se pierdan.
6. Publica la versión del tronco que incluye la corrección incorporada.
7. Cierra la rama de correcciones para ahorrar recursos.

**Fusionar ramas**

Antes de fusionar, asegúrate de que:

- No hay ningún documento que se vaya a fusionar en el tronco
- Tú mismo no tienes ningún documento sacado del tronco
- Todos los documentos de la sucursal se han registrado

Para fusionar: en el historial de registros de la rama, selecciona los registros que deseas fusionar (Ctrl+clic para seleccionar varios), haz clic con el botón derecho y selecciona «Fusionar cambios en la rama». Resuelve cualquier conflicto si el mismo documento se ha modificado tanto en la rama como en el tronco. Una vez realizada la fusión, registra los documentos fusionados en el tronco.

Nota:

**Recomendación:** Limita los registros en la rama a unos 30 documentos cada vez. Si tienes 100 documentos prestados, devuélvelos en lotes de 30. Esto soluciona una limitación que se produce al fusionar un gran número de registros.
