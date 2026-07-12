---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Instalación de las nuevas soluciones de cálculo de costes IBM Apptio en proyectos de plantillas antiguas"
breadcrumb:
  - "Costing Standard"
  - "Configuración"
source_path: "cost-transparency/configuration/config-instnew.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Instalación de las nuevas soluciones de cálculo de costes IBM Apptio en proyectos de plantillas antiguas

## Términos clave

**Versión de servidor**

- Se refiere a la versión de IBM Apptio del software TBM Studio instalado. Determina las capacidades y la compatibilidad de la plataforma.
- Para comprobar la versión actual, vaya a **Configuración** > **Acerca de.**
- Serie actual: 12.11.1x

**Plantilla / Versión del componente**

- Se refiere a la versión del contenido listo para usar (OOTB) (tablas de datos, modelos, informes).
- Cada solución está vinculada a una versión específica del componente.
- Para comprobar la versión del componente, vaya a **TBM Studio** > **Proyecto** > **Configuración del proyecto** > **Versión del componente.**

Nota:

- Para instalar las nuevas soluciones, no es necesario actualizar todos los componentes existentes.
- Consulte la sección **[Detalles](#aicot__solutionversiontable "(se abre en una pestaña o una ventana nueva)")** de la versión de la solución para identificar la versión del servidor y la versión de la plantilla necesarias para la solución que desee.

**Pasos**

- **Comprueba la versión del servidor** : asegúrate de que la versión del servidor de tu instancia sea igual o posterior a la versión de lanzamiento de la solución.
- **Identifique la versión requerida del componente** : utilice **[los detalles de la versión de la solución](#aicot__solutionversiontable "(se abre en una pestaña o una ventana nueva)")** para encontrar la versión del componente (por ejemplo, v120 ).
- **Cambiar temporalmente la versión del componente** : Vaya a **Proyecto** > **Configuración del proyecto**. Cambia la versión del componente para que coincida con la versión de la solución.
- **Instalar los componentes de la solución** : vaya a la pestaña **Componentes** e instale los componentes necesarios de la solución.
- **Actualizar los componentes existentes (si es necesario)** : revertir y volver a aplicar las personalizaciones después de actualizar los componentes o aplicar manualmente los cambios en las tablas maestras según la guía de configuración.
- **Revertir el cambio en la «Configuración del proyecto** »: volver a la versión original del componente para evitar que aparezcan avisos de actualización.

**Consejos profesionales**

- Documente los cambios personalizados para facilitar su reutilización.
- Consulte siempre la Guía de configuración proporcionada con la solución.
- Podemos tener múltiples versiones de diferentes componentes en un proyecto.

## Detalles del lanzamiento de la versión de la solución

Tabla 1. Detalles del lanzamiento de la versión de la solución

| IBM Apptio Cálculo del coste de nuevas soluciones | Fundamentos del cálculo de costes | Norma de cálculo de costes | Plantilla | Versión de servidor |
| --- | --- | --- | --- | --- |
| Impacto del TCO de la TI híbrida | - | Sí | v120 | 12.11.12 |
| Coste total de propiedad de la nube pública | Sí | Sí | v120+v200 | 12.11.13 |
| Apptio - Integración con Turbonomic (disponible para todos) | - | Sí | v120 | 12.11.13 |
| Costo total de propiedad y uso de la IA | - | Sí | v120 | 12.11.14 |
| Costo total de propiedad del mainframe | - | Sí | v120 | 12.11.17 |
| Información sobre los costes de mantenimiento de Maximo | N/D | N/D | v200 | 12.11.17 |
| Informes de costes de retirada | - | Sí | V120 | 12.11.17 |
| Costo total de propiedad del producto | - | Sí | v120 | 12.11.18 |
| Coste total de propiedad (TCO) de los centros de datos | - | Sí | v120 | 12.11.22 |
| Informes predefinidos modernizados – Lote 1 (Finanzas, Proveedores, Aplicaciones, Mano de obra, Coste total de propiedad de la nube pública, Coste total de propiedad del mainframe, Coste total de propiedad de la IA, Servicios) | - | Sí | v120 | 12.11.22 |
