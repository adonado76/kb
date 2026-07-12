---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Creación de métricas personalizadas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Métricas de modelo"
source_path: "studio/new-uc/reference/model-studio-reference/custom-metric-creation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Creación de métricas personalizadas

**Creación de una métrica modelada**

1. En la pestaña Inicio, haz clic en Nuevo > Métrico
2. Escribe un nombre y haz clic en Aceptar
3. Establece el tipo de modelo en «Modelo»
4. Configurar el tipo de métrica (coste, precio o numérico)
5. Configura el formato de la tabla y el formato del gráfico según sea necesario
6. Pulse Guardar

**Creación de una métrica calculada**

1. En la pestaña Inicio, haz clic en Nuevo > Métrico
2. Escribe un nombre y haz clic en Aceptar
3. Establece el tipo de modelo en «Calculado»
4. Introduce la fórmula de cálculo del valor
5. Establecer el comportamiento temporal (suma, promedio o recalcular)
6. Configurar el formato de visualización
7. Pulse Guardar

**Nota:** Una vez creada una métrica calculada, los campos «Tipo de modelo» y «Cálculo del valor» pasan a ser de solo lectura.

**Ejemplo: Indicador de desviación presupuestaria**

Crea una métrica calculada que muestre la diferencia entre el presupuesto y el coste:

- Nombre: Desviación\_presupuestaria
- Tipo de modelo: Calculado
- Cálculo del valor: =Presupuesto - Coste
- Comportamiento temporal: Recalcular
- Formato de tabla: =Currency($\_)

Consulte la sección 3.2.8: para obtener información sobre cómo crear métricas personalizadas y conocer los procedimientos detallados

Consulte la sección «Fórmulas y funciones» de 5.4: para conocer la sintaxis de los cálculos

**Tema principal:** [Métricas del modelo](../../../../studio/new-uc/reference/model-studio-reference/model-metrics.html)
