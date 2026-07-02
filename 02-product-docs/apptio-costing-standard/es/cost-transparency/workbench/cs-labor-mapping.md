---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Cartografía laboral"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso del informe"
  - "Recaudación de costes"
source_path: "cost-transparency/workbench/cs-labor-mapping.html"
images:
  - "resources/images/ct_images/lm-1.jpg"
  - "resources/images/ct_images/lm-2.jpg"
  - "resources/images/ct_images/lm-3.jpg"
  - "resources/images/ct_images/s-1.jpg"
  - "resources/images/ct_images/s-3.jpg"
  - "resources/images/ct_images/s-5.png"
  - "resources/images/ct_images/s-6.jpg"
  - "resources/images/ct_images/s-7.jpg"
  - "resources/images/ct_images/s-8.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cartografía laboral

Labor Workbench ofrece a los responsables financieros, de centros de coste y de recursos la posibilidad de introducir y mantener información relacionada con la mano de obra para enriquecer y mejorar la calidad de los datos procedentes de RR.HH. y otros sistemas, así como de asignar la mano de obra a las torres de recursos informáticos que soportan las personas, incluidas las aplicaciones, los productos y/o los servicios.

****Labor Workbench - Configuración****

1. (TBM Studio): Instalar el componente CTF-Labor Workbench.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-1.jpg)
2. (TBM Studio): Cargar conjunto de datos Laborales del cliente. Realice las transformaciones necesarias si procede.
3. (TBM Studio): Asignar el conjunto de datos del cliente a Labor Feed.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-3.jpg)
4. (TBM Studio): Guarde y registre los cambios.

   **Banco de trabajo**
5. (Vista de informe): Vaya a Workbench > Informe de asignación de mano de obra > Ficha Enriquecimiento de datos de mano de obra. Verifique que se muestren los datos de mano de obra y actualice las columnas que incluyen Tipo de función, Tipo de empleado, ID de proveedor y Ubicación según sea necesario.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-5.png)
6. (Vista de informe): Vaya a Workbench > Informe de asignación de mano de obra > pestaña Asignación de mano de obra y asigne cada fila de mano de obra a una o más torres de recursos de TI, subtorres de recursos de TI e ID de aplicación según sea necesario. Además, también puede verificar el Factor de ponderación de la columna según sea necesario. Guarde los cambios y publique el archivo ET Transform de Mapeo Laboral.

   **Recomendaciones** :

   "Factor de Ponderación" puede utilizarse para capturar el coste real de la mano de obra en los escenarios en los que han formado parte de una o más Torres de Recursos TI/Sub-Torres de Recursos TI.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-6.jpg)

   Nota:
   - Los desplegables de torres de recursos TI y subtorres de recursos TI dependen de los datos maestros de las torres de recursos TI.
   - El desplegable ID de aplicación depende de los Datos maestros de aplicaciones.
7. (Vista de informe): Vaya a Workbench > Informe de asignación de mano de obra > pestaña Asignaciones faltantes y compruebe si falta alguna línea de mano de obra asignada a torres y subtorres de recursos de TI.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-7.jpg)
8. (TBM Studio): Abra el objeto del modelo Mano de obra y verifique las imputaciones de costes de Mano de obra a Seguimiento horario y Otras imputaciones de mano de obra.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-8.jpg)

## Informes

**Enriquecimiento de los datos laborales**

Ofrece la posibilidad de mejorar los metadatos para los recursos de mano de obra interna y externa, incorporados desde los datos de mano de obra de IDP, y permitir un análisis más rico de sus gastos de mano de obra:

- Equipo (Ejemplo: Escuadras)
- Rol
- Tipo de empleado
- ID de proveedor (si procede)
- Ubicación

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/lm-1.jpg)

**Asignaciones laborales**

Los usuarios pueden actualizar su lista de mano de obra asignando un recurso de mano de obra a:

- Tipo y categoría de solución
- Direccionable
- Identificación de la oferta
- ID de proyecto
- Asignación Ponderación
  - Permite determinar en qué Tipo de solución/Categoría de solución/Proyecto trabaja el recurso. La ponderación por defecto es de 1 (100%) para cada empleado; sin embargo, los usuarios pueden ajustar o dividir los porcentajes de recursos en sus áreas correspondientes.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/lm-3.jpg)

**Asignaciones que faltan**

Identifica los recursos laborales que no se han asignado a Soluciones.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/lm-2.jpg)
