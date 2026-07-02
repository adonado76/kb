---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Guía de configuración de los informes de asunción de costes"
breadcrumb: []
source_path: "cost-transparency/configuration/cost-takeout-config-guide.html"
images:
  - "resources/images/ct_images/cto-reports.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Guía de configuración de los informes de asunción de costes

## Visión general

Es importante comprender la finalidad y los objetivos de los informes de asunción de costes antes de conocer la configuración técnica.

Personas: Líderes de Unidades de Negocio, Gestores de Proveedores, Gestores de Compras, Líderes de Soluciones, Propietarios de Aplicaciones, Propietarios de Servicios.

Para: Líderes de organizaciones que desean identificar oportunidades para reducir y optimizar costes en mano de obra, proveedores y gasto en aplicaciones.

Valor: Los equipos de TI y Finanzas tienen dificultades para identificar oportunidades de reducción de costes de gran impacto debido a la fragmentación de los datos y a la falta de informes específicos sobre reducción de costes en IBM Apptio. Necesitan una visibilidad clara de las áreas específicas de los generadores de costes para optimizar su gasto en mano de obra, proveedores y aplicaciones.

Solución: Informes de asunción de costes

Producto: Apptio Norma de cálculo de costes

## Casos de uso

Informes listos para usar diseñados para ayudar a los usuarios de IBM Apptio a

- Identificar oportunidades para reducir y optimizar los costes de mano de obra, proveedores y aplicaciones
  - Apoyar la planificación estratégica de la plantilla y las decisiones de contratación
  - Optimice su cartera de proveedores
  - Optimice y racionalice su cartera de aplicaciones
- Permita que las organizaciones tomen decisiones rápidas, basadas en datos y defendibles.

## Requisitos previos

Los prerrequisitos para la solución de informes de asunción de costes son:

- IBM Apptio Licencia Costing Standard.
- IBM Apptio Versión del servidor: R12.11.17 (o superior).
- Versión de los componentes v120 en la configuración del proyecto
  - Consulte [esta guía](install-apptio-ibm-costing-old-template.html) para instalar componentes de v120 en proyectos con versiones de componentes anteriores.

## Instalación de componentes

El núcleo de la solución de Informes de Retirada de Costes se presenta a través del componente Informes de Retirada de Costes. Para los nuevos clientes, también será necesario instalar los componentes típicos, como la fuente de costes, la mano de obra, el proveedor, los activos fijos, las aplicaciones, etc., de acuerdo con la arquitectura general prevista. Los clientes existentes pueden reutilizar los componentes instalados previamente sin ningún cambio.

Estos cambios deben realizarse en TBM Studio

1. Vaya al icono Componentes en la pestaña Proyecto e instale el componente Informes de asunción de costes.

   ![Informes del CTO](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cto-reports.png)

   Para que se iluminen los informes de retirada de gastos, es posible que algunos de estos componentes deban estar preinstalados y configurados
   - CTF-Fuente de coste
   - CTF-Laboral
   - CTF-Vendedor
   - CT Apps- Solicitud
   - CTF - Torres IT
   - CT Apps - Almacenamiento
   - CT Apps- Servidor
   - Información sobre proveedores Contratos
2. Verifique y compruebe los cambios. Los tres informes estarán disponibles en sus respectivas colecciones:
   - Informe de costes de mano de obra: disponible en la colección Mano de obra
   - Informe de costes de proveedores: disponible en la colección de proveedores
   - Informe de costes de aplicación: disponible en la colección de aplicaciones
