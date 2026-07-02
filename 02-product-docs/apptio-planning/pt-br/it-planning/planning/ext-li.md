---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Itens de linha externos"
breadcrumb:
  - "Planning"
  - "Trabalhando com planos"
source_path: "it-planning/planning/ext-li.html"
images:
  - "resources/images/it_planning_images/edit-mli.png"
  - "resources/images/it_planning_images/edit-mode.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Itens de linha externos

Os itens de linha externos permitem gerenciar dados planejados originados de sistemas externos e trazê-los para o Apptio Planning para visibilidade e análise, sem permitir que os usuários finais os editem.

Observação: as funções de administrador ou responsável pelo processo orçamentário são necessárias para gerenciar itens externos.

**Principais recursos**

- Os itens externos podem ser importados para as guias **Finanças** (Resumo e Outros), **Contratos**, **Ativos, Mão de obra** e **Atividade de mão de obra**.
- Eles são marcados com **Is External = true** na importação.
- **Os proprietários de centros de custo não podem editar** itens de linha externos - eles são somente de leitura.
- Apenas **administradores ou proprietários do processo orçamentário** podem importar itens de linha externos.
- Somente usuários com **ExternalLineEdit** permissão podem editar itens de linha externos.

## Importar itens externos

Você pode importar dados externos da **visualização herdada** ou da **nova visualização**.

1. Navegue até Despesas e selecione a guia para importar Linhas Externas para ( **Resumo**, **Contratos**, **Ativos, Mão de obra, Atividade de mão de obra ou Outros).**
2. **Escolha a visualização apropriada:**
   1. **Legacy View** → Clique no menu **Actions (Ações** )
      1. Selecione **Importar finanças externas...,** **Importar contratos externos...,** ou **Importar ativos externos...**
   2. **New View** → Clique no **menu de reticências (...)** na tabela
      1. Selecione **Importar finanças externas...,** **Importar contratos externos...,** ou **Importar ativos externos...**
3. Selecione **Replace All** (substituir todos os dados externos existentes) ou **Update Data** (atualizar códigos de itens de linha correspondentes).
4. Conclua o upload para confirmar as partidas individuais externas.

## Editar itens externos

Os itens externos só podem ser editados na **Nova Visualização**.

Os usuários devem ter a **ExternalLineEdit** permissão (concedida por padrão às funções de administrador e proprietário do processo orçamentário).

**Editar uma única linha externa**

1. Clique com o botão direito do mouse na linha externa.
2. Selecione **Editar Linha Externa** para ativar o modo de edição.
3. Clique em **Sair do modo de edição** para retornar a todos os itens da linha.

**Editar várias linhas externas**

1. Selecione uma ou mais linhas externas usando as caixas de seleção.
2. Abra o **menu de reticências (...)** na tabela.
3. Selecione **Editar <tipo de item de linha> externo selecionado...**, dependendo da guia que você está editando.
4. Clique em **Sair do modo de edição** para retornar a todos os itens da linha.

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/edit-mli.png)

**Ativar o modo de edição para todas as linhas externas**

1. Abra os **pontos de suspensão (...) menu** na mesa.
2. Selecione **Editar todos os <tipo de item de linha> externos...**
3. Todas as linhas externas entram no modo de edição.
4. Selecione **Sair do modo de edição** para salvar todas as alterações e retornar a todos os itens da linha.

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/edit-mode.png)

**Excluindo linhas externas**

1. No Modo de Edição, selecione uma ou mais linhas externas usando as caixas de seleção.
2. Ou:
   1. Clique com o botão direito do mouse e selecione **Excluir** ou
   2. Use o botão **Excluir** na barra de ferramentas da tabela.
