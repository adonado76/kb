---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Promoción a producción y primera ejecución completa del estándar de facturación"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/promote-bill.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Promoción a producción y primera ejecución completa del estándar de facturación

Después de facturar, se validan el contenido estándar y el comportamiento del punto final en Staging:

1. **Bloqueo de preparación**
   - Evita nuevos registros y mantén estable la compilación probada.
2. **Ejecutar el control de calidad final en Staging.**
   - Confirmar:
     - Todos los principales servicios y consumidores tienen cargos.
     - Los informes de dominio se rellenan según lo esperado.
     - La varianza y los resultados de la tasa unitaria parecen razonables.
3. **Promocionar la compilación a producción**
   - Promocionar la versión validada del proyecto Costing Standard.
   - Esto también actualiza eficazmente el contenido del punto final del estándar de facturación.
4. **Ejecutar modelos estándar de facturación en producción**
   - Ejecutar modelos de facturación para el período objetivo en Producción.
   - Validar:
     - Resultados básicos y específicos.
     - Informes clave para el período.
5. **Abre el punto final del estándar de facturación para dirigirte a tu público objetivo.**
   - Confirme que:
     - Los usuarios previstos pueden ver el punto final.
     - Los informes se generan correctamente.

Los filtros de seguridad funcionan según lo previsto.
