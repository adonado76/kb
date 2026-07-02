---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Cortadores de filtros"
breadcrumb: []
source_path: "studio/reports/filter-slicers.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep046.png"
  - "resources/images/studio_images/studioimages/reports/rep143.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cortadores de filtros

**Aplica-se a** : TBM Studio 12.0 e posterior

Para limitar os valores exibidos no fatiador, adicione um ou mais filtros ao fatiador. Quando um usuário visualizar o fatiador, ele verá os resultados filtrados. Um fatiador antes e depois da filtragem é mostrado na imagem a seguir:

![Cortadores de filtros](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep046.png)

## Adicionar um filtro a um fatiador

1. Arraste um campo do **Project Explorer** para a área **Filtros** do painel **Configuração do fatiador**.
2. Clique com o botão direito do mouse no campo e selecione **Edit Filter (Editar filtro** ) no menu pop-up. A caixa de diálogo **Edit Filter (Editar filtro** ) é exibida, conforme mostrado na imagem a seguir:![Adicionar um filtro a um fatiador](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep143.png)
3. Selecione os valores que deseja exibir no fatiador e clique em **OK**.
   - Para adicionar um valor personalizado à lista, clique no link **Add a custom filter (Adicionar um filtro personalizado** ).
   - A **opção Valores não mostrados no momento**, quando marcada, incluirá todos os valores que não podem ser exibidos no filtro porque excedem o limite de 1.000 valores.
   - Se houver mais de 1.000 valores disponíveis no filtro, você verá uma mensagem alertando-o sobre esse fato e sugerindo que use a caixa Filtro na parte superior da lista para encontrar valores adicionais.

## Publicar o filtro em uma perspectiva

Assim como ocorre com outros componentes de relatório baseados em objetos, você pode publicar um filtro em uma perspectiva personalizada. O filtro publicado pode ser usado na criação de outros componentes.

Para publicar um filtro:

1. Clique com o botão direito do mouse no filtro na área **Filtros**.
2. Aponte para **Publish** e selecione uma perspectiva existente ou crie uma nova perspectiva.

## Remover um filtro de um fatiador

Para remover um filtro de um fatiador, execute uma das seguintes ações:

- Arraste o filtro para fora da área **Filtros**.
- Clique com o botão direito do mouse no filtro na área **Filtros** e selecione **Remover** no menu pop-up.
