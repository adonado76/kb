---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Listas personalizadas"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/custom-lists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Listas personalizadas

Observação: *as funções de administrador ou proprietário do processo orçamentário são necessárias para gerenciar listas personalizadas.*

As listas personalizadas permitem que os administradores definam um conjunto de valores permitidos para um único atributo em uma tabela de itens de linha. Eles são comumente usados para padronizar a entrada de dados — por exemplo, criando uma lista *de status* com valores como “Selecionado”, “Entrevistado” e “Contratado” para uso em itens de linha de mão de obra.

## Criar uma lista personalizada

1. Navegue até **Configuração** → **Listas personalizadas**.
2. Selecione **Adicionar** (➕).
3. Digite um **nome** para a lista.

   Observação: os nomes das listas não podem ser renomeados posteriormente.
4. Na seção **Valores**, clique em **Adicionar** (➕) para inserir valores.
5. Use a alça de arrastar (⋮⋮) para reordenar os valores ou selecione **Excluir** (🗑) para removê-los.
6. Quando terminar, clique em **Adicionar** para finalizar a lista.

## Usando listas personalizadas em esquemas de itens de linha

As listas personalizadas são usadas para criar listas de seleção de um único atributo que podem ser adicionadas a qualquer esquema de item de linha como um atributo personalizado.

1. Navegue até **Configuração → Esquema** e selecione um tipo de esquema.
2. Selecione **Adicionar** para criar um atributo personalizado.
3. Definir **Tipo de Dados = Lista**.
4. Selecione a **Lista Personalizada** que você criou anteriormente.
5. Clique em **Adicionar** para criar o atributo da lista.

Depois de adicionado, o atributo aparecerá como um campo suspenso na tabela de itens associados, garantindo uma entrada de dados padronizada e controlada para os usuários finais.
