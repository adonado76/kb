---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "GCP Acreditación mediante acciones masivas"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectar Google Cloud"
source_path: "admin/gcp-credentialing-bulk-actions.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Acreditación mediante acciones masivas

**Visión general**

Las acciones masivas en la pantalla de credenciales de proveedores permiten a los administradores completar rápidamente el proceso de acreditación por adelantado en Cloudability.

Actualmente, esto está disponible para proyectos GCP, donde es posible:

1. Guardar rápidamente varias cuentas sin credenciales
2. Verifique en bloque varias cuentas para completar el proceso de acreditación de forma más rápida y sencilla.

**Requisitos previos**

**Guardar nuevas credenciales**Asegúrese de haber optado por la acreditación automatizada de los proyectos GCP para utilizar el ID de la organización GCP durante el proceso de acreditación**Verificar credenciales**No se requieren requisitos previos, podrás verificar todas las cuentas.

**Instrucciones**

Al hacer clic en **Acciones masivas** se abrirá una pantalla con varias pestañas.

Nota: Las funciones de cada pestaña son independientes entre sí.

**Guardar nuevas credenciales**

Esta función es aplicable a las cuentas GCP que cumplan los requisitos previos mencionados anteriormente.

1. Esta pantalla no aparecerá si no hay cuentas configuradas con el ID de organización de GCP

La pantalla muestra todas las cuentas con el estado Credenciales necesarias (X roja). Para guardar las credenciales

1. Seleccione las cuentas que necesitan credenciales.
2. Haga clic en **Revisar selección**.
3. Haga clic en **Guardar.**

Esto activaría el proceso de guardado masivo y el botón de acciones masivas se desactivaría hasta que el proceso finalizara.

1. Una vez guardadas, las cuentas pasarán al estado No verificado.
2. Descargue la plantilla « GCP » (Aplicación de políticas de seguridad de la consola de administración de Azure) de una de las cuentas guardadas y aplíquela a las cuentas « GCP » (Aplicación de políticas de seguridad de Azure) en la consola « GCP » (Administración de Azure).
3. Una vez completado, active la verificación de credenciales para las cuentas seleccionadas en el paso anterior.

**Verificar credenciales**

Esta pantalla muestra todas las cuentas excepto las que tienen el estado Credenciales necesarias (X roja).

Antes de activar la verificación masiva, asegúrese de que la plantilla se haya descargado y aplicado en la consola GCP.

1. Seleccione las cuentas que deben verificarse.
2. Haga clic en "Revisar selección"
3. Haga clic en **Verificar.**

Esto activaría el proceso de verificación masiva y el botón de acciones masivas se desactivaría hasta que el proceso finalizara.

Una vez completado, las cuentas pasarán a un estado de credencial verificada o a un estado de credencial no válida (debido a errores).

Nota: La duración de la finalización de las acciones masivas depende del número de cuentas.

**Tema principal:** [Conectar Google Cloud](../admin/connect-google-cloud-premium.html)
