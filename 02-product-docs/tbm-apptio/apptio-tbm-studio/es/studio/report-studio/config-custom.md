---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración y personalización"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
source_path: "studio/report-studio/config-custom.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración y personalización

## Cumplimiento de accesibilidad

El nuevo Report Studio está diseñado para facilitar la accesibilidad y cumple con los estándares de accesibilidad de la sección 508. La experiencia incluye compatibilidad con navegación por teclado, lectores de pantalla y patrones de interfaz de usuario accesibles para garantizar que los usuarios con diversas necesidades de accesibilidad puedan crear y ver informes.

## Localización

El nuevo Report Studio ahora incluye soporte para la localización, lo que permite a los usuarios de todas las regiones disfrutar de una interfaz fluida y coherente en su idioma y formato preferidos.

La siguiente sección explica cómo funciona la localización en diversos aspectos de Report Studio.

- Localización de texto estático: todos los elementos de texto estático (etiquetas, botones, elementos de menú y mensajes) del nuevo Report Studio ahora se pueden localizar.
  - Actualmente, se admite la traducción al japonés.
  - Cuando cambie el idioma de la aplicación a japonés, todo el texto estático de Report Studio aparecerá automáticamente en japonés.
- Datos y configuración: El nuevo Report Studio es totalmente compatible con datos y configuraciones que no estén en inglés.
  - Puede utilizar caracteres que no sean del alfabeto inglés en los nombres de los informes, los filtros o los campos de datos.
  - Las configuraciones, como los nombres de columnas, los filtros o las etiquetas personalizadas, pueden incluir texto localizado sin afectar a la funcionalidad del informe.
- Formato específico de la configuración regional: El formato de números, fechas y otros datos sensibles a la configuración regional sigue automáticamente las convenciones de la configuración regional seleccionada por el usuario.
  - Por ejemplo, los usuarios con la configuración regional japonesa verán los números formateados con comas y marcadores decimales según las convenciones japonesas.
- Gestión de divisas: El nuevo Report Studio admite proyectos con una sola divisa distinta al dólar estadounidense.
  - Los proyectos configurados con una moneda base específica mostrarán todos los valores monetarios utilizando el símbolo y el formato de moneda correspondientes.
  - Ejemplo: un proyecto configurado en yenes japoneses mostrará todos los valores monetarios con el símbolo del yen en todos los informes.

## Configuración multidivisa

Si la función multidivisa está habilitada para su proyecto, los informes se pueden ver y probar en diferentes divisas y tipos de tasa (real o planificada).

**Multidivisa en Report Studio (Admin)**

Los administradores pueden probar los informes en diferentes divisas directamente en Report Studio antes de publicarlos o compartirlos.

¿Cómo cambiar la moneda en Report Studio?

1. Abra el informe en Report Studio.
2. Haga clic en el menú Avanzado.
3. Seleccione Configuración multidivisa.
4. Elija:
   1. Una moneda
   2. Tipo de tasa (real frente a plan)

Cada moneda habilitada admite tanto tipos de tasa reales como planificadas.

El informe se volverá a generar inmediatamente en función de la moneda y el tipo de cambio seleccionados.

**Cuándo utilizar esto**

- Validar la precisión de los informes en todas las divisas
- Plan de pruebas frente a escenarios de tasa real
- Vista previa en otras monedas
- Asegúrese de que el formato y los totales se muestren correctamente

**Multidivisa en el visor de informes (usuarios finales)**

Si el proyecto tiene habilitada la función multidivisa, aparecerá un selector de divisas en el informe del visor de informes.

**Comportamiento predeterminado**

- Los informes se abren en la moneda y el tipo de cambio preferidos por el usuario.
- El informe se genera automáticamente utilizando esa configuración.

**Cambiar la moneda en el visor**

1. Utilice el menú desplegable del selector de moneda en el informe
2. Elija cualquier moneda habilitada
3. Seleccione el tipo de tarifa deseado (real o planificada)

El informe se vuelve a renderizar al instante utilizando la configuración seleccionada.

**Persistencia de sesión**

- La moneda y el tipo de cambio seleccionados se mantienen durante toda la sesión de visualización de divisas del usuario.

**Comportamiento de exportación**

La moneda y el tipo de cambio seleccionados se aplican a las exportaciones:

- **La exportación a PDF** refleja la moneda seleccionada actualmente.
- **La exportación a Excel** (componentes individuales) refleja la moneda seleccionada actualmente.

- **[Pasos para habilitar los informes OOTB modernizados (NX) en una instancia](../../studio/report-studio/ootb-report-pp.html)**  
   de cliente Este documento describe los **pasos necesarios para habilitar los informes OOTB modernizados (New Experience (NX))** en una instancia de cliente. Estos informes ofrecen una mayor claridad, una mejor comprensión y una experiencia más intuitiva, al tiempo que siguen utilizando los **mismos conjuntos de datos que Classic TBM Studio**.
- **[IBM Apptio Guía del Asistente de migración de informes](../../studio/report-studio/migration-assistant.html)**
