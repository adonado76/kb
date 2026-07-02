---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear asignaciones de varios niveles"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Crear asignaciones"
source_path: "studio/new-uc/howtoguides/build-cost-model/create-multi-tier-allo.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear asignaciones de varios niveles

**Objetivo:** Crear un flujo de costes completo que distribuya los costes a través de los distintos niveles de la organización, desde los costes de origen, pasando por los objetos intermedios, hasta los consumidores finales de la empresa.

**Cuándo utilizarlo:** Su modelo de costes requiere varios pasos de asignación para reflejar con precisión cómo se distribuyen los costes en su organización. La mayoría de las implementaciones de TBM utilizan entre cuatro y seis niveles.

**Tiempo estimado:** entre 45 y 60 minutos para un modelo de cuatro niveles

## Comprensión de los flujos de costes en varios niveles

En la modelización de costes empresariales, los costes rara vez fluyen directamente desde el origen hasta el destino final. En cambio, pasan por capas intermedias que aportan contexto empresarial y permiten generar informes detallados.

**Patrón habitual de distribución de costes de una tuneladora:**

|  |
| --- |
| **Costes reales por fuente**  *(Libro mayor, facturas, costes de personal)*  ▼  **Mano de obra │ Proveedores │ Instalaciones** (Nivel 1)  ▼  **Servicios tecnológicos** (Nivel 2)  *(Informática, almacenamiento, redes, usuario final)*  ▼  **Solicitudes** (Nivel 3)  *( SAP, Salesforce, Aplicaciones personalizadas)*  ▼  **Unidades de negocio** (Nivel 4)  *(Ventas, Marketing, Operaciones, Recursos Humanos)* |

## Paso a paso: cómo crear un modelo de asignación de cuatro niveles

**Escenario:** Crear un flujo de costes completo desde la fuente de costes, pasando por la mano de obra, los servicios y las aplicaciones, hasta las unidades de negocio.

## Fase 1: Configuración de la estructura del modelo

1. **Asegúrate de que todas las tablas tengan los pasos del modelo**
   - Cada tabla del flujo de costes necesita que se añada un paso «Modelo» a su canalización de transformación.
   - Tablas: Fuente de costes, Mano de obra, Servicios tecnológicos, Aplicaciones, Unidades de negocio.
2. **Planificar la secuencia de asignación**
   - Fuente de costes → Mano de obra (por tipo de gasto = «Mano de obra»)
   - Fuente de costes → Instalaciones (por tipo de gasto = «Instalaciones»)
   - Mano de obra → Servicios tecnológicos (por porcentaje de dedicación)
   - Servicios tecnológicos → Aplicaciones (por consumo de servicios)
   - Aplicaciones → Unidades de negocio (por titularidad de la aplicación)
3. **Echa un vistazo a todas las tablas**
   - Revisa todas las tablas que forman parte de la cadena de asignación.

## Fase 2: Configurar las asignaciones de nivel 1

En «Fuente de costes», cree asignaciones independientes para cada objeto de primer nivel:

1. **Asignación de mano de obra:** Añadir desde el filtro para Tipo de gasto = «Mano de obra»
2. **Asignación de instalaciones:** Añadir filtro «De» para Tipo de gasto = «Instalaciones»
3. **Asignación de proveedores:** Añadir filtro «De» para el tipo de gasto que NO ESTÉ EN («Mano de obra», «Instalaciones»)

## Fase 3: Configurar las asignaciones de nivel 2

Desde cada objeto de primer nivel, asigna a Servicios Tecnológicos:

- Mano de obra → Servicios tecnológicos: Relación de datos = Tipo de función → Categoría de servicio, Ponderación por = % de asignación de tiempo
- Instalaciones → Servicios tecnológicos: Peso por metro cuadrado
- Proveedores → Servicios tecnológicos: Relación de datos = Categoría de contrato → Categoría de servicio

**Fase 4: Configurar las asignaciones de los niveles 3 y 4**

- **Servicios tecnológicos → Aplicaciones:** Uso = Consumo, Columna «Consumo» = Unidades consumidas, Columna «Capacidad» = Capacidad total
- **Aplicaciones → Unidades de negocio:** Relación de datos = Propietario de la aplicación → Código de unidad de negocio, Ponderación por = Número de usuarios

**Fase 5: Validar el flujo completo**

1. **Ver el diagrama del modelo**
   - Abre la vista del diagrama del modelo para comprobar que todas las líneas de asignación estén conectadas.
   - Comprueba si hay objetos huérfanos o conexiones que falten.
2. **Realizar un seguimiento de los costes a lo largo del modelo**
   - Seleccione una sola partida de costes en «Fuente de costes».
   - Utiliza la función de trazabilidad para seguirlo en cada etapa.
3. **Realizar un cálculo del modelo**
   - Realice un cálculo del modelo para el período actual.
   - Consulte el informe del modelo (vista de Sankey) para visualizar el flujo de costes.

## Buenas prácticas para entornos de varios niveles

**Asigna hacia abajo, no hacia arriba**

- Los costes deben distribuirse siempre desde la fuente de costes hacia abajo a lo largo del modelo.
- Los flujos inversos generan complejidad y posibles referencias circulares.

**Mantener una granularidad coherente**

- Cada nivel debe tener una granularidad uniforme dentro de sí mismo.
- Evita mezclar datos muy detallados y datos muy agregados en el mismo nivel.

**Documentar el modelo**

- Añade descripciones a cada objeto del modelo en las que se explique su finalidad.
- Elabora un diagrama visual del flujo de costes previsto para la comunicación con las partes interesadas.

**Tema principal:** [Crear asignaciones](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
