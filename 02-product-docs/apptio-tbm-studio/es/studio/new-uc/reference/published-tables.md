---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tablas publicadas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Data Studio Referencia"
source_path: "studio/new-uc/reference/published-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tablas publicadas

## Visión general

Las tablas publicadas ofrecen un mecanismo específico para exportar datos desde TBM Studio sin necesidad de utilizar informes.

**Ventajas:**

- No es necesario gestionar los permisos de los informes
- La exportación estará disponible inmediatamente después de que finalice el cálculo de desarrollo
- Definiciones de exportación localizables y fáciles de mantener
- Independiente de la interfaz de TBM Studio

## Creación de tablas publicadas

**Método 1: Crear uno nuevo**

1. Ve a la pestaña Inicio > Nuevo
2. Seleccionar tabla publicada
3. Introduce el nombre y la categoría
4. Haz clic en Aceptar

**Método 2: A partir de una tabla de informes existente**

1. Abrir informe con la tabla de origen
2. Haz clic con el botón derecho del ratón en la tabla del informe
3. Selecciona «Crear tabla publicada»
4. Introduce el nombre y la categoría

## Configuración del precálculo

|  |  |
| --- | --- |
| **Valor** | **Descripción** |
| Activo (marcado) | El sistema precalcula la tabla; lista al realizar la llamada a la API (por defecto) |
| Inactivo (sin marcar) | El sistema realiza el cálculo en la primera solicitud de API |

**Tema principal:** [Referencia de « Data Studio »](../../../studio/new-uc/reference/data-studio-reference.html)
