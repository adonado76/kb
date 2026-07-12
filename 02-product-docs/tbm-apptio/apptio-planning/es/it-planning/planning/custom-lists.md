---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Listas personalizadas"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/custom-lists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Listas personalizadas

Nota: *Para gestionar listas personalizadas se requieren roles de administrador o responsable del proceso presupuestario.*

Las listas personalizadas permiten a los administradores definir un conjunto de valores permitidos para un único atributo en una tabla de partidas individuales. Se utilizan habitualmente para estandarizar la introducción de datos, por ejemplo, creando una lista *de estados* con valores como «Seleccionado», «Entrevistado» y «Contratado» para su uso en partidas de mano de obra.

## Crear una lista personalizada

1. Vaya a **Configuración** → **Listas personalizadas**.
2. Selecciona **Añadir** (➕).
3. Introduzca un **nombre** para la lista.

   Nota: Los nombres de las listas no se pueden cambiar posteriormente.
4. En la sección **Valores**, haga clic en **Añadir** (➕) para introducir los valores.
5. Utiliza el controlador de arrastre (⋮⋮) para reordenar los valores, o selecciona **Eliminar** (🗑) para eliminarlos.
6. Cuando haya terminado, haga clic en **Añadir** para finalizar la lista.

## Uso de listas personalizadas en esquemas de partidas individuales

Las listas personalizadas se utilizan para crear listas de selección de un solo atributo que se pueden añadir a cualquier esquema de partida individual como atributo personalizado.

1. Vaya a **Configuración → Esquema** y seleccione un tipo de esquema.
2. Seleccione **Añadir** para crear un atributo personalizado.
3. Establecer **tipo de datos = Lista**.
4. Seleccione la **lista personalizada** que ha creado anteriormente.
5. Haga clic en **Añadir** para crear el atributo de la lista.

Una vez añadido, el atributo aparecerá como un campo desplegable en la tabla de partidas asociada, lo que garantiza una introducción de datos estandarizada y controlada para los usuarios finales.
