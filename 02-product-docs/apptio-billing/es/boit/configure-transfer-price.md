---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Configurar los precios de transferencia"
breadcrumb: []
source_path: "boit/configure-transfer-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Configurar los precios de transferencia

◆ Se aplica a: Billing Standard en TBM Studio 12.7 y posteriores

Los precios de transferencia se refieren a las normas y métodos para fijar el precio de las transacciones dentro de una misma entidad jurídica y entre entidades jurídicas que comparten la propiedad o el control. Muchas organizaciones multinacionales, especialmente en las industrias de servicios bancarios y financieros, dividen su negocio en entidades jurídicas separadas (por ejemplo, separando las operaciones de banca de inversión de las de banca comercial) entre los países en los que operan.

Cuando los servicios se consumen entre entidades jurídicas, suele aplicarse a esos servicios un precio de transferencia o margen de beneficio. Los analistas financieros de las empresas globales necesitan imputar y asignar con precisión esos costes y precios de servicios entre entidades jurídicas, y ajustar las facturas para cumplir los requisitos de información reglamentaria y de conformidad.

**VER TAMBIÉN** : [Informe de Transferencias Intercompañías y Cobros Cruzados (Precios de Transferencia) - Billing Standard](transfer-pricing-report.html "(se abre en una pestaña o una ventana nueva)")

Requisitos previos

- Instale y configure los siguientes componentes de Billing Standard :
  - Billing Standard Fundación
  - Billing Standard Precio
- Recoge los siguientes datos:
  - Nombres y relaciones entre las entidades jurídicas geográficas, los servicios que prestan y el mecanismo de precios de transferencia utilizado en cada caso
  - Normas fiscales que se aplican al margen de beneficio de los precios de transferencia entre ubicaciones geográficas específicas
  - Un cuadro de normas seguidas por las unidades de negocio de facturación cruzada que residen en la misma entidad jurídica que una entidad jurídica consumidora (para más información, véase el cuadro siguiente)

**Conjuntos de datos y modelos sobre precios de transferencia**

En la configuración se utilizan los siguientes conjuntos de datos:

- **Datos maestros de precios de transferencia entre empresas** - Este conjunto de datos utiliza datos de clientes que definen las tasas de recargo de los precios de transferencia entre entidades jurídicas específicas.
- **Inter Company Transfer Pricing** - Esta es la versión modelada de los Datos Maestros de Precios de Transferencia entre Empresas.
- **Datos maestros de tributación de** entidades jurídicas - Este conjunto de datos utiliza datos de clientes que definen los tipos impositivos de recargo de precios de transferencia entre entidades jurídicas específicas.

Los siguientes modelos se crean con el caso de uso de precios de transferencia. Las flechas rojas indican el origen de los conductores.

Configurar los precios de transferencia

1. Cargue los siguientes conjuntos de datos:   

   | Conjunto de datos | Caso de uso | Descripción | Columnas clave |
   | --- | --- | --- | --- |
   | Precios de transferencia | Precios de transferencia, precios de transferencia con fiscalidad | Define los porcentajes de recargo de los precios de transferencia entre entidades jurídicas y, en algunos casos, servicio por servicio | Persona jurídica proveedora, Ubicación proveedora, Servicio (opcional), Persona jurídica consumidora, Ubicación consumidora, Tasa de recargo (por ejemplo, introduzca 0.15 para un recargo del 15%) |
   | Precios de transferencia Tipos impositivos | Precios de transferencia con fiscalidad | Define los tipos impositivos del recargo de precios de transferencia entre entidades jurídicas y, en algunos casos, servicio por servicio | Entidad jurídica proveedora, ubicación proveedora, servicio (opcional), entidad jurídica consumidora, ubicación consumidora, tipo impositivo de recargo (por ejemplo, introduzca 0.15 para un tipo impositivo del 15%) |
2. Añada los conjuntos de datos a los conjuntos de datos maestros correspondientes.
3. Verificar que las métricas modeladas fluyen correctamente desde los Precios de Transferencia entre Compañías, a través de las Unidades de Negocio, hasta las Entidades Legales y los Cargos Cruzados.
