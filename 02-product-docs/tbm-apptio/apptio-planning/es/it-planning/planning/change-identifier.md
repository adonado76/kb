---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Cambiar identificadores"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/change-identifier.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Cambiar identificadores

La función Identificadores de cambio permite a los administradores actualizar los identificadores del sistema (códigos) utilizados por las dimensiones de datos de referencia, como centros de coste, cuentas, proyectos y departamentos.

Nota: Para cambiar los identificadores se requieren roles de administrador o responsable del proceso presupuestario.

Los identificadores actúan como claves únicas orientadas al sistema que Planning utiliza para hacer referencia y conectar datos entre planes, importaciones, API e integraciones. Mientras que los nombres descriptivos están orientados al usuario y pueden cambiar, los identificadores proporcionan estabilidad y coherencia.

## Comportamiento importante

- Cambiar un identificador no actualiza el nombre que se muestra del valor de la dimensión.
- Los planes existentes, independientemente de su estado (nuevo, abierto o final), se reasignan automáticamente al nuevo identificador.
- Los identificadores deben ser únicos dentro de la dimensión.

## Dimensiones compatibles

La función Identificadores de cambio se aplica a la mayoría de las dimensiones estándar y personalizadas, incluidas:

- Cuenta
- Centro de costes
- Departamento
- Tipo de actividad laboral
- Ubicación
- Proyecto
- Grupo de proyecto
- Función laboral del proyecto
- Controlador de varianza
- Proveedor
- Dimensiones personalizadas

## Cómo cambiar los identificadores

**1. Exportar la plantilla de identificadores de cambios**

1. Vaya a **Configuración** → **Datos de referencia**.
2. Seleccione la dimensión que desea actualizar.
3. Abre los **puntos suspensivos (...) menú** y seleccione **Plantilla de identificadores**.
4. Exporta la plantilla de identificadores como un archivo CSV.

**2. Actualizar los identificadores**

En el CSV exportado:

- Deje intactos los registros **de código** existentes.
- Actualice la columna **Nuevo código** con los nuevos códigos que desea aplicar.
- **No** modifique los valores que no desee cambiar.

**3. Importar la plantilla actualizada**

1. Abre los **puntos suspensivos (...) menú** y seleccione **Cambiar identificadores**.
2. Importa el archivo CSV actualizado.
3. Revise los resultados de la validación.

**4. Revisar y aplicar los cambios**

Si todo parece correcto, confirme el cambio.
