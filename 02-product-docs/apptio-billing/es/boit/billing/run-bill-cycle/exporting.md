---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Exportación y publicación de diarios"
breadcrumb:
  - "Billing"
  - "Ejecutar el ciclo de facturación"
source_path: "boit/billing/run-bill-cycle/exporting.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Exportación y publicación de diarios

En el caso de las devoluciones, los resultados de facturación suelen alimentar los sistemas financieros como diarios.

Pasos típicos:

1. **Preparar el conjunto de datos del diario**
   - Utilice un informe o una exportación que contenga:
     - Identificadores de consumidores que coinciden con las estructuras financieras.
     - Asignaciones de segmentos GL o códigos contables.
     - Importes por cuenta, consumidor y período.
     - Cualquier campo de referencia obligatorio, como el tipo de documento o la descripción.
2. **Validar los totales del diario**
   - Confirme que:
     - La suma de los asientos contables coincide con el total de los cargos de facturación.
     - No hay líneas huérfanas con códigos faltantes.
     - Los débitos y los créditos se equilibran si ambos están presentes en la exportación.
3. **Exportar en el formato requerido**
   - Ajuste el orden de las columnas, los nombres de los campos y los tipos de datos para que se ajusten a los requisitos del sistema financiero.
   - Guarde en el formato requerido, normalmente CSV, texto de ancho fijo o un diseño fácil de integrar.
4. **Entregar o cargar a Finanzas**
   - O bien:
     - Proporcione el archivo al departamento financiero para que lo carguen manualmente.
     - Utilice un proceso de integración para enviar directamente las revistas.

1. **Confirmar publicación y rastro**
   - Verifique que:
     - Las revistas se aceptaron sin errores.
     - El sistema financiero muestra los totales previstos por cuenta y consumidor.
     - Capture referencias o identificadores de documentos para auditorías y conciliaciones.

Aunque la organización solo utilice actualmente el showback, puede resultar útil disponer de salidas listas para el diario, de modo que se pueda habilitar el chargeback más adelante sin necesidad de rediseñar el modelo de facturación.
