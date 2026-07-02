---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Cartografía empresarial"
breadcrumb:
  - "Cloudability Premium"
  - "Configuración"
  - "Organiza tus gastos en la nube"
source_path: "admin/business-tags.html"
images:
  - "images/business-mapping-addnew.png"
  - "images/business-mapping-addstmt.png"
  - "images/business-mapping-edit.png"
  - "images/business-mapping-listview.png"
  - "images/business-mapping-rule-structure.png"
  - "images/business_mapping_mceclip3.jpg"
  - "images/business_mappingmceclip4.jpg"
  - "images/business_mappingmceclip6.jpg"
  - "images/execution-flow.png"
  - "images/export_import_bm.png"
  - "images/tagging-flow.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cartografía empresarial

## ¿Qué son las correspondencias empresariales?

Las asignaciones de negocio se utilizan para crear dimensiones de negocio que clasifican el gasto en la nube según la taxonomía de tu organización.

A diferencia de las dimensiones proporcionadas por los proveedores o basadas en la facturación, las dimensiones empresariales ofrecen una mayor flexibilidad y control. Utilizan reglas de evaluación —denominadas «declaraciones de mapeo empresarial»— para traducir los metadatos específicos de los proveedores y la facturación en conceptos empresariales significativos. Los conceptos empresariales son las categorías y estructuras que utiliza una organización para interpretar los datos brutos y convertirlos en información adecuada para la elaboración de informes y la toma de decisiones.

El motor de reglas de Business Mapping admite lógicas complejas y puede evaluar una amplia variedad de atributos tanto de los datos de facturación como de los de consumo. Entre ellos se incluyen campos proporcionados por los proveedores, como etiquetas, nombres de cuentas, regiones y nombres de servicios. Cloudability amplía aún más esta funcionalidad al ofrecer atributos mejorados, como la familia de uso y el tipo de arrendamiento, lo que permite una clasificación más detallada y precisa.

Nota:

El número máximo de registros para una dimensión de negocio es de 300 000.

El número máximo de extractos en todas las dimensiones de negocio es de 500 000.

## ¿Cómo funcionan las correspondencias empresariales?

Evaluado tras la ingestión

Cuando se importan los datos de facturación, Cloudability evalúa cada partida de coste según tus reglas de asignación empresarial. Puedes considerar estas reglas como algo similar a una instrucción «case»: cuando se encuentra una coincidencia, el nombre de la instrucción asociada se utiliza como valor para la dimensión de negocio.

Este valor puede ser:

- Una etiqueta estática que definas tú (por ejemplo, «Marketing», «No conforme»), o
- Un atributo dinámico (por ejemplo, el valor de una etiqueta del propio elemento).

En cuanto una regla se cumple, el procesamiento se detiene y no se evalúan más reglas. Si no hay ninguna regla que coincida, se asigna el valor por defecto.

Actualizaciones automáticas

Cada vez que tu proveedor de servicios en la nube envía un nuevo conjunto de datos de facturación, Cloudability vuelve a aplicar el conjunto actual de instrucciones de «Business Mapping».

Consejos para crear dimensiones empresariales

Elige un nombre claro

Cada dimensión empresarial debe tener un nombre. Elige un nombre que transmita claramente su finalidad, ya que aparecerá en los informes y en todo el sitio web Cloudability.

Establecer un valor por defecto

Indica un valor por defecto, que se asignará cuando ninguna regla coincida. Entre los valores predeterminados más habituales se encuentran «Sin asignar», «Desconocido», «No conforme» o «Sin definir ».

Comprender la estructura de las reglas

Cada declaración de mapeo empresarial consta de:

1. Nombre : el valor asignado a la dimensión empresarial cuando se produce una coincidencia. Puede tratarse de un valor estático o de uno que se rellene dinámicamente a partir de un atributo de una partida de costes (por ejemplo, una etiqueta).
2. Expresión de coincidencia : una condición que evalúa los atributos de las partidas de costes. Estas expresiones pueden utilizar lógica booleana compleja, un amplio conjunto de operadores y cualquier atributo relevante de las partidas de costes.

Nota: Los cambios en las declaraciones de Business Mapping se aplican automáticamente a los datos de facturación del mes en curso. Para aplicar actualizaciones a los datos históricos, envíe una solicitud de reprocesamiento o póngase en contacto con el soporte Cloudability o con su TAM para obtener ayuda.

El diagrama puede ayudar a comprender los conceptos que subyacen a la estructura del Business Mapping:

![](../../../../03-media/cloudability-premium/images/business-mapping-rule-structure.png)

**1. Mapeo empresarial** (nivel superior)

- El marco general de asignación de costes
- Contiene varias dimensiones

**2. Dimensiones** (Categorías)

- Unidades organizativas de la empresa
- Ejemplos: Departamento, centro de costes, proyecto, entorno
- Cada dimensión contiene varias reglas

**3. Reglas** (lógica de asignación)

- Define cómo se asignan los recursos a las categorías
- Cada regla contiene una o más instrucciones
- Las reglas tienen un orden de prioridad

**4. Declaraciones** (Condiciones)

- Condiciones lógicas individuales
- Consultar los metadatos específicos de la nube
- Varias expresiones se combinan mediante la lógica AND/OR

```
Business Mapping: "Cost Allocation Framework"
│
├── Dimension: "Department"
│   │
│   ├── Rule 1 (Priority 1): "Engineering Resources"
│   │   ├── Statement 1: tag:Department EQUALS "Engineering"
│   │   └── Statement 2: tag:Environment EQUALS "Production"
│   │   → Result: Assign to "Engineering"
│   │
│   ├── Rule 2 (Priority 2): "Marketing Resources"
│   │   └── Statement 1: account_id EQUALS "123456789"
│   │   → Result: Assign to "Marketing"
│   │
│   └── Rule 3 (Priority 3): "Default"
│       └── Statement 1: tag:Department IS EMPTY
│       → Result: Assign to "Unallocated"
│
└── Dimension: "Environment"
    │
    ├── Rule 1: "Production"
    │   └── Statement 1: tag:Environment EQUALS "Production"
    │   → Result: Assign to "Production"
    │
    └── Rule 2: "Non-Production"
        ├── Statement 1: tag:Environment EQUALS "Development"
        └── Statement 2: tag:Environment EQUALS "Testing"
        → Result: Assign to "Non-Production"
```

## Trabajar con mapeos de negocio

Enumeración y análisis de las dimensiones empresariales

Desde la página de inicio de «Business Mappings», puedes ver una lista de todas las dimensiones empresariales que has configurado y hay varias acciones que puedes realizar. Puedes configurar un máximo de 10 dimensiones empresariales.

![Lista de dimensiones de la cartografía empresarial](../../../../03-media/cloudability-premium/images/business-mapping-listview.png)

Crear nuevas dimensiones empresariales

Para crear una nueva dimensión empresarial:

1. En la página «Business Mapping», selecciona «Nueva dimensión empresarial» en el menú «Añadir».
2. En la ventana «Añadir una asignación empresarial », introduce el nombre de la dimensión y el valor por defecto > Selecciona «Añadir una asignación empresarial ».

   ![Añadir ventana emergente para la creación de un nuevo negocio](../../../../03-media/cloudability-premium/images/business-mapping-addnew.png)
3. En la página «Asignación empresarial», selecciona el icono de configuración (engranaje) situado junto a la dimensión recién creada > Selecciona «Editar asignación empresarial».
4. Haz clic en «Añadir una declaración ».
5. Asigna un nombre a la expresión > Selecciona «ID de cuenta» como dimensión y «igual a» como operador. Selecciona un valor en el menú desplegable «Seleccionar valor» > Haz clic en «Guardar ».

   ![Añadir una instrucción a una asignación empresarial](../../../../03-media/cloudability-premium/images/business-mapping-addstmt.png)
6. También puedes rellenar la dimensión «Business» mediante la función de importación/exportación. Solo tienes que adjuntar el archivo JSON con la estructura definida del objeto «Business Dimension» que se describe aquí [: «Business Mappings Endpoint»](../api-v3/business_mappings_endpoint.html)

   ![Mapeo de actividades de exportación e importación](../../../../03-media/cloudability-premium/images/export_import_bm.png)

Modificar o crear una dimensión empresarial

La mayor parte de tus acciones en esta página consistirán en gestionar los informes de métricas empresariales correspondientes a las dimensiones de tu empresa. Es decir, añadir, modificar o eliminar las instrucciones que constituyen la base de cualquier mapeo. En las siguientes secciones abordaremos los elementos clave de cualquier declaración.

![Editar captura de pantalla del mapa empresarial](../../../../03-media/cloudability-premium/images/business-mapping-edit.png)

Nota:

Cuando una asignación empresarial hace referencia a otra asignación, al actualizar la dimensión a la que se hace referencia también se actualizará el campo «Última actualización» de la dimensión dependiente. Por ejemplo, si la asignación empresarial B hace referencia a la asignación empresarial A, cualquier actualización que se realice en la asignación A actualizará automáticamente la marca de tiempo de «Última actualización» tanto de la asignación empresarial A como de la asignación empresarial B.

Opciones para el nombre

Como se ha mencionado anteriormente, el nombre que introduzcas al crear cualquier expresión se convertirá en el valor de la dimensión de negocio si el componente de coincidencia devuelve «true». Tienes dos opciones para el nombre en sí. Podrías simplemente introducir una cadena estática.

También puedes crear un nombre de dimensión dinámica seleccionando el icono del lápiz situado junto al nombre.

A continuación, recibirás una lista de dimensiones entre las que elegir, que incluye etiquetas y muchos otros elementos que te resultarán familiares. La ventaja de esta función es que, en una coincidencia, la dimensión de negocio puede adoptar el valor de cualquier atributo de la propia partida de costes. Un buen ejemplo de cómo utilizar este aspecto dinámico sería algo así como : «Si existe la etiqueta A, entonces la dimensión de negocio debería adoptar el valor de la etiqueta A ». Probablemente, la siguiente instrucción trataría de qué hacer en caso de que la etiqueta A no exista.

Qué significa

En lugar de asignar un valor fijo a una dimensión de negocio, puedes asignar el valor real procedente de una etiqueta o un atributo del propio recurso. Esto hace que las correspondencias sean flexibles y escalables.

**Asignación estática (valor fijo):**

```
IF tag:Department EQUALS "Engineering"
THEN Department = "Engineering"  ← Fixed value
```

**Asignación dinámica (utilizar el valor de la etiqueta):**

```
IF tag:Department IS NOT EMPTY
THEN Department = [value of tag:Department]  ← Dynamic value
```

**Ejemplo completo: asignación de departamentos**

Supongamos que tienes recursos con etiquetas de departamento diferentes:

- Recurso 1: tag:Departamento = «Ingeniería»
- Recurso 2: tag:Departamento = «Marketing»
- Recurso 3: tag:Departamento = «Ventas»
- Recurso 4: Sin etiqueta de departamento

**Enfoque tradicional (varias reglas estáticas):**

```
Rule 1:
  IF tag:Department EQUALS "Engineering"
  THEN Department = "Engineering"

Rule 2:
  IF tag:Department EQUALS "Marketing"
  THEN Department = "Marketing"

Rule 3:
  IF tag:Department EQUALS "Sales"
  THEN Department = "Sales"

Rule 4:
  IF tag:Department IS EMPTY
  THEN Department = "Unallocated"
```

**Enfoque dinámico (regla única):**

```
Rule 1 (Priority 1):
  IF tag:Department IS NOT EMPTY
  THEN Department = [value of tag:Department]
  
Rule 2 (Priority 2):
  IF tag:Department IS EMPTY
  THEN Department = "Unallocated"
```

![](../../../../03-media/cloudability-premium/images/tagging-flow.png)

![nombre, empresa, mapa, captura de pantalla](../../../../03-media/cloudability-premium/images/business_mapping_mceclip3.jpg)

Operadores

Con la interfaz de usuario de Business Mapping, dispondrás de una amplia gama de operadores para comprobar la lógica de tu expresión. A continuación se muestran algunos ejemplos que incluyen operadores como «mayor que», que pueden resultar útiles para realizar comprobaciones con elementos como las fechas. Elige un operador que haga que tu enunciado sea lo más sencillo posible. Si utilizas nuestra API, dispondrás de algunas opciones adicionales, entre las que se incluyen las expresiones regulares.

![Captura de pantalla del mapa de negocio de los operadores](../../../../03-media/cloudability-premium/images/business_mappingmceclip4.jpg)

Lógica booleana

Dentro de una instrucción individual, puedes agrupar expresiones mediante operadores «OR» y combinarlas con operadores «AND» para obtener el resultado lógico exacto que se ajuste a tus reglas de negocio. A continuación se muestra un ejemplo muy sencillo:

![Añadir captura de pantalla de la asignación empresarial de la lógica booleana](../../../../03-media/cloudability-premium/images/business_mappingmceclip6.jpg)

**Operadores booleanos**

Las asignaciones de negocio utilizan dos operadores booleanos principales:

- **Y** : Todas las afirmaciones deben ser VERDADERAS
- **O** : Al menos una de las afirmaciones debe ser VERDADERA

**Flujo de ejecución**

![](../../../../03-media/cloudability-premium/images/execution-flow.png)

**Ejecución de la lógica «AND»**

Todas las expresiones deben dar como resultado «VERDADERO»:

```
Rule: "Production Engineering Resources"

Statement 1: tag:Department EQUALS "Engineering"
AND
Statement 2: tag:Environment EQUALS "Production"
AND
Statement 3: region STARTS WITH "us-"

Execution:
┌─────────────────────────────────────────────┐
│ Resource: EC2 Instance                      │
│ - tag:Department = "Engineering"  → TRUE    │
│ - tag:Environment = "Production"  → TRUE    │
│ - region = "us-east-1"            → TRUE    │
│                                             │
│ Result: TRUE AND TRUE AND TRUE = TRUE       │
│ Action: Apply mapping                       │
└─────────────────────────────────────────────┘

┌─────────────────────────────────────────────┐
│ Resource: RDS Instance                      │
│ - tag:Department = "Engineering"  → TRUE    │
│ - tag:Environment = "Development" → FALSE   │
│ - region = "us-west-2"            → TRUE    │
│                                             │
│ Result: TRUE AND FALSE AND TRUE = FALSE     │
│ Action: Skip to next rule                   │
└─────────────────────────────────────────────┘
```

**Ejecución de la lógica «O»**

Al menos una expresión debe dar como resultado «VERDADERO»

```
Rule: "Engineering or DevOps Resources"

Statement 1: tag:Department EQUALS "Engineering"
OR
Statement 2: tag:Department EQUALS "DevOps"
OR
Statement 3: tag:Team EQUALS "Platform"

Execution:
┌─────────────────────────────────────────────┐
│ Resource: Lambda Function                   │
│ - tag:Department = "Marketing"    → FALSE   │
│ - tag:Department = "DevOps"       → TRUE    │
│ - tag:Team = "Sales"              → FALSE   │
│                                             │
│ Result: FALSE OR TRUE OR FALSE = TRUE       │
│ Action: Apply mapping                       │
└─────────────────────────────────────────────┘

┌─────────────────────────────────────────────┐
│ Resource: S3 Bucket                         │
│ - tag:Department = "Marketing"    → FALSE   │
│ - tag:Department = "Sales"        → FALSE   │
│ - tag:Team = "Support"            → FALSE   │
│                                             │
│ Result: FALSE OR FALSE OR FALSE = FALSE     │
│ Action: Skip to next rule                   │
└─────────────────────────────────────────────┘
```

**Lógica booleana mixta (AND + OR)**

Regla: «Recursos de producción para ingeniería o DevOps" »

```
(Statement 1: tag:Department EQUALS "Engineering"
 OR
 Statement 2: tag:Department EQUALS "DevOps")
AND
Statement 3: tag:Environment EQUALS "Production"
```

Orden de ejecución:

1. Evalúa primero el grupo «O»: (Afirmación 1 O Afirmación 2)

2. A continuación, evalúa la operación «Y» con la instrucción 3

Ejemplo 1:

```
┌─────────────────────────────────────────────┐
│ Resource: EC2 Instance                      │
│ Step 1: Evaluate OR group                   │
│   - tag:Department = "Engineering" → TRUE   │
│   - tag:Department = "DevOps"      → FALSE  │
│   - Result: TRUE OR FALSE = TRUE            │
│                                             │
│ Step 2: Evaluate AND                        │
│   - OR Result = TRUE                        │
│   - tag:Environment = "Production" → TRUE   │
│   - Result: TRUE AND TRUE = TRUE            │
│                                             │
│ Final Result: TRUE                          │
│ Action: Apply mapping                       │
└─────────────────────────────────────────────┘
```

Ejemplo 2:

```
┌─────────────────────────────────────────────┐
│ Resource: RDS Instance                      │
│ Step 1: Evaluate OR group                   │
│   - tag:Department = "Marketing"   → FALSE  │
│   - tag:Department = "DevOps"      → FALSE  │
│   - Result: FALSE OR FALSE = FALSE          │
│                                             │
│ Step 2: Evaluate AND                        │
│   - OR Result = FALSE                       │
│   - tag:Environment = "Production" → TRUE   │
│   - Result: FALSE AND TRUE = FALSE          │
│                                             │
│ Final Result: FALSE                         │
│ Action: Skip to next rule                   │
└─────────────────────────────────────────────┘
```

## **Orden de ejecución y evaluación en cortocircuito**

**Lógica AND - Cortocircuito:**

Afirmación 1 Y Afirmación 2 Y Afirmación 3

Si la afirmación 1 es FALSA

→ Detener la evaluación (el resultado ya es FALSO)

→ No evalúes la afirmación 2 ni la 3

→ Pasar a la siguiente regla

**Lógica OR - Cortocircuito:**

Afirmación 1 O Afirmación 2 O Afirmación 3

Si la afirmación 1 es VERDADERA

→ Detener la evaluación (el resultado ya es TRUE)

→ No evalúes la afirmación 2 ni la 3

→ Aplicar la correspondencia

¿Cómo puedo utilizar la API para extraer datos o actualizar los BM?

Puedes utilizar las API de « Cloudability » para extraer y actualizar las asignaciones empresariales (BM). La documentación de la API para extraer o actualizar las asignaciones de negocio está disponible en el apartado «[Punto final de asignaciones de negocio](../api-v3/business_mappings_endpoint.html) ».

¿Cómo puedo crear una regla de mapeo empresarial con varias sentencias y expresiones?

Cloudability te permite crear tus propias dimensiones personalizadas mediante «Business Mappings», un motor basado en reglas en el que cada regla puede contener más de una instrucción. Dentro de una instrucción individual, puedes agrupar expresiones mediante operadores «OR» y combinarlas con operadores «AND» para obtener el resultado lógico exacto que se ajuste a tus reglas de negocio.

Si más de una expresión de la instrucción devuelve «True», el valor final evaluado dependerá del operador AND u OR. Por ejemplo: hay dos expresiones: Exp1 y Exp2

Si « Exp1 » = «True» y « Exp2 » = «True», entonces « Exp1 » Y « Exp2 » devolverían «True», y « Exp1 » O « Exp2 » devolverían «True»

Si « Exp1 » = «True» y « Exp2 » = «False», o viceversa, entonces « Exp1 » Y « Exp2 » devolverían «False», y « Exp1 » O « Exp2 » devolverían «True»

Si Exp1 = False y Exp2 = False, entonces Exp1 Y Exp2 devolverían False, y Exp1 O Exp2 devolverían False

¿Cómo puedo consultar o acceder a la lógica de los BM?

Ve a «Organizar» > «Asignaciones empresariales». Se mostrará la lista de asignaciones empresariales. Haz clic en el icono con forma de engranaje para editar las asignaciones de empresas. Aquí se muestran las sentencias utilizadas en la lógica de las asignaciones empresariales. Además, puedes utilizar el icono de la flecha hacia abajo para ver la expresión de la regla de la instrucción.

Preguntas frecuentes sobre dimensiones y métricas

¿Cómo se adaptan los distintos indicadores de costes a los diferentes casos de uso?

Cloudability admite las siguientes cinco métricas de costes habituales:

Coste (de catálogo), Coste (total), Coste (ajustado), Coste (amortizado) y Coste (ajustado y amortizado).

El caso de uso más adecuado para cada métrica de costes depende de los requisitos específicos de la empresa. Es importante analizar detenidamente las necesidades y los objetivos de la empresa a la hora de seleccionar la métrica adecuada.

¿Podemos impedir que los usuarios vean determinadas dimensiones o métricas en Cloudability?

Actualmente, no es posible impedir que los usuarios vean determinadas dimensiones o métricas en Cloudability. Por defecto, todos los usuarios podrían ver todas las dimensiones o métricas en Cloudability.

- **[Organizar los datos mediante esquemas jerárquicos de negocio](../admin/hierarchical-business-mapping.html)**
- **[Métricas empresariales en Cloudability](../admin/business-metrics.html)**

**Tema principal:** [Organiza tu gasto en la nube](../admin/tag-data.html)
