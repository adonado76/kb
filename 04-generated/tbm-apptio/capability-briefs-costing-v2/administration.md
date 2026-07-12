---
tbm_concept: "Administration (roles y permisos de usuario, modelo de upgrade de Costing Standard, gestión del impacto de personalizaciones)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/admin/user-role-perm.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/admin/upgrade-cs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/admin/con-ver-lay.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/admin/cust-contet.md
last_updated: "2026-07-05"
---
# Administration — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

Un modelo de costo bien construido puede degradarse rápidamente sin dos disciplinas de gobernanza: control claro de quién puede ver y modificar qué dentro del proyecto, y un proceso ordenado para absorber actualizaciones del producto sin romper personalizaciones ya construidas. El brief de Configuration ya advirtió que la personalización tiene un costo futuro en cada upgrade — esta categoría es donde ese costo se gestiona de forma concreta.

## Cómo lo resuelve Apptio Costing Standard

### Roles y Permisos de Usuario

El modelo de permisos de Costing Standard distingue entre roles administrativos con acceso completo de configuración (gestión de componentes, datos de referencia, reglas de asignación) y roles de consumo con acceso a reportes y análisis pero sin capacidad de alterar el modelo — un patrón consistente con el resto del portafolio Apptio ya documentado (Planning distingue Admin/Budget Process Owner de Cost Center Owner de forma análoga). Los permisos pueden ajustarse a nivel granular, permitiendo construir roles personalizados que combinen exactamente el acceso que una organización necesita, en lugar de forzar una elección entre acceso total o acceso mínimo.

### El modelo de Upgrade de Costing Standard, en capas

**Upgrading Costing Standard** cubre el proceso general de actualización del producto — moviendo un proyecto de una versión de plantilla a otra, incorporando nuevas capacidades (como los módulos de AI TCO o Hybrid IT TCO Impact ya documentados, que requieren explícitamente instalarse en templates v120+).

**Content Version Upgrade** es un concepto más específico: el contenido predefinido de IBM Apptio (reportes, reglas de asignación, taxonomía) tiene su propio ciclo de versión, potencialmente independiente del ciclo de versión de la plataforma en sí — permitiendo absorber mejoras de contenido sin necesariamente requerir un upgrade de plataforma completo.

**Customizations and how they affect content upgrades** es, en efecto, la respuesta operativa a la advertencia ya planteada en el brief de Configuration: documenta específicamente qué tipos de personalización entran en conflicto con qué tipos de actualización de contenido, y qué pasos se requieren para reconciliar una personalización existente con un nuevo release de contenido estándar — el mecanismo formal de gestión de riesgo de upgrade que la advertencia general de Configuration anticipaba.

## Por qué importa en una conversación con el cliente

La documentación explícita de "Customizations and how they affect content upgrades" es una de las piezas de contenido más valiosas de todo el proyecto para conversaciones de gobernanza de largo plazo: le da a un Admin de cliente un marco concreto para evaluar, antes de aprobar una personalización, cuál será su costo de mantenimiento en el próximo ciclo de upgrade — una conversación que demasiadas implementaciones posponen hasta que ya es un problema.

El modelo de roles granular es un buen punto de discovery en organizaciones con estructuras de gobierno de datos financieros estrictas (bancos, aseguradoras): permite construir un modelo de acceso que refleje exactamente su política interna de separación de funciones entre quien configura el modelo de costo y quien solo lo consume para reporte.

La separación entre Content Version Upgrade y Upgrade de plataforma general es útil para calibrar expectativas de esfuerzo: un cliente puede beneficiarse de mejoras de contenido (nuevos reportes, reglas de asignación refinadas) sin necesariamente enfrentar la complejidad de un upgrade de plataforma completo — vale la pena aclarar esta distinción antes de que el cliente asuma que cualquier mejora de contenido implica un proyecto de upgrade mayor.

## Documentos fuente

- User Roles and Permissions — `02-product-docs/apptio-costing-standard/en/cost-transparency/admin/user-role-perm.md`
- Upgrading Costing Standard — `02-product-docs/apptio-costing-standard/en/cost-transparency/admin/upgrade-cs.md`
- Content Version Upgrade — `02-product-docs/apptio-costing-standard/en/cost-transparency/admin/con-ver-lay.md`
- Customizations and how they affect content upgrades — `02-product-docs/apptio-costing-standard/en/cost-transparency/admin/cust-contet.md`

*Nota: no se identificaron links públicos de ibm.com/docs embebidos verificables en esta categoría. Hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*