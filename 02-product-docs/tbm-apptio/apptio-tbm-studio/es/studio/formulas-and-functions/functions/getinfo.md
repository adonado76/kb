---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "GetInfo función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/getinfo.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetInfo función

**Se aplica a** : TBM Studio 12.0 y posteriores

Devuelve una amplia gama de información sobre un proyecto.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Cualquier campo en el que se pueda introducir una fórmula
- !NEWCOLUMN en una ruta de datos
- Columnas de fórmulas en tablas de informes
- Texto dinámico
- Apptio guion

## Sintaxis

`GETINFO("attribute",["DomainName:ProjectName"])`

Las cotizaciones son obligatorias.

## Argumentos

*atributo*

Puede ser uno de los siguientes:

- `"project.startDate"` (Devuelve la primera fecha del proyecto)
- `"project.endDate"` (Devuelve la última fecha del proyecto)
- `"project.effectiveStartDate"` (Devuelve el conjunto effectiveStartDate. Fechas de los controles de rendimiento de honores)
- `"project.effectiveEndDate"` (Devuelve el conjunto effectiveEndDate. Fechas de los controles de rendimiento de honores)
- `“project.fyMonthIndex”` (Devuelve un índice de 0 a 11 correspondiente al mes del año fiscal currentDete( ).
- `“project.isRealTimeCalculation”` (Devuelve 'true' si el proyecto está en modo tiempo real, y 'fals' si está precalculado)
- `“project.request.currency.code”`(Devuelve la moneda seleccionada para la sesión actual)
- `“project.request.currency.exchange.rate.type”`(Devuelve el tipo de cambio de moneda seleccionado para la sesión actual)
- `“project.request.locale”`(Devuelve la configuración regional seleccionada para la sesión actual. Por defecto es la configuración regional del proyecto, pero puede ser anulada por una preferencia del usuario)
- `“project.isRealTimeCalculation”`(Devuelve 'true' si el proyecto está en modo tiempo real, y 'fals' si está precalculado.
- `table.transformName`(Devuelve el nombre de la tabla primaria que respalda la consulta, si existe)
- `table.lastMaterialRevision`(Similar a db.contents.lastMaterialRevision pero devolviendo la última revisión que obligó a recalcular esta tabla)
- `db.contents.lastMaterialRevision` (El número de revisión del último cambio material en el auditlog de un proyecto. Un cambio es material si puede afectar a las cifras calculadas previamente. El número de revisión es una lista delimitada por.de los ID de registro de auditoría de la última entrada de registro de auditoría en cada registro de auditoría de la pila de proyecto derivada para el proyecto)
- `db.contents.currentRevision` (El número de revisión de la última modificación del cálculo del proyecto actual. El número de revisión es un. lista delimitada de los ID de auditlog de la última entrada de auditlog en cada auditlog de la pila de proyectos derivados del proyecto)

*DomainName:ProjectName*

Especifica el dominio que contiene el proyecto y el nombre del proyecto. Si especifica un nombre de dominio, debe especificar también el nombre del proyecto. Forman parte del mismo argumento. El argumento debe ser un valor de etiqueta codificado entre comillas. No puede ser una referencia a otra columna o fórmula.

## Tipo de retorno

Etiqueta

## Notas

Puede introducir la siguiente función en un cuadro HTML para comprobar si la función funciona correctamente.

`<%=GETINFO("attribute",”<%=DomainName%>:<%=ProjectName%>”)%>`

## Ejemplo

El siguiente ejemplo devuelve la fecha de inicio del proyecto de la empresa ABC en el dominio docs.org.

```
=GetInfo("project.startDate","docs.org:ABC
          Company")
```

`=GetInfo("project.startDate”)`
