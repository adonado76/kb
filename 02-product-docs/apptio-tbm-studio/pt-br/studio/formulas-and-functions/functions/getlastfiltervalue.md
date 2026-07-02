---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "GetLastFilterValue função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/getlastfiltervalue.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu283.png"
  - "resources/images/studio_images/studioimages/studio/stu284.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetLastFilterValue função

**Aplica-se a** : TBM Studio 12.0 e posterior

Retorna o último valor aplicado a um filtro.

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Texto dinâmico

## Sintaxe

`GetLastFilterValue(column)`

## Argumentos

*coluna*

A coluna da qual será recuperado o último valor de filtro aplicado.

## Tipo de retorno

Sequência

## Exemplo A

O seguinte retornaria o valor "Sales" (Vendas)

`!Filter[Business Unit=Sales]`

## Exemplo B

Suponha que você tenha o relatório mostrado na imagem a seguir:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu283.png)

Você gostaria que o nome da tabela mudasse com base na seleção do fatiador. Por exemplo, na imagem anterior, o UNIX foi selecionado no fatiador e você gostaria que o nome da tabela fosse Custos do servidor - UNIX, conforme mostrado na imagem a seguir:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu284.png)

Para criar o nome da tabela dinâmica:

1. Oculte o cabeçalho padrão da tabela abrindo a caixa de diálogo **Propriedades** da tabela, selecionando a guia **Geral** e desmarcando a opção **Mostrar cabeçalho**.
2. Adicione uma caixa de texto HTML ao relatório com o seguinte código HTML:

   ```
   <font face="Arial"><p
                 style="color:#3366CD;text-align:left;font-size:10pt">Server Costs -
                 <%=getLastFilterValue()%></p></font>
   ```
3. Posicione a caixa HTML acima da tabela para servir como o nome da tabela.
4. Selecione a caixa de texto HTML.
5. Na caixa de diálogo **Configuração de HTML**, adicione o campo Tipo de servidor à área **Linhas**.
6. Oculte o cabeçalho padrão da caixa de texto HTML abrindo a caixa de diálogo **Propriedades** da tabela, selecionando a guia **Geral** e desmarcando a opção **Mostrar cabeçalho**.

**Veja também** : [GetLastFilterColumn](getlastfiltercolumn.htm "(Abre em uma nova guia ou janela)")
