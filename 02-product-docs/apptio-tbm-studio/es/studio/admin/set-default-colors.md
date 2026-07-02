---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Establecer los colores por defecto para las métricas del proyecto"
breadcrumb: []
source_path: "studio/admin/set-default-colors.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Establecer los colores por defecto para las métricas del proyecto

**Se aplica a** : TBM Studio 12.0 y posteriores

Utilice la propiedad **Color Spec** para cambiar los colores por defecto de las métricas de un proyecto.

- Para todos los gráficos, utilice la propiedad Color Spec en el cuadro de diálogo Editar configuración del proyecto. Acceda al cuadro de diálogo haciendo clic en Definición en la pestaña Proyecto.
- Para un gráfico individual, utilice la propiedad **Color Spec** en la pestaña **Gráfico** del cuadro de diálogo **Propiedades** del gráfico.

Para acceder a la propiedad, en la pestaña **Proyecto**, en el grupo **Configuración de página**, haga clic en **Configuración del proyecto.** Puede especificar colores alternativos para las métricas introduciendo una cadena **Color Spec** con el siguiente formato:

`metric=color-spec[;metric=color-spec]`

Los elementos de la cadena se describen a continuación.

- **métrica** - Cualquier métrica del gráfico tal y como aparece su nombre en la leyenda del gráfico. No se admiten asteriscos.
- **Color Spec** - Una cadena que describe el color. Las cadenas de color válidas son:
  - **Colores planos** : negro, gris, gris claro, gris oscuro, blanco. "Transparente" también es compatible y hará que una barra o línea sea invisible.
  - **Colores degradados** : azul, rojo, verde, amarillo, violeta, marrón, azul cielo, verde claro, naranja, azul oscuro, verde oscuro, morado, aguamarina, rosa, verde azulado, carmesí.
  - También puede anteponer el prefijo **flat** a cualquiera de los colores degradados para obtener una versión sin degradado, por ejemplo: **flatblue**.
  - Un signo de exclamación (! ) delante de una especificación de color indica que la especificación de color siguiente no debe utilizarse en ninguna parte del gráfico.

Puede especificar varias Espec. de color separándolas con punto y coma (; ) como en el siguiente ejemplo:

`Cost=blue;Budget=green;!purple`

Este ejemplo especifica: El coste es azul, el presupuesto es verde y no se utiliza el morado. Sólo se admite una métrica por color. Si establece dos métricas con el mismo color, sólo la primera métrica utilizará el color seleccionado. Puede utilizar códigos hexadecimales para especificar los colores. Por ejemplo, para especificar azul:

`Cost=#082f6d`
