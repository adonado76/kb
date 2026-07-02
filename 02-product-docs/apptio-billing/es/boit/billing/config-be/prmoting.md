---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Promoción a producción y primera puesta en marcha"
breadcrumb:
  - "Billing"
  - "Configuración de los elementos esenciales de facturación (implementación)"
source_path: "boit/billing/config-be/prmoting.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Promoción a producción y primera puesta en marcha

Una vez que Billing Essentials funcione como se espera en Staging:

1. **Bloqueo de la puesta en escena**
   - Evita que los nuevos registros alteren la compilación de ensayo que se está probando.
2. **Ejecutar el control de calidad final en Staging.**
   - Confirmar:
     - Todas las ofertas requeridas tienen tarifas.
     - Todos los consumidores requeridos tienen cargos.
     - No aparecen valores inesperados cero o negativos donde no deberían aparecer.
3. **Promocionar la compilación a producción**
   - Promocione la compilación de Staging validada a Producción siguiendo el proceso estándar del entorno.
4. **Ejecutar modelos de facturación en producción**
   - Ejecute los modelos de Billing Essentials en producción para el período objetivo.
   - Confirme que los resultados se rellenan correctamente.
5. **Publicar informes dirigidos a públicos específicos.**
   - Asegúrate de que los administradores, analistas y otros roles puedan ver la recopilación de informes de facturación.

Ejecuta una serie final de pruebas de humo en los informes de producción.
