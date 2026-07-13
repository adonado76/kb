---
tbm_concept: "Tag & Label Mapping (normalización de tags/labels de facturación por vendor, con reglas de precedencia y formatos exactos)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/spend-tag-label-mapping.md
last_updated: "2026-07-13"
---
# Setup — Organize - Tag & Label Mapping — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Cada proveedor de nube expone sus propias tags y labels con formato, reglas de precedencia y método de recolección distintos — algunos llegan directo en el archivo de facturación, otros requieren credenciales adicionales vía API. Tag & Label Mapping es la capa que normaliza toda esa heterogeneidad en dimensiones de reporte consistentes, para que "Environment" o "Owner" signifiquen lo mismo sin importar si el recurso vive en AWS, Azure, GCP, OCI, o en una plataforma SaaS como Databricks o Snowflake.

## Cómo lo resuelve IBM Cloudability Standard

**Soporte diferenciado por vendor, con métodos de recolección distintos.** AWS separa tags a nivel de recurso (vía CUR, sin permisos extra) de tags a nivel de cuenta (vía API, requiere el permiso `organizations:ListTagsForResource`, no disponible en Cloudability Gov). El formato cambia entre CUR legado (`aws:<tag key>` para tags de AWS, `<tag key>` para tags de usuario) y CUR 2.0 (`aws_<tag key>`, `user_<tag key>`) — un cliente que migra de CUR legado a CUR 2.0 tiene que reconfigurar sus Tags & Labels desde cero.

Azure diferencia tres niveles — resource (`cldy:Azure:ResourceTag:<key>`, sin permisos extra), resource group (`cldy:Azure:ResourceGroupTag:<key>`, requiere `management:Reader` o el permiso específico de la API de Resource Groups), y subscription (`cldy:Azure:SubscriptionLevelTag:<key>`, requiere `subscription:ReadSubscription`). Existe una regla de fallback importante: si un tag key existe tanto a nivel de recurso como de resource group y se mapea la llave genérica (ej. `project`), Cloudability usa el valor a nivel de recurso cuando está presente, y solo cae al de resource group si el de recurso está vacío — para evitar ese fallback automático, hay que mapear explícitamente la llave con prefijo `cldy:Azure:ResourceTag:`.

GCP expone labels de recurso, proyecto y sistema desde el billing export sin permisos adicionales, con una regla de precedencia fija cuando la misma llave existe en más de un nivel: **Resource > Project > System**. Los labels resultantes de "GKE Cost Allocation" nativo de GCP (prefijo `goog-k8s-*` o `k8s-*`) no se soportan — para costeo de contenedores por namespace/label hay que usar la feature de Cloudability Containers en su lugar.

OCI, IBM Cloud, Databricks, MongoDB y Snowflake tienen cada uno su propio formato de tag namespaced (ej. `cldy:oci:compartmentname`, `cldy:databricks:workspaceid`, `cldy:mongodb:groupid`, `cldy:snowflake:account:<key>` / `cldy:snowflake:warehouse:<key>`), todos sin permisos adicionales salvo el caso de Snowflake, que requiere habilitar la vista `TAG_REFERENCES` para que los tags a nivel de warehouse se poblén.

**Kubernetes labels son un caso aparte — no vienen de facturación.** Los labels de K8s no existen en la data de billing; son un resultado de la feature de Container Insights y solo están disponibles para mapeo una vez que se provisiona un clúster soportado (EKS, GKE, AKS, OpenShift) con el IBM FinOps Agent.

**Límite documentado: 50 dimensiones de reporte para Tags & Labels** — IBM incrementó este límite en 20 (de 30 a 50) específicamente para beneficiar a clientes multi-nube con muchas llaves de tag/label distintas.

**Regla de resolución cuando un recurso tiene múltiples tag keys**: Cloudability toma el primer tag key válido (con valor) en el orden en que fue agregado a la lista de la dimensión — no hay soporte para mapear múltiples tag keys a una sola dimensión vía regex o wildcards.

**Regla de precedencia configurable cuando el mismo recurso tiene tag, resource group tag, y subscription tag simultáneamente (caso Azure).** El orden en que se agregan los tag keys a la dimensión determina cuál gana: si se agrega primero el resource-level tag en la secuencia, ese gana para cualquier recurso que lo tenga, y solo cae al siguiente nivel de la secuencia (resource group, luego subscription) para los recursos que no tengan el nivel anterior. Si se invierte el orden (resource group primero), el resource group tag gana para todos los recursos que lo tengan, sin importar que también tengan resource-level tag.

**Cambios de valor de tag no son retroactivos.** Si un tag cambia de valor en el lado del CSP (ej. de "playground" a "game"), la data histórica ya escrita mantiene el valor viejo — solo la data nueva refleja el cambio. Para corregir retroactivamente hay dos rutas: usar Business Mappings (que sí se pueden aplicar a data histórica), o abrir un caso de soporte para que Apptio dispare un **data refetch** — con la advertencia explícita de que un refetch sobrescribe toda la data previa con los valores actuales, y en el caso de tags jerárquicos (cuenta/subscripción) Cloudability tomará el valor **actual** de esos tags y lo aplicará a toda la data re-obtenida.

## Por qué importa en una conversación con el cliente

**RETOS QUE RESUELVE:** clientes multi-cloud enfrentan el problema de que "Environment" en AWS no es lo mismo que "Environment" en Azure a nivel de formato — sin esta capa de normalización, cada reporte tendría que lidiar con la heterogeneidad de cada vendor por separado. También resuelve la pregunta recurrente de por qué aparecen valores `(not set)`: puede ser que el vendor no esté configurado para incluir esos tags en el export (ej. AWS Billing Preferences no incluye el tag en el CUR), que el recurso simplemente no esté etiquetado, que el spend no sea "taggable" (soporte, comisiones de compromiso, impuestos, snapshots de EBS), o que falte solicitar un reprocess de la data histórica.

**VALOR DIFERENCIAL:** la documentación de reglas de precedencia (Azure resource > resource group > subscription, GCP resource > project > system) es un detalle que anticipa conflictos de tagging antes de que el cliente los descubra en producción — vale la pena mapearlo explícitamente durante el diseño de taxonomía en vez de asumir un comportamiento por defecto. El límite de 50 dimensiones y el hecho de que fue ampliado específicamente por presión de clientes multi-cloud es un dato útil para clientes con huella grande en más de tres proveedores. La distinción entre Business Mappings (retroactivo) y Tag & Label Mapping (no retroactivo salvo refetch) es la pregunta correcta a hacer antes de prometerle a un cliente que un cambio de tagging "arreglará" reportes históricos.

## Documentos fuente

- Tag and Label Mapping — `kb/02-product-docs/apptio-cloudability-standard/en/spend-tag-label-mapping.md`
- Fuente oficial: https://www.ibm.com/docs/en/cloudability-commercial/cloudability-standard/saas?topic=spend-tag-label-mapping

*Nota: versión en español/portugués se genera en una siguiente pasada.*
