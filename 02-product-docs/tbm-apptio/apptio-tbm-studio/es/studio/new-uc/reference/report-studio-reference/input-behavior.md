---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Comportamiento de entrada"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe - Componentes de entrada"
source_path: "studio/new-uc/reference/report-studio-reference/input-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Comportamiento de entrada

**Bloqueo a nivel de celda (control de concurrencia)**

TBM Studio evita los conflictos de edición mediante bloqueos a nivel de celda:

- Cuando el usuario A empieza a editar una celda, esa celda se bloquea
- El usuario B ve la celda como bloqueada y no puede editarla
- El bloqueo se mantiene hasta que el usuario A guarde o cancele
- Evita las actualizaciones parciales y las colisiones de datos

**Guardar flujo de trabajo**

TBM Studio utiliza un sistema de guardado manual, no de guardado automático:

- Edición: El usuario modifica los valores de las celdas
- Guardar: el usuario hace clic en «Guardar» para aplicar los cambios en la tabla editable
- Publicar: el usuario hace clic en «Publicar» para enviar los datos a la tabla de transformación

Importante: Al guardar se aplican los cambios a la tabla editable. La publicación aplica esos cambios a la tabla de transformación posterior y activa el recálculo.

**Tema principal:** [Componentes del informe - Componentes de entrada](../../../../studio/new-uc/reference/report-studio-reference/report-component-input-components.html)
