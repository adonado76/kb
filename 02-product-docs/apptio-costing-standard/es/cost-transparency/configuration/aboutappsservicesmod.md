---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Acerca de la configuración del módulo de aplicaciones y servicios"
breadcrumb: []
source_path: "cost-transparency/configuration/aboutappsservicesmod.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Acerca de la configuración del módulo de aplicaciones y servicios

El módulo de aplicaciones y servicios se utiliza para asignar los costes de las torres de recursos informáticos a la infraestructura asociada y, en última instancia, a la tabla de aplicaciones y servicios. Los informes resultantes pueden utilizarse para obtener información sobre el gasto de la cartera de aplicaciones y servicios. El módulo de Aplicaciones y Servicios es un requisito previo para el módulo de Unidades de Negocio. Para configurar el Módulo de Aplicaciones y Servicios, instale los componentes de CT Apps.

Se aplica a: Costing Standard en TBM Studio 12.0 y posteriores

## Personalizado

A diferencia del módulo Costing Standard Foundation, el módulo Aplicaciones y Servicios suele personalizarse para adaptarse a los datos disponibles en una organización. Las descripciones de los datos y la configuración de los módulos Aplicaciones y Servicios deben tomarse como una forma de configurar los componentes. La configuración final de los componentes puede ser diferente.

## Requisitos de configuración para el módulo de aplicaciones y servicios

El módulo Costing Standard Foundation (CTF) es un requisito previo para el módulo Aplicaciones y servicios. Una vez completada y validada la instalación del módulo CTF, puede empezar a utilizar el módulo de aplicaciones y servicios asignando partes de los gastos de la torre de recursos de TI directamente a la tabla de datos maestros de aplicaciones en función de reglas básicas. Sin embargo, a medida que se obtienen más datos sobre la infraestructura y se dispone de relaciones para asignar de forma defensiva el gasto de la infraestructura a las aplicaciones de apoyo, es probable que se opte por empezar a introducir los datos en la aplicación y proporcionar poco a poco un modelo de costes más defendible.

## Componentes del módulo

Los componentes Aplicaciones y Servicios no se instalan automáticamente al crear un proyecto Costing Standard . Debe instalar cada componente por separado. Puede instalar cualquier combinación de los componentes. No dependen unos de otros.

El Módulo de Aplicaciones y Servicios CT incluye los siguientes componentes:

- CT Apps - Aplicaciones
- CT Apps - Comunicación
- CT Apps - Centros de citas
- Aplicaciones CT - Dispositivos de usuario final
- Aplicaciones CT - Mainframes
- CT Apps - Red
- CT Apps - Servidores
- CT Apps - Componente de servicios
- CT Apps - Componente Service Desk
- CT Apps - Componente de almacenamiento

| Si modificaste este archivo no maestro: | Debe añadir los datos a este fichero maestro: |
| --- | --- |
| Lista de torres de recursos informáticos | Datos maestros de la torre de recursos informáticos |
| Objetivos de utilización de servidores | Servidores Datos maestros |
| Objetivos de utilización del almacenamiento | Datos maestros de almacenamiento |
| El almacenamiento fija objetivos de utilización | Dispositivos de almacenamiento Datos maestros |

## Instalar los componentes

Los componentes del módulo de aplicaciones y servicios se instalan siguiendo los mismos pasos que para la instalación de los componentes del módulo CTF. El orden de instalación de los componentes es indiferente.

1. Haga clic en la pestaña Proyecto.
2. Haga clic en Componentes en la cinta de opciones.
3. Haga clic en uno de los componentes CT.
4. Pulse Instalar.
5. Haga clic en Ver todos los componentes.
6. Repita los pasos 4 a 6 para el resto de componentes del TC.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
