---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Configuración de la nube para el cálculo de costes estándar 12.6"
breadcrumb: []
source_path: "cost-transparency/configuration/ctconfig12_6.html"
images:
  - "resources/images/ct_images/10550_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configuración de la nube para el cálculo de costes estándar 12.6

Apptio permite a los responsables de TI gestionar y optimizar de forma proactiva el consumo de nubes públicas y tomar decisiones más informadas sobre el uso y la compra de nubes con análisis en tiempo real para supervisar el gasto y otros costes asociados, como los de mano de obra y asistencia.

Se aplica a: Costing Standard en TBM Studio 12.6 y posteriores, con Plantilla v106 y posteriores.

**NOTA** : Para obtener instrucciones aplicables a versiones de Costing Standard anteriores a 12.6, consulte [Configuración de Nube para el cálculo de costes estándar 12.1 a 12.5x](cloudservices-12-5.html "Utilice el componente CTF - Cloud Service Provider para importar datos de uso de servicios web. El componente es opcional.").

## Antes de empezar

Para que los costes de la nube se calculen correctamente, los datos del proveedor deben introducirse en la aplicación Costing Standard . Los datos del proveedor identifican los costes procedentes de los servicios web y los asignan a los servicios en nube. El modelo que figura a continuación muestra la relación.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/10550_1.png)

## Acerca de esta tarea

Si utiliza Amazon Web Services ( AWS ), Microsoft Azure, SoftLayer, o CenturyLink, puede importar los datos de uso de los informes mensuales de uso y facturación. Los datos se utilizan en los informes CTF y en los informes de aplicaciones y servicios. Los datos pueden ayudarle a comparar el coste de los servicios en nube con el de los servicios internos. Para utilizar los datos de los servicios web, debe instalar el componente CTF - Cloud Service Provider.

Los siguientes componentes opcionales importan datos de uso de servicios web:

- CTF - Proveedor de servicios en nube
- CTF - Amazon Web Services
- CTF - Azure
- CTF - Gestión de empresas en la nube

Apptio Costing Standard en TBM Studio 12.6 y posteriores incluye la capacidad de importar informes mensuales de uso y facturación de datos en la nube. Los datos se utilizan en los informes de Costing Standard , que permiten comparar el coste de los servicios en nube con los servicios internos.

## Paso 1 - Instalar el componente Proveedor de Servicios en la Nube

### Procedimiento

1. Abra el proyecto Costing Standard .
2. Haga clic en la pestaña **Proyectos**.
3. Haga clic en **Componentes** en la cinta.
4. Haga clic en el componenteCTF **- Proveedor de servicios en la nube**.
5. Haga clic en **Instalar**.

### Resultados

Al instalar el componente Proveedor de servicios en la nube:

- Se añade un objeto Proveedor de servicios en nube al modelo de costes.
- Los siguientes conjuntos de datos se crean en la categoría Proveedor de servicios en nube:
  - Cloud Service Provider Lookup Master Data se utiliza para asignar los tipos de uso de su organización a los tipos de uso de Apptio.
  - Los datos maestros del proveedor de servicios en nube se utilizan para asignar los datos de facturación de los servicios en nube a los informes de nube de Apptio.
- Los siguientes conjuntos de datos se crean en la categoría z\_Cloud Service Provider Configuration:
  - Proveedor de servicios en nube Apptio Lookup enumera los tipos de uso de servicios en nube de Apptio.
  - Provider Lookup enumera los tipos de uso de los servicios en la nube de su organización.
- Se crean los siguientes informes CBM:
  - Resumen del proveedor de servicios en nube
  - IT Finance - Resumen del proyecto de ley sobre proveedores de servicios en nube
  - Gestión de TI - Proveedor de servicios en nube
  - Gestión de TI - Proveedor de servicios en la nube - Detalle
