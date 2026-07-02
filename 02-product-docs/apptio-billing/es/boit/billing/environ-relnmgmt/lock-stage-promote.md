---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Bloqueo de la fase de preparación y promoción a producción"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Entornos y gestión de lanzamientos"
source_path: "boit/billing/environ-relnmgmt/lock-stage-promote.html"
images:
  - "resources/images/boit_images/unlockstg.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Bloqueo de la fase de preparación y promoción a producción

Antes de promover los cambios a Producción, el entorno de ensayo debe **bloquearse** para evitar que los nuevos registros generen compilaciones adicionales.

Secuencia típica:

1. **Bloqueo de preparación**
   - Evita que se creen nuevas compilaciones en Staging.
   - Garantiza que el control de calidad se realice en una compilación de prueba estable.
2. **Ejecutar control de calidad en la fase de preparación**
   - Validar:
     - Los modelos de facturación funcionan correctamente.
     - Los informes de facturación se abren y muestran los datos según lo previsto.
     - Los casos de uso clave de facturación (facturas, vistas detalladas, diarios) funcionan correctamente.
3. **Promocionar a producción**
   - Una vez completado el control de calidad, la compilación aprobada pasa a producción.
   - La promoción puede ser:
     - Realizado inmediatamente.
     - Programado para ocurrir después de que se complete una compilación o durante una ventana de mantenimiento definida.
4. **Desbloquear Staging**
   - Una vez que la producción se esté ejecutando en la compilación aprobada, se podrá desbloquear la fase de ensayo.
   - El trabajo de desarrollo puede reanudarse y las nuevas construcciones pueden pasar a la fase de preparación.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/unlockstg.png)

Fig. n.º: Entorno de ensayo bloqueado con el botón Desbloquear en la cinta de opciones Compilar mostrando «Desbloquear».

Puntos clave:

- Prueba siempre el comportamiento de facturación en el entorno de pruebas antes de pasar al entorno de producción.
- El bloqueo de la fase de ensayo es esencial para evitar probar accidentalmente una compilación y promover otra diferente.
