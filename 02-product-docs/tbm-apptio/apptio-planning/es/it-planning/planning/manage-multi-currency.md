---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Multidivisa"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/manage-multi-currency.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Multidivisa

Apptio La planificación admite configuraciones multidivisa que permiten introducir, visualizar y conciliar datos financieros en distintas divisas. Esto es especialmente útil para organizaciones globales que gestionan presupuestos en varias regiones.

## Multidivisa

Nota: Se requieren los roles de Administrador o Propietario de Proceso Presupuestario para editar la configuración del Perfil de Empresa.

1. Haga clic en el icono **de engranaje** y abra **Perfil de empresa**.
2. En la sección **Divisa**, marque **Activar Multidivisa**.
3. Establezca la **Moneda** por defecto para su entorno.
4. *(Opcional)* Active **Mostrar códigos de moneda ISO en lugar de símbolos** si prefiere los códigos ISO (por ejemplo, USD, EUR) a los símbolos de moneda.
5. Haga clic en **Guardar** para aplicar los cambios.

## Configuración de tipos de cambio multidivisa

Una vez activada la multidivisa, tendrás que configurar los tipos de cambio para que el sistema pueda convertir con precisión los valores entre divisas.

Apptio La planificación utiliza dos tablas de tipos de cambio distintas:

- **Actuals Tipo de cambio** - aplicado a periodos históricos
- **Tipo de cambio del plan** - aplicado al plan y al periodo de previsión

**Pasos para configurar los tipos de cambio:**

1. Vaya a **Configuración > Datos de Referencia > Tipo de Cambio Real** o **Tipo de Cambio Plan**.
2. Abra el **menú Elipses** y elija:
   1. **Exportar plantilla** para descargar una plantilla en blanco, o bien
   2. **Exportar** para descargar los datos de tarifas existentes para su actualización.
3. Rellene el fichero y defina los siguientes campos:
   1. **De Moneda** - Código ISO de la moneda base (moneda por defecto definida en el Perfil de la Empresa)
   2. **A Moneda -** Código ISO de la moneda de destino
   3. **Tasa** - la tasa de conversión
   4. **Fecha de** entrada en vigor: fecha de inicio de la tarifa. Utilice el formato de fecha AAAA-MM-DD o MM-DD-AAAA.
4. Asegúrese de definir la **tasa base** estableciendo la **moneda por defecto** en sí misma - por ejemplo, USD → USD con una tasa de 1.
5. **Importe** el archivo actualizado y **publique** los cambios.

## Introducción de valores de partidas individuales en distintas monedas

- Cuando el modo multidivisa está activado, cada partida incluirá una **Divisa**. Las partidas sólo pueden editarse cuando el **menú global Divisa** (en la barra de navegación superior) está en **Original**.
- Puede introducir valores en cualquier moneda definida por línea.
- Para ver los valores convertidos, seleccione una moneda del **menú global Moneda** - la tabla de Gastos y los cuadros de mando convertirán automáticamente todos los valores a la moneda seleccionada utilizando el **tipo de cambio** apropiado para ese periodo y tipo de datos (Reales o Plan).

## Configurar divisas predeterminadas por departamento

Nota: Para gestionar Datos de Referencia se requieren los roles de Administrador o Propietario de Proceso Presupuestario.

Puede definir una moneda por defecto para cada departamento para garantizar que la entrada de datos se ajusta a los requisitos financieros locales o regionales.

**Pasos:**

1. Abra la tabla de datos de referencia **del Departamento**.
2. **Exporte** los datos del Departamento e introduzca el **código de moneda predeterminado** deseado en la columna **Moneda** para cada Departamento.
3. **Vuelva a importar** el archivo actualizado y **publique** los cambios.

Si un Departamento no tiene definida una divisa, se utilizará la **divisa por defecto** (definida en el Perfil de la Empresa) cuando se acceda a ese departamento.
