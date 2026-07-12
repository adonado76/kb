---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Componente CTF Vendors: instalar y configurar"
breadcrumb: []
source_path: "cost-transparency/configuration/ctfvendors.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Componente CTF Vendors: instalar y configurar

Para configurar los proveedores, instale el componente CTF-Vendors y cargue los datos del archivo de datos maestros de proveedores de su organización. El componente CTF-Vendors no se instala automáticamente con el proyecto estándar Costing Standard . Los datos para rellenar la tabla de datos maestros de proveedores en la aplicación Costing Standard suelen proceder del archivo de datos maestros de proveedores de la aplicación financiera de su organización, como Oracle Financials o SAP ERP Financials.

## Acerca de las llaves

Las claves de la tabla de datos maestros de proveedores están predefinidas y no deben modificarse.

| Clave | Basado en | Lógica |
| --- | --- | --- |
| Coste Fuente\_Vendedor Clave | ID de proveedor  Coste Fuente Clave  Metafield | Añada el texto CS\_Vendor al campo ID de proveedor y al metacampo Clave de fuente de coste. |
| Clave Vendor\_ITRT | Vendedor CSP KeyIT Recurso TowerIT Recurso Subtorre | IF Vendor\_CSP Clave = Vendor\_CSP\_null THEN Añada el texto Vendor\_ITRT con IT Resource Tower y IT Resource Sub-tower ELSE Establecer el texto en Vendor\_ITRT\_null |
| Clave Vendor\_CSP | ¿Es CSP  Nombre de distribuidor | IF Es CSP = sí THEN Añada el texto Vendor\_CSP con el nombre del proveedor ELSE Establecer el texto en Vendor\_CSP\_null |

## Instalar el componente

El componente CTF - Vendedores no se instala con el proyecto estándar Costing Standard .

Para instalar el componente CTF - Vendedores:

1. Abra el proyecto Costing Standard .
2. Haga clic en la pestaña **Proyecto**.
3. Haga clic en **Componentes** en la cinta de opciones.
4. Haga clic en el componente **CTF - Proveedores**.
5. Haga clic en **Instalar**.

## Fuentes de datos habituales

Las cifras de los proveedores suelen extraerse de un libro mayor.

## Carga

Normalmente, se carga una única tabla de proveedores que se anexa a la tabla de Datos maestros de proveedores. El conjunto de datos debe contener campos que puedan asignarse a los campos apropiados de la tabla Datos maestros del proveedor.

## Completar el conjunto de datos maestros

Existe un conjunto de datos maestros asociado al componente CTF - Proveedores: Datos maestros de proveedores

## Campos obligatorios y recomendados

A continuación se enumeran los campos obligatorios y recomendados necesarios para iluminar los informes estándar de proveedores.

- Es CSP (obligatorio)
- Subpotencia de recursos informáticos (obligatorio)
- Torre de recursos informáticos (obligatorio)
- Función del proveedor (obligatorio)
- ID de proveedor (obligatorio)
- Gestor de proveedores (recomendado)
- Nombre del proveedor (obligatorio)
- Servicio de proveedores (recomendado)
- Tipo de proveedor (obligatorio)

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
