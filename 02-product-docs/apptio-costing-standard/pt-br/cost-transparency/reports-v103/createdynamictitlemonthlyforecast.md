---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Criar um título dinâmico para um relatório de previsão mensal"
breadcrumb: []
source_path: "cost-transparency/reports-v103/createdynamictitlemonthlyforecast.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Criar um título dinâmico para um relatório de previsão mensal

**Problema**

Você cria um relatório de previsão mensal. Você deseja que o título inclua o mês da previsão, exibido como 1+11, 2+10, 3+9, etc. O título deve ser, por exemplo, "1+11 Forecast as of Jan 2015".

**Solução**

Use Dynamic Text no objeto HTML para avaliar a data selecionada no seletor de datas e traduzir para a notação X+(12-X).

`<%=EVAL(CurrentDate("MM")-1)&"+"&EVAL(13-CurrentDate("MM"))&"
Forecast as of "&CurrentDate("MMM ffff")%>`
