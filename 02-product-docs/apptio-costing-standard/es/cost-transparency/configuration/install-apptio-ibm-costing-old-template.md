---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Instalación de las nuevas soluciones de cálculo de costes IBM Apptio en proyectos de plantillas antiguas"
breadcrumb: []
source_path: "cost-transparency/configuration/install-apptio-ibm-costing-old-template.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Instalación de las nuevas soluciones de cálculo de costes IBM Apptio en proyectos de plantillas antiguas

## Términos clave

**Versión de servidor**

- Se refiere a la versión del software IBM Apptio TBM Studio instalada. Determina las capacidades y la compatibilidad de la plataforma.
- Para comprobar la versión actual, vaya a **Ajustes** > **Acerca de**
- Serie actual: 12.11.1x

**Plantilla / Versión del componente**

- Se refiere a la versión del contenido Out-of-the-Box (OOTB) (tablas de datos, modelos, informes).
- Cada solución está vinculada a una versión específica del componente.
- Para comprobar la versión del componente, vaya a **TBM Studio** > **Proyecto** > **Configuración del proyecto** > **Versión del componente**

Nota:

- Para instalar las nuevas soluciones, no es necesario actualizar todos los componentes existentes.
- Consulte la sección **[Detalles de la versión de la solución](#aicot__solutionversiontable "(se abre en una pestaña o una ventana nueva)")** para identificar la versión del servidor y la versión de la plantilla necesarias para la solución deseada.

**Pasos**

- **Compruebe la versión del servidor** : Asegúrese de que la versión del servidor de su instancia es igual o más reciente que la versión de lanzamiento de la solución.
- **Identifique la versión requerida del componente** : Utilice **[los detalles de la versión de la solución](#aicot__solutionversiontable "(se abre en una pestaña o una ventana nueva)")** para encontrar la versión del componente (por ejemplo, v120 ).
- **Cambiar temporalmente la versión del componente** : Vaya a **Proyecto** > **Configuración del proyecto**. Cambie la Versión del componente para que coincida con la versión de la solución.
- **Instale los componentes de la solución** : Vaya a la pestaña **Componentes** e instale los componentes necesarios de la solución.
- **Actualice los componentes existentes (si es necesario)** : Revierta y vuelva a aplicar las personalizaciones después de actualizar los componentes o aplique manualmente los cambios a las Tablas Maestras según la Guía de Configuración.
- **Revertir el cambio de "Ajustes del proyecto"** : Volver a la Versión del Componente original para evitar avisos de actualización.

**Consejos profesionales**

- Documente los cambios personalizados para facilitar su reaplicación.
- Consulte siempre la Guía de configuración suministrada con la solución.
- Podemos tener varias versiones de distintos componentes en un proyecto.

## Detalles de la versión de la solución

Cuadro 1. Detalles de la versión de la solución

| IBM Apptio Cálculo de costes de nuevas soluciones | Aspectos básicos del cálculo de costes | Norma de cálculo de costes | Plantilla | Versión de servidor |
| --- | --- | --- | --- | --- |
| Impacto de la TI híbrida en el coste total de propiedad | - | Sí | v120 | 12.11.12 |
| TCO de la nube pública | Sí | Sí | v120+v200 | 12.11.13 |
| Apptio - Integración de Turbonomic (GA) | - | Sí | v120 | 12.11.13 |
| TCO y uso de la IA | - | Sí | v120 | 12.11.14 |
| TCO de mainframe | - | Sí | v120 | 12.11.17 |
| Información sobre los costes de mantenimiento de Maximo | N/D | N/D | v200 | 12.11.17 |
| Informes de asunción de costes | - | Sí | V120 | 12.11.17 |
| TCO del producto | - | Sí | v120 | Pendiente de publicación |
