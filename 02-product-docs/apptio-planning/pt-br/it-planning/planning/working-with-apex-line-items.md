---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Trabalhando com itens de linha do Apex"
breadcrumb: []
source_path: "it-planning/planning/working-with-apex-line-items.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Trabalhando com itens de linha do Apex

Este tópico explica como gerenciar itens de linha do Apex no aplicativo, incluindo adição, inserção, duplicação, importação, exportação e exclusão de itens de linha.

## Antes de começar

Todos os recursos listados aqui estão disponíveis apenas para os clientes que não têm PFP ou SDP. Quando um administrador ou proprietário do processo orçamentário ativa o recurso Apex Line Item Table, os usuários com função não administrativa podem alterar a visualização da tabela entre `Classic View` e `New View`.

## Procedimento

- Adicionar itens de linha:
  1. Acima da tabela de itens de linha, selecione o ícone (Imagem do sinal de mais (+)).
  2. Na janela `New Line Item` , selecione os atributos da nova linha.
  3. Selecione `Add` para adicionar o item de linha.

     Como alternativa, selecione `Add Another` para adicionar mais itens de linha e selecione `Add` para adicionar os itens de linha.
  4. Para adicionar atributos opcionais, clique duas vezes na célula da tabela e insira os detalhes.
- Inserir itens de linha:
  1. Clique com o botão direito do mouse em uma linha.
  2. Selecione Insert Row Above (Inserir linha acima ) ou Insert Row Below (Inserir linha abaixo ) para inserir uma linha.
  3. Na janela Novo item de linha, selecione os atributos da nova linha.
  4. Selecione Adicionar para adicionar o item de linha.

     Selecione Add Another (Adicionar outro) para adicionar mais itens de linha e selecione Add (Adicionar ) para adicionar os itens de linha.
  5. Para adicionar atributos opcionais, clique duas vezes na célula da tabela e insira os detalhes.
- Excluir itens de linha:
  1. Clique com o botão direito do mouse no item de linha.
  2. Selecione a opção Excluir. É exibida uma janela pop-up de confirmação.
  3. Digite o endereço `LineItem Code` e selecione Delete (Excluir ).
- Itens de linha duplicados:
  1. Clique com o botão direito do mouse no item de linha.
  2. Selecione Duplicate Row.
- Importar itens de linha:
  1. Acima da tabela Expenses (Despesas ), selecione o ícone Options (Opções ).
  2. Para importar itens de linha externos, selecione Importar finanças externas.

     Como alternativa, para importar itens de linha não externos, selecione Importar finanças.
- Exportar itens de linha:
  1. Acima da tabela Expenses (Despesas ), selecione o ícone Options (Opções ).
  2. Para exportar um modelo de tipo de despesa, selecione Exportar modelo financeiro.

     Como alternativa, para exportar itens de linha, selecione Exportar finanças.
- Dica de ferramenta da lista de opções dependente

  Quando você seleciona uma opção em uma coluna, isso pode restringir as opções que podem ser selecionadas em outra coluna, pois o site Planning exclui automaticamente as opções que seriam incompatíveis com a opção selecionada na primeira coluna.

  Por exemplo, cada projeto pode estar usando um conjunto diferente de centros de custo. Quando o centro de custo em uma linha é alterado, a lista de opções que podem ser selecionadas para o projeto nessa linha também muda. Essas opções podem ser um subconjunto de todos os projetos disponíveis no ambiente.

  Os usuários podem achar isso confuso porque veem uma lista diferente de opções para linhas diferentes na mesma coluna.

  Um ícone de dica de ferramenta agora é exibido na célula da tabela (Adicionar imagem da dica de ferramenta da lista de opções Dependent dep\_tool\_pick.png )

  Quando você passa o mouse sobre a dica de ferramenta, ela exibe uma mensagem específica da coluna, explicando qual coluna é responsável pela filtragem das opções da lista. (Adicionar imagem da dica de ferramenta da lista de opções Dependente dep\_tool\_pick1.png )

  Esse recurso só está disponível nas tabelas de itens de linha do Apex. Não está disponível em tabelas clássicas de itens de linha.

  Os filtros de itens de linha ainda não são compatíveis com as tabelas de itens de linha do Apex. Quando as tabelas de itens de linha do Apex suportam Filtros de itens de linha, as colunas filtradas pela configuração do filtro de itens de linha usarão a dica de ferramenta da lista de opções dependente.
- Excluir despesas em massa:
  1. No menu de navegação, selecione Despesas > Nova visualização.
  2. Selecione as linhas que deseja excluir clicando na caixa de seleção ou usando `SHIFT + down
     arrow` do teclado para selecionar várias linhas
  3. Selecione o ícone (Excluir imagem do ícone) na barra de menu acima da tabela. Como alternativa, você também pode fazer a mesma operação no menu de contexto usando o botão direito do mouse.
  4. É exibida uma caixa de diálogo de confirmação de exclusão.
  5. Observação: quando a exibição de despesas é agrupada por uma ou mais colunas, as operações no nível da linha, como adicionar linha, copiar linha, excluir linha e duplicar linha, não estão disponíveis.

     Forneça os detalhes de confirmação na caixa de entrada de confirmação e selecione o botão `Delete` .
