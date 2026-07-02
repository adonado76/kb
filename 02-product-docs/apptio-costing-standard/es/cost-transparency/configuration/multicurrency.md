---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Configurar multidivisa para Cloud"
breadcrumb: []
source_path: "cost-transparency/configuration/multicurrency.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configurar multidivisa para Cloud

Puede activar la compatibilidad multidivisa para los productos de Apptio Cloud.

Se aplica a: Cloud para Costing Standard en TBM Studio 12.4.1 y posteriores; Apptio Cloud Business Management en TBM Studio 12.6 y posteriores

## Introducción

Puede activar el soporte multidivisa para los productos de Apptio Cloud para hacer lo siguiente:

- Convierta billetes a la moneda base dentro de su proyecto Apptio
- Mostrar una moneda de sesión en los informes

Para obtener información adicional relacionada con la función multidivisa, consulte [Configurar multidivisa](../../studio/formulas-and-functions/functions/tablematch.html "Devuelve un valor basado en una tabla de reglas que funciona como un conjunto de sentencias IF. Cada fila de la tabla de reglas define una regla. Las condiciones en la misma fila se combinan con AND, y los valores dentro de la misma celda se tratan como condiciones OR.").

Las siguientes instrucciones de configuración son específicas para configurar los archivos de facturación de AWS y Azure en “ConvertToBase”.

Nota:

Para los productos de Apptio Cloud, los valores de la columna Tipo de los datos que cargue en la tabla Cambio de divisas deben estar etiquetados como "Real" en sus datos brutos para que funcione la función multidivisa.

## Instrucciones para nuevos clientes

Para los nuevos clientes, sólo se requiere un paso: Actualizar el Azure EA Detailed Bill Master Data.CurrencyCode con el código de moneda de la factura.

## Instrucciones para clientes existentes con CCM configurado

Haga los siguientes cambios:

## AWS Datos maestros de la factura de imputación de costes

Añada las siguientes columnas:

- **Moneda base BlendedRate** =If(lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",BlendedRate,ConvertCurrencyToBase(BlendedRate,CurrencyCode,"Actual" ))
- **Moneda base CostBeforeTax** =If(lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",CostBeforeTax,ConvertCurrencyToBase(CostBeforeTax,CurrencyCode,"Actual" ))
- **Moneda base Créditos=If** (lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",Credits,ConvertCurrencyToBase(Credits,CurrencyCode,"Actual" ))
- **Base Currency TaxAmount=If** (lookup(CurrencyCode,Currency Exchange,Currency Code,Type)="",TaxAmount,ConvertCurrencyToBase(TaxAmount,CurrencyCode,"Actual" ))
- **Moneda base TotalCost** =If(lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",TotalCost,ConvertCurrencyToBase(TotalCost,CurrencyCode,"Actual" ))

Actualice el anexo en los datos maestros del proveedor de servicios en nube:

Incorpore **los datos maestros de la factura de asignación de costos AWS.** **Moneda base TotalCost** a **Data.Cost maestros del proveedor de servicios en la nube. Costo**

## AWS RDS Datos maestros de compras de RI

Añade las siguientes columnas:

- Precio fijo de **la divisa base** =If(lookup(Código de divisa,Cambio de divisa,Código de divisa,Tipo)="",Precio fijo Price,ConvertCurrencyToBase(Fixed,Código de divisa, "Actual"))
- Cargo recurrente **por moneda base** =If(lookup(Código de moneda,Cambio de moneda,Código de moneda,Tipo)="",Cargo recurrente por hora Charge,ConvertCurrencyToBase(Hourly Cargo recurrente,Código de moneda, "Actual"))
- **Precio de uso de la moneda base** = Si (búsqueda (Código de moneda, Cambio de moneda, Código de moneda, Tipo)="", Price,ConvertCurrencyToBase(Usage, Código de moneda, "Actual"))

Modifique las siguientes columnas existentes:

- Coste efectivo UpFront =Precio fijo en moneda base/((Plazo en Years\*31536000 )/Plazo transcurrido(Inicio,Vencimiento))
- Tarifa combinada = Tarifa inicial horaria+Cargo recurrente en moneda base+Precio de uso en moneda base

Actualizar el anexo en los datos maestros de las instancias reservadas

- Adjuntar AWS RDS RI Compras Maestro Data.Base Moneda Cargo Recurrente en Instancias Reservadas Maestro Data.Recurring Cargos
- Adjuntar AWS RDS RI Compras Maestro Data.Base Moneda Precio Fijo en Instancias Reservadas Maestro Data.UpFront Coste

## AWS Datos maestros de compras de RI

Añade las siguientes columnas:

- Precio fijo de **la divisa base** =If(lookup(Código de divisa,Cambio de divisa,Código de divisa,Tipo)="",Precio fijo Price,ConvertCurrencyToBase(Fixed,Código de divisa, "Actual"))
- Cargo recurrente **por moneda base** =If(lookup(Código de moneda,Cambio de moneda,Código de moneda,Tipo)="",Cargo recurrente por hora Charge,ConvertCurrencyToBase(Hourly Cargo recurrente,Código de moneda, "Actual"))
- **Precio de uso de la moneda base** = Si (búsqueda (Código de moneda, Cambio de moneda, Código de moneda, Tipo)="", Price,ConvertCurrencyToBase(Usage, Código de moneda, "Actual"))

Modifique las siguientes columnas existentes:

- **Tarifa horaria inicial** =IF( RowCount(AWS RI Modificaciones Maestro Data)>0,Effective UpFront Coste/(Transcurrido(Inicio,Vencimiento)/3600),((Moneda Base Precio Fijo/Plazo en Años)/8760))
- **Tarifa combinada** = Tarifa inicial horaria+Cargo recurrente en moneda base+Precio de uso en moneda base
- **Ayuda de precio inicial** =if(Moneda base fija Price=0,SumIf(Parent,ID de instancia reservada,Moneda base precio fijo)\*Ponderación de huella,Moneda base precio fijo)

Actualice el anexo en los datos maestros de las instancias reservadas:

- Añada AWS RI Purchases Master Data.Base Currency Recurring Charge a Reserved Instances Master Data.Recurring Charges
- Añadir AWS RI Compras Maestro Data.Base Moneda Precio Fijo en Instancias Reservadas Maestro Data.UpFront Coste

## Recomendaciones Datos maestros

Devuelva los siguientes conjuntos de datos a OOTB dentro del componente Nube - Recomendaciones:

Recomendaciones Conjunto de datos maestros

En caso de que existan modificaciones, realice los siguientes cambios:

- Añadir nueva columna **Código de moneda** ="USD"
- Modificar el **ahorro mensual estimado** =If(lookup(Código de moneda,Cambio de moneda,Código de moneda Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency, "Actual"))

## Transformación de optimización de instancias reservadas de Amazon EC2

**Coste** inicial cambiado a tipo = Numérico

## Amazon EC2 Optimización de Instancias Reservadas con Plazo

Añadir nueva columna Código de moneda ="USD"

Modifique las siguientes columnas existentes:

- **Factura estimada (RIs actuales)** =If(lookup(Código de moneda,Cambio de moneda,Código de moneda Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency, "Actual"))
- **Factura estimada (RIs actuales)\_|\_1** =If(lookup(Código de moneda,Cambio de moneda,Código de moneda Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency, "Actual"))
- **Factura estimada (RIs optimizados)** =If(lookup(Código de moneda,Cambio de moneda,Código de moneda Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency, "Actual"))
- **Factura estimada (RIs optimizados)\_|\_1** =If(lookup(Código de moneda,Cambio de moneda,Código de moneda Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency, "Actual"))
- **Ahorro mensual estimado** =If(lookup(Código de moneda,Cambio de moneda,Código de moneda Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency, "Actual"))
- **Estimación mensual Savings\_|\_1** =If(lookup(Código de moneda,Cambio de moneda,Código de moneda Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency, "Actual"))
- **Coste inicial** =If(lookup(Código de moneda,Cambio de moneda,Código de moneda Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency, "Actual"))
- **Coste inicial\_|\_1=If** (lookup(Código de moneda,Cambio de moneda,Código de moneda Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency, "Actual"))

## Azure Datos maestros de factura detallados de EA

Añade las siguientes columnas:

- **CurrencyCodeNOTE** Añada un valor en este campo para definir la moneda de su factura Azure.
- **Moneda base ResourceRate** =If(lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",ResourceRate,ConvertCurrencyToBase(ResourceRate,CurrencyCode,"Actual" ))
- **BaseCurrency ExtendedCost** =If(lookup( CurrencyCode,Currency Cambio,Moneda Code,Type)="",ExtendedCost,ConvertCurrencyToBase(ExtendedCost,CurrencyCode,"Actual" ))

Actualice el anexo en los datos maestros del proveedor de servicios en nube:

Adjunte **Azure EA Detailed Fact Master Data.Base Currency ExtendedCost** en **Cloud Service Provider Master Data.Cost**

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
