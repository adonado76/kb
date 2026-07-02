---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Instalación de las nuevas soluciones de cálculo de costes IBM Apptio en proyectos de plantillas antiguas"
breadcrumb: []
source_path: "studio/admin/installing-new-solutions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Instalación de las nuevas soluciones de cálculo de costes IBM Apptio en proyectos de plantillas antiguas

## Términos clave que debe conocer

**Versión del servidor:**

- Se refiere a la versión del software IBM Apptio TBM Studio instalada. Determina las capacidades y la compatibilidad de la plataforma.
- Los usuarios pueden comprobar su versión actual en: Configuración > Acerca de
- Serie actual: 12.11.1x

**Plantilla / Versión del componente:**

- Se refiere a la versión del contenido Out-of-the-Box (OOTB) (tablas de datos, modelos, informes).
- Cada solución está vinculada a una versión específica del componente.
- Compruébelo en: TBM Studio > Proyecto > Configuración del proyecto > Versión del componente

Importante:

- Para instalar las nuevas soluciones, NO es necesario actualizar todos los componentes existentes.
- Consulte la tabla de la página siguiente para identificar la versión de servidor y la versión de plantilla necesarias para la solución deseada.

## Guía paso a paso

1. **Compruebe la versión del servidor:** Asegúrese de que la versión del servidor de su instancia es igual o más reciente que la versión de lanzamiento de la solución.
2. **Identifique la versión requerida del componente:** Utilice la tabla de versiones de soluciones para encontrar la versión del componente (por ejemplo, v120 ).
3. **Cambiar temporalmente la versión del componente:** Vaya a Proyecto > "Configuración del proyecto". Cambie la Versión del componente para que coincida con la versión de la solución.
4. **Instale los componentes de la solución:** Vaya a la pestaña Componentes e instale los componentes necesarios de la solución.
5. **Actualice los componentes existentes (si es necesario):** Revierta y vuelva a aplicar las personalizaciones después de actualizar los componentes O aplique manualmente los cambios a las Tablas Maestras según la Guía de Configuración.
6. **Revertir el cambio de "Ajustes del proyecto":** Vuelva a la versión original del componente para evitar los avisos de actualización.

Para saber más, vea el vídeo: [Cómo instalar los nuevos componentes de la solución de cálculo de costes IBM Apptio en proyectos con versiones de plantillas anteriores](https://community.ibm.com/community/user/viewdocument/how-to-install-new-ibm-apptio-costi?CommunityKey=2e85ed45-9b8a-486c-bd55-019253d466eb "(se abre en una pestaña o una ventana nueva)")

Consejo: Documente los cambios personalizados para facilitar su reaplicación. Consulte siempre la Guía de configuración suministrada con la solución.

## Detalles de la versión de la solución

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| IBM Apptio Cálculo de costes  Nuevas soluciones | Aspectos básicos del cálculo de costes | Norma de cálculo de costes | Plantilla | Versión de servidor |
| Impacto de la TI híbrida en el coste total de propiedad | - | Sí | v120 | 12.11.12 |
| TCO de la nube pública | Sí | Sí | v120 + v200 | 12.11.13 |
| Apptio - Integración de Turbonomic (GA) | - | Sí | v120 | 12.11.13 |
| TCO y uso de la IA | - | Sí | v120 | 12.11.14 |
| TCO de mainframe | - | Sí | v120 | Pendiente de publicación |
| Información sobre los costes de mantenimiento de Maximo | N.A. | N.A. | v200 | 12.11.15 |
| TCO del producto | - | Sí | v120 | Pendiente de publicación |
