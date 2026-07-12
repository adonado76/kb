---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Comunicaciones: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestructura"
  - "Comunicaciones"
source_path: "cost-transparency/infra-use-cases/comm-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Comunicaciones: Introducción

El componente de comunicaciones permite a las organizaciones asignar los costes de infraestructura de comunicaciones, como circuitos, servicios de voz y cargos basados en el uso, a los consumidores correspondientes. Permite una asignación transparente y justificable del gasto en comunicaciones a aplicaciones, servicios y unidades de negocio, lo que ayuda a establecer con precisión el coste total de propiedad (TCO) de las aplicaciones y los servicios.

## Instalación de componentes

**Aplicaciones CT – Comunicaciones**

El componente Comunicaciones instala un nuevo objeto Comunicaciones, que admite conjuntos de datos y lógica de asignación utilizados para distribuir los costes de comunicación a los servicios que los consumen. Permite asignar los costes de comunicación a los servidores que dan soporte a los centros de datos, a los dispositivos de los usuarios finales que dan soporte a la conectividad de las oficinas y los trabajadores, y a servicios empresariales específicos, como centros de atención telefónica o quioscos minoristas.

Debe instalar los siguientes componentes antes de instalar el componente Communications:

CTF – Fuente de costes

CTF – Torres de TI

## Fuentes comunes de datos

Los datos sobre los costes y el uso de las comunicaciones suelen obtenerse del libro mayor y de los sistemas de gastos de telecomunicaciones o redes. El nivel de detalle disponible depende de los datos de origen proporcionados y determina cómo se asignan los costes a los datos maestros de comunicaciones para su distribución y presentación de informes.

## Conjuntos de datos

Cuando se instala el componente CT Apps – Communications, se crea un grupo Communications con las siguientes tablas:

Comunicaciones (tabla modelo)

Datos maestros de comunicaciones

Después de cargar los datos de comunicación, asigne la tabla de datos maestros de comunicaciones. Una vez mapeados, los costes fluyen desde las torres de recursos de TI a las comunicaciones, y desde las comunicaciones a los servidores y servicios empresariales dentro del modelo de costes.
