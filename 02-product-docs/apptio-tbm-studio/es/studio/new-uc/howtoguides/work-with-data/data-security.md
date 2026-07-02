---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Seguridad de datos"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
source_path: "studio/new-uc/howtoguides/work-with-data/data-security.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Seguridad de datos

**Tipo de contenido:** Guía práctica

**Destinatarios:** Administradores, analistas de negocios

**Requisitos previos:** Conocimientos sobre tablas de transformación y conceptos básicos de gestión de usuarios

**Secciones relacionadas:** Sección 4.4 (Modelo de seguridad), Sección 6.3 (Seguridad y cumplimiento normativo)

## Introducción

La seguridad a nivel de fila (RLS) permite controlar qué filas de datos puede ver cada usuario en las tablas y los informes. En lugar de restringir el acceso a tablas completas, RLS permite filtrar los datos a un nivel granular en función del usuario que consulte la información. Por ejemplo, es posible que un director regional solo vea los datos de costes de su unidad de negocio, mientras que un director financiero vea los datos de todas las unidades.

En esta sección se ofrece una guía práctica y detallada para implementar RLS en la capa de datos. Para comprender el funcionamiento de la seguridad en TBM Studio, consulte **la sección «Modelo de seguridad de 4.4:** ». Para obtener información sobre la configuración de seguridad a nivel de administrador y las consideraciones de cumplimiento normativo, consulte **la sección «Seguridad y cumplimiento normativo de 6.3:** ».

**Conceptos clave**

- **Seguridad a nivel de fila (RLS):** un mecanismo de filtrado de datos que restringe las filas visibles en función del usuario actual. Anteriormente se denominaba «Filtros de vista» en TBM Studio 11.
- **Tabla de asignación:** tabla que define qué usuarios pueden acceder a qué elementos de datos. Contiene los ID de usuario y los elementos que tienen permiso para ver.
- **Proyecto de seguridad a nivel de fila:** un proyecto de sistema específico en el que se almacenan las tablas de correspondencias. Este proyecto se crea automáticamente al instalar una nueva instancia de « Apptio » y da servicio a todos los proyectos del dominio.
- **Paso RLS:** un paso del proceso añadido para transformar tablas que hace referencia a tablas de asignación con el fin de aplicar filtros de seguridad.

## Comprensión de la arquitectura de RLS

Antes de implementar RLS, conviene comprender cómo interactúan sus componentes:

1. **Las tablas de correspondencia** definen las relaciones entre el usuario y los datos. Se encuentran en el proyecto específico de seguridad a nivel de fila y asignan los ID de usuario a los valores de datos concretos (como unidades de negocio, centros de coste o regiones) a los que cada usuario puede acceder.
2. Se añaden **pasos RLS** para transformar los flujos de trabajo. Cada paso hace referencia a una tabla de correspondencias y especifica qué columna de la tabla de datos debe filtrarse según dicha correspondencia.
3. **Durante la ejecución**, cuando un usuario consulta una tabla o un informe, el sistema compara su ID de usuario con la tabla de correspondencias para determinar qué filas mostrar.

Importante: Las tablas no heredan automáticamente la configuración de RLS. Debes añadir un paso de RLS a cada tabla que requiera filtrado de seguridad. Si tu modelo tiene varias tablas (por ejemplo, «Cost Source» y «IT Resource Towers»), debes configurar RLS en cada una de ellas por separado.

Advertencia: La seguridad a nivel de fila afecta a todos los usuarios, excepto a los administradores. Los administradores tienen acceso al modo Studio y pueden crear informes que eludan el RLS, añadirse a las tablas de asignación o desactivar el RLS por completo. No confíes únicamente en RLS para proteger los datos confidenciales de los usuarios con privilegios de administrador.

- **[Guía práctica 1: Aplicar la seguridad a nivel de fila a las tablas](../../../../studio/new-uc/howtoguides/work-with-data/htg-arls.html)**
- **[Aplicar seguridad a nivel](../../../../studio/data_studio/apply-row-level-security.html)**   
   de fila ◆ Aplicable a: TBM Studio12.2 y versiones posteriores
- **[Guía práctica 2: Controlar el acceso mediante la asignación de usuarios](../../../../studio/new-uc/howtoguides/work-with-data/htg-cacc.html)**
- **[Buenas prácticas para la seguridad a nivel de fila](../../../../studio/new-uc/howtoguides/work-with-data/bp-rls-wn.html)**
