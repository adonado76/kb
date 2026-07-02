---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "GetInfo função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/getinfo.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetInfo função

**Aplica-se a** : TBM Studio 12.0 e posterior

Retorna uma ampla gama de informações sobre um projeto.

## Onde usar

Essa função pode ser usada em:

- Qualquer campo em que você possa inserir uma fórmula
- !NEWCOLUMN em um caminho de dados
- Colunas de fórmula em tabelas de relatórios
- Texto dinâmico
- Apptio roteiro

## Sintaxe

`GETINFO("attribute",["DomainName:ProjectName"])`

As cotações são obrigatórias.

## Argumentos

*atributo*

Pode ser um dos seguintes:

- `"project.startDate"` (Retorna a primeira data do projeto)
- `"project.endDate"` (Retorna a última data do projeto)
- `"project.effectiveStartDate"` (Retorna o conjunto effectiveStartDate. Datas de controles de desempenho de honras)
- `"project.effectiveEndDate"` (Retorna o conjunto effectiveEndDate. Datas de controles de desempenho de honras)
- `“project.fyMonthIndex”` (Retorna um índice de 0 a 11 que corresponde ao mês do ano fiscal currentDete( ).
- `“project.isRealTimeCalculation”` (Retorna 'true' se o projeto estiver no modo de tempo real e 'fals' se for pré-calculado)
- `“project.request.currency.code”`(Retorna a moeda selecionada para a sessão atual)
- `“project.request.currency.exchange.rate.type”`(Retorna o tipo de taxa de câmbio selecionado para a sessão atual)
- `“project.request.locale”`(Retorna a localidade selecionada para a sessão atual. O padrão é a localidade do projeto, mas ela pode ser substituída por uma preferência do usuário)
- `“project.isRealTimeCalculation”`(Retorna 'true' se o projeto estiver no modo de tempo real e 'fals' se for pré-calculado.
- `table.transformName`(Retorna o nome da tabela primária que faz o backup da consulta, se houver)
- `table.lastMaterialRevision`(Semelhante a db.contents.lastMaterialRevision, mas devolvendo a última revisão que exigiu que essa tabela fosse recalculada)
- `db.contents.lastMaterialRevision` (O número da revisão da última alteração material no registro de auditoria de um projeto. Uma alteração é relevante se puder afetar os números que foram calculados anteriormente. O número de revisão é uma lista delimitada de IDs de registro de auditoria da última entrada de registro de auditoria em cada registro de auditoria da pilha de projetos derivados para o projeto)
- `db.contents.currentRevision` (O número da revisão da última alteração do cálculo do projeto atual é atual a partir de. O número da revisão é um. lista delimitada dos IDs de registro de auditoria da última entrada de registro de auditoria em cada registro de auditoria da pilha de projetos derivados do projeto)

*DomainName:ProjectName*

Especifica o domínio que contém o projeto e o nome do projeto. Se estiver especificando um nome de domínio, você também deverá especificar o nome do projeto. Eles fazem parte do mesmo argumento. O argumento deve ser um valor de rótulo codificado entre aspas. Não pode ser uma referência a outra coluna ou fórmula.

## Tipo de retorno

Rótulo

## Notas

Você pode inserir a seguinte função em uma caixa HTML para testar se a função está funcionando corretamente.

`<%=GETINFO("attribute",”<%=DomainName%>:<%=ProjectName%>”)%>`

## Exemplo

O exemplo a seguir retorna a data de início do projeto da ABC Company no domínio docs.org.

```
=GetInfo("project.startDate","docs.org:ABC
          Company")
```

`=GetInfo("project.startDate”)`
