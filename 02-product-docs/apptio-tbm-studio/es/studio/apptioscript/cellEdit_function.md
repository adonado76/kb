---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Funciones Enviar correo y Editar celda"
breadcrumb: []
source_path: "studio/apptioscript/cellEdit_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Funciones Enviar correo y Editar celda

Se han lanzado dos funciones que permiten activar un correo electrónico en función de un cambio de evento en una tabla editable.

- **SendMail( )** función
  - Sintaxis general: `SendEmail("email address","Subject","Content")`
- **cellEdit( )** - mejora de las prestaciones
  - Sintaxis general: `cellEdit("column_name")` donde el nombre de la columna es opcional. Si se incluye un nombre de columna, el evento se activará sólo si se realiza un cambio de celda en esa columna. Para la función SendMail, esto elimina el "reenvío" de un correo electrónico si se modifican otras columnas.

**Ejemplo de código para un caso de uso de planificación de la demanda**

```
if eventType = "cellEdit(Submission_Status)"
'
if {row.Submission Status} = "Submitted"
' Send email to designated Approver
SendEmail(row.Approver,"Demand Plan submitted for review and approval","Demand Plan submitted by " & row.Submitter & " for the " & row.Organization Name & " department. Here is any special comment from the submitter: " & row.Submission Comment)
end if
'
end if
```

De forma similar, podría configurarse un script para enviar un correo electrónico al remitente si el aprobador "rechaza" el plan enviado.
