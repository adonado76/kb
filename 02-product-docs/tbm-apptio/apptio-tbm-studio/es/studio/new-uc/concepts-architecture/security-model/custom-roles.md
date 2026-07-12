---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Roles personalizados"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Control de acceso basado en roles (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/custom-roles.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Roles personalizados

Si los roles predeterminados no se ajustan a las necesidades de tu organización, puedes crear roles personalizados con los permisos exactos que necesites. Los roles personalizados te permiten aplicar el principio del mínimo privilegio, es decir, conceder a cada usuario exactamente el acceso que necesita y nada más.

**Cuándo crear roles personalizados**

- Necesitas un rol que se sitúe entre el de «usuario avanzado» y el de «usuario empresarial»; por ejemplo, usuarios que puedan ver los datos de staging pero no editar los modelos
- Desea restringir el acceso a la carga de datos a un equipo concreto, pero permitir que otros usuarios puedan consultar los informes
- Las cuentas de servicio de la API necesitan permisos mínimos (como acceso solo para subir archivos o solo para descargarlos)
- Quieres separar las tareas de edición de informes de las de edición de modelos

**Nivel de detalle de los permisos**

Los permisos en TBM Studio se dividen en cuatro categorías:

|  |  |  |
| --- | --- | --- |
| **Categoría** | **Ejemplos** | **Uso habitual** |
| Ver permisos | ViewObjectReports, ViewMetricReports, ViewTransformReports, ViewReportsSavedForEveryone, ViewAllData | Controlar qué tipos de informes y datos pueden ver los usuarios |
| Permisos de edición | Editar modelos, Editar informes personales, UploadData | Controlar quién puede modificar modelos, crear informes y cargar datos |
| Permisos de Acceso | AccessDev, AccessStg, AccessProd | Controlar a qué entornos (desarrollo, staging, producción) pueden acceder los usuarios |
| Permisos de ejecución | DrillDown, InteractiveBenchmarksAndCostData, Ver «Proactivo» | Control de funciones interactivas como la navegación por niveles y el acceso a datos de referencia |

**Principios de diseño de roles personalizados**

1. Empieza con el rol predeterminado más parecido y modifica los permisos, en lugar de crear uno desde cero.
2. Documenta la finalidad y el público destinatario de cada rol personalizado.
3. Prueba los roles personalizados suplantando la identidad de un usuario asignado a dicho rol antes de la implementación.
4. Revise periódicamente las funciones personalizadas para asegurarse de que siguen ajustándose a las necesidades de la organización.

Nota:

**Buenas prácticas: Roles de API**

En el caso de las cuentas de servicio de API, crea roles personalizados específicos con solo los permisos necesarios para la integración concreta. En el caso de las cuentas de solo carga, concede los permisos AccessDev, y UploadData. En el caso de las cuentas de solo descarga, conceda a AccessProd,, AccessStg, y DrillDown, los permisos de visualización correspondientes

**Tema principal:** [Control de acceso basado en roles (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
