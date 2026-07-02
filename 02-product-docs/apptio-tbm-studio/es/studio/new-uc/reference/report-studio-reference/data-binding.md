---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Enlace de datos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe - Componentes de entrada"
source_path: "studio/new-uc/reference/report-studio-reference/data-binding.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Enlace de datos

Los componentes de entrada se vinculan a columnas de tablas editables, que almacenan los datos introducidos por el usuario en la base de datos del proyecto.

**Vinculación a columnas editables de una tabla**

Todos los componentes de entrada se configuran en el paso «Configurar columnas» de la tabla editable:

- Selecciona la tabla editable en el Explorador de proyectos
- Ve a Pasos > Configurar columnas
- Selecciona o añade una columna para configurarla
- Configura las propiedades de la columna (tipo, validación, valores posibles, etc.)

**Comportamiento de sincronización bidireccional**

Los cambios realizados en los componentes de entrada de los informes se aplican en todo el sistema de la siguiente manera:

- El usuario edita una celda del informe
- El valor se almacena en el lado del cliente (estado pendiente)
- El usuario hace clic en «Guardar» para aplicar los cambios en la tabla editable
- El usuario hace clic en «Publicar» para enviar los datos a la tabla de transformación asociada
- Los cálculos de compilación o de entorno de pruebas incorporan los valores actualizados

Importante: La vinculación no se realiza en tiempo real. Los usuarios deben guardar y publicar los cambios de forma explícita para que surtan efecto en el modelo de costes.

**Tema principal:** [Componentes del informe - Componentes de entrada](../../../../studio/new-uc/reference/report-studio-reference/report-component-input-components.html)
