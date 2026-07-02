---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Requisitos relativos a los datos de los conductores"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Conductores"
source_path: "studio/new-uc/reference/model-studio-reference/driver-data-requirements.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Requisitos relativos a los datos de los conductores

**Requisitos de la columna**

|  |  |  |
| --- | --- | --- |
| **Requisito** | **Descripción** | **Consecuencias en caso de incumplimiento** |
| Tipo numérico | La columna «Driver» debe contener valores numéricos | El controlador no se ha tenido en cuenta; no fluye ningún valor |
| Valores distintos de cero | La columna debe contener valores para las filas | Las filas con valores nulos aportan 0 $ |
| Datos del periodo | Debe haber datos para el período activo | No hay ningún valor de controlador para ese periodo |
| Transformar el éxito | La transformación de la tabla debe completarse | Cálculos del modelo bloqueados |

Advertencia: Si una columna numérica contiene al menos un valor no numérico, los controladores que hagan referencia a dicha columna pueden fallar sin mostrar ningún mensaje de error. Comprueba siempre los tipos de datos en Data Studio.

**Tema principal:** [Conductores](../../../../studio/new-uc/reference/model-studio-reference/drivers.html)
