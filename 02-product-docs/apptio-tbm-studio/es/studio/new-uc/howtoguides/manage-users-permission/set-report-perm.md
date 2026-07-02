---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar permisos de informes por rol"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Gestionar usuarios y permisos"
  - "Control de accesos"
source_path: "studio/new-uc/howtoguides/manage-users-permission/set-report-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar permisos de informes por rol

|  |  |
| --- | --- |
| **Objetivo** | Controlar qué roles de usuario pueden ver e interactuar con informes específicos |
| **Tiempo estimado** | Entre 10 y 15 minutos por informe |
| **Requisitos previos** | Rol de administrador o rol personalizado con los permisos adecuados; roles configurados en el proyecto |

## Cuándo utilizar este procedimiento

Utiliza los permisos de informes cuando necesites restringir el acceso a informes completos o colecciones de informes a roles de usuario específicos. Esta es la primera línea de control de acceso: si un usuario no puede ver un informe, no puede acceder a ninguno de los datos que contiene.

**Pasos**

**Opción A: Establecer permisos al crear un informe**

1. Ve a **TBM Studio** y haz clic en la pestaña **Inicio**.
2. Haz clic en **«Nuevo»** y, a continuación, selecciona «**Informe** ».
3. Introduce un nombre y una descripción para el informe.
4. En la sección **«Visible para»**, selecciona qué roles pueden ver este informe. Las opciones dependen de los permisos de tu rol.
5. Complete la configuración restante del informe y haga clic en **Aceptar**.

**Opción B: Modificar los permisos de un informe existente**

1. En el **Explorador de proyectos**, ve a **«Informes»** y busca el informe.
2. Echa un vistazo al informe.
3. En la pestaña **Proyectos**, en el grupo **Avanzadas**, haz clic en **Permisos**.
4. En el cuadro de diálogo de permisos, seleccione o deseleccione los roles para controlar la visibilidad de los informes.
5. Haz clic en **«Aplicar»** para guardar los cambios.
6. Compila el informe para aplicar los cambios al entorno de prueba.

**Opción C: Configurar la visibilidad de los componentes por rol**

En los casos en los que los distintos roles deban ver componentes diferentes dentro del mismo informe, utilice la visibilidad de componentes basada en roles en lugar de crear informes separados:

1. Echa un vistazo al informe y ábrelo en el diseñador de informes.
2. Crea un contenedor **de grupo** para los componentes que deben ser específicos de cada rol.
3. Añade al grupo los componentes (tablas, gráficos) que deben ser visibles para un rol específico.
4. Configura el grupo para que solo sea visible para el rol de destino.
5. Repite los pasos 2 a 4 para cada rol que requiera una vista diferente.
6. Coloca los grupos uno encima de otro en la superficie de presentación.
7. Consulta el informe.

Nota: Si un usuario tiene varios roles con diferentes configuraciones de visibilidad de grupo, verá los componentes del rol que se encuentra en la parte superior de la pila de grupos.

## Resultados previstos

- Los usuarios con roles autorizados ven el informe en el Buscador de informes y pueden acceder a él
- Los usuarios que no tengan los roles necesarios no verán el informe en la lista
- La visibilidad de los componentes (si está configurada) muestra contenido adecuado para cada rol en los informes compartidos

## Errores habituales

- **Permisos heredados ( pre-12.7 ):** En configuraciones anteriores, al habilitar los permisos basados en roles se creaban copias independientes de los informes para cada rol. TBM Studio 12.7 + utiliza un enfoque unificado. Si dispone de copias de informes heredados, consulte «Migrar el control de acceso a los informes» en la sección 6.3.
- **Informes predeterminados:** No se pueden eliminar los informes predeterminados. Utiliza los permisos para restringir el acceso.
- **Olvidarse de guardar:** los cambios en los permisos no surtirán efecto hasta que se guarde el informe y se complete el cálculo.

## Tareas relacionadas

- [Crear y gestionar colecciones de informes](../create-reports/build-rc.html)
- [Configurar roles personalizados](config-custom-roles.html)
- Desactivar informes (Sección « 6.3 »)

**Tema principal:** [Control de acceso](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
