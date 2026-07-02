---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Crear un título dinámico para un informe mensual de Previsiones"
breadcrumb: []
source_path: "cost-transparency/reports-v103/createdynamictitlemonthlyforecast.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Crear un título dinámico para un informe mensual de Previsiones

**Problema**

Se crea un informe mensual de reprevisión. Desea que el título incluya el mes de previsión, mostrado como 1+11, 2+10, 3+9, etc. El título debe ser, por ejemplo, "1+11 Previsiones a enero de 2015".

**Solución**

Utilice Texto dinámico en el objeto HTML para evaluar la fecha seleccionada en el selector de fecha y traducirla a notación X+(12-X).

`<%=EVAL(CurrentDate("MM")-1)&"+"&EVAL(13-CurrentDate("MM"))&"
Forecast as of "&CurrentDate("MMM ffff")%>`
