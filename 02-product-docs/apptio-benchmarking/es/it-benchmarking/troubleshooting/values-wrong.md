---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Los valores parecen incorrectos o sospechosos"
breadcrumb:
  - "Benchmarking"
  - "Informes comparativos"
  - "Solución de problemas y preguntas frecuentes"
source_path: "it-benchmarking/troubleshooting/values-wrong.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Los valores parecen incorrectos o sospechosos

**Nuestro valor es mucho más alto o más bajo que el de nuestros competidores.**

Síntoma  
: una métrica muestra que se encuentra muy por encima o por debajo del rango de sus pares por un factor considerable, no solo un 10-20 %.   
Posibles causas

- Incoherencia en las unidades (miles frente a unidades monetarias completas, GB frente a TB, etc.)
- Error de volumen (recuentos incorrectos, alcance incorrecto)
- Desajuste en el alcance (usted incluye costes que otros excluyen, o viceversa)
- Datos de año incorrecto o año parcial

Qué hay que comprobar

1. Consulte la definición de la métrica ( **[Referencia de datos y metodología](../home.html#benchmarking__data-methodology)** ): numerador y denominador.
2. Confirme que el total de costes en Costing coincide con el de Finanzas para ese año.
3. Confirme que el volumen proviene del sistema correcto y coincide con la realidad.
4. Comprueba si hay errores en las unidades (por ejemplo, TB introducido como GB).
5. Verifique que el año seleccionado sea un año completo, no un semestre.

Respuesta breve que puede enviar  
: Este valor está fuera de rango porque los datos subyacentes de coste o volumen no se ajustan a la definición del índice de referencia. Estamos validando el alcance y las unidades, y actualizaremos la correspondencia para que la comparación sea significativa.

**Nuestro ratio de gasto en TI difiere considerablemente de las cifras internas del departamento financiero.**

El gasto en TI de   
SymptomBenchmarking como porcentaje de los ingresos difiere de la opinión del departamento financiero.   
Posibles causas

- Diferente alcance de TI (por ejemplo, TI + telecomunicaciones frente a solo TI)
- Diferente alcance de los ingresos (grupo frente a segmento, bruto frente a neto)
- Diferencias monetarias o temporales
- El benchmarking utiliza definiciones de TI alineadas con TBM; Finanzas utiliza categorías internas

Qué hay que comprobar

1. Compare el alcance de TI: qué grupos de costes y funciones se incluyen en ambos lados.
2. Confirmar que el alcance de los ingresos y el período coinciden con el alcance de los costes de TI.
3. Compruebe la moneda y cualquier hipótesis sobre los tipos de cambio.

Respuesta breve que puede enviar  
: La proporción difiere porque Benchmarking utiliza una definición estándar de costes e ingresos de TI alineada con TBM que no coincide exactamente con la visión interna de Finanzas. Conciliaremos el alcance y las definiciones y luego acordaremos una visión única para las comparaciones externas.

**La tendencia de referencia interanual experimenta un aumento inesperado.**

Síntoma  
: una métrica se mantiene estable durante años y, de repente, sube o baja sin que se produzca ningún evento operativo evidente.   
Posibles causas

- Cambios en el modelo TBM (reconfiguración, nuevas torres, cambios en el alcance del proyecto)
- Comparativa que apunta a un proyecto o alcance de costes diferente para ese año
- Cambio en el perfil organizativo que altera el grupo de pares
- Actualización del conjunto de datos de referencia que modificó la composición de los pares

Qué hay que comprobar

1. Revisar los registros de cambios en TBM/costes en torno al año bisiesto.
2. Confirme que la evaluación comparativa utiliza el mismo proyecto y alcance de cálculo de costes a lo largo de los años.
3. Comprueba si tu perfil cambió de sector, rango de tamaño o región en ese año.
4. Si es necesario, compare con los registros de cambios de referencia anteriores para ver si la cobertura ha cambiado.

Respuesta breve que puede enviar  
: El salto se debe principalmente a cambios estructurales o de configuración, no a un único evento operativo. Hemos cambiado la forma en que se asignan los costes o con qué pares nos comparamos, por lo que marcaremos ese año como una ruptura estructural en lugar de una tendencia suave.
