---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Casos de uso habituales de las tuneladoras"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Fundamentos de la TBM"
source_path: "studio/new-uc/concepts-architecture/tbm-use-cases.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Casos de uso habituales de las tuneladoras

La metodología TBM admite varios casos de uso distintos, cada uno de los cuales responde a una necesidad empresarial diferente. Comprender estos casos de uso te ayudará a diseñar la implementación de TBM Studio de manera que aporte el máximo valor a tu organización.

## Showback

**¿Qué es**  
? El «showback» es la práctica de comunicar los costes de TI a las unidades de negocio con fines de transparencia, sin llegar a facturárselos. Las unidades de negocio pueden ver cuánto les cuesta el uso de los servicios de TI, pero estos cargos son meramente informativos: no afectan a los presupuestos de los departamentos ni dan lugar a transferencias financieras.

**Cuándo utilizarlo**  

- Su organización es nueva en TBM y desea ir adquiriendo conciencia de los costes de forma gradual
- Debes validar tu modelo de costes antes de vincularlo a consecuencias financieras reales
- Las unidades de negocio aún no están preparadas para asumir la responsabilidad de los costes de TI
- Quieres impulsar un cambio de comportamiento a través de la transparencia, en lugar de mediante la presión económica

**Ventajas y limitaciones**  

|  |  |
| --- | --- |
| **Ventajas** | **Limitaciones** |
| Una forma de introducir la transparencia de costes con un riesgo mínimo | No hay incentivos económicos para optimizar el consumo |
| Genera confianza en los datos sobre costes antes de su aplicación | Las unidades de negocio pueden ignorar los informes informativos |
| Da tiempo para perfeccionar los modelos de asignación | Requiere un esfuerzo constante sin un retorno de la inversión inmediato |

**Ejemplo** de   
situación: El equipo de TI de Acme Corp elabora informes mensuales de rendición de cuentas para cada unidad de negocio en los que se detallan los costes de TI que se les han asignado. El departamento de Ventas estima que el gasto en servicios de TI asciende a $2.4M/month. Aunque no hay intercambio de dinero, el vicepresidente de ventas empieza a preguntar por qué su sistema CRM cuesta más que la media del sector, lo que da pie a una conversación productiva sobre optimización.

Nota: **Por qué es importante en TBM Studio**   
TBM Studio permite realizar el showback a través de los paneles de control de Report Studio, que muestran los costes asignados por unidad de negocio. La seguridad a nivel de fila garantiza que cada responsable de unidad de negocio solo vea sus propios datos de costes. No es necesaria ninguna integración de facturación adicional.

## Retorno de cargos

**Qué es:**   
Chargeback lleva la transparencia un paso más allá al facturar directamente a las unidades de negocio por su consumo de TI. Los costes de TI se transfieren del presupuesto de TI a los departamentos usuarios mediante operaciones financieras formales, normalmente en forma de asientos contables internos o cargos entre empresas.

**Cuándo utilizarlo**

- Su organización cuenta con modelos de costes consolidados y validados
- Las unidades de negocio han asumido la responsabilidad del consumo de TI
- Es necesario crear incentivos económicos para optimizar el consumo
- Tu equipo de finanzas se encarga de los procesos internos de transferencia de costes

**Consideraciones sobre la implementación**

- **La precisión de los datos es fundamental:** los errores en las devoluciones afectan directamente a los presupuestos de los departamentos, por lo que su modelo de asignación debe estar debidamente validado
- **La comunicación es fundamental:** las unidades de negocio deben comprender en qué consisten los gastos que se les imputan y cómo pueden influir en los costes
- **Resolución de litigios:** Establecer un procedimiento claro para que las unidades de negocio puedan impugnar los cargos que consideren incorrectos
- **Calendario:** Sincroniza los ciclos de devoluciones con el proceso de cierre financiero de tu organización

**Ejemplo de situación:**   
Tras un año de «showback» satisfactorio, Acme Corp pasa al «chargeback». Cada trimestre, los gastos de TI se imputan a las unidades de negocio y se transfieren mediante asientos contables. El departamento de marketing, que ahora paga $1.8M/quarter por los servicios de TI, ha fusionado dos plataformas de análisis que se solapaban, lo que supone un ahorro anual de $200K.

Nota:

**Por qué es importante en TBM Studio**

La función de tablas publicadas de TBM Studio ( Data Studio ) permite realizar reembolsos mediante la exportación de datos de costes asignados en un formato estructurado adecuado para su importación a su sistema ERP o financiero. Las métricas de presupuesto y previsión, junto con los costes, permiten realizar un seguimiento de las variaciones para la conciliación de los reembolsos.

## Optimización de costes

Los datos de TBM constituyen la base para identificar y aprovechar las oportunidades de ahorro de costes. Al comprender el coste real de los servicios de TI y cómo se distribuyen los costes por toda la organización, es posible identificar ineficiencias, redundancias y oportunidades de optimización que pasan desapercibidas sin unos datos de costes estructurados.

**Patrones comunes de optimización**

- **Eliminación de redundancias:** Identificar servicios duplicados o recursos infrautilizados en todas las unidades de negocio
- **Optimización de la capacidad:** ajustar la capacidad de la infraestructura a la demanda real mediante el análisis de los indicadores de consumo
- **Consolidación de proveedores:** Aprovecha la visibilidad de los costes a nivel de proveedor para negociar mejores contratos o consolidar proveedores
- **Optimización de la nube:** compara los costes de las soluciones locales con los de la nube para cargas de trabajo específicas
- **Eficiencia laboral:** Analizar los costes de personal por servicio para identificar oportunidades de automatización o mejora de los procesos

Nota:

**Por qué es importante en TBM Studio**

El informe de modelos de TBM Studio (vista de Sankey) ofrece una visualización intuitiva de los flujos de costes, lo que facilita la detección de asignaciones desproporcionadas. Las métricas calculadas permiten realizar análisis de variaciones y detectar tendencias. Las funciones de desglose te permiten rastrear cualquier coste hasta su origen para realizar un análisis de las causas fundamentales.

## Realización de evaluaciones comparativas (Benchmarking)

El análisis comparativo consiste en comparar los costes de TI con puntos de referencia, ya sean valores de referencia internos, otras organizaciones del sector o estándares de la industria. Una evaluación comparativa eficaz ayuda a responder a la pregunta: «¿Estamos gastando lo justo?»

**Tipos de análisis comparativo**

- **Comparación entre periodos:** realiza un seguimiento de los costes mes a mes o año tras año para identificar tendencias
- **Comparación entre unidades de negocio:** compara los costes por usuario o por transacción entre las distintas divisiones
- **Análisis comparativo del sector:** compara tus ratios de costes con los de otras empresas del sector utilizando las categorías estandarizadas de la taxonomía TBM

Nota:

**Por qué es importante en TBM Studio**

La gestión de periodos de TBM Studio te permite consultar datos de costes de varios meses para realizar análisis de tendencias. Las métricas calculadas permiten determinar la variación interanual, y la alineación con la taxonomía estandarizada de la plataforma facilita la comparación con referencias externas.

## Elaboración de presupuestos y previsiones

Los datos de TBM sirven de base para la planificación del presupuesto de TI, ya que ofrecen una visión detallada y ascendente de los costes de TI. En lugar de establecer presupuestos basándose en el gasto del año anterior más un porcentaje, TBM permite elaborar presupuestos por niveles de servicio, en los que cada servicio de TI tiene su propio objetivo de costes.

**Capacidades clave**

- **Análisis de desviaciones:** comparar los costes reales con el presupuesto de cada periodo para detectar a tiempo los sobrecostes
- **Presupuestos por servicio:** establecer y supervisar los presupuestos de cada servicio de TI en lugar de por categorías generales
- **Escenarios hipotéticos:** simular el impacto de los cambios (incorporación de usuarios, retirada de aplicaciones, migración a la nube) en los costes generales de TI

Nota:

**Por qué es importante en TBM Studio**

TBM Studio admite varias métricas de modelo al mismo tiempo, normalmente «Coste», «Presupuesto» y «Previsión». Las tres métricas se procesan mediante el mismo modelo de asignación, lo que garantiza una metodología coherente. Los paneles de Report Studio pueden mostrar comparaciones entre los datos presupuestados y los reales, y las tablas editables permiten a los equipos financieros introducir y ajustar las hipótesis presupuestarias.
