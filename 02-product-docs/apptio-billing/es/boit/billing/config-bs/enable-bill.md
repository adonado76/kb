---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Habilitar el punto final del estándar de facturación y el acceso a los informes"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/enable-bill.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Habilitar el punto final del estándar de facturación y el acceso a los informes

Una vez validado el contenido en Staging, se pueden preparar el punto final y los informes para los usuarios.

Pasos:

1. **Confirmar enlace del punto final estándar de facturación**
   - Asegúrese de que el punto final apunte al proyecto y los entornos correctos de Costing Standard.
2. **Promocionar los informes requeridos en el punto final.**
   - Decida qué colecciones de informes están incluidas en el alcance de la puesta en marcha:
     - Servicios y consumidores.
     - Nube.
     - Aplicaciones.
     - Infraestructura.
     - Proyectos.
     - Variación / precios.
     - Revistas.
     - Publícalos y clasifícalos adecuadamente.
3. **Configurar el acceso a los informes**
   - Alinear el acceso a los informes con las funciones:
     - Administradores y analistas: acceso amplio.
     - Propietarios de servicios o productos: vistas relevantes para sus dominios.
     - Finanzas: informes de tasa unitaria, varianza y diario.
4. **Prueba de humo del punto final**
   - Inicie sesión con un perfil de usuario típico.
   - Confirmar:
     - Informes abiertos y respuestas.
     - Los filtros y los desgloses funcionan.

La seguridad funciona como se espera.
