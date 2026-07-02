---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Varias monedas"
breadcrumb: []
source_path: "it-planning/planning/support-multiple-currencies.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Varias monedas

Apptio Planning respaldan las necesidades de planificación, elaboración de informes y análisis de las organizaciones que trabajan con varias divisas. Entre las funciones que admiten varias divisas se incluyen las siguientes:

- Una moneda única y común utilizada para todas las conversiones monetarias. La moneda común suele ser la moneda de registro de la organización. Todas las tasas de conversión de moneda se fijan contra esta moneda y, a menos que se especifique otra, es la moneda de visualización por defecto por Centro de Coste. Para más información, consulte [Establecer la moneda común](set-common-currency.html "Se utiliza una única moneda común para todas las conversiones monetarias. La moneda común suele ser la moneda de registro de la organización. Todas las tasas de conversión de moneda se fijan contra esta moneda y, a menos que se especifique otra, es la moneda de visualización por defecto por Centro de Coste.").
- Compatible con todas las monedas que utilizan un código ISO. Para más información sobre la lista de códigos reconocidos internacionalmente, consulte [https://www.iso.org/iso-4217-currency-codes.html](https://www.iso.org/iso-4217-currency-codes.html "(se abre en una pestaña o una ventana nueva)"). El código ISO especifica la abreviatura de tres letras de la moneda (por ejemplo, USD para el dólar estadounidense), y la visualización correcta de la moneda (por ejemplo, el símbolo $ y la colocación de comas y decimales). Un administrador puede seleccionar que se muestren los códigos ISO de las divisas en lugar de los símbolos de las divisas y puede habilitar funciones para admitir varias divisas.
- Asignación opcional de una moneda local para centros de coste de grupo o individuales. Los códigos de moneda local de los Centros de Coste se gestionan como datos de referencia del Centro de Coste. Si no se especifica ningún código de moneda local, se utiliza por defecto la sociedad.
- Tablas de tipos de cambio independientes para los datos financieros previstos (presupuesto y previsiones) y reales. Las tablas de tipos de conversión definen los tipos de conversión de divisas (FX) con respecto a la moneda común, y se gestionan como datos de referencia. Los tipos de conversión temporales de los datos reales pueden ayudar a distinguir la desviación real del plan de la desviación debida a las fluctuaciones monetarias.
- Soporte de tipos de conversión por divisa en las tablas de tipos. Especifique los índices de conversión a cualquier escala, desde diaria hasta anual. Los tipos de conversión por moneda permiten introducir importes presupuestarios en una moneda local para el Centro de Coste, convirtiéndolos después a la moneda común (o a cualquier otra moneda admitida) cuando se resuman.

## Habilitar funciones multidivisa

Los usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario pueden habilitar las funciones multidivisa. Elija si desea mostrar u ocultar las funciones de compatibilidad con varias divisas. La compatibilidad con varias divisas se establece en la sección Perfil de la empresa y se aplica a todos los usuarios del inquilino seleccionado en ese momento. Para más información, consulte [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.").

1. En el menú Apptio Planning , haga clic en el botón Configuración y, a continuación, en Perfil de empresa.
2. En la sección Configuración, seleccione Activar Multidivisa.

   Nota: Si desea cambiar la visualización de los valores de moneda de un símbolo de moneda a un código de moneda ISO de tres letras, seleccione Mostrar códigos de moneda ISO en lugar de Símbolos. Por ejemplo, un valor monetario CA$30.68M, puede mostrarse como 30.68M CAD. Esto aporta claridad a las organizaciones y usuarios que trabajan con diversas monedas.
3. Seleccione Guardar y Salir.

Atención: Una vez activadas las funciones multidivisa, realice las siguientes tareas:

- [Establecer la moneda comúnEstablezca](set-common-currency.html "Se utiliza una única moneda común para todas las conversiones monetarias. La moneda común suele ser la moneda de registro de la organización. Todas las tasas de conversión de moneda se fijan contra esta moneda y, a menos que se especifique otra, es la moneda de visualización por defecto por Centro de Coste.") la moneda común para su organización
- [Requisito de datos de referenciaImportar](import-publish-currency.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario del Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") y publicar tipos de cambio
- [Ingresar o mostrar valores de artículos de línea en diferentes monedas](enter-display-line.html "Cuando la compatibilidad con varias monedas está activada, una lista de monedas en la parte superior derecha de la página le permite mostrar los valores financieros del plan presupuestario o de la previsión de partidas en un valor de moneda distinto de la moneda de la empresa.") Ingresar o mostrar valores de artículos de línea en diferentes monedas
