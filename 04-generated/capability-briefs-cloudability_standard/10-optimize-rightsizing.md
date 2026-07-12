---
tbm_concept: "Optimize — Rightsizing (recomendaciones de dimensionamiento por tipo de recurso a través de cuatro proveedores de nube, Autoscale Action, preferencias globales, y snoozing)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/optimize-rightsizing.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-explorer.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-awsec2.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-ec2-autoscaling-group-asg.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-ebs.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-elasticip.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-lambda.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-rds.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-amazon-redshift.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-s3.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-azure-compute.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-azure-compute-scale-sets.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-azure-disk.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-azure-sql.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-azure-blob-storage.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-gcp-google-compute-engine-gce.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-gcp-google-compute-engine-gce-managed-instance-groups-mig.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-gcp-google-persistent-disk-gpd.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-gcp-google-cloud-storage-gcs.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-oci-virtual-machines-vms.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-autoscale-action.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-kubernetes-containers.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-preferences.md
  - kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-snoozing-recommendations.md
last_updated: "2026-07-09"
---
# Optimize — Rightsizing — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Con el marco conceptual de Workload Optimization ya establecido en el capítulo anterior, Rightsizing es su implementación concreta: recomendaciones específicas por recurso individual, a través de 18 tipos de servicio distintos en cuatro proveedores de nube, más un motor de preferencias que permite ajustar la agresividad y el alcance de esas recomendaciones a la tolerancia al riesgo real de la organización.

## Cómo lo resuelve IBM Cloudability Standard

**Ventana de recomendación por defecto: 10 días, con justificación explícita.** "10 días captura las tendencias de performance más recientes y es más predictivo del uso futuro de recursos" — con la opción de extender a 30 días para un análisis de tendencia más amplio.

**Cobertura por proveedor, con 18 dashboards especializados:**
- **AWS (8 servicios)** — EC2, EC2 Auto Scaling Groups (ASG), EBS, Elastic IP, Lambda (requiere permisos IAM específicos y Lambda Insights habilitado para obtener métricas de memoria), RDS, Redshift, y S3.
- **Azure (5 servicios)** — Compute, Compute Scale Sets, Disk, SQL, y Blob Storage.
- **GCP (4 servicios)** — Google Compute Engine (GCE), GCE Managed Instance Groups (MIG), Persistent Disk, y Cloud Storage.
- **OCI (1 servicio)** — Virtual Machines.

**Estructura consistente de dashboard a través de todos los tipos de recurso**: tabla de recomendaciones con columnas de Resource ID/Name/Account, selector de cuenta, selector de ventana temporal (10/30 días), sistema de filtros (por menú desplegable o por clic directo en valores hipervinculados de la tabla), y tres KPIs estándar — **Total Spend**, **Estimated Idle Savings** (ahorro de recomendaciones de terminación) y **Estimated Rightsizing Savings** (ahorro de recomendaciones de redimensionamiento). Caso especial documentado: Elastic IP solo soporta recomendaciones de terminación (no redimensionamiento), por lo que su Estimated Rightsizing Savings siempre muestra 0.

**Autoscale Action — la recomendación más sofisticada técnicamente, para cargas de trabajo elásticas.** Resuelve el problema de recursos con picos de utilización muy variables (CPU, red, memoria, GPU), que tradicionalmente se sobre-aprovisionan para cubrir el pico máximo, generando gasto excesivo el resto del tiempo. En vez de redimensionar una sola instancia, recomienda **convertirla en un Auto Scaling Group (ASG)** de múltiples instancias más pequeñas que escalan según demanda — modelando target tracking sobre CPU, red, memoria y GPU (cuando disponible) para derivar el conteo mínimo y máximo de instancias recomendado. El razonamiento del conteo máximo está documentado con un ejemplo numérico concreto: si la instancia original tiene 4 veces más memoria que la instancia recomendada del ASG, se recomienda un conteo máximo de 4 instancias, para igualar la capacidad total. Ventaja de costo explícita: no se cobra por instancias del ASG que no están activas. Limitaciones documentadas: el riesgo se fija en un mínimo de 1 (no todas las cargas de trabajo son apropiadas para ASG), y los miembros de un ASG ya existente quedan excluidos de este tipo de recomendación.

**Kubernetes Containers** — recomendaciones de rightsizing aplicadas a nivel de contenedor, complementando el Container Cost Allocation ya documentado en Insights.

**Rightsizing Preferences — control global de qué recomendaciones se muestran, en dos pestañas.** **Compute (VM) Preferences** con cinco dimensiones configurables: Generations and Instances (excluir tipos de instancia no vigentes, o limitar recomendaciones a la misma familia de instancia para preservar cobertura de compromisos existentes), Processor Architecture (excluir arquitecturas específicas, permitir recomendaciones cross-arquitectura con advertencia de verificar compatibilidad de carga de trabajo primero), Capacity Reduction (incluir recomendaciones que reducirían capacidad disponible cuando no hay métricas de utilización para esa dimensión), Cost Saving Threshold (monto mínimo de ahorro en 30 días para que una recomendación se muestre; cero desactiva el filtro), y Resource Lifespan (eliminar recomendaciones de recursos inactivos por un período especificado). **Object Storage (S3) Preferences** permite excluir clases específicas de almacenamiento (Standard, Intelligent Tiering, Standard-IA, One Zone-IA, Glacier en sus variantes) de las recomendaciones.

**Múltiples niveles de filtrado documentados explícitamente**: preferencias globales (Settings), filtros en la página de Rightsizing misma, y filtros adicionales dentro del panel de detalle de cada recomendación individual.

**Snoozing Recommendations** — la capacidad de posponer temporalmente una recomendación sin descartarla permanentemente, para casos donde el equipo ya conoce la oportunidad pero no puede actuar de inmediato (ej. una ventana de mantenimiento programada).

## Por qué importa en una conversación con el cliente

La cobertura de 18 tipos de servicio a través de cuatro proveedores es el mejor argumento de amplitud de producto para cualquier cliente multi-nube — vale la pena confirmar explícitamente cuáles de estos 18 servicios corresponden a la huella real de infraestructura del cliente antes de la primera demo, para enfocar la conversación en lo relevante.

Autoscale Action es el ejemplo más sofisticado y persuasivo de todo el módulo de Rightsizing para conversaciones con equipos de infraestructura técnicamente maduros — el razonamiento matemático detrás del conteo de instancias (igualar capacidad total, no solo aproximar) genera confianza en que la recomendación no es una heurística simplista.

Las Rightsizing Preferences (en particular Generations and Instances, que puede limitar recomendaciones a la misma familia para preservar compromisos existentes) es la pregunta de discovery correcta antes de activar rightsizing para un cliente que ya tiene Reserved Instances o Savings Plans vigentes — sin esta configuración, Rightsizing podría recomendar migrar a un tipo de instancia que invalide la cobertura de un compromiso ya comprado.

## Documentos fuente

- Rightsizing (índice) — `kb/02-product-docs/apptio-cloudability-standard/en/optimize-rightsizing.md`
- Rightsizing Explorer — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-explorer.md`
- AWS EC2 — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-awsec2.md`
- AWS EC2 Auto Scaling Group (ASG) — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-ec2-autoscaling-group-asg.md`
- AWS EBS — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-ebs.md`
- AWS Elastic IP — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-elasticip.md`
- AWS Lambda — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-lambda.md`
- AWS RDS — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-rds.md`
- Amazon Redshift — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-amazon-redshift.md`
- AWS S3 — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-aws-s3.md`
- Azure Compute — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-azure-compute.md`
- Azure Compute Scale Sets — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-azure-compute-scale-sets.md`
- Azure Disk — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-azure-disk.md`
- Azure SQL — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-azure-sql.md`
- Azure Blob Storage — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-azure-blob-storage.md`
- GCP Google Compute Engine (GCE) — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-gcp-google-compute-engine-gce.md`
- GCP GCE Managed Instance Groups (MIG) — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-gcp-google-compute-engine-gce-managed-instance-groups-mig.md`
- GCP Google Persistent Disk (GPD) — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-gcp-google-persistent-disk-gpd.md`
- GCP Google Cloud Storage (GCS) — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-gcp-google-cloud-storage-gcs.md`
- OCI Virtual Machines (VMs) — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-oci-virtual-machines-vms.md`
- Autoscale Action for Rightsizing — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-autoscale-action.md`
- Rightsizing Kubernetes Containers — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-kubernetes-containers.md`
- Rightsizing Preferences — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-preferences.md`
- Snoozing Recommendations — `kb/02-product-docs/apptio-cloudability-standard/en/rightsizing-snoozing-recommendations.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
