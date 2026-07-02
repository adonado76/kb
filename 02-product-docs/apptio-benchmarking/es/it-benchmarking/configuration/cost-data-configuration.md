---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Configuración de datos de costes"
breadcrumb:
  - "Benchmarking"
  - "Guía de configuración"
source_path: "it-benchmarking/configuration/cost-data-configuration.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Configuración de datos de costes

## Conexión con el cálculo de costes

Los datos sobre costes indican a Interactive Benchmarking qué debe comparar. Puede alimentarlo directamente desde Costing o mediante entrada manual.   
En la configuración de Benchmarking:

1. Integre con la plataforma de cálculo de costes seleccionando «Transparencia de costes».
2. Validar la conexión.
3. Seleccione el proyecto de cálculo de costes principal que contiene su gasto real en TI.
4. Seleccione el período fiscal del año fiscal que debe utilizarse para sus puntos de referencia de referencia.
5. Recuperar los datos.

![Conectarse a Costing](../../resources/images/it%20benchmarking_images/connect-to-costing.png)

Cheques:

- Confirme que el coste total de TI coincide con el presupuesto financiero para ese año.
- Confirma que todas las torres de recursos principales tengan cantidades distintas de cero.
- Si falta algún valor o cree que merece una sustitución, introduzca los valores manualmente y guárdelos antes de continuar.

**Introducción manual de**  
 costes Utilice la introducción manual solo cuando:

- No ha implementado un proyecto de cálculo de costes o este no está disponible.
- Estás realizando una prueba piloto con datos simplificados.
- Está cargando datos desde un modelo externo similar a TBM.

Este método es adecuado para empezar, pero si desea un uso continuo y controlado, le recomendamos que lo integre con IBM Apptio Costing.

**Verifique la**   
configuración de la moneda y el año fiscal. Asegúrese de que:

- La moneda utilizada para los costes y los ingresos de TI es la misma.
- El período que se utiliza para la evaluación comparativa es un año fiscal completo, no un semestre ni un período mixto.
- Si Costing utiliza varias divisas, la conversión se realiza antes de que los datos lleguen a Benchmarking.

En la configuración de Interactive Benchmarking, establezca la moneda predeterminada.

![Configuración interactiva de benchmarking – Moneda predeterminada](../../resources/images/it%20benchmarking_images/currency-fiscal-year.png)

## Fondos comunes de costes de TBM

La compatibilidad con Cost Pool está disponible hasta la versión 4 de TBM y anteriores. Los detalles de los grupos de costes aparecen en la tabla siguiente:

Tabla 1.

| Fondo común de costes | Descripción |
| --- | --- |
| Mano de obra externa | Honorarios de contratistas externos, viajes y gastos. |
| Instalaciones y energía | Espacio del centro de datos, energía, seguridad y otros gastos operativos. |
| Hardware del sistema | Gastos de hardware. |
| Trabajo interno | Salarios, prestaciones, gastos y ocupación de los empleados. |
| Otros | Gastos diversos o no estándar. |
| Servicios externos | Proveedores externos de servicios gestionados. |
| Software | Gastos de software por compras de software no capitalizadas. |
| Telecomunicaciones | Gastos de conectividad de redes de voz y datos, incluidos los gastos de circuitos y uso. |

Nota: El grupo de costes «Instalaciones y energía» es específico de las instalaciones de los centros de datos. Excluye los gastos de oficina y otras instalaciones. Por lo general, las instalaciones de oficina deben asignarse al grupo de costes «Mano de obra interna».
