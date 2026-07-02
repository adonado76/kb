---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller de servicios a las empresas"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/bsworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller de servicios a las empresas

## Pasos para poblar sus Servicios Empresariales

Llegados a este punto, debe rellenar sus Servicios de empresa con los datos de sus servicios de empresa. Si no dispone de una lista de servicios empresariales, puede utilizar una lista de sus aplicaciones o grupos de aplicaciones. Los pasos siguientes describen cómo rellenar los Servicios Empresariales.

1. Si dispone de una lista de servicios empresariales, puede cargarla en Apptio y colocarla en Servicios a empresas
2. Si no dispone de una lista, puede hacer lo siguiente:
   1. Localizar la lista de referencia de todos los servicios empresariales
   2. Exportar la lista fuera de Apptio
   3. Cargar en una nueva tabla llamada "Cliente" Lista de servicios empresariales
   4. Configure con búsquedas para extraer cualquier información necesaria y añadirla a los servicios empresariales.

## Acerca del identificador de servicio comercial

El identificador del conjunto de datos Todos los servicios empresariales es el ID de servicio. Debe ser un identificador único para cada servicio.

## Acerca de las Claves de los Servicios Empresariales

Las claves del conjunto de datos Todos los servicios empresariales son en su mayoría definidas por el usuario. La lógica recomendada figura en el cuadro siguiente.

| Clave | La clave de campo se basa en | Lógica recomendada |
| --- | --- | --- |
| **Clave App\_Service** | Definida por el usuario | ="App\_Service"&&Identificación del servicio Si utiliza una lista de aplicaciones como sus servicios, la lógica recomendada es:  ="App\_Service"&&Identificación de la aplicación |
| **Clave\_Servicio\_Proyecto** | ID de servicio | ="Servicio\_Proyecto" && ID de servicio |
| **ITRT\_Servicio Clave** | Definida por el usuario | ="ITRT\_Service" && ID de servicio |
| **Service\_Service Allocations Direct Key (En 11.6 )** | Definida por el usuario | ="Service\_Service Allocations Direct Key" && ID de servicio |

## Columnas computadas comunes necesarias para los servicios empresariales

No es necesario crear columnas computadas específicas. Variará en función de sus datos.

## Asignar datos a Todos los datos de servicios empresariales

Cuando publicó la biblioteca de servicios, se rellenó el conjunto de datos Todos los servicios empresariales. En este punto no es necesario asignar ningún dato.

## Revisar el objeto Business Services en los modelos

| Modelo | Acciones |
| --- | --- |
| **Coste** | Asegúrese de que los valores fluyen hacia el objeto Indirecto de Asignación de Servicios. De los Servicios Empresariales a las Asignaciones de Servicio Indirectas, asigne utilizando la Referencia Basada en Datos con una ponderación par (esta es la configuración por defecto). Las claves que unen las Aplicaciones a los Servicios de Negocio son las columnas Clave de ID de Servicio en ambos conjuntos de datos.  De la Asignación indirecta de servicios a la Asignación de unidades de negocio, asigne utilizando un factor de ponderación como el número de personas. |
| **CapEx** | Asegúrese de que los valores fluyen hacia el objeto Indirecto de Asignación de Servicios. De los Servicios Empresariales a las Asignaciones de Servicio Indirectas, asigne utilizando la Referencia Basada en Datos con una ponderación par (esta es la configuración por defecto). Las claves que unen las Aplicaciones a los Servicios de Negocio son las columnas Clave de ID de Servicio en ambos conjuntos de datos.  De la Asignación Indirecta de Servicios a la Asignación de Unidades de Negocio, utilizando un factor de ponderación como el número de empleados. |

## Revisar los informes de los Servicios Empresariales

Los siguientes informes se actualizan después de haber configurado el objeto Business Services:

- Revisión de servicios
- Cartera de servicios
- Lista de servicios
- Categoría de servicio - Detalle
- Detalle de servicio
- Detalle de la oferta de servicios
- Revisión del servicio - Detalle
- Servicios - Grupo Detalle
- Servicios - Evolución del coste unitario
- Cartera de aplicaciones - Detalle - Grupos de costes
- Cartera de aplicaciones - Detalle - IT Towers

Para ver los detalles de estos informes (incluida la navegación, las funciones, los objetivos y las preguntas a las que responde cada informe), consulte la Guía del usuario de Costing Standard disponible en la Ayuda en línea.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
