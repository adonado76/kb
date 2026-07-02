---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Vista del proyecto de gasto en tecnología"
breadcrumb:
  - "Billing"
  - "Patrones de diseño y casos de uso"
source_path: "boit/billing/design-uc/uc-project.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Vista del proyecto de gasto en tecnología

Nota: **Se aplica únicamente a la norma de facturación.**

**Problema**

Los equipos de cartera o PMO desean comprender los gastos tecnológicos por proyecto para un período o año determinado.

**Entradas**

- Datos maestros del proyecto (ID, nombre, propietario, tipo)
- Asignaciones de costes/uso a proyectos (mano de obra, infraestructura, nube, etc.)
- Configuración de facturación que:
  - Facturas proyectos directamente, o
  - Etiquetas cargos con atributos del proyecto

**Pasos**

1. Verificar **las asignaciones del proyecto** :
   - Confirmar que la mano de obra, la infraestructura y el uso de la nube estén vinculados a los proyectos pertinentes.
2. Ejecutar modelos estándar de facturación para el período.
3. Abre el **informe de facturación del proyecto** :
   - Filtrar por el período actual.
   - Ver cargos por proyecto y servicio.
4. Aplica filtros adicionales según sea necesario:
   - Patrocinador, cartera, tipo de proyecto.
5. Exportar o cortar más:
   - Proyectos principales por gasto en tecnología.
   - Cargos por proyecto por unidad de negocio o consumidor.

**Informes clave**

- Resumen de facturación del proyecto (Proyecto × Servicio × Periodo)
- Informe detallado del proyecto (con los colaboradores subyacentes)
- Panel de control de la cartera que destaca los proyectos más importantes por gasto
