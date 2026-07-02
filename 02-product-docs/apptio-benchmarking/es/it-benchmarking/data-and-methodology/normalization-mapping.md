---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Normalización y mapeo"
breadcrumb:
  - "Benchmarking"
  - "Informes comparativos"
  - "Datos y metodología Referencia"
source_path: "it-benchmarking/data-and-methodology/normalization-mapping.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Normalización y mapeo

Aquí es donde tu modelo se gana la confianza o la pierde.

**Alineación de la taxonomía**   
TBM Los puntos de referencia se alinean con el estándar TBM:

- Grupos de costes
- Torres de recursos y subtorres de recursos

El modelo de su proyecto de cálculo de costes debe:

- Asigne cuentas GL, datos de proveedores y otras fuentes a los mismos grupos de costes
- Asignar los costes a torres de recursos y subtorres de recursos que se correspondan con las definiciones de referencia

Si tienes:

- Torres de recursos personalizadas
- Grupos de costes personalizados
- Categorías mixtas que combinan múltiples grupos estándar

entonces necesitas reglas de mapeo explícitas. La desalineación es la principal causa de que «estos puntos de referencia parezcan incorrectos»

**Ámbito e inclusiones**  
 Debe decidir y documentar qué se incluye en el ámbito.   
Inclusiones típicas para los costes de TI:

- Mano de obra y contratistas para funciones de TI
- Hardware, software y servicios en la nube
- Servicios de proveedores que dan soporte a los servicios de TI
- Depreciación o amortización de activos tecnológicos

Exclusiones típicas:

- Externalización de procesos empresariales en los que las tecnologías de la información no son el factor principal
- Gastos generales corporativos no relacionados con TI que no se asignan a TI
- Gastos extraordinarios únicos, si el proveedor los excluye

Sus elecciones de alcance deben reflejar, en la medida de lo posible, la forma en que se orienta a los colaboradores de los índices de referencia para que informen.

**Normalización**   
de divisas Los índices de referencia externos se expresan en una divisa de referencia.   
Su entorno:

- Debe utilizar una única moneda de trabajo para los datos que introduce en Benchmarking
- Debe asegurarse de que tanto los costes como los ingresos de TI utilicen la misma moneda durante el periodo

Si opera con varias divisas:

- La conversión debe realizarse en la fase inicial del cálculo de costes o antes de la introducción manual
- Documento que indica las tasas y los plazos que utiliza para la conversión

Mezclar monedas sin decir nada es una forma segura de crear tonterías.

**A** lineación  
 temporal. No compare: su previsión para el año actual con un punto de referencia que refleje los datos reales del año pasado. A menos que lo estés haciendo deliberadamente y lo estés indicando claramente.

El patrón claro es: los datos reales del año fiscal N frente al año fiscal N de referencia. Cuando los ejercicios fiscales difieren entre organizaciones, el proveedor de referencias aplica sus propias reglas de alineación; solo hay que ser coherente.

**Trat** amiento como capital frente  
 a gasto: los índices de referencia suelen tener en cuenta los costes periódicos de TI, que incluyen:

- Gastos de explotación
- Depreciación o amortización de inversiones tecnológicas capitalizadas
- Costes de arrendamiento, según el enfoque contable

Si su modelo de costes de TI excluye la depreciación, mientras que los puntos de referencia la incluyen, sus ratios no coincidirán.   
Debe:

- Alinear el tratamiento de la amortización ( CapEx ) y la depreciación con las directrices de referencia
- O, al menos, comprender la diferencia y evitar denominar a esas métricas «gasto real en TI» en un sentido contable interno
