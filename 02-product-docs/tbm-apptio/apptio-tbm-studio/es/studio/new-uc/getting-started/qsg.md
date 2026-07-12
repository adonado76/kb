---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía de inicio rápido"
breadcrumb:
  - "TBM Studio"
  - "Cómo empezar"
source_path: "studio/new-uc/getting-started/qsg.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía de inicio rápido

## Tu primer modelo de costes

|  |  |
| --- | --- |
| **Tipo de contenido** | Guía de aprendizaje |
| **Destinatarios** | Nuevos usuarios |
| **Tiempo de finalización** | 10 minutos |
| **Requisitos previos** | Acceso a un proyecto de TBM Studio (entorno de desarrollo), conocimientos básicos sobre conceptos de costes de TI, archivo de datos de costes de muestra (formato Excel o CSV ) |

## Lo que lograrás

En este tutorial de 10 minutos, descubrirás el flujo de trabajo completo de TBM Studio mediante:

- Cargar tu primer archivo de datos de costes
- Creación de una transformación de datos sencilla
- Creación de una asignación de costes básica
- Cómo generar tu primer informe de costes

Al final, verás cómo los costes de TI pasan de los datos brutos a los informes útiles, pasando por las asignaciones.

## Antes de empezar

Asegúrate de tener:

- Una cuenta de TBM Studio con acceso a un proyecto
- Un pequeño archivo de datos de costes de muestra listo para cargar

Nota: Aunque para este tutorial se recomienda utilizar una plantilla de datos de ejemplo estandarizada, es posible que actualmente no haya ninguna disponible en tu proyecto. Puede utilizar cualquier archivo sencillo de datos de costes (Excel o CSV ) que contenga, como mínimo, las siguientes columnas: Fuente del coste (por ejemplo, «Nómina», «Servicios en la nube»), Departamento o Unidad de negocio, Importe (valor numérico del coste) y Mes o Fecha.

## Paso 1: Accede a TBM Studio y ve a Data Studio

***Duración:*** *1 minuto*

1. Inicia sesión en TBM Studio con tus credenciales
2. En el panel **«Proyectos»**, selecciona el proyecto que se te ha asignado
3. Asegúrate de que te encuentras en el entorno **de desarrollo** (que aparece en la barra de navegación superior)
4. En el panel **«Explorador de proyectos»** de la izquierda, despliega « **Data Studio** »

**Resultado esperado:** Verás la estructura de carpetas « Data Studio » con las tablas existentes (si las hay) en tu proyecto.

## Paso 2: Sube tus datos de costes

***Duración:*** *2 minutos*

1. Haz clic en la pestaña **«Inicio»** de la barra de herramientas
2. Haz clic en **Nuevo** → **Tabla**
3. Introduce el nombre de la tabla: *«Mis primeros datos de costes»*
4. Selecciona una categoría: *«Tutorial»* (esto ayuda a organizar las tablas)
5. Haz clic **en Aceptar**

La tabla se crea y el proceso de transformación se abre automáticamente.

1. En el paso **«Fuente»**, haz clic en **«Cargar archivo»**
2. Arrastra el archivo de datos al área de carga o haz clic para buscarlo y seleccionarlo
3. TBM Studio detecta automáticamente:
   - Fila de encabezado (normalmente la fila 1)
   - Tipos de columna (Etiqueta, Numérico, Estado/Fecha)
4. Revisa la configuración del paso **de importación** :
   - Comprueba que la opción **«Iniciar importación en la fila»** esté configurada correctamente (normalmente la fila 2 para los datos)
   - Revisa la lista **de columnas** : comprueba que los tipos de columna se detectan correctamente
   - Asegúrate de que todas las columnas de costes numéricos tengan el tipo «Número»
5. Haz clic en **«Guardar»** en la pestaña «Inicio»
6. Haz clic en el paso **«Tabla»** del flujo de trabajo para obtener una vista previa de tus datos

**Resultado esperado:** Verás los datos que has subido mostrados en una tabla con todas las filas y columnas visibles. Los encabezados de las columnas coinciden con los de tu archivo y los tipos de datos se han identificado correctamente.

**Problemas habituales** : si los números aparecen como texto, haz clic en la columna en el paso «Importar» y cambia el tipo a «Número». Si ves algún error, comprueba que tu archivo no tenga filas en blanco al principio.

## Paso 3: Crear una transformación sencilla

***Duración:*** *2 minutos*

Ahora vas a añadir una transformación sencilla para depurar o mejorar tus datos.

1. En el flujo de trabajo **de pasos de transformación**, haz clic en **«Añadir paso»** (icono +)
2. Selecciona **«Filtro»** entre los tipos de pasos
3. Configura el filtro:
   - Haz clic en **«Añadir condición»**
   - Selecciona la columna del importe del coste
   - Establece el operador en **>** (mayor que)
   - Introduce el valor: **0** (para excluir los valores cero o negativos)
4. Haz clic **en Aceptar**
5. Haz clic en el paso **«Tabla»** para obtener una vista previa de los resultados filtrados

**Resultado esperado:** La tabla ahora solo muestra las filas en las que el coste es superior a cero. El número de filas puede ser inferior al de la carga original.

Consejo: Este es un ejemplo básico. En proyectos reales, es posible que tengas que añadir pasos para unir datos, asignar valores o aplicar fórmulas.

## Paso 4: Añade tu tabla al modelo

***Duración:*** *2 minutos*

Para asignar costes, su tabla debe formar parte del modelo de costes.

1. En el proceso de transformación, haz clic en **«Añadir paso»**
2. Selecciona **«Modelo»** como tipo de paso
3. Haz clic en el nuevo paso **«Modelo»** del proceso

Se abre la vista «Modelo de una sola tabla», en la que se muestra la tabla en el centro.

1. Haz clic en tu mesa (el rectángulo del centro)
2. En el panel **«Filas»**, marque las columnas clave que identifican las partidas de costes únicas (por ejemplo, «Fuente de coste», «Departamento»)
3. En el panel **«Controladores»** de la izquierda, haz clic en **«Añadir controlador de unidad»**
4. Configurar el controlador de la unidad:
   - **Añadir a** : Selecciona la métrica de coste (normalmente «Coste»)
   - **Uso** : Seleccionar **columna**
   - **Columna** : Selecciona la columna de importe/coste
5. Haz clic **en Aceptar**
6. Haz clic en **«Guardar»** en la pestaña «Inicio»
7. Haz clic en **«Check-in»** para que los cambios surtan efecto

**Resultado esperado:** Tu tabla es ahora un objeto modelo que puede recibir o enviar asignaciones de costes. En la vista del modelo puedes ver los totales de los costes.

**Entender lo que ha pasado:** Acabas de crear un «controlador de unidad», que indica al modelo de dónde proceden los valores de coste de tu tabla.

## Paso 5: Crear una asignación básica (opcional)

***Duración:*** *2 minutos*

Nota: Este paso requiere una segunda tabla u objeto en tu modelo. Si tu proyecto ya cuenta con un objeto de modelo (como «Unidades de negocio» o «Aplicaciones»), puedes crear una asignación sencilla.

**Si existe una tabla de destino:**

1. En la vista Modelo, haz clic en **«Añadir asignación»** en el panel de la derecha
2. Configure la asignación:
   - **Para** : Seleccionar el objeto de destino (por ejemplo, «Unidades de negocio»)
   - **Condición** : Selecciona una columna coincidente que exista en ambas tablas (por ejemplo, «Departamento»)
3. Haz clic en **«Vista previa»** para ver cómo se distribuirán los costes
4. Haz clic en **Guardar**

**Resultado esperado:** Verás cómo los costes se transfieren de la tabla de origen a la tabla de destino según el factor determinante que hayas seleccionado.

**Si no hay ningún destino:** omite este paso por ahora. Ya has completado la carga de los datos básicos y la integración del modelo. El siguiente paso sería colaborar con un administrador para establecer los objetivos de asignación.

## Paso 6: Genera tu primer informe

***Duración:*** *3 minutos*

Ahora vas a crear un informe sencillo para visualizar tus datos.

1. En el **Explorador de proyectos**, despliega **la sección «Informes»**
2. Haz clic en la pestaña **Inicio** → **Nuevo** → **Informe**
3. Introduce el nombre del informe: *«Mi primer informe de costes»*
4. Introduce la descripción: *«Tutorial: primer informe de costes»*
5. Selecciona «**Visible para** »: elige los permisos adecuados (o mantén los predeterminados)
6. Selecciona el diseño: **Estándar ( 1024px )** con **la opción «Añadir encabezado»** marcada
7. Haz clic **en Aceptar**

Se abre el editor de informes.

1. En el panel «**Configuración de componentes** », arrastra una **tabla** al lienzo del informe
2. Configura la tabla:
   - **Fuente de datos** : Seleccione su objeto de modelo (por ejemplo, «Mis primeros datos de costes»)
   - **Filas** : Arrastra tu dimensión clave (por ejemplo, «Fuente de coste» o «Departamento») al área de Filas
   - **Valores** : Arrastra la métrica de costes al área de Valores
3. La tabla se rellena con tus datos
4. Añade un **filtro** para mejorar la interactividad:
   - Arrastra el componente **«Slicer»** hasta situarlo encima de la tabla
   - Configúralo para filtrar por una de tus dimensiones (por ejemplo, Departamento)
5. Haz clic en **Guardar**
6. Haz clic **en «Check-in»**

**Resultado esperado:** Dispone de un informe operativo que muestra sus costes según la dimensión seleccionada. El filtro permite a los usuarios filtrar los datos de forma interactiva.

Consejo: Haz clic en los valores del filtro para filtrar la tabla: ¡acabas de crear un informe interactivo!

## Comprueba que lo has conseguido

Habrás completado con éxito la guía de inicio rápido si puedes:

- Consulta los datos que has subido en Data Studio
- Visualiza tu tabla en el modelo con un controlador de unidad configurado
- Accede a tu informe y consulta los datos de costes que se muestran
- Utiliza el filtro para filtrar el informe

**Enhorabuena.** Acabas de completar todo el flujo de trabajo de TBM Studio: Datos → Modelo → Informe.

## ¿Qué viene a continuación?

Ahora que ya conoces el flujo de trabajo básico, echa un vistazo a los siguientes pasos:

**Próximos pasos inmediatos**

- **Familiarízate con la interfaz** : consulta la sección « 1.4 » (Navegación por la interfaz) para comprender mejor el espacio de trabajo
- **Comprender los conceptos básicos** : Lee la sección « 1.2 » (Conceptos básicos) para profundizar en el conocimiento de las tablas, los modelos y las métricas

**Desarrolla tus habilidades**

- **Para el trabajo con datos** : consulta la sección « 3.1 » (Trabajar con datos) para conocer técnicas avanzadas de carga y transformación
- **Para la modelización de costes** : consulte la sección « 3.2 » (Crear modelos de costes) para crear asignaciones de varios niveles
- **Para la generación de informes** : consulte la sección « 3.3 » (Crear informes) para crear visualizaciones avanzadas

**Rutas basadas en roles**

- **Analistas de negocios** : Sección 2.1 (Itinerario de aprendizaje para analistas de negocios)
- **Equipos de finanzas de TI** : Sección « 2.2 » (Itinerario de aprendizaje para finanzas de TI)
- **Administradores** : Sección « 2.3 » (Itinerario de aprendizaje para administradores)

## Obtener ayuda

- Si se producen errores, consulte la sección « 7.1 » (Problemas comunes y soluciones)
- Para obtener información detallada sobre cualquier función, consulte la sección 5 (Referencia)

## Resolución de problemas

| **Emitir** | **Solución** |
| --- | --- |
| **No se puede subir el archivo** | Comprueba el formato del archivo (debe ser.xlsx,.xls o.csv) y asegúrate de que el nombre del archivo no contenga caracteres especiales (utiliza solo letras, números, guiones bajos y guiones) |
| **Las columnas se muestran con un tipo incorrecto** | En el paso «Importar», cambia manualmente el tipo de columna haciendo clic en ella y seleccionando el tipo correcto en el menú desplegable |
| **No veo la opción «Paso del modelo»** | Asegúrate primero de haber guardado la tabla. El paso «Modelo» solo se puede añadir una vez creada la tabla |
| **El informe no muestra ningún dato** | Asegúrate de haber guardado los cambios en la tabla y el modelo. Los informes solo muestran datos de los objetos registrados |
| **No puedo hacer el check-in** | Primero debes guardar los cambios (haz clic en «Guardar» en la pestaña «Inicio») y, a continuación, podrás realizar el check-in |
| **Actualizar el espacio de trabajo** | Comprueba la pestaña «Inicio» de la barra de menús para ver si la opción «Actualizar área de trabajo» está activa. Si está activo, haz clic en el icono para actualizar tu espacio de trabajo y asegurarte de que ves las últimas actualizaciones. |
