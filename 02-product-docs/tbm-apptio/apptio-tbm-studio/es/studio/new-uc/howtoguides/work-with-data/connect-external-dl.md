---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Conectarse a fuentes de datos externas ( DataLink )"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Importación y gestión de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/connect-external-dl.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conectarse a fuentes de datos externas ( DataLink )

**Objetivo:** Configurar la integración automática de datos entre TBM Studio y los sistemas externos mediante los conectores de DataLink para eliminar la necesidad de cargar archivos manualmente.

**Cuándo utilizar este procedimiento:** Utilice DataLink cuando necesite:

- Automatizar las cargas de datos periódicas (diarias, semanales, mensuales)
- Conéctese a ServiceNow para el intercambio de datos sobre el coste total de propiedad (TCO) de la aplicación
- Extraer datos de los sistemas de la empresa sin intervención manual
- Mantener flujos de datos coherentes sin necesidad de preparar los archivos manualmente

**Requisitos previos:**

- Acceso de administrador a TBM Studio y DataLink
- Datos de acceso para la fuente de datos externa (base de datos de ServiceNow,, etc.)
- Para la aplicación TCO de « ServiceNow: » instalada (versión de Quebec, París u Orlando)
- Para cargas a través de la API: autenticación de la API configurada (véase la sección 3.5.1 )

**Tiempo estimado:** entre 20 y 30 minutos para la configuración inicial; 5 minutos para los cambios en la programación

## Pasos

## Parte 1: Preparación de TBM Studio (integración con ServiceNow )

1. **Configurar informes de TCO en TBM Studio:** Crea los informes que enviarán datos a ServiceNow,, incluidos el informe de TCO de la aplicación (con la composición del grupo de costes) y el TCO de la aplicación (con la composición de la torre de recursos de TI).
2. **Configura las columnas obligatorias** en tus informes:
   - **Modelo de costes:** Configurado como «Cálculo de costes de aplicaciones empresariales»
   - **Ejercicio fiscal:** Utiliza la fórmula = «FY» & CurrentDate("YY" ) & «:» & «&Q» & gettimeoffset(«Quarter», «Start», «Year») + 1
   - **Aplicación empresarial:** Nombre de la aplicación (debe coincidir con la tabla `cmdb\_ci\_business\_app` de ServiceNow )
   - **Importe:** Utiliza la fórmula = QuarterToDate(Cost )
3. **Obtener las URI de la API de los informes:** ve a cada informe, haz clic con el botón derecho del ratón, selecciona «**Mostrar URI de la API** » y copia la URI en formato JSON URL.

## Parte 2: Configurar una conexión c DataLink

1. **Crear una nueva conexión:** Abre DataLink,, haz clic en «**Nueva conexión** », introduce un nombre para la conexión y haz clic en «**Siguiente** ».
2. **Selecciona el conector:** elige **el conector « ServiceNow : Apps & Services TCO Egress»** y haz clic en «**Siguiente** ».
3. **Selecciona un agente:** elige entre el agente basado en la nube (alojado en Apptio, configuración más rápida) o el agente local (mejor rendimiento para los datos locales).
4. **Configurar la autenticación:**

Selecciona el tipo de autenticación: Básica (nombre de usuario/contraseña) o OAuth 2.0 (basada en tokens, solo para agentes en la nube)

**Para la autenticación básica:**

- Introduce una base de datos de ServiceNow URL (por ejemplo, https://, {instance}, service-now.com )
- Introduce tu nombre de usuario y contraseña

**Para la autenticación de OAuth 2.0 :**

- Registra primero DataLink como aplicación cliente en ServiceNow
- Introduce la autorización URL, el token URL, el ID de cliente y el secreto de cliente
- Especificar el ámbito (LECTURA y ESCRITURA o solo LECTURA)
- Haz clic en **«Obtener token de acceso»**
  1. **Introduzca los detalles del informe:** seleccione el servidor BIIT, seleccione los informes, pegue las URL de los informes (en formato JSON) y seleccione el periodo de tiempo.
  2. **Programar la conexión:** elige entre «Programar por hora» (días y horas concretos) o «Programar por evento» (ejecutar una vez finalizada otra conexión).
  3. **Comprueba la conexión:** ejecuta la conexión manualmente para verificar la configuración, revisa los registros en busca de errores y comprueba que los datos aparecen en ServiceNow.

## Resultados previstos

- DataLink La conexión se ha autenticado correctamente en el sistema externo
- Los datos se transfieren automáticamente entre los sistemas según lo programado
- Los datos están disponibles en las tablas de TBM Studio para su uso en modelos e informes
- Los datos sobre el coste total de propiedad (TCO) de « ServiceNow: » aparecen en los paneles de control de « ServiceNow »

## Errores habituales y solución de problemas

**Problema:** La autenticación falla

**Solución:** Verifica las credenciales, vuelve a obtener un token de OAuth si ha caducado y asegúrate de que la cuenta de servicio tenga los permisos necesarios en ambos sistemas.

**Problema:** La conexión funciona, pero no aparecen datos

**Solución:** Comprueba que la URI de la API del informe esté en formato JSON y se haya copiado correctamente; verifica que el periodo de tiempo seleccionado contenga datos; revisa los registros de DataLink.

**Problema:** La conexión programada no se ejecuta

**Solución:** Comprueba la configuración de la programación, verifica el estado del agente y, en el caso de las programaciones basadas en eventos, asegúrate de que se haya completado la conexión de activación.

## ¿Qué viene ahora?

- Supervisar la actualidad de los datos: configurar alertas para datos que faltan o se retrasan (Sección 6.4 )
- [Transformar datos integrados](transform-enrich-data.html) : aplicar transformaciones para normalizar los datos (Sección 3.1.2 )
- Programar compilaciones coordinadas: sincronizar los cálculos del modelo con los calendarios de integración (Sección 6.1 )

**Tema principal:** [Importación y gestión de datos](../../../../studio/new-uc/howtoguides/work-with-data/data-import-mgmt.html)
