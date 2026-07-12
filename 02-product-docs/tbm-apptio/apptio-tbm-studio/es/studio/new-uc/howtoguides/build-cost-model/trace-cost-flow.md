---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Seguimiento de los flujos de costes a lo largo del modelo"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Modelización avanzada"
source_path: "studio/new-uc/howtoguides/build-cost-model/trace-cost-flow.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Seguimiento de los flujos de costes a lo largo del modelo

## Objetivo

Utilice el diagrama del modelo y las funciones de desglose para rastrear los flujos de costes y responder a la pregunta: «¿De dónde procede este coste?»

## Cuándo utilizar este procedimiento

Utiliza el seguimiento de costes cuando:

- Una parte interesada pregunta por qué una unidad de negocio o un servicio ha recibido un importe concreto
- Observas resultados de asignación inesperados y necesitas determinar la causa
- Debes comprobar que los costes se contabilizan correctamente
- Estás depurando costes no asignados
- Debe auditar la ruta de asignación con fines de cumplimiento normativo o de revisión financiera

**Requisitos previos**

- Se ha creado y calculado el modelo (los costes se distribuyen a través de las asignaciones)
- Sabes qué objeto de modelo o qué importe de coste quieres rastrear

## Tiempo estimado

Entre 5 y 15 minutos (dependiendo de la complejidad del modelo)

## Comprender las vistas del modelo

TBM Studio ofrece tres vistas complementarias para el seguimiento de los flujos de costes:

- Modelador de objeto único: muestra los controladores y las asignaciones de una tabla cada vez. Ideal para una configuración detallada y una visibilidad inmediata de los tráficos entrantes y salientes.
- Vista de diagrama: muestra todos los objetos del modelo y sus conexiones en una disposición visual. Lo mejor para comprender la estructura completa del modelo y la navegación.
- Informe del modelo (vista de Sankey): presenta los flujos de costes en una visualización por niveles de fácil manejo. Ideal para la comunicación con las partes interesadas y el seguimiento de principio a fin.

## Método 1: Uso de la vista de diagrama

La vista de diagrama ofrece una visualización general de todo el modelo de costes, similar a un diagrama de Visio.

1. En el Explorador de proyectos, despliega el modelo y haz clic en el diagrama del modelo (o accede a él desde el menú Ver).
2. El diagrama muestra todos los objetos del modelo como rectángulos unidos por líneas de asignación. El grosor de cada línea es proporcional al valor que la atraviesa.
3. Utiliza los controles de zoom y desplazamiento para explorar modelos de gran tamaño.
4. Haz clic en cualquier objeto del modelo (rectángulo) para abrir el modelador de objetos individuales de esa tabla, que muestra sus entradas y salidas.
5. Para seguir una ruta de asignación concreta, haga clic en los siguientes elementos de la cadena: Fuente de costes → Proveedores → Servicios tecnológicos → Soluciones → Unidades de negocio.

## Método 2: Uso del modelador de objetos individuales

El Modelador de objetos individuales ofrece un seguimiento detallado de las entradas y salidas de una tabla concreta.

1. En el Explorador de proyectos, haz clic en el objeto del modelo que deseas rastrear y, a continuación, haz clic en el paso «Modelo».
2. La vista muestra lo siguiente: la columna de la izquierda muestra los controladores entrantes y las asignaciones; la parte central muestra el objeto actual; y la columna de la derecha muestra las asignaciones salientes.
3. Haga clic en cualquier asignación entrante (en el lado izquierdo) para ver qué fuente aporta el coste y qué criterios de correspondencia o ponderación se aplican.
4. Haz clic en cualquier asignación de salida (en la parte derecha) para ver hacia dónde se dirigen los costes y qué método de distribución se utiliza.
5. Haz clic en un objeto de destino para acceder a la vista del modelador de ese objeto, lo que te permitirá seguir el rastro hacia las etapas posteriores.

## Método 3: Profundizar en los detalles

Para un seguimiento detallado, utilice la función de desglose para ver los detalles de la asignación a nivel de fila.

1. En la vista «Model step», haz clic en el icono de menú (≡) de la tabla en la que quieras profundizar.
2. Haga clic en «Desglosar» y seleccione una columna (por ejemplo, «Centro de datos», «Nombre del proveedor» o «Grupo de costes»).
3. Ahora, la vista muestra cada valor único de esa columna junto con sus costes asociados.
4. Haz clic en un valor concreto (por ejemplo, un centro de datos específico) para ver únicamente las asignaciones hacia o desde ese valor.
5. Para volver a la vista de tabla, haz clic en el icono de la flecha de retorno situado en la esquina superior izquierda del nivel.

## Ejemplo: Identificación de un gasto imprevisto

**Situación** : El responsable de una unidad de negocio pregunta por qué se le han cobrado 50 000 dólares en concepto de costes de red, cuando esperaba que la factura fuera menor.

1. Abre el objeto del modelo «Unidades de negocio» y busca la unidad de negocio en cuestión.
2. Revisa las asignaciones entrantes para ver qué objetos de nivel superior han generado costes de red.
3. Haga clic en la asignación de Servicios Tecnológicos para ver los criterios de selección y la ponderación.
4. Navega hacia arriba hasta el objeto «Servicios tecnológicos» y vuelve atrás hasta «Proveedores».
5. Sigue rastreando hasta que identifiques la fuente de coste original y comprendas la ruta de asignación.

## Mejores prácticas

- Utiliza la vista de diagrama para la incorporación de nuevos miembros del equipo y la formación
- Utilice las funciones de trazabilidad para identificar asignaciones inesperadas antes de modificar el modelo
- Comprueba los costes no asignados tras modificar la lógica de asignación; a menudo indican problemas de configuración
- Registrar las rutas de asignación de documentos con fines de auditoría mediante informes modelo

## Tareas relacionadas

- [Crear informes modelo](create-model-rep.html)
- [Gestionar los costes no asignados](handle-unallocated-costs.html)
- [Ver el diagrama del modelo](view-model-diagram.html)

**Tema principal:** [Modelización avanzada](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
