---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Filtros de itens de linha (listas de seleção dependentes)"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/itp-dependent-picklists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Filtros de itens de linha (listas de seleção dependentes)

Observação: *as funções de administrador ou responsável pelo processo orçamentário são necessárias para gerenciar filtros de itens de linha.*

**Os filtros de itens** permitem controlar quais valores aparecem em um campo suspenso com base nas seleções feitas em outra coluna. Isso melhora a precisão da entrada de dados, impedindo que os usuários vejam opções irrelevantes ou inválidas.

Por exemplo:

- Quando um usuário seleciona um **Centro de Custos**, você pode restringir o menu suspenso **Conta** para mostrar apenas as contas associadas a esse Centro de Custos.
- Os filtros podem ser encadeados para criar dependências em vários níveis (por exemplo, Centro de Custos → Conta → Fornecedor).

**Importante:**

Os filtros de itens de linha afetam apenas o que é exibido no menu suspenso. Eles não modificam os dados já inseridos.

**Exemplo**

Dado o seguinte mapeamento:

|  |  |
| --- | --- |
| **Conta** | **Centro de Custos** |
| ACCT\_6000 | **CC-200** |
| ACCT\_6100 | **CC-200** |
| ACCT\_6200 | **CC-200** |
| ACCT\_3001 | **CC-200** |
| ACCT\_3002 | CC-210 |
| ACCT\_3011 | CC-210 |
| ACCT\_2006 | CC-220 |
| ACCT\_4021 | CC-220 |

Se um usuário selecionar **Centro de Custos = CC-200**, o menu suspenso **Conta** exibirá apenas:

- ACCT\_6000
- ACCT\_6100
- ACCT\_6200
- ACCT\_3001

## Criar um filtro de item de linha

1. Navegue até **Configuração** → **Filtros de itens de linha**.
2. Selecione **Adicionar** (➕) no canto superior direito. A caixa de diálogo **Adicionar filtro de item de linha** é exibida.
3. Insira os seguintes detalhes:
   1. **Nome** – Um nome de filtro exclusivo
   2. **Coluna** – A dimensão que você deseja filtrar
   3. **Filtrar por** – O atributo cujo valor determina as opções filtradas
4. Selecione **Adicionar** para criar o filtro.
5. Selecione o filtro na tabela.
6. Exportar o modelo de filtro:
   1. Selecione o **menu reticências** → **Exportar para arquivo** ou clique com o botão direito do mouse no filtro e escolha **Exportar para arquivo**.
   2. Você também pode exportar um modelo em branco através **do menu Ellipsis** → **Exportar modelo.**
7. Preencha o arquivo CSV:
   1. Adicione linhas que mapeiam os valores **da coluna** para os valores **do filtro**
   2. Para dimensões que utilizam **o Código** como identificador único, você deve usar o código (não o nome).
   3. Cada linha só pode ter um valor por coluna.
8. Importe o mapeamento:
   1. Selecione **o menu reticências** → **Importar do arquivo** ou clique com o botão direito do mouse no filtro e escolha **Importar do arquivo.**
   2. Carregue o CSV.

## Atualizar um filtro de item de linha

1. Navegue até **Configuração** → **Filtros de itens de linha** e selecione o filtro a ser atualizado.
2. Exporte o mapeamento atual usando **o menu Ellipsis** → **Exportar para arquivo**.
3. Edite o CSV para adicionar, modificar ou excluir linhas.
4. Importe o CSV atualizado usando **o menu Ellipsis** → **Importar do arquivo**.

   Os mapeamentos atualizados entram em vigor imediatamente.

## Excluir um filtro de item de linha

1. Navegue até **Configuração** → **Filtros de itens de linha**.
2. Clique com o botão direito do mouse no filtro que deseja excluir e selecione **Excluir**.

Depois de excluído, o filtro não será mais aplicado aos menus suspensos em nenhuma tabela de itens de linha.
