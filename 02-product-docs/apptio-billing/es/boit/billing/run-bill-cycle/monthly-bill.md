---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Proceso de facturación mensual"
breadcrumb:
  - "Billing"
  - "Ejecutar el ciclo de facturación"
source_path: "boit/billing/run-bill-cycle/monthly-bill.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Proceso de facturación mensual

Cada período de facturación suele seguir una serie de pasos repetibles.

Un patrón común se ve así:

1. **Cerrar el período**
   - Alinearse con Finanzas en cuanto al cierre del período de facturación.
   - Congele o capture los datos de origen cuando sea necesario para que los volúmenes no cambien en Facturación.
2. **Actualizar datos de costes y consumo**
   - Asegúrese de que Costing haya recibido los datos de costes más recientes del periodo.
   - Actualizar los datos de consumo en Facturación:
     - Uso, tickets, dispositivos, uso de la nube, métricas de proyectos y similares.
3. **Realizar comprobaciones de control de calidad.**
   - Ejecutar informes de control de calidad estándar:
     - Asignaciones faltantes (consumidor, oferta, objetos de dominio).
     - Aumentos o descensos repentinos del volumen.
     - Cargos cero o negativos que no deberían existir.
4. **Revisar los proyectos de ley**
   - Los analistas y administradores revisan los cargos por oferta y consumidor.
   - Los propietarios de servicios o productos validan los cargos correspondientes a sus áreas.
5. **Aplicar correcciones si es necesario.**
   - Solucione los problemas de datos en los sistemas de origen, las tablas de asignación o las tablas de tarifas.
   - Vuelva a ejecutar las comprobaciones de control de calidad.
6. **Aprobar proyectos de ley**
   - Una vez completado el control de calidad, obtenga la aprobación de los responsables designados:
     - A menudo, los propietarios de servicios o productos y el departamento financiero.
7. **Resultados de la publicación**
   - Publicar/enviar por correo electrónico facturas o informes de reembolso a los consumidores.

Exportar y entregar los diarios a Finanzas.
