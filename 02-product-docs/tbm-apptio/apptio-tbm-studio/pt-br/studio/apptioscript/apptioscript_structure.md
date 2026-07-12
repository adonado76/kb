---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "ApptioScript estrutura"
breadcrumb: []
source_path: "studio/apptioscript/apptioscript_structure.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioScript estrutura

ApptioScript a estrutura consiste em instruções, tabelas editáveis, variáveis e texto dinâmico.

A estrutura de nível superior de um ApptioScript consiste em um ou mais dos seguintes itens:

- Definição de um subprocedimento
- Definições
- Chamada de subprocedimentos
- Instruções

## Instruções

Declarações simples
:   As instruções simples são chamadas de método, como os dois exemplos a seguir:

    `Return("Foo")`

    `EditRow(...)`

Declarações de atribuição
:   Você pode atribuir o valor de uma expressão a uma variável em um objeto Apptio scriptable. Atualmente, isso só é usado em tabelas editáveis no script onCellValueChanged. Para isso, insira o objeto de linha com script no procedimento. O objeto de linha tem valores de célula que podem ser acessados pelo site columnName. A célula tem os seguintes atributos que podem ser definidos:

    - isRequired = valor
    - isEditable = valor

      Ao atribuir um valor a uma célula, você pode usar qualquer uma das funções do site Apptio que tenham contexto válido.

      [Saiba mais sobre fórmulas e funções](../formulas-and-functions/introduction-to-formulas-and-functions.htm "(Abre em uma nova guia ou janela)")

      Exemplo:

      ```
      Sub MyProcedure(row)
      row.columnA.isRequired = "true"
      row.columnB.isEditable = "false"
      row.columnB = UPPER(columnC)
      row.columnC = "foo"
      End Sub
      ```

Colunas com espaços
:   Ao trabalhar com colunas que contêm espaços, você deve envolver todo o identificador em chaves.

    Exemplo:

    ```
    If {Vendor ID} != ""
    {row.Purchase Description.isRequired} = "true"
    End If
    ```

Se as declarações
:   A sintaxe de uma instrução If é a seguinte:

    ```
    If condition
    [statements]
    ElseIf condition
    [statements]
    End If
    ```

    Você pode aninhar instruções If dentro de instruções If. A condição ElseIf é opcional. Você pode ter mais de um ElsIf. A condição segue a mesma sintaxe e semântica das expressões de filtro da função If.

    [Saiba mais sobre a função If](../formulas-and-functions/functions/if.htm "(Abre em uma nova guia ou janela)")

Subprocedimento
:   Um subprocedimento é uma série de instruções ApptioScript delimitadas pela instrução Sub e pela instrução End Sub. Um subprocedimento pode ser chamado várias vezes. Cada vez que um subprocedimento é chamado, os comandos incluídos são executados, começando com o primeiro comando executável após o comando Sub e terminando com o comando End Sub.

    Um subprocedimento pode declarar uma lista opcional de argumentos que são passados para ele quando é chamado. Os argumentos são declarados na instrução Sub.

    Exemplo:

    ```
    Sub Test(arg1, arg2)
    Return(arg1)
    End Sub
    ```

    Para chamar um procedimento, use o nome do procedimento e passe a ele o número correto de argumentos. Para chamar o procedimento Test no exemplo acima, use a seguinte instrução.

    `Test("foo", "bar")`

Comentários
:   Os comentários devem estar em sua própria linha. Um comentário não pode ser adicionado a uma linha que contenha não-comentários. A linha de comentário começa com o caractere de tique '. Tudo o que vem depois do tique até o final de uma linha é ignorado pelo analisador. Os comentários de várias linhas exigem seu próprio ' no início de cada linha.

    `' This line is a comment and is ignored by the parser.`

## Tabela editável

Você pode anexar um script a uma tabela editável que é executada em uma das seguintes condições:

- Ao sair de uma célula editada
- Quando você adiciona uma nova linha
- No carregamento inicial ou na atualização do conjunto de dados no componente de relatório.

## Variáveis

Existem duas variáveis que você pode usar em seus scripts.

Linha
:   Row é a linha atual na qual o script está sendo executado. Uma linha tem células, e uma célula tem três atributos de script: isRequired, isEditable e o valor.

    O script a seguir mostra o uso deles:

    ```
    if columnB = "bar"
    row.columnA = "foo"
    row.columnA.isRequired = "true"
    row.columnA.isEditable = "true"
    end if
    ```

eventType
:   eventType pode ser usado para executar uma lógica específica quando um usuário edita uma célula, por exemplo, para atualizar um registro de data e hora.

    eventType pode ter os seguintes valores: 'onload', 'cellEdit', ou 'addRow'.

    Aqui está um exemplo:

    ```
    if eventType = "cellEdit" OR eventType = "addRow"
    row.name = "<%=$CurrentUser:Users.Id%>"
    end if
    ```

## Texto dinâmico

ApptioScript suporta texto dinâmico <%=%>.

Dica: antes de qualquer linha do site ApptioScript ser executada, todo o texto dinâmico é avaliado e substituído no script.
