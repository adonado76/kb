---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Achatar uma hierarquia de dados"
breadcrumb: []
source_path: "studio/data_studio/flatten-hierarchy.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu285.png"
  - "resources/images/studio_images/studioimages/studio/stu286.png"
  - "resources/images/studio_images/studioimages/studio/stu287.png"
  - "resources/images/studio_images/studioimages/studio/stu288.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Achatar uma hierarquia de dados

**Aplica-se a** : TBM Studio 12.0 e posterior

Se estiver trabalhando com uma tabela que tenha dados hierárquicos e uma coluna pai e uma coluna filha, e colocar essa tabela em um relatório, os recursos do fatiador serão limitados. Para oferecer aos usuários o máximo de flexibilidade no uso de slicers, achate o conjunto de dados adicionando uma etapa de achatamento de hierarquia ao pipeline de transformação. Esse recurso adiciona colunas à transformação do conjunto de dados (uma coluna para cada nível da hierarquia). Em seguida, você pode criar segmentações para cada uma das colunas.

## Exemplo

O conjunto de dados mostrado na imagem a seguir é baseado em uma hierarquia geográfica. Se você criar um relatório a partir do conjunto de dados e adicionar segmentações para as colunas **Parent** e **Child**, obterá o relatório mostrado na imagem a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu285.png)

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu286.png)

Suponha que você queira ver todas as entradas nos EUA. Quando você seleciona **USA** no fatiador **Parent**, obtém o resultado mostrado na imagem a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu287.png)

Mas, e se você quiser que os usuários possam ver todas as entradas associadas aos EUA? Você pode conseguir isso achatando a hierarquia usando o recurso **Achatar hierarquia**. O recurso **Achatar hierarquia** pega as informações em uma coluna **Pai** e uma coluna **Filho** e adiciona colunas de Nível que podem ser usadas com fatiadores. O resultado é mostrado na imagem a seguir. Ao achatar a hierarquia, você oferece aos usuários o máximo de flexibilidade ao usar fatiadores.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu288.png)

Para que o recurso **Achatar hierarquia** funcione corretamente:

- Cada combinação pai-filho deve ser exclusiva. Se houver combinações duplicadas, será exibida uma mensagem de erro nas colunas recém-geradas.
- Para cada combinação de pai e filho, o filho não pode ter mais de um pai.
