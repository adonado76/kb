---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Uso de la cartera de compromisos para comprender el rendimiento histórico"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Guía para la gestión de compromisos"
source_path: "product/using_commitment_portfolio_to_understand_historical_performance.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Uso de la cartera de compromisos para comprender el rendimiento histórico

## **Propósito**

El objetivo de este documento es ofrecer una visión general de cómo utilizar la cartera de compromisos. A modo de resumen, puede utilizar la cartera de compromisos para comprender cómo se han comportado los compromisos existentes a lo largo del tiempo, qué riesgos existen de cara al futuro y proporcionar un punto de partida para iniciar la conversación sobre qué oportunidades quedan. Cuando se utiliza plenamente, esta página combina la información táctica con la interpretación estratégica, lo que permite a los profesionales de FinOps pasar rápidamente de las señales (KPI) a las acciones (alertas, informes, recomendaciones).

## **Cómo acceder y utilizar**

La página Cartera de compromisos se encuentra en la sección Optimizar del menú de navegación de la izquierda y está organizada por proveedor. Cada pestaña comparte una estructura común para que puedas comparar entre nubes sin cambiar de modelo mental. La barra de herramientas de la cabecera le permite crear una vista de cartera centrada

**Tipo de compromiso**

Esta selección está organizada por proveedor ( AWS ), a servicio ( EC2 ), a tipo de compromiso ( EC2 Instancias reservadas). Tenga en cuenta que la página de servicio intermedio no es necesaria cuando existe un único tipo de compromiso que cubre el servicio.

- **Todos los niveles** (página de inicio basada en el proveedor): Muestra todos los servicios/tipos admitidos para el proveedor seleccionado.
- **Nivel de servicio** : Muestra todos los tipos de compromiso admitidos para el servicio seleccionado.
- **Nivel de tipo** : Muestra todas las clases de compromiso de los distintos tipos.

**Cuenta**

El selector de cuentas controla el uso de las cuentas que está analizando y extrae automáticamente cualquier compromiso que afecte a ese uso, incluso si esos compromisos se adquirieron en otro lugar. Por ejemplo, si el compromiso de la Cuenta A cubre el uso en la Cuenta B, la selección de la Cuenta B sola seguirá reflejando el impacto del compromiso de A en el uso de B. Como práctica recomendada, elija cuentas que coincidan con la configuración de uso compartido de la consola de su proveedor para que el análisis refleje cómo se comparten realmente los compromisos. El selector representa la naturaleza jerárquica de sus cuentas y es multiselección.

- Al seleccionar una(s) cuenta(s) de pagador (Gestión, Suscripción, Facturación) se seleccionan todas las cuentas vinculadas que se encuentran debajo de ella.
- La selección de una(s) cuenta(s) específica(s) vinculada(s) (Miembro, Suscripción, Proyecto) muestra un estado de selección parcial en la cuenta del pagador.

Puede restringir por la cuenta facturada utilizando los filtros de la tabla. Para conocer las jerarquías de proveedores y los ámbitos de compartición, consulte [Estructura de cuentas por proveedor](commitments_vendor_account_structure.html).

**Base de coste**

La elección de precios de lista o ajustados permite a los usuarios entender sus recomendaciones a partir de tarifas de lista o negociadas por encargo y compromiso. Los KPI y las tablas reflejan la base que seleccione. Tenga en cuenta que es posible que las páginas de compromiso de Azure aún no dispongan de un conmutador. En su caso, los valores reflejan la costumbre. Para más información, consulte [Cómo influyen los precios personalizados en los compromisos](custom_pricing_factors_across_commitments.html)

**Período de análisis**

Esta selección controla todos los KPI y los metadatos de las tablas de la página. Por defecto es el último mes y las horas están en UTC. Nuestra sugerencia es evitar informar sobre las 24 horas más recientes para permitir que los datos terminen de procesarse en nuestro pipeline. Para más información, consulte [Frescura de datos](data_freshness.html).

## **Interpretación de los KPI de la cartera**

- El Ahorro Neto y el Coste de Compromiso Restante son KPI en dólares referidos al periodo de análisis.
- La Tasa de Ahorro, la Utilización y la Cobertura son KPIs de tasa circunscritos al periodo de análisis.
- Tasa de Ahorro de Cartera (TAC) = Ahorro Neto Comprometido ÷ Gasto Comprometido (según la base seleccionada). El PSR aísla el efecto de los descuentos por compromiso de los precios negociados a la carta, lo que lo convierte en una métrica de cartera más limpia que la Tasa de Ahorro Efectiva (ESR) cuando hay tarifas negociadas en juego. Cuando la base de costes es la lista, el PSR es igual al ESR, ya que todos los valores se refieren a la tarifa de lista y no hay ahorros debidos a las tarifas negociadas. Para más información, consulte [Indicadores clave de rendimiento del compromiso](commitments_key_performance_indicators.html).
- La utilización se pondera por el impacto/tamaño relativo de los compromisos en el cuadro.
- Los modales de detalles de KPI están disponibles para Ahorro Neto y Cobertura. Estos modales proporcionan información adicional para comprender cómo se calcula el KPI. Para más información, consulte [Ahorro neto](net_savings_modal.html) comprometido y [Modalidades de cobertura](coverage_modal.html).

## **Panel de resumen y detalles por tipo**

Debajo de la cabecera está la tabla. Cada fila resume un compromiso. Las columnas se adaptan al tipo de compromiso seleccionado. Haga clic en Detalles en cualquier fila para abrir el panel de detalles (cajón derecho). Mostramos la siguiente información:

- Todos los metadatos disponibles para el compromiso.
- KPIs asignados a este compromiso (mismas definiciones que los KPIs de cabecera).
- Tendencias visuales del ahorro neto diario y la utilización durante el periodo de análisis seleccionado. Incluimos un conmutador de vida útil para ajustar el gráfico a toda la vida del compromiso, independientemente del periodo de análisis actual.

**Operaciones de tabla y filtros**

- **Ordenar** : Haga clic en el encabezado de una columna para ordenar de forma descendente, haga clic de nuevo para ascendente, una tercera vez para restablecer.
- **Mostrar/Ocultar columnas** : Utilice el control de columnas para elegir qué campos mostrar.
- **Paginación** : Los controles de paginación estándar aparecen debajo de la tabla.
- **Exportar** : El botón «Exportar» genera un archivo « CSV » en formato «lo que ves es lo que obtienes» para el ámbito actual y las columnas visibles.

**Añadir filtro y filtrado en línea**

- Utilice añadir filtro (debajo de la barra de herramientas de la cabecera) para filtrar por cualquier campo admitido.
- Las celdas que están hipervinculadas están disponibles para filtrar, seleccionando una celda vinculada filtrará la tabla por ese atributo y añadirá una ficha a la barra de filtrado.

**Alertas y opiniones**

- **Alertas** : El botón de alertas de la parte superior derecha abre las [Alertas de compromiso](setting_commitment_alerts.html) para configurar los correos electrónicos de Caducidad y Umbral de utilización.
- **Soporte de vistas** : La Cartera admite vistas de alcance de cuenta y proveedor. Aquí no se admiten otras asignaciones empresariales porque las métricas por compromiso no se pueden calcular de forma fiable con reasignaciones arbitrarias.

**Tablas agrupadas frente a tablas no agrupadas de GCP**

En el caso de « GCP », la cartera admite dos perspectivas complementarias, determinadas por la forma en que GCP presenta los compromisos (créditos sin identificadores de compromiso por uso y CUD de recursos multidimensionales). En las exportaciones, el ID de reserva no suele estar configurado.

- **Vista agrupada:** Agrupa los compromisos en el ámbito aplicable (por ejemplo, cuenta de facturación/región para los CUD de la CME). En esta vista, la aplicación puede mostrar métricas de rendimiento por grupo.
- **Vista no agrupada:** Refleja AWS / Azure con una fila por compromiso. Algunas métricas de rendimiento por elemento se omiten cuando los datos subyacentes carecen de granularidad por compromiso. El Panel de detalles agrupados enumera los CUD que componen el grupo.

## **Utilizar esta página para aplicar las mejores prácticas**

- **Horizonte temporal** : Tendencia por mes/trimestre para señales a nivel de cartera; utilizar semana/día para confirmar estacionalidad.
- **Disciplina de base** : Mantenga la coherencia entre la fuente del precio y la base de reconocimiento en todas las comparaciones. Para obtener más información, consulte [el enfoque del compromiso Cloudability respecto a los costos](commitment_approach_to_cost.html) y [cómo los factores de precios negociados influyen en los compromisos.](custom_pricing_factors_across_commitments.html)
- **Showback/Chargeback** : Utilice los filtros de cartera y los enlaces de [cobertura](coverage_modal.html) para desglosar la cobertura y la no cobertura por equipo/aplicación para la rendición de cuentas.
- **Preparación para la renovación** : Compare el ahorro neto y la utilización de los artículos próximos a caducar; decida renovarlos, canjearlos (si procede) o simplemente dejarlos caducar.
- **Control del despilfarro** : La persistencia del rojo en el [Ahorro Neto](net_savings_modal.html) suele indicar desajustes en el alcance, exceso de compras o estacionalidad: ajuste el plazo, el alcance o la combinación de categorías.

## **Puntos de partida clave**

- La cartera es su visión única de los compromisos en propiedad y del rendimiento histórico.
- Primero, lea los KPI agregados y, a continuación, utilice el panel de detalles y las ventanas emergentes ( [Cobertura](coverage_modal.html) / [Ahorro neto](net_savings_modal.html) ) para comprender los factores determinantes.
- Utilice filtros, conmutadores agrupados/no agrupados y el contexto del proveedor para pasar de la señal a la acción.
- Utilizar [alertas](setting_commitment_alerts.html) y [recomendaciones para](using_commitment_recommendations_to_analyze_savings_opportunities.html) poner en práctica las conclusiones.
- Trate la cartera como su sistema de registro; revísela semanalmente para comprobar tendencias y mensualmente para planificar renovaciones.

**Tema principal:** [Guía para la gestión de compromisos](../product/guide_to_commitment_management.html)
