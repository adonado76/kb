---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Uso de recomendaciones de compromiso para analizar oportunidades de ahorro"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Guía para la gestión de compromisos"
source_path: "product/using_commitment_recommendations_to_analyze_savings_opportunities.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Uso de recomendaciones de compromiso para analizar oportunidades de ahorro

## Finalidad

El objetivo de este documento es ofrecer una visión general de cómo utilizar las Recomendaciones de Compromiso. A nivel de resumen, puede utilizar las Recomendaciones de Compromisos para comprender dónde existen oportunidades de ahorro basadas en su gasto actual en la nube y en los compromisos que ya posee. Las recomendaciones son generadas por un modelo propio que aplica sus preferencias y limitaciones empresariales. La página de detalles le permite ejecutar análisis de sensibilidad y de suposición hipotética para crear un argumento comercial para las compras incrementales y dar forma a una estrategia de compromiso optimizada para su organización.

## Cómo acceder y utilizar

La página Recomendaciones de compromiso se encuentra en la sección Optimizar del menú de navegación de la izquierda y, al igual que la cartera, está organizada por proveedor.cada pestaña comparte una estructura común para que puedas comparar entre nubes sin cambiar de modelo mental. La barra de herramientas de la cabecera le permite crear una vista de recomendaciones centrada:

**Tipo de compromiso**

Esta selección está organizada por proveedor ( AWS ), a servicio ( EC2 ), a tipo de compromiso ( EC2 Instancias reservadas). Tenga en cuenta que la página de servicio intermedio no es necesaria cuando existe un único tipo de compromiso que cubre el servicio.

- **Todos los niveles** (página de inicio basada en el proveedor): Muestra todos los servicios/tipos compatibles del proveedor seleccionado.
- **Nivel de servicio** : Muestra todos los tipos de compromiso admitidos para el servicio seleccionado.
- **Nivel de tipo** : Muestra todas las clases de compromiso de los distintos tipos.

En particular, las páginas agregadas a nivel de proveedor y de servicio garantizan que las recomendaciones proporcionadas sean mutuamente excluyentes entre sí. Para más información sobre este comportamiento, consulte la sección de tipo de recomendación más abajo.

**Cuenta**

El selector de cuentas elige el uso de las cuentas que nuestro modelo analizará para una recomendación. Por lo general, la mejor práctica consiste en elegir una selección de cuenta que se corresponda con sus preferencias de uso compartido configuradas en la consola del proveedor. Como no disponemos de un sistema para consultar esta información, ofrecemos la opción de configurarlo en la aplicación. El selector representa la naturaleza jerárquica de sus cuentas y es multiselección.

- Al seleccionar una(s) cuenta(s) de pagador (Gestión, Suscripción, Facturación) se seleccionan todas las cuentas vinculadas que se encuentran debajo de ella.
- La selección de una(s) cuenta(s) específica(s) vinculada(s) (Miembro, Suscripción, Proyecto) muestra un estado de selección parcial en la cuenta del pagador.

  Para obtener más información sobre la terminología de las cuentas, consulte [Estructura de las cuentas por proveedor](commitments_vendor_account_structure.html)

**Acción**

Relevante sólo para AWS en este momento, esta selección le permite elegir si desea evaluar recomendaciones de Compra, Intercambio o Infrautilizado. Esto es especialmente relevante en el caso de AWS EC2, donde las instancias reservadas convertibles ofrecen mayor flexibilidad para alcanzar niveles más altos de cobertura.

**Plazo**

Esta selección indica a nuestro modelo qué longitud de término debe analizar en las recomendaciones proporcionadas. Para los tipos de recomendación óptima y de destino, este desplegable mostrará Mix cuando se muestren varias recomendaciones de términos en la página.

**Base de coste**

La elección de precios de lista o ajustados permite a los usuarios entender sus recomendaciones a partir de tarifas de lista o negociadas por encargo y compromiso. Los KPI y las tablas reflejan la base que seleccione. Tenga en cuenta que es posible que las páginas de compromiso de Azure aún no dispongan de un conmutador. En su caso, los valores reflejan la costumbre. Para obtener más información, consulte [Cómo influyen los precios negociados en los compromisos](custom_pricing_factors_across_commitments.html).

**Periodo de análisis**

Esta selección controla todos los KPI y los metadatos de las tablas de la página. El perfil de uso por defecto, el nombre de preferencia del periodo de análisis por defecto en toda la página de recomendaciones, es el último mes anterior y las horas están en UTC. Nuestra sugerencia es evitar informar sobre las 24 horas más recientes para permitir que los datos terminen de procesarse en nuestro pipeline. Para más información, consulte [Frescura de datos](data_freshness.html).

Es importante señalar que nuestro modelo actual se basa únicamente en el periodo de análisis seleccionado. Para obtener más información sobre la selección de un intervalo de análisis adecuado para su caso de uso, consulte el Perfil de uso.

**Opciones de pago**

Específicamente para AWS y Azure, esta selección determina cómo se pagarían las recomendaciones seleccionadas. A menudo se aplica un descuento adicional al pagar por adelantado.

**Clase de oferta**

En el caso concreto de las instancias reservadas de AWS EC2, esta selección determina si se ofrecen recomendaciones estándar o convertibles.

**Región Preferencia**

En el caso concreto de las instancias reservadas de AWS EC2, esta selección determina si se ofrecen recomendaciones limitadas a una región o a una zona de disponibilidad.

**Cuentas compartidas**

Esta selección determina si las recomendaciones se refieren a cuentas individuales o se agregan al pagador.

**Umbrales de tasa**

Esta selección actúa como un filtro sencillo para especificar qué umbrales de utilización y tasa de ahorro son relevantes a la hora de calcular las recomendaciones

## Interpretación de los KPI de recomendación

Todos los indicadores clave de rendimiento se basan en nuestro modelo de recomendación. Se impulsan formalmente a partir del periodo de análisis seleccionado.

- El ahorro neto se define como el ahorro bruto previsto menos los residuos previstos de las compras propuestas en el ámbito de aplicación.
- El PSR (esperado), el CSR (esperado) y el CDR (conocido) se utilizan para ayudar a interpretar las recomendaciones
- Mostramos la cobertura actual y futura para transmitir cómo cambiaría la cobertura si se compraran las recomendaciones especificadas.
- La utilización se pondera por el impacto relativo/tamaño de las recomendaciones en la tabla.

## Página de resumen y detalles por tipo

Debajo de la cabecera está la tabla. Cada fila resume una recomendación. Las columnas se adaptan al tipo de compromiso seleccionado.a diferencia del cajón de la cartera, la acción de detalles abre una página de detalles dedicada a esa recomendación. A partir de aquí, el ámbito de aplicación se centra en esta recomendación, proporcionando un gráfico y capacidad de ajuste.

**Operaciones de tabla y filtros**

- **Ordenar** : Haga clic en el encabezado de una columna para ordenar de forma descendente, haga clic de nuevo para ascendente, una tercera vez para restablecer.
- **Mostrar/Ocultar columnas** : Utilice el control Columnas para elegir qué campos mostrar.
- **Paginación** : Los controles de paginación estándar aparecen debajo de la tabla.
- **Exportar** : El botón «Exportar» genera un archivo « CSV » en formato WYSIWYG (lo que ves es lo que obtienes) para el ámbito actual y las columnas visibles.

**Añadir filtro y filtrado en línea**

- Utilice Añadir filtro (debajo de la cabecera) para filtrar por cualquier campo admitido.
- Las celdas que están hipervinculadas están disponibles para filtrar, seleccionando una celda vinculada filtrará la tabla por ese atributo y añadirá una ficha a la barra de filtrado.

**Alertas y opiniones**

- **Soporte de vistas** : La página de recomendaciones admite vistas de alcance de cuenta y proveedor. Aquí no se admiten otras asignaciones empresariales porque las métricas por compromiso no se pueden calcular de forma fiable con reasignaciones arbitrarias.

****Página de recomendaciones****

- **KPI modelados** : Ahorro neto, Tasa de ahorro, Cobertura, Utilización para las recomendaciones actualmente seleccionadas.
- **Gráfico de análisis** : Refleja la estructura del Gestor de Compromisos con el coste de compromiso actual superpuesto con el coste de la recomendación propuesta y el coste a la carta resultante.
- **Ficha resumen de detalles** : Muestra los detalles específicos de la recomendación y la información adicional necesaria para evaluarla
- **Ajuste de la recomendación** : El botón de acción Ajustar permite a los usuarios utilizar nuestro modelo para ajustar la recomendación. Aquí admitimos tres métodos de ajuste. Para más información, consulte la sección Tipo de recomendación.
- **Enlaces a informes** : Proporcionamos enlaces a los informes para facilitar la comprensión del gasto comprometido que respalda la recomendación. Lo mejoraremos en el futuro añadiendo la modalidad de cobertura a la página de recomendaciones.

## Tipo de recomendación

Cloudability produce múltiples modos de recomendación para adaptarse a diferentes estilos de decisión. Estos modos están disponibles para su comparación tanto en la página de resumen como en la de detalles.

**Recomendación óptima-** Esta recomendación maximiza el ahorro neto de los compromisos. Por lo tanto, analizamos los distintos parámetros de compromiso correspondientes al tipo de compromiso seleccionado y ofrecemos una recomendación que permite obtener la tasa de ahorro prevista (CSR) más elevada, basándonos en el consumo cubrible durante el periodo de análisis seleccionado. En los casos en que un servicio tenga varios tipos de compromiso aplicables (computación), la página «Todos» ofrecerá la recomendación óptima entre los tipos de compromiso disponibles. Las páginas dedicadas a cada tipo de compromiso no tendrán en cuenta la posibilidad de utilizar otros tipos de compromiso a la hora de determinar la recomendación óptima.

Tomando AWS como ejemplo, EC2 puede estar cubierto por EC2 Instancias Reservadas, EC2 Planes de Ahorro de Instancias y Planes de Ahorro de Computación. En la página de recomendaciones de Todos los cálculos, la recomendación óptima buscará entre los tres tipos de compromisos aplicables para recomendar lo que es óptimo entre los gastos comprometidos. Cuando esté en la página Todos EC2, la recomendación óptima buscará en los dos tipos de compromiso específicos de EC2 para recomendar lo que es óptimo a través de los gastos comprometidos mientras se ignoran los Planes de Ahorro de Computación. Por último, en la página de recomendaciones de Planes de Ahorro de Instancias EC2, la recomendación óptima demostrará cuál es el máximo ahorro que se puede conseguir con los Planes de Ahorro de Instancias EC2, ignorando las Instancias Reservadas EC2

Nota: El comportamiento óptimo de las recomendaciones se introdujo con [las mejoras](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=cloudability-whats-new-in#topic__cldy-commit-mgmt-2.0subrelease "(se abre en una pestaña o una ventana nueva)") en las recomendaciones de compromiso de la versión « AWS » en mayo de 2026

**Recomendación objetivo-** Esta recomendación maximiza el ahorro neto de los compromisos dadas las preferencias configuradas.

Nota: La recomendación de «Target» solo está disponible actualmente para GCP. Está previsto que en una futura versión se incorpore compatibilidad con otros proveedores.

**Recomendación modificada** : esta recomendación refleja el comportamiento de la página de recomendaciones antes de la introducción del tipo de recomendación óptima. La recomendación modificada se limita a maximizar el ahorro dentro de las opciones simuladas. Cuando una combinación de selecciones se ajusta a los parámetros de recomendación «Óptima» o «Objetivo», la página cambiará el tipo de recomendación de «modificada» a «calculada». Cualquier otra combinación de selecciones dará lugar a que se modifique el tipo de recomendación.**Recomendación personalizada** : los usuarios pueden personalizar una recomendación a través de la página de detalles de la recomendación; para ello, deben hacer clic en el botón «Personalizar» y elegir una de las tres opciones disponibles. Los tres métodos de recomendación personalizados son los siguientes:

- **Importe del compromiso** : Este método simplemente toma en una cantidad que desea comprometerse, ya sea en términos de la demanda o el costo de compromiso, y le proporciona el resultado esperado basado facilitado a través de la interfaz de usuario de recomendación.
- Porcentaje **de cobertura** : Este método asume que usted desea construir un caso de negocio para un porcentaje de cobertura que difiere de su estrategia de compromiso objetivo configurado. Introduzca un porcentaje de cobertura y nuestro modelo intentará estimar qué compra daría como resultado el porcentaje de cobertura deseado para la variante actual.
- **Uso mínimo sostenido** : Este método supone que desea cubrir todo el uso sostenido. Proporcionamos una entrada para omitir hasta el 5% de las horas de uso que sean atípicas.

  Nota: La recomendación personalizada sigue teniendo en cuenta la utilización prevista en función del periodo de análisis seleccionado.

## **Utilizar esta página para aplicar las mejores prácticas**

- **Comprender el rendimiento actual** : Compruebe siempre primero la cartera para tener un conocimiento sólido de los próximos vencimientos y la utilización actual.
- **Comprender el nivel de cobertura actual** : Nuestras recomendaciones no tienen en cuenta los futuros vencimientos de los compromisos
- **Comprenda cómo podría cambiar el uso** : Nuestras recomendaciones se basan en el uso actual y, por tanto, no tienen en cuenta los aumentos o disminuciones de uso.
- **Configurar preferencias de compromiso** : Configuramos sus preferencias de compromiso por defecto para mostrar una recomendación de objetivo. Recomendamos revisar estas preferencias y ajustarlas a su empresa antes de utilizar la página de recomendaciones.
- **Compare Óptimo vs Objetivo vs Personalizado** : Si la cobertura óptima supera materialmente la cobertura objetivo, valide su tolerancia al riesgo ajustando sus preferencias de compromiso. Puede estar dejando sobre la mesa un ahorro considerable. Utilice entradas personalizadas para desarrollar una comprensión a nivel de resumen de cómo las diferentes preferencias podrían afectar a sus recomendaciones
- **Construya un caso de negocio** : Utilice la página de detalles de las recomendaciones para crear un caso de negocio para una estrategia de cobertura a largo plazo o una compra incremental.

## Puntos de partida clave

- Las recomendaciones reflejan la estructura de la cartera, pero están orientadas al futuro y son viables.
- La página de detalles es un espacio de trabajo completo: inspeccione los supuestos, vea los gráficos y ajuste las propuestas.
- Utilice los modos Óptimo/Objetivo/Personalizado/Ajustado para ajustar las decisiones al riesgo, la política y las restricciones de tesorería.
- Configure las preferencias para configurar la recomendación objetivo; utilice [Cobertura](coverage_modal.html) y [Ahorro neto](net_savings_modal.html) en cartera para obtener contexto adicional.

**Tema principal:** [Guía para la gestión de compromisos](../product/guide_to_commitment_management.html)
