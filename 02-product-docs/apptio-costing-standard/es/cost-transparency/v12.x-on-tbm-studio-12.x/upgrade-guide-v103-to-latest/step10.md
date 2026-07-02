---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Paso 10: Fusionar todos los demás componentes"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step10.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Paso 10: Fusionar todos los demás componentes

Repita el paso 9 para seguir fusionando hasta 5 ramas de actualización individuales (de una sola vez) y las posteriores comprobaciones del tronco (en desarrollo) en el mismo orden recomendado en el [paso 6: Actualice todos los demás componentes de la rama de actualización](step6.html) :

- Fusión 1 (hasta 5 elementos de fusión)
  - **Configuración del proyecto** : Cambie a la nueva versión de plantilla, como v104.

    Nota: Debe ser el primer elemento de la primera fusión.

    Verifique en Trunk que la Configuración del Proyecto cambió en Desarrollo y Puesta en Escena.
  - **Revisión TBM** : Desactivar el componente.

    Verifique en Trunk que el componente TBM Review ya no esté instalado para Desarrollo y Puesta en Escena.
  - **ATUM v2.0** : Desactiva el componente.

    Verifique en Trunk que el componente ATUM v.2.0 ya no está instalado para Development y Staging.
  - **CTF- Fuente de costes** : Revertir las métricas calculadas y actualizar el componente.

    Compruebe en el tronco que no aparece ninguna flecha de actualización en el componente CTF-Fuente de costes en Desarrollo y puesta a disposición.
  - **Parámetros** : Cambio a la página de inicio del Cálculo del coste del servicio.

    Vaya a la aplicación Costing Standard . Debería ver la nueva página de inicio de la versión que ha seleccionado. (Más información)

    Nota: Este paso sólo es necesario si ha instalado el componente TBM Review disponible en v103.
- Fusión 2 (hasta 5 elementos de fusión)
  - **CT- Calidad** : Mejora el componente.

    Verifique en Trunk que no hay ninguna flecha de actualización en el componente CT-Calidad en Desarrollo y Puesta a punto.
  - **CT- Mano de obra** : Actualizar el componente.

    Verifique en Trunk que no hay ninguna flecha de actualización en el componente CTF- Labor en Desarrollo y Puesta a punto.
  - **CTF- Torres IT** : Revierte las métricas calculadas y actualiza el componente.

    Verifique en Trunk que no hay flecha hacia arriba en el componente CTF- IT Towers en Desarrollo y Puesta en Escena.
  - **CTF- Seguimiento del tiempo** : Actualice el componente.

    Verifique en Trunk que no hay ninguna flecha de actualización en el componente CTF- Time Tracking en Development y Staging.
  - **Proyectos CTF** : Actualizar el componente.

    Verifique en Trunk que no hay ninguna flecha de actualización en el componente CTF- Projects en Development and Staging.
- Fusión 3 (hasta 5 elementos de fusión)
  - **CTF- Servicio en la nube** : Revertir las métricas calculadas y actualizar el componente.

    Verifique en Trunk que no hay ninguna flecha de actualización en el componente CTF- Cloud Services en Development y Staging.
  - **CTF- Amazon Web Services** : Actualizar el componente.

    Verifique en Trunk que hay flecha noupgrade en el componente CTF- AWS en Desarrollo y Staging.
  - **CTF- Azure** : Actualizar el componente.

    Verifique en Trunk que no hay ninguna flecha de actualización en el componente CTF- Azure en Desarrollo y Puesta en Escena.
  - **CT Apps- Aplicaciones** : Revertir las métricas calculadas y actualizar el componente.

    Compruebe en Trunk que no hay ninguna flecha de actualización en el componente Aplicaciones en Desarrollo y puesta en escena.
  - **CT- Unidades de negocio** : Revertir las métricas calculadas y actualizar el componente.

    Verifique en Trunk que no hay ninguna flecha de actualización en el componente CT- Business Units en Development and Staging.

## Información relacionada

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
