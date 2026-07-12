---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Funções Send Mail e Cell Edit"
breadcrumb: []
source_path: "studio/apptioscript/cellEdit_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Funções Send Mail e Cell Edit

Dois recursos foram lançados para dar suporte à capacidade de acionar um e-mail com base em uma alteração de evento em uma tabela editável.

- **SendMail( )** função
  - Sintaxe geral: `SendEmail("email address","Subject","Content")`
- **cellEdit( )** - aprimoramento de recursos
  - Sintaxe geral: `cellEdit("column_name")` onde o nome da coluna é opcional. Se um nome de coluna for incluído, o evento será acionado somente se uma alteração de célula for feita nessa coluna. Para a função SendMail, isso elimina o "reenvio" de um e-mail se outras colunas forem alteradas.

**Exemplo de código para um caso de uso de planejamento de demanda**

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

De maneira semelhante, um script pode ser configurado para enviar um e-mail ao remetente se o aprovador "rejeitar" o plano enviado.
