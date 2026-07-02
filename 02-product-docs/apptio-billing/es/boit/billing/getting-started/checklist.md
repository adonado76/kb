---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Lista de verificación de implementación"
breadcrumb:
  - "Billing"
  - "Cómo utilizar esta guía"
source_path: "boit/billing/getting-started/checklist.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Lista de verificación de implementación

Para cualquiera que esté planificando o modificando una implementación de facturación, esta lista de verificación de alto nivel resume la guía. Las secciones posteriores proporcionan los pasos detallados.

**Confirmar la edición de facturación y los componentes en uso.**

- Determine si la organización utiliza Billing Essentials o Billing Standard.
- Verifique que se haya seleccionado la versión correcta de la plantilla de componentes. Consulte [las notas](../release-notes/whats-new.html "Esta sección describe únicamente los cambios en el contenido de facturación listo para usar, no en la plataforma subyacente. Para las actualizaciones a nivel de plataforma, como el comportamiento de TBM Studio y el servidor cliente, los lectores deben revisar las notas de la versión de TBM Studio y tener en cuenta los cambios aplicables junto con lo que se documenta aquí.") de la versión para conocer las versiones aplicables.

**Revisar los requisitos previos**

- Verifique que Costing esté implementado y sea estable.
- Confirme que las tablas maestras y los conjuntos de datos necesarios existen o que existe un plan para completarlos.

**Alinear roles y acceso**

- Identifique a los administradores, analistas, propietarios de servicios o productos, altos directivos y otras partes interesadas.
- Confirme que se ha concedido el acceso adecuado en el front-end y, cuando corresponda, en TBM Studio.

**Planificar entornos y promociones**

- Decida cómo se desarrollan y prueban los cambios en Desarrollo y Preproducción.
- Defina el proceso de promoción y las aprobaciones para trasladar las compilaciones a producción.

**Diseñar el ciclo de facturación**

- Acordar los periodos de facturación, los plazos y los puntos de control de validación.
- Defina quién valida, quién aprueba y quién recibe los resultados finales.

**Elija la ruta de configuración.**

- Utilice [Configuración de Billing Essentials (Implementación)](../config-be/be-overvie.html "En esta sección se describe cómo se configura Billing Essentials en un proyecto de Costing Essentials, desde la instalación de los componentes hasta las primeras facturas utilizables. Se da por hecho que Costing Essentials ya está implementado y es estable.") para Billing Essentials.
- Utilice [la configuración del estándar de facturación (implementación)](../config-bs/bs-overview.html "En esta sección se describe cómo se configura Billing Standard sobre un proyecto de Costing Standard, desde la instalación de los componentes hasta las primeras facturas con dominios enriquecidos utilizables. Se supone que Costing Standard ya está implementado y es estable.") para el estándar de facturación.

**Planificar la formación y la incorporación**

- Utilice la [Guía de formación basada en funciones](../role-based-tg/train-objectives.html "En esta sección se describe cómo formar a diferentes públicos para que el sistema de facturación se utilice y se confíe en él, y no solo se implemente técnicamente. Úsalo para diseñar la incorporación, la formación continua y los traspasos cuando las personas cambian de funciones.") para determinar qué funciones necesitan qué secciones e informes.

Una vez que estos puntos estén claros, el resto de la guía se puede leer de forma selectiva, utilizando las notas de edición y los resúmenes de las secciones para encontrar la profundidad necesaria para una tarea determinada.
