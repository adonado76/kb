---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Ejecutar el cálculo del estándar de facturación en Desarrollo/Puesta en escena"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/run-bill.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Ejecutar el cálculo del estándar de facturación en Desarrollo/Puesta en escena

Una vez que se hayan establecido los dominios maestros, las unidades, los precios y las asignaciones, se podrá probar el cálculo del estándar de facturación.

Pasos:

1. **Ejecutar modelos de facturación en desarrollo**
   - Ejecutar los modelos principales de la norma de facturación:
     - Servicios y consumidores.
     - Modelos específicos de dominio (nube, aplicaciones, infraestructura, proyectos).
     - Modelos de precio y varianza, si están configurados.
2. **Inspeccionar los resultados clave**
   - Compruebe:
     - Tablas de cargos básicos (servicios × consumidores).
     - Vistas de dominio (nube, servidores, almacenamiento, dispositivos, aplicaciones, proyectos).
     - Tablas de varianza y tablas de tasas unitarias.
3. **Publicar y probar informes en Desarrollo.**
   - Abrir informes representativos de facturación estándar para:
     - Gastos generales.
     - Al menos un dominio (por ejemplo, nube o aplicaciones).
     - Se utilizaron las vistas de tasa unitaria y varianza.
4. **Pasar a la fase de prueba para realizar un control de calidad completo.**
   - Después de la validación inicial, registre los cambios.
   - Validar con datos más completos en Staging:
     - Vuelva a ejecutar los modelos de facturación.
     - Ejecutar informes de control de calidad y excepciones.
     - Validar las opiniones de las partes interesadas clave (responsables de la nube, propietarios de aplicaciones, equipos de infraestructura, finanzas).
