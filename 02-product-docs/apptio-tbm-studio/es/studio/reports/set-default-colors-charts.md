---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Definir los colores por defecto de las métricas en los gráficos"
breadcrumb: []
source_path: "studio/reports/set-default-colors-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Definir los colores por defecto de las métricas en los gráficos

**Se aplica a** : TBM Studio 12.0 y posteriores

Utilice la propiedad **Color Spec** para cambiar los colores por defecto de las métricas en todos los gráficos o en un único gráfico.

- Para todos los gráficos, utilice la propiedad **Color Spec** para proyectos. Acceda a la propiedad haciendo clic en **Configuración del proyecto** en la pestaña **Proyecto**.
- Para un gráfico individual, utilice la propiedad **Color Spec** en la pestaña **Gráfico** del cuadro de diálogo **Propiedades**.

Puede especificar colores alternativos para las métricas introduciendo una cadena **Color Spec** con el siguiente formato:

> `metric=color-spec[;metric=color-spec]`

Los elementos de la cadena se describen a continuación.

**métrica** - Cualquier métrica del gráfico tal y como aparece su nombre en la leyenda del gráfico. No se admiten asteriscos.

**Color Spec** - Una cadena que describe el color. Las cadenas de color válidas son:

- **Colores planos** : negro, gris, gris claro, gris oscuro, blanco. "Transparente" también es compatible y hará que una barra o línea sea invisible.
- **Colores degradados** : azul, rojo, verde, amarillo, violeta, marrón, azul cielo, verde claro, naranja, azul oscuro, verde oscuro, morado, aguamarina, rosa, verde azulado, carmesí.
- También puede anteponer el prefijo **flat** a cualquiera de los colores degradados para obtener una versión sin degradado, por ejemplo: **flatblue**.
- Un signo de exclamación (! ) delante de una especificación de color indica que la especificación de color siguiente no debe utilizarse en ninguna parte del gráfico.

Puede especificar varias Espec. de color separándolas con punto y coma (; ) como en el siguiente ejemplo:

> `Cost=blue;Budget=green;!purple`

Este ejemplo especifica: El coste es azul, el presupuesto es verde y no se utiliza el morado.

Sólo se admite una métrica por color. Si establece dos métricas con el mismo color, sólo la primera métrica utilizará el color seleccionado.

Los códigos de color hexadecimales (por ejemplo, #ff55ff ) son válidos, al igual que las palabras clave de color. Por ejemplo, para especificar azul para la métrica Coste:

> `Cost=#082f6d`

A continuación se muestran los colores disponibles:

| Color | Muestra | Color | Muestra | Color | Muestra |
| --- | --- | --- | --- | --- | --- |
| blue | imagen | púrpura | imagen | negro | Negro |
| rojo | imagen | azul claro | imagen | gris | Gris |
| verde | imagen | rosa | imagen | gris claro |  |
| amarillo | imagen | verde agua | imagen | gris oscuro | Gris oscuro |
| violeta | imagen | carmesí | imagen | blanco | Blanco |
| marrón | imagen | naranja | imagen |  |  |
| azul cielo | imagen | azul oscuro | imagen |  |  |
| verde claro | imagen | verde oscuro | imagen |  |  |

## Paleta de colores personalizada

**Se aplica a** : 12.10.10 y posteriores

El valor del campo Color Spec es el valor primario y no puede ser anulado por la paleta de colores personalizada que se elija para el informe.

Para saber más, consulte [Paleta de colores personalizada](../admin/color-enhancement.html).
