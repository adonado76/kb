---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Orden de asignación y procesamiento"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura del modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/allocation-order.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Orden de asignación y procesamiento

## Por qué el orden es importante

En un modelo de costes de varios niveles, las asignaciones no se ejecutan todas al mismo tiempo. El orden en que se procesan las asignaciones determina los resultados finales, ya que las asignaciones posteriores dependen del resultado de las anteriores.

Pensemos en una cadena sencilla: «Fuente de costes» realiza una asignación a «Proveedores», y «Proveedores» realiza una asignación a «Unidades de negocio». La asignación a los proveedores debe completarse antes de que las unidades de negocio puedan recibir su parte; de lo contrario, no habría costes que distribuir desde los proveedores.

## Secuenciación basada en dependencias

TBM Studio determina automáticamente el orden de asignación basándose en el gráfico de dependencias del modelo. El sistema analiza qué objetos alimentan a qué otros objetos y establece una secuencia de procesamiento que respeta estas dependencias.

**Las reglas son:**

- Las asignaciones de un objeto se ejecutan únicamente una vez que se han completado todas las asignaciones entrantes a dicho objeto
- Los objetos sin dependencias anteriores (objetos fuente) se procesan en primer lugar
- Los objetos que se encuentran al mismo nivel y no dependen unos de otros pueden procesarse en paralelo
- La secuencia de procesamiento es determinista: el mismo modelo siempre genera el mismo orden de ejecución

## Asignaciones por niveles

En la mayoría de los modelos del mundo real, los costes pasan por múltiples niveles intermedios antes de llegar a su destino final. Esto se denomina asignación de varios niveles o de varios saltos.

**Cómo funcionan los flujos de varios niveles**

Analicemos un coste de 1.000 dólares a través de un modelo de cinco niveles:

|  |  |  |  |
| --- | --- | --- | --- |
| **Nivel** | **Objecto** | **¿Qué pasa?** | **Resultado** |
| 1 | Fuente del coste | Se contabilizan 1.000 dólares procedentes del libro mayor como gasto del centro de datos | Valor de origen: 1.000 dólares |
| 2 | Proveedores | Se ha emparejado con Dell según el ID de proveedor; se transfieren 1.000 dólares a Dell | Dell recibe 1.000 dólares |
| 3 | Servicios técnicos | Asignado a recursos de computación (70 %) y almacenamiento (30 %) en función del uso | Equipo: 700 $, Almacenamiento: 300 $ |
| 4 | Soluciones | Los 700 dólares de Compute se reparten entre el ERP (400 dólares) y el CRM (300 dólares) en función del volumen de transacciones | ERP: 400 $, CRM: 300 $ |
| 5 | Unidades de negocio | Los 400 $ del ERP se reparten entre Ventas (240 $) e Ingeniería (160 $) en función del número de usuarios | Venta: 240 $, Alquiler: 160 $ |

En cada nivel, el motor de asignación aplica las reglas definidas para ese objeto de modelo. El resultado de una etapa se convierte en la entrada de la siguiente. Por eso es fundamental seguir una secuencia adecuada, y por eso el diagrama del modelo resulta indispensable para comprender el flujo de costes.

## Dependencias circulares

Se produce una dependencia circular cuando el objeto A asigna memoria al objeto B y el objeto B, a su vez, asigna memoria al objeto A (ya sea directamente o a través de una cadena de objetos intermedios). Esto genera un bucle infinito que no se puede resolver mediante el procesamiento secuencial habitual.

**El enfoque de TBM Studio:**

- **Prevención:** El gráfico del modelo no debe contener ciclos. TBM Studio comprueba el gráfico de dependencias y evita que se creen configuraciones de asignación que den lugar a flujos circulares.
- **La recursión como excepción:** la asignación recursiva (sección 4.3.4 ) es el único mecanismo admitido para gestionar las dependencias mutuas. Utiliza un procesamiento iterativo con límites de precisión e iteraciones para converger en un resultado.
- **Detección:** Si se crea inadvertidamente una dependencia circular (normalmente debido a configuraciones complejas con varios objetos), el proceso de compilación notifica un error en lugar de entrar en un bucle infinito.

Nota:

**Cómo evitar las dependencias circulares**

Diseña la jerarquía de tu modelo de manera que el flujo sea unidireccional: desde las fuentes de costes en la parte inferior hasta los usuarios de la empresa en la parte superior. Si necesitas una asignación hacia atrás, plantéate si sería más adecuado recurrir a la asignación recursiva o a una jerarquía de modelos reestructurada.
