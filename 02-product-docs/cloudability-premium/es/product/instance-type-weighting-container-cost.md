---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "VM ponderaciones basadas en la familia"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Imputación de los costes de los contenedores"
source_path: "product/instance-type-weighting-container-cost.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# VM ponderaciones basadas en la familia

¿Qué es la ponderación de recursos?

Aunque calcular el coste de cada clúster de K8s resulta relativamente sencillo —basta con identificar las máquinas virtuales y los discos subyacentes—, se requiere un trabajo adicional para desglosar cada VM /disco de modo que puedan asignarse (los archivos de facturación de los proveedores no contienen información que facilite esta tarea). Identificación de los recursos (CPU, memoria, red, etc.) se consumen a través de Namespaces o etiquetas, entonces es clave poder vincular una contribución de costes a estos recursos. Aquí es donde entra en juego la ponderación de los recursos.

Cuando hablamos de «peso de CPU» o «peso de memoria», nos referimos al porcentaje del coste total del nodo (es decir, VM ) que debe atribuirse al uso de la CPU o de la memoria. Cuando lanzamos por primera vez nuestra función de asignación de costes de contenedores, esta se basaba en ponderaciones estándar que se aplicaban a todos los tipos de contenedores ( VM ). Aunque en general ha funcionado bien, ha quedado claro que la gran variedad de tipos de nodos en uso ha hecho necesario un planteamiento más matizado.

Nuevas ponderaciones basadas en la familia de « VM »

VM El sistema de ponderación se ajustará mejor a la forma en que cada uno de los proveedores relaciona el coste con la CPU, la memoria, el disco y la red; esto puede determinarse comparando los precios y la cantidad de cada recurso entre las dos familias. He aquí cómo hacerlo, empezando por el disco y la red.

Disco y red

Para las familias de « VM » que no disponen de almacenamiento local, es muy sencillo: la contribución al coste es del 0 %. Para las familias que sí disponen de almacenamiento local, calculamos el impacto de ese almacenamiento. Por ejemplo, si nos fijamos en AWS EC2, los tipos m5.xlarge, m5d.xlarge y VM tienen exactamente el mismo vCPU y la misma memoria, y solo m5d cuenta con almacenamiento local. Dado que el servicio « m5.xlarge » cuesta 0.192 por hora y el servicio « m5d.xlarge » 0.226 por hora, este recargo adicional de 0,034 $ por almacenamiento representa el 15 % del coste total de « m5d.xlarge ».

En cuanto a los gastos de red, dado que no son específicos de VM y, por lo general, suponen un factor menor, hemos aplicado un coste estándar del 5 % a todos los tipos de VM. Por lo tanto, el resto del coste de VM se reparte entre la memoria y la CPU, lo que en el caso de m5.xlarge supondría un 95 % y en el de m5d.xlarge, un 80 %.

Memoria y CPU

Para dividir este coste restante, podemos realizar una comparación similar —aunque más compleja— entre las familias de procesadores « VM » con el fin de calcular el coste por « vCPU » y por GB de memoria. Para cualquier consulta sobre VM,

VM tarifa por hora = número de operaciones de lectura/escritura ( vCPU ) \* tarifa de lectura/escritura ( vCPU ) + memoria \* tarifa de memoria

Si logramos calcular la tasa de « vCPU » y la tasa de memoria, es posible establecer la proporción (es decir, las ponderaciones) para cualquier familia de « VM ». Aunque hay dos variables desconocidas (las tasas), podemos resolverlas utilizando dos ecuaciones distintas: una para la familia objetivo VM y otra para una familia «base» VM.

Vale la pena explicar brevemente cómo se elige una familia de bases VM. Lo primero que hay que tener en cuenta es que la placa base VM será del mismo fabricante de procesadores, ya sea AMD, Intel o Graviton. También daremos prioridad a una familia de « VM » de la misma generación. Por ejemplo, si la dirección de destino es c6i, la familia base VM que se utilizará será probablemente m6i o r6i.

Una vez determinadas las tasas de la CPU ( vCPU ) y de la memoria para cada familia de procesadores ( VM ), resulta sencillo calcular las ponderaciones: basta con multiplicar la cantidad de CPU ( vCPU ) y de memoria por sus respectivas tasas y, a continuación, establecer la relación entre el coste de la CPU y el de la memoria. Tenga en cuenta, debido a la forma en que los proveedores facturan sus máquinas virtuales, que estos ratios son coherentes a nivel de familia.

¿Qué significa esto para la imputación de costes?

- Las cifras de costes a nivel de clúster no se ven afectadas. Este cambio sólo se aplica a los espacios de nombres y a las etiquetas.
- Las ponderaciones estándar utilizadas anteriormente inclinaban la asignación hacia el uso de memoria. Con esta versión, ahora todo depende totalmente de cómo aplique el fabricante las tarifas para la familia específica de procesadores « VM », pero, en general, esto ha vuelto a inclinar la balanza hacia el uso de la CPU.
- Este cambio se ha realizado tanto en los valores que se encuentran en la función Asignación de costes de contenedores como en las dimensiones Espacio de nombres y Etiqueta dentro de los informes básicos.
- Esta mejora se aplica tanto a Kubernetes como a ROSA clusters

**Tema principal:** [Asignación de costes de contenedores](../product/k8s-cost-allocation.html)
