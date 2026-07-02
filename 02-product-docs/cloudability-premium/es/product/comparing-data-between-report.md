---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Comparación de datos entre la interfaz de usuario del informe y las exportaciones de CSV"
breadcrumb:
  - "Cloudability Premium"
  - "Datos de referencia"
source_path: "product/comparing-data-between-report.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Comparación de datos entre la interfaz de usuario del informe y las exportaciones de CSV

Cuando exporte sus informes en Cloudability, podrá observar:

- Las unidades de medida de algunas métricas no coinciden entre la interfaz de usuario del informe y los datos exportados de CSV.
- Algunos encabezados de columna no coinciden entre la interfaz de usuario del informe y los datos exportados de CSV.

**Diferencia en las unidades de medida ( UoM ) entre la interfaz de usuario del informe y los datos exportados de CSV**

Los datos exportados en CSV pueden mostrar una unidad de medida diferente para algunas métricas. Para algunas medidas, como los GB y los porcentajes, queremos proporcionar los valores como decimales con toda la precisión disponible y sin formato, de modo que pueda aplicar el formato que desee para usos programáticos y no tenga que intentar "analizar" el formato. Sin embargo, proporcionar estos "números brutos" con precisión decimal completa en la interfaz de usuario del informe haría que la interfaz de usuario fuera menos utilizable.

**Diferencia en los encabezados de las columnas entre la interfaz de usuario del informe y los datos exportados de « CSV »**

Consulta esta tabla para comprender la correspondencia entre los encabezados de las columnas que difieren entre los datos exportados de « CSV » y la interfaz de usuario del informe:

| Encabezado en el archivo « CSV » exportado | Encabezado en la interfaz de usuario del informe | Observaciones |
| --- | --- | --- |
| coste\_facturado | Coste (total combinado) | � |
| tasa\_mezclada | Tasa (combinada) | � |
| coste\_antes\_de\_impuestos | Coste (total sin mezclar antes de impuestos) | � |
| Iops | IOPS Meses | � |
| gb\_meses | GiB/meses | � |
| byte\_horas | GiB/horas | � |
| Mes | Mes (Categoría) | � |
| clave\_servicio | Código del producto | � |
| nombre\_servicio | Nombre de producto | � |
| zona\_región | Zona de disponibilidad | � |
| identificador\_cuenta | ID de la cuenta del pagador | � |
| nombre\_cuenta | Nombre de la cuenta del pagador | � |
| identificador\_cuenta\_proveedor | ID de cuenta | � |
| nombre\_grupo [x] | Grupo de cuentas [x] | x' representa la cardinalidad de los grupos de cuentas (por ejemplo: Grupo de cuentas 1, Grupo de cuentas 2, Grupo de cuentas 3) en su entorno Cloudability. |
| es\_capex | Gastos únicos | � |
| Semana | Semana (Categoría) | � |
| bytes\_transferidos | Transferencia de datos ( GiB ) | � |
| coste\_no\_mezclado | Coste (total) | � |
| tasa\_no\_mezclada | Tasa (sin combinar) | � |
| tasa\_utilización\_reservada | Tasa de cobertura reservada | � |
| identificador\_de\_recursos | ID de recurso | � |
| recuento\_identificadores\_recursos | Recuento de recursos | � |
| coste\_amortizado\_total | Coste (amortizado) | � |
| identificador\_reserva | ID de reserva | � |
| nombre\_servicio\_mejorado | Nombre de servicio | � |
| año\_mes | Mes (Año) | � |
| año\_semana | Semana (año) | � |
| coste\_ajustado | Ajuste de costes | � |
| coste\_ajustado | Coste (ajustado) | � |
| Categoría[x] | Dimensión empresarial [x] | x' representa la cardinalidad de las Dimensiones de Negocio (Por ejemplo: Business Dimension 1, Business Dimension 2, Business Dimension 3) en su entorno Cloudability. |
| clave de categoría[x] | Clave de dimensión empresarial [x] | x' representa la cardinalidad de las claves de dimensión empresarial (por ejemplo: Clave de dimensión empresarial 1, Clave de dimensión empresarial 2, Clave de dimensión empresarial 3) en su entorno Cloudability. |
| coste\_amortizado\_ajustado\_total | Coste (amortizado ajustado) | � |
| coste\_público\_a\_petición | Coste (Lista) | � |
| clase\_oferta | Clase de reserva | � |
| nombre\_cluster\_contenedor | Nombre de clúster | � |
| espacio\_nombre\_contenedor | Espacio de nombres | � |
| ancestros\_numeros | GCP Números de ascendencia | � |
| coste amortizado de la cuota de participación | Coste Fairshare (Amortizado) | � |
| coste\_utilizado\_amortizado | Coste utilizado (amortizado) | � |
| amortizado\_idle\_cost Inactivo | Coste (amortizado) | � |
| coste\_compartido\_ajustado | Coste Fairshare (ajustado) | � |
| coste\_utilizado\_ajustado | Coste Utilizado (Ajustado) | � |
| coste\_idle\_ajustado | Coste de inactividad (ajustado) | � |
| coste amortizado de las participaciones ajustado | Coste Fairshare (amortizado ajustado) | � |
| coste\_utilizado\_amortizado\_ajustado | Coste Utilizado (Ajustado Amortizado) | � |
| coste\_inactivo\_amortizado\_ajustado Inactivo | Coste (amortizado ajustado) | � |
