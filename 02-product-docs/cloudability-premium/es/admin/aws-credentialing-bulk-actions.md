---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "AWS Acreditación mediante acciones masivas"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conexión con AWS - Guía de integración de clientes"
source_path: "admin/aws-credentialing-bulk-actions.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Acreditación mediante acciones masivas

**Visión general**

La pantalla Acciones masivas en las credenciales de proveedores permite a los administradores completar rápidamente el proceso de acreditación por adelantado en Cloudability.

Actualmente esto está disponible para AWS cuentas vinculadas donde su posible:

1. Guardar rápidamente varias cuentas sin credenciales
2. Actualizar varias cuentas
3. Verifique en bloque varias cuentas para completar el proceso de acreditación de forma más rápida y sencilla.

**Requisitos previos**

**Guardar nuevas credenciales:**Asegúrese de haber optado por la acreditación automática de cuentas vinculadas para AWS al acreditarse**.****Verificar credenciales:**No se requieren requisitos previos y podrás verificar todas las cuentas.

**Instrucciones**

Al hacer clic en **Acciones masivas** se abrirá una pantalla con varias pestañas.

Nota: Las funciones de cada pestaña son independientes entre sí.

**Guardar nuevas credenciales**

Esta función es aplicable a las cuentas de AWS si se cumplen los requisitos previos mencionados anteriormente.

1. Esta pantalla no se mostrará si no hay cuentas configuradas utilizando la credencialización automática de cuentas vinculadas.

La pantalla muestra todas las cuentas con el estado Credenciales necesarias (X roja). Para guardar las credenciales

1. Seleccione las cuentas que necesitan credenciales.
2. Haga clic en **Revisar selección**
   1. Añada la región SCP necesaria para AWS.
3. Haga clic en **Guardar.**

Esto activaría el proceso de guardado masivo y el botón de acciones masivas se desactivaría hasta que el proceso finalizara.

1. Una vez guardadas, las cuentas pasarán al estado No verificado.
2. Por favor, descargue la plantilla Cloud Formation de una de las cuentas que se guardó y aplíquela a las cuentas AWS en la consola AWS como stackset.
3. Una vez completado, active verificar cuenta(s) para las cuentas seleccionadas en el paso anterior.

**Actualizar credenciales**

La pantalla muestra todas las cuentas excepto las que tienen el estado Credenciales necesarias (X). Para actualizar las credenciales

1. Seleccione las cuentas que deben actualizarse.
2. Haga clic en "Revisar selección"
   1. Añada la región SCP necesaria para AWS.
3. Haga clic en **Guardar.**

Esto activaría el proceso de actualización masiva y el botón de acciones masivas se desactivaría hasta que el proceso finalizara.

Una vez completado, active Verificar credenciales.

**Verificar credenciales**

Esta pantalla muestra todas las cuentas excepto las que tienen el estado Credenciales necesarias (X).

Antes de activar la verificación masiva, asegúrese de que la plantilla se ha descargado y aplicado en la consola AWS para las cuentas vinculadas a AWS. Para verificar las credenciales

1. Seleccione las cuentas que deben verificarse.
2. Haga clic en **Revisar selección**
3. Haga clic en **Verificar.**

Esto activaría el proceso de verificación masiva y el botón de acciones masivas se desactivaría hasta que el proceso finalizara.

Una vez completado, las cuentas pasarán a un estado de credencial verificada o a un estado de credencial no válida (debido a errores).

Nota: En caso de que el número de cuentas sea elevado, puede tardar unos minutos.

**Tema principal:** [Conexión con AWS - Guía de integración de clientes](../admin/aws-credentialing-premium-home.html)
