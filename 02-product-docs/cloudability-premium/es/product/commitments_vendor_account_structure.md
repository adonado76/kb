---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Estructura de cuentas por proveedor"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Comprender los conceptos básicos de la gestión de compromisos en Cloudability"
source_path: "product/commitments_vendor_account_structure.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Estructura de cuentas por proveedor

## Finalidad

El objetivo de este documento es llevar la jerarquía de cuentas en la nube al plano práctico. Es fundamental comprender cómo afecta la estructura de las cuentas al reparto de compromisos, la visibilidad y la elaboración de informes a través de Cloudability Commitments. Si aún no lo ha hecho, revise las definiciones formales de cuenta en [Cómo difiere la gestión de compromisos entre proveedores de servicios en la nube](commitment_management_across_providers.html).

## Por qué la estructura de las cuentas afecta a los compromisos

Los beneficios del compromiso fluyen según los ámbitos específicos del proveedor (org, perfil de facturación, proyecto, región/AZ). Cloudability mapea estas jerarquías:

- Calcule correctamente los KPI en los distintos niveles de relevancia.
- Recomendar compras en el límite de reparto correcto en función de las preferencias.
- Proporcionar a nuestros usuarios la capacidad de acreditar correctamente sus cuentas para extraer sistemáticamente los datos adecuados necesarios.

No acreditar y configurar correctamente las preferencias puede dar lugar a suposiciones y recomendaciones incorrectas que podrían conducir a un informe incorrecto o, lo que es peor, a una compra errónea. Además, las API públicas rara vez proporcionan preferencias de uso compartido de forma sistemática. Esto requiere una introducción manual para garantizar que tanto la cartera como las recomendaciones se ajustan a cómo se aplican realmente los descuentos.

## Cómo Cloudability asigna las jerarquías de sus cuentas

Cloudability ingiere los metadatos del proveedor y los normaliza en función de algunas ideas básicas utilizadas en toda la aplicación.

**Cuenta Pagadora** - Es el titular de la factura y el lugar común donde se suelen facturar formalmente los compromisos. Tenga en cuenta que a menudo el compromiso puede adquirirse a nivel de pagador o de cuenta vinculada. Si la opción de compartir está activada, el compromiso se compartirá normalmente entre las cuentas vinculadas del pagador.

**Cuenta vinculada -** Donde se ejecutan y utilizan los recursos.

En cuanto al producto, nuestro objetivo es ofrecer una selección de cuentas jerárquica y multiselección en todas las páginas. Aunque en el momento de escribir estas líneas aún no disponíamos de esta funcionalidad, tenemos previsto cumplir nuestro compromiso. Por ahora, la dirección de las páginas es la siguiente:

**Gestor de compromisos** : agrega datos de todas las cuentas de proveedores. Permite la selección múltiple. Tanto para los datos reales (históricos) como para los previstos (futuros), la selección de cuentas actúa como un selector de uso.

**Cartera de compromisos** - Muestra resúmenes por tipo y detalles por cuenta/suscripción/proyecto.

**Recomendaciones de Compromiso** - Respeta su intención de compartir (org wide vs. scoped) y los filtros de cuenta.

## AWS

*Estructura de la cuenta*

**Cuenta de gestión (pagador** ) - Recibe la factura consolidada; a menudo es la cuenta de compras de los RI/planes de ahorro.

**Cuentas de los miembros (vinculadas)** - Donde se ejecutan los recursos y se generan los costes.

**Unidades organizativas (UO)** : "carpetas" jerárquicas para políticas y gobernanza (no contenedores de facturación). No es de especial interés para los compromisos.

*Comportamiento compartido*

El reparto de compromisos es un ajuste a nivel de organización. Cuando se activa esta opción, los descuentos pueden aplicarse automáticamente a todas las cuentas de los miembros, independientemente de la ubicación de la OU.

La compartición de regiones es relevante para los compromisos en los que las cargas de trabajo y el compromiso se despliegan y adquieren en la región o zona de disponibilidad

## Azure

*Estructura de la cuenta*

**Cuenta de facturación** (EA/MCA) - Construcción de contrato de nivel superior.

**Perfil de facturación** (MCA) - Propietario de la factura; a menudo su límite de reparto principal.

**Sección de facturas** (MCA) - Cubos de subfacturas utilizados para asignaciones/visualizaciones.

**Suscripción** - Contenedor de recursos y unidad de facturación.

*Comportamiento compartido*

El ámbito compartido aplica las prestaciones en todo un contexto de facturación (por ejemplo, inscripción en EA o perfil de facturación / sección de factura de MCA)

La suscripción única o el grupo de recursos único limitan las prestaciones a ese ámbito

## GCP

*Estructura de la cuenta*

**Cuenta de facturación** - Donde se gestionan los compromisos y los abonos; propietario de la factura.

**Proyecto** - Contenedor de recursos donde se ejecutan las cargas de trabajo y se generan los costes.

*Comportamiento compartido*

Es necesario activar el uso compartido en la consola de GCP. Se gestiona a nivel de Cuenta de Facturación.

La región es relevante para los CUD de recursos de la CME y algunos CUD de gastos, como los CUD de SQL en la nube.

## Sugerencias

1. Acredite primero las cuentas de pagador correctas; confirme las cuentas vinculadas y revise cualquier permiso especial por servicio.
2. Establezca la configuración de uso compartido de su cuenta por pagador en las preferencias de compromiso para garantizar que se establezca por defecto la configuración de uso compartido correcta en las recomendaciones.
3. Verifique que la compartición está activada a nivel del pagador antes de confiar en la cobertura de toda la organización en Portfolio.
4. Confirme los ajustes de uso compartido y establézcalos en las preferencias de compromiso.
5. Compruebe periódicamente estos ajustes.

## Conclusiones

La estructura de la cuenta es crucial para el correcto funcionamiento en Cloudability Compromisos. Asegúrese de que las cuentas tengan las credenciales correctas y de que las preferencias de uso compartido estén configuradas de forma que las funciones de compromiso funcionen correctamente.

**Tema principal:** [Comprender los fundamentos de la gestión de los compromisos en Cloudability](../product/commitment_management_basics.html)
