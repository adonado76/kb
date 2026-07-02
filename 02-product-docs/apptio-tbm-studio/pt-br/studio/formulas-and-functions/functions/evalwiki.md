---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "EvalWiki função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/evalwiki.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# EvalWiki função

**Aplica-se a** : TBM Studio 12.0 e posterior

A função EvalWiki é usada para avaliar links wiki e texto dinâmico e formatá-los para exibição em um relatório. A função pode ser usada somente em relatórios. Ele não pode ser usado em conjuntos de dados. Para obter informações adicionais sobre o uso de links Wiki, consulte Codificação de links para outros relatórios no Guia de relatórios.

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`EvalWiki(wikitext)`

## Argumentos

*wikitexto*

Uma cadeia de texto Wiki.

## Exemplo 1: Uso de texto dinâmico em vários relatórios

Suponha que você tenha um grande bloco de texto que deseja manter em um local no sistema e colocar em várias páginas de relatório. Isso pode ser feito usando EvalWiki. Crie um conjunto de dados de uma linha (e. g.: TextBlocks ) com uma coluna chamada Text (Texto). Digite o bloco de texto na célula da tabela.

Em um relatório, adicione um componente HTML que inclua <%=EvalWiki(TextBlocks:Text )%>. Isso avaliará os links wiki e o texto dinâmico nesse valor. A extração do valor por meio de uma pesquisa normal não fará isso.

## Exemplo 2: Como adicionar links às células em uma tabela

Suponha que você queira ter várias colunas em uma tabela de um relatório e que, nessas colunas, você queira links que levem o usuário a lugares diferentes. Isso pode ser feito usando EvalWiki:

1. Em TBM Studio, insira uma nova coluna na tabela.
2. Na caixa de diálogo **Editar coluna**, marque a opção **Forçar rótulo**.
3. Insira uma fórmula como a seguinte:

   ```
   =EvalWiki("[[/myObject/!FILTER[myColumn="""&myColumn&"""]/ myReport|click here
                 to see my report]]")
   ```

Isso criará um link que navega para um relatório de objeto filtrado no objeto myObject. Ele filtrará para mostrar apenas as linhas em que myColumn nesse relatório de objeto é igual ao valor de myColumn na tabela atual.
