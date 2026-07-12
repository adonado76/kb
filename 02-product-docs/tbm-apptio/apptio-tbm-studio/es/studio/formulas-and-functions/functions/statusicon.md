---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "StatusIcon función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/statusicon.html"
images:
  - "resources/images/studio_images/studioimages/icons/small_blueicon.png"
  - "resources/images/studio_images/studioimages/icons/small_grayicon.png"
  - "resources/images/studio_images/studioimages/icons/small_greenicon.png"
  - "resources/images/studio_images/studioimages/icons/small_redicon.png"
  - "resources/images/studio_images/studioimages/icons/small_yellowicon.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# StatusIcon función

**Se aplica a** : TBM Studio 12.0 y posteriores

\* **\*\*Depreciada\*\*\*** Esta función ha sido sustituida por la función [Icono](icon.htm "(se abre en una pestaña o una ventana nueva)").

Evalúa dos expresiones y devuelve una de las cinco etiquetas HTML <img> para iconos de colores en función de los resultados.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas de fórmulas en tablas de informes
- Texto dinámico
- Métricas calculadas e informes con columnas de métricas

## Sintaxis

`StatusIcon(green_expression,red_expression)`

## Argumentos

*expresión\_verde*

Una expresión que se evalúa como verdadero o falso. Si es verdadero, la función devuelve un

icono verde ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_greenicon.png).

*expresión\_roja*

Una expresión que se evalúa como verdadero o falso. Si es verdadero, la función devuelve un

icono rojo ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_redicon.png).

Si ambas expresiones se evalúan como verdaderas, la función devuelve un icono azul ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_blueicon.png).

Si ninguna de las expresiones se evalúa como verdadera, la función devuelve un icono amarillo ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_yellowicon.png).

Si hay un error en las reglas (por ejemplo, si se especifica una variable que no existe), la función devuelve un icono gris ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_grayicon.png).

**Notas** :

Las expresiones admiten los operadores AND y OR.

Por ejemplo:

```
StatusIcon(green_expression AND
          green_expression,red_expression AND (red_expression OR
      red_expression))
```

El orden de evaluación es AND y luego OR. Las operaciones entre paréntesis se evalúan primero.

## Tipo de retorno

Serie

## Observaciones

Sólo se pueden utilizar expresiones simples, iguales a las utilizadas en [IF](if.htm "(se abre en una pestaña o una ventana nueva)").

## Ejemplo

Supongamos el siguiente ejemplo:

`StatusIcon(CostPerGB<2,CostPerGB>3)`

Vuelve:

- Verde si CostPerGB es inferior a 2.
- Rojo si CostPerGB es superior a 3.
- Amarillo si CostPerGB está entre 2 y 3.

Dado que ambas expresiones no pueden ser verdaderas, esta función nunca puede devolver azul.

Si CostPerGB no existe, la función devuelve gris.

**Véase también** : [Icono](icon.htm "(se abre en una pestaña o una ventana nueva)")
