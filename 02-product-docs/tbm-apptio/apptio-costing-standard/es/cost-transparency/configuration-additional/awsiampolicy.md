---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Apptio - AWS Política IAM"
breadcrumb: []
source_path: "cost-transparency/configuration-additional/awsiampolicy.html"
images:
  - "resources/images/ct_images/8285_1.png"
  - "resources/images/ct_images/8285_2.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Apptio - AWS Política IAM

- Se aplica a: Apptio Costing Standard o Apptio Cloud Cost Management ejecutándose en TBM Studio v12.3.3 o posterior.

El documento adjunto incluye la política IAM basada en JSON necesaria al configurar un nuevo rol en AWS.This La política IAM incluye varios permisos que permiten a Datalink (Classic) acceder a los datos de su entorno AWS que CCM necesita para proporcionar análisis sobre su coste y consumo de AWS, así como recomendaciones de Trusted Advisor. La siguiente figura muestra las distintas secciones de la política IAM.

Nota: Sólo la primera sección ( S3-related ) es necesaria para los usuarios del conector multicloud.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8285_1.png)

La API de asistencia es la única opción para acceder a los datos de Trusted Advisor y requiere el permiso de asistencia para funcionar correctamente. La siguiente captura de pantalla de la documentación de AWS ilustra la limitación y, para obtener más información, puede consultar la documentación de AWS disponible aquí: [Introducción al soporte AWS](https://docs.aws.amazon.com/awssupport/latest/user/getting-started.html "(se abre en una pestaña o una ventana nueva)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8285_2.png)

[Enlace al archivo de políticas](https://community.apptio.com/viewdocument/apptio-aws-iam-policy?CommunityKey=15f4e51d-d06f-4641-94c5-f2598d137d06&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)")
