---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cambios en la gestión del estado del espacio de trabajo de TBM Studio"
breadcrumb: []
source_path: "studio/troubleshooting/sensitive-info-disclosure.html"
images:
  - "resources/images/studio_images/ts-1.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cambios en la gestión del estado del espacio de trabajo de TBM Studio

Se aplica a: Servidor 12.11.8/ BFF-2.8.0

Esta funcionalidad permite a los usuarios restaurar eficazmente su espacio de trabajo después de que el usuario vuelva de nuevo a TBM Studio .

## En segundo plano

TBM Studio actualmente almacena la información del estado del espacio de trabajo localmente en el navegador. Esta información incluye:

- Últimos documentos consultados
- Abrir carpetas
- Abrir documentos
- Última aplicación seleccionada (CT o TBM Studio)
- Detalles del proyecto (si se utilizó TBM Studio por última vez)

## Problemas de seguridad y cambios aplicados

Una reciente auditoría de seguridad identificó como vulnerabilidad el almacenamiento de datos sensibles en el navegador. Para solucionar este problema, se han introducido los siguientes cambios:

- Los usuarios tendrán la opción de desactivar el almacenamiento en el navegador de la información sobre el estado del espacio de trabajo.
- Desactivar el almacenamiento en el navegador impedirá la restauración automática del espacio de trabajo anterior al iniciar sesión.

## Impacto en los usuarios

## TBM Studio Usuarios

Por defecto, los usuarios accederán a la página de cálculo en lugar de a su último proyecto al abrir TBM Studio.

El estado del espacio de trabajo guardado anteriormente, como el proyecto activo, las secciones del explorador, las pestañas y el estado del documento de salida, ya no se restaurarán automáticamente.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ts-1.png)

## CT - Billing Standard Usuarios

Sin impacto en los usuarios finales.

## Preguntas más frecuentes (FAQ)

¿Es obligatorio desactivar el almacenamiento en el navegador?

No, es una función opcional disponible para todos los clientes en todas las regiones.

Clientes gubernamentales: El almacenamiento del navegador está desactivado por defecto para los clientes gubernamentales. No pueden restaurar el estado anterior a menos que se habilite el almacenamiento mediante la configuración `/data`.

¿Pueden los usuarios tener tanto seguridad como restauración del espacio de trabajo?

Actualmente, esto no es posible. Sin embargo, los usuarios pueden establecer un proyecto por defecto en TBM Studio para asegurarse de que aterrizan en ese proyecto en lugar de en la página de cálculo. Este método no restablecerá otros ajustes del espacio de trabajo.

¿Cómo desactivar el almacenamiento en el navegador?

Esta información no está destinada a notas de difusión pública. Los clientes gubernamentales pueden ponerse en contacto con su CSM para habilitar el almacenamiento a través de `/data`.

## Notas adicionales

Este cambio afecta a la versión 12.11.8 del servidor y a la versión 2.8.0 del BFF.

Aunque este cambio puede causar inconvenientes, estamos explorando soluciones alternativas para restaurar la información del estado del espacio de trabajo de forma segura en el futuro. Se recomienda a todos los usuarios que consideren cuidadosamente la relación entre seguridad y comodidad a la hora de decidir si desactivan el almacenamiento en el navegador.
