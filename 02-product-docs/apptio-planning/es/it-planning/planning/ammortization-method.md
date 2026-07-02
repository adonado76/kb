---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Métodos de amortización"
breadcrumb:
  - "Planning"
  - "Planificación de contratos"
source_path: "it-planning/planning/ammortization-method.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Métodos de amortización

La amortización de contratos es el proceso de distribución del coste de un contrato a lo largo de varios periodos.

## Visión general

Apptio La planificación admite cinco métodos de amortización, cada uno con casos de uso específicos para gestionar los costes de los contratos:

1. [Línea recta Períodos pares](#amormeth__sleven)
2. [Línea recta por días naturales](#amormeth__slcal)
3. [Prorrateo en línea recta primero y último](#amormeth__slfirst)
4. [Línea recta por duración](#amormeth__sldur)
5. [Amortización manual](#amormeth__slamor)

Apptio La planificación también es compatible con **las prórrogas de contratos**, lo que permite que los costes continúen más allá de la fecha de finalización del contrato original. Las ampliaciones pueden aplicar nuevos tipos y, opcionalmente, componerse con el tiempo.

A continuación se describen los casos de uso de cada método de amortización:

## 1. Línea recta Períodos pares

Distribuye el coste total del contrato uniformemente entre todos los periodos, independientemente del número de días de cada periodo. Un periodo se considera completo aunque el contrato sólo cubra un único día dentro del mismo.

**Ejemplo:**

Fecha de inicio del contrato: 15 de enero de 2025

Fecha de finalización del contrato: 15 de junio de 2025

Duración: 6 meses

Importe: $6,000

**Sin extensión:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Ene** | **Feb** | **mar** | **Abr** | **Mayo** | **Jun** | **jul** | **Ago** | **Sep** | **Oct** | **nov** | **Dic** |
| 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares |  |  |  |  |  |  |

Enero-Junio = 6.000 $ / 6 meses = 1.000 $

**Con prórroga hasta finales de año:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Ene** | **Feb** | **mar** | **Abr** | **Mayo** | **Jun** | **jul** | **Ago** | **Sep** | **Oct** | **nov** | **Dic** |
| 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares | 1000 dólares |

## 2. Línea recta por días naturales

Distribuye el coste proporcionalmente al número de días de cada mes durante el contrato. Los periodos con más días reciben una parte mayor, contándose tanto la fecha de inicio como la de finalización.

**Ejemplo:**

Fecha de inicio del contrato: 15 de enero de 2025

Fecha de finalización del contrato: 15 de junio de 2025

Duración: 152 días

Importe: $6,000

**Sin extensión:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Ene** | **Feb** | **mar** | **Abr** | **Mayo** | **Jun** | **jul** | **Ago** | **Sep** | **Oct** | **nov** | **Dic** |
| 671 dólares | 1105 dólares | 1224 dólares | 1184 dólares | 1224 dólares | 592 dólares |  |  |  |  |  |  |

Ene = 6000 $ \* 17 días / 152 días = 671 $

Febrero = 6.000 $ \* 28 días / 152 días = 1.105 $

Mar = 6.000 $ \* 31 días / 152 días = 1.224 $

Abr = 6.000 $ \* 30 días / 152 días = 1.184 $

Mayo = 6.000 $ \* 31 días / 152 días = 1.224 $

Jun = 6000 $ \* 15 días / 152 días = 592 $

**Con prórroga hasta finales de año:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Ene** | **Feb** | **mar** | **Abr** | **Mayo** | **Jun** | **jul** | **Ago** | **Sep** | **Oct** | **nov** | **Dic** |
| 671 dólares | 1105 dólares | 1224 dólares | 1184 dólares | 1224 dólares | 1184 dólares | 1224 dólares | 1224 dólares | 1184 dólares | 1224 dólares | 1184 dólares | 1224 dólares |

Ene = 6000 $ \* 17 días / 152 días = 671 $

Febrero = 6.000 $ \* 28 días / 152 días = 1.105 $

Mar = 6.000 $ \* 31 días / 152 días = 1.224 $

Abr = 6.000 $ \* 30 días / 152 días = 1.184 $

Mayo = 6.000 $ \* 31 días / 152 días = 1.224 $

Jun = (6.000 $ \* 15 días / 152 días) + (6.000 $ \* 15 días / 152 días) = 1.184 $

Jul = 6.000 $ \* 31 días / 152 días = 1.224 $

Agosto = 6.000 $ \* 31 días / 152 días = 1.224 $

Sep = 6.000 $ \* 30 días / 152 días = 1.184 $

Octubre = 6.000 $ \* 31 días / 152 días = 1.224 $

Nov = 6.000 $ \* 30 días / 152 días = 1.184 $

Diciembre = 6.000 $ \* 31 días / 152 días = 1.224 $

## 3. Prorrateo en línea recta primero y último

Prorratea el primer y el último periodo de un contrato por el número de días y, a continuación, distribuye uniformemente el coste restante entre los periodos intermedios.

**Ejemplo:**

Fecha de inicio del contrato: 15 de enero de 2025

Fecha de finalización del contrato: 15 de junio de 2025

Duración: 152 días

Importe: $6,000

**Sin extensión:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Ene** | **Feb** | **mar** | **Abr** | **Mayo** | **Jun** | **jul** | **Ago** | **Sep** | **Oct** | **nov** | **Dic** |
| 671 dólares | 1184 dólares | 1184 dólares | 1184 dólares | 1184 dólares | 592 dólares |  |  |  |  |  |  |

Ene = 6000 $ \* 17 días / 152 días = 671 $

Febrero = 6.000 $ - 671 $ - 592 $ / 4 meses = 1.184 $

Mar = $6000 - $671 - $592 / 4 meses = $1,184

Abr = 6.000 $ - 671 $ - 592 $ / 4 meses = 1.184 $

Mayo = 6.000 $ - 671 $ - 592 $ / 4 meses = 1.184 $

Jun = 6000 $ \* 15 días / 152 días = 592 $

**Con prórroga hasta finales de año:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Ene** | **Feb** | **mar** | **Abr** | **Mayo** | **Jun** | **jul** | **Ago** | **Sep** | **Oct** | **nov** | **Dic** |
| 671 dólares | 1184 dólares | 1184 dólares | 1184 dólares | 1184 dólares | 1184 dólares | 1214 dólares | 1214 dólares | 1214 dólares | 1214 dólares | 1184 dólares | 1194 dólares |

Contrato original: 15 de enero - 15 de junio de 2025

Primera prórroga: Jun 16 - Nov 15, 2025

Segunda prórroga: 16 de noviembre de 2025 - 16 de abril de 2026

Ene = 6000 $ \* 17 días / 152 días = 671 $

Febrero = 6.000 $ - 671 $ - 592 $ / 4 meses = 1.184 $

Mar = $6000 - $671 - $592 / 4 meses = $1,184

Abr = 6.000 $ - 671 $ - 592 $ / 4 meses = 1.184 $

Mayo = 6.000 $ - 671 $ - 592 $ / 4 meses = 1.184 $

Jun = (6.000 $ \* 15 días / 152 días) + (6.000 $ \* 15 días / 152 días) = 1.184 $

Jul = 6.000 $ - 671 $ - 592 $ / 4 meses = 1.184 $

Agosto = 6.000 $ - 671 $ - 592 $ / 4 meses = 1.184 $

Sep = $6000 - $671 - $592 / 4 meses = $1,184

Octubre = 6.000 $ - 671 $ - 592 $ / 4 meses = 1.184 $

Nov = (6.000 $ \* 15 días / 152 días) + (6.000 $ \* 15 días / 152 días) = 1.184

Dic = 6.000 $ - 592 $ - 631 $ / 4 meses = 1.194 $

## 4. Línea recta por duración

Comprueba si las fechas de inicio y fin del contrato cubren totalmente los periodos en los que se encuentran. Si ambos son periodos completos, el coste se divide uniformemente entre todos los periodos. Si la fecha de inicio o fin no cubre completamente el último periodo, al último periodo se le asigna 0, y el coste se distribuye uniformemente entre los periodos restantes.

**Ejemplo:**

Fecha de inicio del contrato: 15 de enero de 2025

Fecha de finalización del contrato: 15 de junio de 2025

Duración: 152 días = 5 meses

Importe: $6,000

**Sin extensión:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Ene** | **Feb** | **mar** | **Abr** | **Mayo** | **Jun** | **jul** | **Ago** | **Sep** | **Oct** | **nov** | **Dic** |
| 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares |  |  |  |  |  |  |  |

Enero-mayo = 6.000 $ / 5 meses = 1.200 $

**Con prórroga hasta finales de año:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Ene** | **Feb** | **mar** | **Abr** | **Mayo** | **Jun** | **jul** | **Ago** | **Sep** | **Oct** | **nov** | **Dic** |
| 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares | 1.200 dólares |

Ene-Dic = 6.000 $ / 5 meses = 1.200 $

## 5. Amortización manual

Permite a los usuarios introducir directamente los importes de amortización para cada periodo, en lugar de depender de métodos calculados por el sistema. Esto proporciona una flexibilidad total para definir exactamente cómo deben distribuirse los costes a lo largo de los periodos.

Si la opción **Actualizar automáticamente el total del contrato** está activada en el Perfil de la empresa, la columna Importe sumará automáticamente el total en función de los importes de amortización introducidos para cada periodo.
