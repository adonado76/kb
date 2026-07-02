---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Data Studio Temas"
breadcrumb:
  - "TBM Studio"
  - "Solución de problemas y asistencia técnica"
  - "Problemas habituales y soluciones"
source_path: "studio/new-uc/ts-support/ds-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data Studio Temas

## Los datos no se cargan o falla la carga

**Síntomas:**

- La carga del archivo falla debido a un error de validación
- La tabla de datos muestra cero filas tras la carga
- La subida parece haberse bloqueado o haber agotado el tiempo de espera

**Posibles causas:**

- El formato del archivo no se ajusta al esquema esperado
- Faltan columnas obligatorias
- Discrepancias en los tipos de datos
- Problemas con la codificación de archivos
- El archivo supera los límites de tamaño

**Soluciones:**

1. **Comprueba el formato y el contenido del archivo** : asegúrate de que el archivo contiene datos y está correctamente delimitado. Comprueba que los encabezados de las columnas se ajusten al esquema previsto. Asegúrate de que las columnas numéricas solo contengan valores numéricos.
2. **Comprueba la validación de las columnas** : abre la tabla de datos y revisa los indicadores de validación (números rojos junto al nombre de la tabla). Haz clic en el icono para ver los errores de validación específicos. Corrija las discrepancias en los tipos de datos del archivo de origen.
3. **Comprueba las particiones de fechas** : asegúrate de que se están cargando los datos correspondientes al periodo de tiempo correcto. Comprueba que las columnas de fecha tengan el formato esperado.

**Consejos para la prevención**

- Comprueba siempre los datos antes de subirlos
- Utiliza el paso de validación de datos para detectar los errores a tiempo
- Mantén unas convenciones coherentes en cuanto a los nombres y el formato de los archivos

*Véase también: Arquitectura de datos (sección 4.2 ), Carga de datos (sección 3.1.1 )*

## La tabla «Transform» no realiza cálculos

**Síntomas:**

- Transform muestra datos obsoletos
- Los objetos del modelo posterior muestran valores incorrectos
- Aparece una insignia de error en la tabla de transformación

**Soluciones:**

1. **Guardar y comprobar si hay errores** : haz clic en «Guardar» en cualquier tabla de transformación que hayas modificado. Fíjate en los indicadores de error (números rojos) que aparecen junto al nombre de la tabla.
2. **Comprobar el estado del documento** : comprueba si el documento está en uso. Si otro usuario lo tiene en uso, ponte de acuerdo con él.
3. **Revisar la lógica de cada paso de transformación** : abrir cada paso de transformación y comprobar las fórmulas. Comprueba si hay referencias circulares.
