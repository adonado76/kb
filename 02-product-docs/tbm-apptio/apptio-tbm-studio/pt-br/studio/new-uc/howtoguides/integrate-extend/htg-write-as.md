---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Guia prático: Como escrever fórmulas n ApptioScript"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Integrar e ampliar"
  - "Scripting"
source_path: "studio/new-uc/howtoguides/integrate-extend/htg-write-as.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia prático: Como escrever fórmulas n ApptioScript

**Objetivo:** Aprender os fundamentos do ` ApptioScript ` e escrever seu primeiro script funcional.

**Tempo estimado:** 30 minutos

**Pré-requisitos:** Acesso ao TBM Studio com pelo menos uma tabela editável

## Noções básicas sobre o ` ApptioScript `

ApptioScript é executado em dois contextos principais: associado a tabelas editáveis (respondendo a alterações nas células, adições de linhas ou carregamento de dados) e associado a botões (executado quando o usuário clica). É essencial compreender esses contextos antes de escrever qualquer roteiro.

Recomenda-se o uso de algum tipo de editor de texto para facilitar a escrita de scripts mais longos. O texto pode ser copiado e colado no editor.

**Onde os scripts são executados**

|  |  |  |
| --- | --- | --- |
| **Local** | **Quando é executado** | **Usos comuns** |
| Script de tabela editável | Ao editar uma célula, adicionar uma linha ou carregar/atualizar a tabela | Validação, formatação de células, trilhas de auditoria, consultas |
| Ação do botão no servidor | Quando o usuário clica no botão | Transições de fluxo de trabalho, operações de dados, operações de cópia |

## Estrutura do roteiro

Cada ` ApptioScript ` é composto por instruções que são executadas sequencialmente. Os elementos básicos são:

- **Instruções** — Chamadas de função que executam ações (por exemplo, ` EditRows( `, ` AddRow( `))
- **Lógica condicional** — If/ElseIf/End Blocos if para ramificação
- **As variáveis** — row e eventType — estão disponíveis nos scripts de tabelas editáveis
- **Subprocedimentos** — Blocos de código reutilizáveis definidos com Sub/End Sub
- **Comentários** — As linhas que começam com ' (apóstrofo) são ignoradas
- **Texto dinâmico** — sintaxe <%=%> para inserir valores em tempo de execução

## Variáveis-chave em scripts de tabelas editáveis

**A variável de linha**

A variável `row` representa a linha que está sendo processada no momento. Você pode ler os valores das células, definir novos valores e controlar as propriedades das células:

```
' Read a cell value
If row.Status = "Complete"
 
' Set a cell value
row.LastUpdated = "<%=CurrentDate()%>"
 
' Make a cell required
row.ApproverName.isRequired = "true"
 
' Make a cell read-only
row.SystemID.isEditable = "false"
 
End If
```

**A variável ` eventType `**

A variável ` eventType ` indica o que acionou o script. Isso é essencial para scripts que devem se comportar de maneira diferente dependendo do contexto:

|  |  |
| --- | --- |
| **eventType Valor** | **Quando isso acontece** |
| "onload" | A tabela é carregada ou atualizada inicialmente |
| "cellEdit" | O usuário edita qualquer célula da linha |
| "cellEdit(ColumnName)" | O usuário edita uma coluna específica (por exemplo, cellEdit(Status )) |
| "addRow" | O usuário adiciona uma nova linha |
| "duplicateRow" | O usuário duplica uma linha existente |

## Passo a passo: crie seu primeiro script

Este passo a passo mostra como criar um script simples de registro de auditoria que registra quem editou uma linha e quando.

## Passo 1: Prepare sua tabela editável

Antes de adicionar um script, certifique-se de que sua tabela editável tenha colunas para armazenar as informações de auditoria. Para este exemplo, adicione duas colunas:

1. **Editado por** — Tipo de etiqueta, para armazenar o ID do usuário
2. **Data de edição** — Tipo de etiqueta, para armazenar o carimbo de data/hora

Dica: Se os nomes das colunas contiverem espaços, você deve colocar todo o identificador entre chaves no seu script: {row.Edited By} em vez de row.EditedBy.

## Passo 2: Acesse o Editor de Scripts

1. Confira a tabela editável
2. Acesse a tabela editável no Explorador de Projetos
3. Vá para **Passos > Script**
4. O editor de scripts é aberto, exibindo qualquer script existente ou uma área em branco para novos scripts

## Etapa 3: Escrever o script de trilha de auditoria

Digite o seguinte script. Isso captura o ID do usuário e o carimbo de data/hora sempre que alguém edita ou adiciona uma linha:

```
' Audit trail: capture who edited and when
' This script runs on every cell edit or new row
 
If eventType = "cellEdit" OR eventType = "addRow"
 ' Store the current user's ID
    {row.Edited By} =
        "<%=$CurrentUser:Users.Id%>"
 
    ' Store the current date and
        time
    {row.Edit Date} =
        "<%=DateFormat(NOW(),"MM-dd-yyyy hh:mm a")%>"
End If
```

## Passo 4: Salvar e testar

1. Clique em **Salvar** para salvar o script
2. Verifique na tabela editável
3. Abra um relatório que contenha esta tabela editável
4. Edite qualquer célula da tabela
5. Verifique se as colunas **“Editado por”** e **“Data de edição”** são preenchidas automaticamente

**Resultado esperado:** Ao editar qualquer célula, a coluna “Editado por” exibe seu ID de usuário (por exemplo, “jsmith”) e a coluna “Data da edição” exibe a data e a hora (por exemplo, “15/01/2025 14h30”).

Dica: Use Debug() para solucionar problemas em scripts. Adicione Debug("Testando: " & row.Status ) para exibir os valores em uma caixa de diálogo durante a execução.

## Usando texto dinâmico

O texto dinâmico (<%=%>) permite inserir valores que são avaliados em tempo de execução. Todo o texto dinâmico é avaliado e substituído antes que qualquer linha de ` ApptioScript ` seja executada.

**Padrões comuns de texto dinâmico:**

|  |  |
| --- | --- |
| **Expressão** | **Retorna** |
| <%=$CurrentUser:Users.Id%> | ID do usuário atual |
| <%=$CurrentUser:Users.Full Nome%> | Nome completo do usuário atual |
| <%=$CurrentUser:Users.Role%> | Função do usuário atual |
| <%=CurrentDate()%> | Data atual (formato padrão) |
| <%=CurrentDate("MMMM:yyyy")%> | Período atual no formato Mês:Ano |
| <%=DateFormat(NOW( ),"mm-dd-aaaa")%> | Data de hoje formatada |
| <%=ProjectName()%> | Nome do projeto atual |

## Armadilhas comuns

- **Esquecer as chaves em colunas com espaços:** use {row.Vendor Name} em vez de row.Vendor Nome
- **Comparações incorretas de cadeias de caracteres:** os valores diferenciam maiúsculas de minúsculas. "Ativo" ≠ "ativo"
- **Falta o End If:** toda instrução If requer um End If correspondente
- **Comentários nas linhas de código:** Os comentários devem estar em uma linha separada. O caractere ' não pode aparecer no final de uma linha de código
- **Valores booleanos como strings:** isRequired e isEditable utilizam os valores de string "true" ou "false", e não os valores booleanos true/false

**Tópico principal:** [Scripting](../../../../studio/new-uc/howtoguides/integrate-extend/scripting.html)
