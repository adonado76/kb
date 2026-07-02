---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Integración de datos de consumo"
breadcrumb:
  - "Billing"
  - "Configuración de los elementos esenciales de facturación (implementación)"
source_path: "boit/billing/config-be/integrate.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Integración de datos de consumo

Los datos de consumo son los que impulsan las unidades en el cálculo de la tasa de consumo ( PxQ ).

Pasos típicos de integración:

1. **Identificar fuentes**
   - Sistemas de gestión de tickets o ITSM (por ejemplo, número de tickets).
   - Sistemas de identidad (usuarios activos).
   - Herramientas de supervisión o medición (capacidad o uso).
   - Hojas de cálculo en las que no existe ningún sistema de registro.
2. **Defina el diseño objetivo.**
   - Cada registro debe incluir:
     - Punto.
     - Identificación del consumidor o una clave mapeable.
     - Ofrecer un identificador o una clave mapeable.
     - Unidades consumidas.
     - Opcionalmente, incluya atributos como entorno, región o centro de costes.
3. **Crear procesos ETL o de carga**
   - Utilice TBM Studio ETL, Datalink o una integración equivalente para cargar datos en la tabla de consumo de facturación.
   - Para feeds pequeños o puntuales, utilice la función «Cargar tabla» y una plantilla controlada de « CSV ».
4. **Ejecutar carga inicial en Desarrollo**
   - Cargue un período de muestra y confirme:
     - Los volúmenes parecen razonables.
     - Las claves hacen coincidir las ofertas y los consumidores.
5. **Promover una lógica de consumo probada**
   - Una vez que los patrones se hayan validado en Desarrollo y Pruebas, pasarlos a Producción.
